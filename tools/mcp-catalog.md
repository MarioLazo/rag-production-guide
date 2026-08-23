# The MCP Catalog

**A governed shortlist of Model Context Protocol servers: organized by what they can reach, not by what they can do.**

There is no shortage of MCP lists. Nearly all of them answer *what does this server do?* Almost none answer the question an enterprise architect actually has to answer before deployment: **what can it touch, what happens when it's wrong, and what governance does it need first?**

This catalog is organized around that question.

> **Confidence and sourcing.** Items marked ✅ are ones I've run directly. Items marked 📋 are widely reported in production use but not personally verified: treat the assessment as secondhand. Ecosystem claims are sourced at the bottom. Last reviewed **2026-08**.

---

## Start here: pick a budget, not a collection

The single most useful constraint I've found, and the one most lists omit:

> **Production agent stacks work best at 5–9 MCP servers.** Below five, the agent is undertooled and falls back to guessing. Above nine, tool-selection accuracy measurably degrades, the model starts picking wrong tools because too many descriptions look plausible.

This changes the exercise. You are not assembling a library, you are spending a budget of roughly seven slots. Every server you add costs accuracy on the ones already there.

The corollary matters just as much: **a server that's occasionally handy is a net negative** if it competes for selection with one you rely on. Cut aggressively.

---

## Risk tiers for MCP servers

The same four tiers used on the [Agent Card](agent-card.md), applied to tools rather than agents. Tier is determined by **blast radius**, what happens when the agent calls it wrong, not by how sophisticated the server is.

| Tier | What it can do | Governance floor |
|---|---|---|
| **1: Read-only, public** | Reads data that is already public or non-sensitive | Log calls. Hosted is fine. |
| **2: Read-only, internal** | Reads internal or proprietary data, writes nothing | Self-host. Access controls. Audit trail. |
| **3: Write, reversible** | Modifies internal state that can be undone | Self-host. Human approval on sensitive paths. Full logging. |
| **4: Write, irreversible or external** | Sends, pays, publishes, deletes, or touches regulated data | Self-host. Explicit per-action approval. Spend caps. Kill switch. |

**The rule that follows from this:** self-host anything at Tier 2 or above. Hosted MCP servers are appropriate for read-only public APIs and very little else. When a server touches proprietary data, "trust the vendor's infrastructure" becomes a decision you have to justify to Risk, not a default.

---

## The catalog

### Tier 1: Read-only, public

Cheap to adopt, low governance burden. Most stacks want two or three of these, not six.

| Server | What it's for | Notes |
|---|---|---|
| **Fetch** ✅ | Retrieves and converts web content for model consumption | Reference implementation. The workhorse. ⚠️ Anything it fetches is untrusted input, see the injection section below |
| **Brave Search / web search** 📋 | Live web search | Pick one search server. Two search tools is the classic budget waste |
| **Time** ✅ | Current time and timezone conversion | Trivial, but agents reason badly about "now" without it |
| **Sequential Thinking** ✅ | Structured multi-step reasoning scaffold | Improves decomposition on complex tasks; costs tokens |

### Tier 2: Read-only, internal

Where most enterprise value actually is. **Self-host these.**

| Server | What it's for | Notes |
|---|---|---|
| **Filesystem** ✅ | Local file read/write within allowed directories | Scope the allowed paths narrowly and deliberately. The default is usually too broad |
| **Git** ✅ | Repository history, diffs, blame | Excellent for code archaeology. Read-only against history |
| **PostgreSQL** 📋 | Schema-aware SQL querying | Connect with a **read-only role**, not app credentials. This is the most common misconfiguration I see |
| **Vector stores**: Chroma, Pinecone, Qdrant 📋 | Semantic retrieval over an indexed corpus | The grounding layer. See [`docs/`](../docs/) for retrieval depth |
| **ClickHouse / analytics DBs** 📋 | Analytical queries over large datasets | Watch query cost, an agent can generate expensive scans without noticing |

### Tier 3: Write, reversible

Real leverage, real need for approval gates.

| Server | What it's for | Notes |
|---|---|---|
| **GitHub** ✅ | Issues, PRs, code, review workflow | Scope the token hard. `repo` scope on a personal account is broader than most people think, and it does *not* include `delete_repo`, which is a feature |
| **Notion / Confluence** 📋 | Read and write knowledge bases | Reversible via page history, which is what keeps it Tier 3 |
| **Slack** 📋 | Read channels, post messages | Posting is socially irreversible even when technically deletable. Treat message-send as Tier 4 |
| **Supabase** 📋 | Database plus auth plus storage | Broad surface. Consider separate servers per concern rather than one with everything |

### Tier 4: Write, irreversible or external

Deploy these last, with approval gates and spend caps, or not at all.

| Server | What it's for | Notes |
|---|---|---|
| **Stripe / payments** 📋 | Payment operations | Money is definitionally irreversible. Per-action human approval, no exceptions |
| **Email / calendar send** 📋 | Sends on your behalf | An agent that can send email can damage relationships faster than it can help |
| **Cloud provider control planes** 📋 | Infrastructure operations | The blast radius is your infrastructure. Read-only IAM unless there's a specific, gated reason |
| **Zapier / automation bridges** 📋 | Connects to thousands of downstream apps | ⚠️ **Tier is inherited from the worst thing it can reach.** A bridge server is only as safe as its most dangerous connection, assess the connections, not the bridge |

### Specialist, worth knowing

| Server | What it's for | Notes |
|---|---|---|
| **Semgrep** 📋 | Static analysis and security scanning | Useful in a review loop, not a build loop |
| **Sentry** 📋 | Error tracking and production diagnostics | Pairs well with incident-response workflows |
| **Playwright / Puppeteer** 📋 | Browser automation | Powerful and genuinely risky, it can reach anything a browser can. Sandbox it |

---

## Before you install anything: the security part

MCP's security model is weaker than most adopters assume, and the failure modes are not the obvious ones.

### Tool poisoning

**Malicious instructions embedded in a tool's *metadata*, its name, description, or parameter docs.** The agent reads that metadata as part of its context. The user never sees it.

This is currently the most prevalent client-side MCP vulnerability. A server can look benign in its documentation and carry instructions in the fields your agent actually reads.

**Controls:** install from verified publishers only. Pin versions, a server that was clean at install can change on update. Review tool descriptions directly, not just the README. Treat an unaudited third-party server the way you'd treat an unaudited dependency with production credentials, because that's what it is.

### Indirect prompt injection

Any server that retrieves external content, web fetch, email, document ingestion, ticket systems, carries untrusted text into your agent's context. An attacker doesn't need to breach anything; they only need to get text in front of your agent.

**Controls:** treat all retrieved content as untrusted. Never let retrieved content authorize a Tier 3+ action without a human in the path. Test with injection probes before production, this is gate 5 on the [Pre-Flight Checklist](pre-flight-checklist.md).

### Agents are privileged identities

The framing that resolves most MCP governance arguments:

> **An agent with MCP tools is a privileged identity.** It authenticates, holds credentials, takes actions, and reaches systems. Govern it like an admin account, least privilege, monitored, revocable, not like a feature.

Concretely: which clients may connect to which servers, which users may invoke which tools, action-level approval for sensitive operations, and a runtime log of every call capturing user, client, server, arguments, and result.

---

## Going deeper by vertical

This catalog is deliberately cross-industry, it organizes by blast radius, which applies everywhere. For **finance and healthcare specifically**, the [Agent Factory Reference](../reference/agent-factory-regulated-industries.md) carries dedicated MCP server sections for each, alongside the regulatory context that determines which of them you can actually deploy.

---

## Selection checklist

Before adding any server to a production stack:

- [ ] **What tier is it?** Determined by blast radius, not sophistication
- [ ] **Does it fit the budget?** If you're at nine, what comes out
- [ ] **Self-hosted if Tier 2+?** Hosted is for read-only public data
- [ ] **Least-privilege credentials?** Read-only DB role, scoped token, restricted paths
- [ ] **Publisher verified and version pinned?**
- [ ] **Tool descriptions actually read?** Not just the README
- [ ] **Does it ingest untrusted content?** If yes, injection probes required
- [ ] **Logging captures user, client, server, arguments, result?**
- [ ] **Human approval on irreversible actions?**
- [ ] **Recorded on the [Agent Card](agent-card.md)?**

---

## What I'd actually run

A defensible starting stack for enterprise work, inside the budget:

| Slot | Server | Tier |
|---|---|---|
| 1 | Filesystem (scoped) | 2 |
| 2 | Git | 2 |
| 3 | GitHub (scoped token) | 3 |
| 4 | Fetch | 1 |
| 5 | One search server | 1 |
| 6 | Your vector store | 2 |
| 7 | PostgreSQL (read-only role) | 2 |

Seven slots. One Tier 3, no Tier 4. Add Tier 4 servers only when a specific workflow requires them, with gates in place first, never speculatively.

---

## Contributions

Running something at scale that belongs here, especially with a governance assessment attached? Open an issue. Particularly interested in Tier 3 and 4 deployments in regulated environments, where the controls are the hard part.

---

## Sources

Ecosystem claims not from direct experience:

- [MCP Security: Risks, Real Incidents & Controls](https://checkmarx.com/learn/mcp-security-risks-real-world-incidents-and-security-controls/), Checkmarx
- [MCP Security Best Practices](https://obot.ai/resources/learning-center/mcp-security/), Obot
- [MCP Tool Poisoning: Enterprise AI Agent Security](https://itecsonline.com/post/mcp-tool-poisoning-enterprise-ai-agent-security-2026), ITECS
- [Model Context Protocol Threat Modeling and Vulnerabilities to Prompt Injection with Tool Poisoning](https://arxiv.org/html/2603.22489v1), arXiv
- [Best MCP Deployment Platforms for Enterprise Teams](https://www.prefect.io/resources/best-mcp-deployment-platforms-enterprise-2026), Prefect (source of the 5–9 server finding)

---

*Part of [Agentic CoE](../README.md). Licensed [CC BY 4.0](../LICENSE), reuse freely, including commercially, **with attribution**.*
