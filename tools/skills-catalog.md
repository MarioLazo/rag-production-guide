# The Skills Catalog

**Agent skills across Claude Code, Codex, Cursor, and Copilot: what's worth adopting, what it costs you, and how to tell whether it actually helped.**

If [MCP servers](mcp-catalog.md) are what your agent can *reach*, skills are what your agent *believes*. A skill is prose that shapes every output the agent produces, loaded into context before it does any work. That makes it powerful, cheap to share, and almost entirely unexamined.

> The most honest summary of the category in 2026: **portable, popular, and unmeasured.** Thousands of skills are shared. Vanishingly few come with any evidence that they improve results.
>
> That's the gap this catalog is about.

> **Confidence and sourcing.** ✅ = I run this directly. 📋 = widely used, not personally verified. Ecosystem claims sourced at the bottom. Last reviewed **2026-08**.

---

## What changed this month

**Agent Plugins 1.0 landed 6 August 2026.** It standardizes exactly two component types: **Agent Skills** and **MCP servers**, inside one directory with a `plugin.json` manifest. Five clients support it: VS Code, Cursor, GitHub Copilot, ChatGPT & Codex, and Kiro.

That matters more than it sounds. Until now, extending an agent meant picking a vendor's format and living with it. A common manifest means a skill you write can travel, and the thing you invest in isn't stranded when you switch tools.

It is nine days old. Treat adoption claims accordingly.

---

## Portability: what actually transfers

The formats are converging but they are not interchangeable. Before writing anything substantial, know where it can go.

| Platform | Format | Portability |
|---|---|---|
| **Claude Code** | Markdown + optional scripts | **Highest.** Plain markdown is the most portable primitive in the category, it's readable, diffable, and trivially adapted |
| **Codex / ChatGPT** | `AGENTS.md` + manifest-driven plugins | Skill system adopted in 2026 and converging, but plugins are the **most rigid and least portable**, manifest-bound |
| **Cursor** | Its own rules format | Does **not** consume Claude Code skill format. Manual translation |
| **GitHub Copilot** | Custom instructions | Instruction-shaped rather than skill-shaped; concepts transfer, files don't |
| **Any Plugins 1.0 client** | `plugin.json` + skills + MCP | The emerging common path. Newest and least proven |

**Practical implication:** write skills as plain markdown with the logic in the prose, not in vendor-specific scaffolding. Markdown ports everywhere with editing. A manifest-bound plugin ports nowhere.

---

## The context budget

The same constraint that governs [MCP servers](mcp-catalog.md) governs skills, for the same reason: **selection accuracy degrades as candidates multiply.**

An agent choosing between four well-scoped skills picks correctly. An agent facing thirty overlapping skills picks by surface plausibility, and their instructions start contradicting each other.

Three rules that follow:

1. **Skills are not free.** Each one consumes context and competes for selection. A skill that helps 5% of the time and confuses selection the rest is a net loss.
2. **Overlap is worse than absence.** Two skills covering similar ground is more damaging than having neither, because now the agent guesses.
3. **Prune on a schedule.** Adopted skills accumulate silently. Nothing forces a review, so schedule one.

---

## Categories worth having

Rather than ranking individual skills, the ecosystem moves too fast for a list to stay honest, here are the categories that consistently earn their context, with representative examples.

### Workflow and process ✅

Skills encoding *how work gets done here*: shipping, reviewing, releasing, investigating.

**[gstack](https://github.com/garrytan/gstack)** ✅, Garry Tan's Claude Code setup, ~23 opinionated tools spanning CEO, designer, eng manager, release manager, doc engineer, and QA roles. The most complete published example of role-based workflow skills. I use the `browse` skill from it regularly for headless UI testing, it catches bugs that unit tests structurally cannot, because it actually opens the page.

**Why this category works:** process knowledge is exactly what a new team member needs and what an agent otherwise lacks. It's also the most defensibly *yours*, nobody else's shipping process is your shipping process.

### Verification and testing ✅

Skills that make an agent check its own work rather than assert success.

The highest-value category and the most underrepresented. An agent that runs the page, reads the output, and reports what actually happened beats one that reports what it intended. Most published skills generate; few verify.

Related: gate 2 of the [Pre-Flight Checklist](pre-flight-checklist.md), independent evaluation, not self-assessment.

### Domain and platform knowledge 📋

Skills teaching an agent a specific platform or domain deeply.

**[UiPath Claude skills](https://github.com/UiPath/skills)** 📋 and similar vendor-published sets, these turn a general agent into one that knows a platform's idioms. Vendor-published skills are usually accurate about their own product and silent about its limitations. Useful, but read them as documentation, not advice.

### Memory and knowledge 📋

Skills wiring an agent into persistent knowledge, vaults, wikis, prior decisions.

**[obsidian-agent-memory-skills](https://github.com/AdamTylerLynch/obsidian-agent-memory-skills)** 📋, persistent memory via an Obsidian vault: the agent orients at session start, navigates by graph traversal, writes discoveries back. Interesting because it treats knowledge as a graph to walk rather than a blob to retrieve.

### Curated collections 📋

**[Coding Agents Conference skills](https://github.com/mlopscommunity/Coding-Agents-Conference-skills)** 📋, skills presented at the March 2026 conference. Conference-sourced collections tend to be higher signal than general awesome-lists, because someone stood on stage and defended each one.

Large "awesome" collections are best treated as **search indexes, not reading lists.** A thousand skills is not a library, it's a haystack.

---

## How to tell whether a skill actually helped

This is the section other catalogs don't have, and the reason most skill adoption is faith-based.

A skill is a change to your agent's behavior. Changes get evaluated. The bar doesn't need to be academic, it needs to exist.

### The minimum viable evaluation

1. **Write down what should improve, before installing.** Fewer review comments? Fewer failed builds? Less rework? If you can't name it, you can't detect it, and you'll keep the skill on vibes.
2. **Collect 5–10 representative tasks.** Real ones from your actual work, not synthetic examples.
3. **Run them without the skill. Save the outputs.**
4. **Install, run the same tasks, compare.**
5. **Check the cost side too**: context consumed, latency, and whether other skills started getting picked less often.

Twenty minutes. It is still more evaluation than almost any published skill has received.

### What to watch for

**Skills that only ever appear to work.** The agent's output *sounds* more rigorous while being no more correct. This is the [Meaning Gap](../README.md) in miniature, improved presentation misread as improved substance.

**Instruction conflicts.** Two skills giving contradictory guidance produces worse output than either alone, and the failure is invisible because the agent never announces the conflict.

**Silent selection drift.** Adding a skill can make a previously reliable one stop being chosen. Nothing alerts you.

**Provenance.** A skill is uninspected instruction with your agent's full permissions behind it. **Read it before installing.** Same standard you'd apply to an MCP server's tool descriptions, and the same reason: what the agent reads is not what you skimmed.

---

## Build or adopt?

| Build your own when | Adopt when |
|---|---|
| It encodes *your* process, shipping, review, standards | It's general craft: testing, refactoring, docs |
| The knowledge is proprietary or hard-won | The domain is a platform someone else knows better |
| You've hit the same correction three times | A published skill already covers it well |

The three-corrections rule is the useful trigger. If you've told the agent the same thing three times, that's a skill. Before that, it's a preference.

---

## Selection checklist

- [ ] **Read the actual skill file**, not the README
- [ ] **Named the outcome** it should improve, before installing
- [ ] **Baseline captured** on 5–10 real tasks
- [ ] **Checked for overlap** with skills already installed
- [ ] **Context cost acceptable?**
- [ ] **Provenance known**, who wrote it, is it maintained
- [ ] **Portable format?** Markdown ports; manifests don't
- [ ] **Review date set**, when will you check whether it's still earning its slot

---

## Contributions

Have a skill with **evidence** behind it, a before/after, a measured outcome, even an informal one? Open an issue. Measured skills are rare and disproportionately valuable, and this catalog would rather have ten with evidence than a thousand without.

---

## Sources

- [Agent Skills in 2026: Portable, Popular, Unmeasured](https://nerdleveltech.com/agent-skills-portable-unmeasured), Nerd Level Tech
- [Claude Code Skills in 2026: The Complete Guide (vs Hooks, vs Subagents, vs MCP)](https://www.totalum.app/blog/claude-code-skills-totalum), Totalum
- [Best Claude Code Skills in 2026: A Curated Directory](https://www.developersdigest.tech/blog/best-claude-code-skills-2026), Developers Digest
- [Codex vs Claude Code: Which Agent for Which Job](https://www.developersdigest.tech/blog/codex-vs-claude-code-april-2026), Developers Digest

---

*Part of [Agentic CoE](../README.md). Licensed [CC BY 4.0](../LICENSE), reuse freely, including commercially, **with attribution**.*
