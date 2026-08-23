# 📋 Meta Prompt: Creating Shareable Technical Knowledge Repositories

> **A reusable template for creating public GitHub repositories that share professional knowledge safely and effectively.**

---

## 🎯 Purpose

Use this meta prompt when you want to:
- Share professional knowledge publicly without legal/professional risk
- Create educational content based on your experience
- Build thought leadership through open-source contributions
- Curate and synthesize knowledge from multiple sources

---

## 🔍 Pre-Creation Risk Analysis

### Step 1: Content Source Assessment

Before creating content, categorize your sources:

| Source Type | Risk Level | Required Action |
|-------------|------------|-----------------|
| **Peer-reviewed academic papers** | ✅ Low | Cite properly |
| **Open-source GitHub repos** | ✅ Low | Credit and link |
| **Official vendor documentation** | ✅ Low | Link to sources |
| **Industry benchmark reports** (Gartner, Forrester) | ✅ Low | Cite organization |
| **Public conference talks/blogs** | ✅ Low | Credit speaker/author |
| **Your synthesis of public knowledge** | ✅ Low | Frame as synthesis |
| **Patterns observed across multiple clients** | 🟡 Medium | Make composite, cite industry research |
| **Specific client/employer work** | 🔴 High | Transform completely or exclude |
| **Proprietary methodologies** | 🔴 High | Check employment agreements |
| **Confidential data/metrics** | 🔴 High | Replace with public benchmarks |

### Step 2: Risk Mitigation Checklist

Before publishing, verify:

- [ ] **No identifiable client details**: No combination of factors points to a real company
- [ ] **Composite framing**: Explicitly stated as illustrative/composite examples
- [ ] **Public sources cited**: Every claim traceable to published source
- [ ] **Math shown transparently**: teaching methodology, not claiming specific outcomes
- [ ] **Ranges used**: Never point estimates for financials
- [ ] **Disclaimers visible**: At top of README and key documents
- [ ] **No guarantees**, "Results will vary" language included
- [ ] **Employment agreement checked**: No conflicts with current/past employers
- [ ] **NDA compliance verified**: No protected information included

### Step 3: Employer/Client Alignment

Questions to resolve before publishing:

1. Does your employment agreement restrict publishing industry knowledge?
2. Are any case studies based on work covered by NDAs?
3. Is your employer comfortable with the publication?
4. Are you using any proprietary frameworks or methodologies?

**Safe positioning:** "Curated synthesis of publicly available research, open-source frameworks, and industry benchmarks."

---

## 📝 Repository Structure Template

```
your-knowledge-repo/
│
├── README.md                          # Landing page with disclaimers
├── CONTRIBUTING.md                    # How others can contribute
├── ACKNOWLEDGMENTS.md                 # Credits to sources
├── LICENSE                            # MIT or CC BY 4.0
│
├── docs/
│   ├── 01-executive-summary.md        # Overview and audience
│   ├── 02-[topic-1].md                # Core content
│   ├── 03-[topic-2].md
│   └── ...
│
├── case-studies/                      # If applicable
│   ├── README.md                      # Disclaimer + overview
│   └── 01-illustrative-case-*.md      # Composite examples
│
├── cheatsheets/                       # Quick references
│   └── *.md
│
└── resources/
    ├── academic-references.md         # Peer-reviewed sources
    ├── industry-benchmarks.md         # Published statistics
    └── open-source-repos.md           # GitHub links
```

---

## 📜 Disclaimer Templates

### Main README Disclaimer (Copy & Customize)

```markdown
## ⚠️ Important Disclaimers

### 📚 Educational Content
This guide is provided for **educational and informational purposes only**. 
It does not constitute professional advice. Before making significant 
[technology/business/financial] decisions, consult with qualified 
professionals appropriate to your situation.

### 🔬 Curated Knowledge, Not Proprietary Information
This guide is a **curated synthesis** of:
- **Peer-reviewed academic research**: Published papers from [venues] 
  ([see references](resources/academic-references.md))
- **Open-source frameworks**: Publicly available GitHub repositories
- **Industry benchmarks**: Published statistics from [organizations]
- **Community knowledge**: Patterns shared in public forums and conferences

**No proprietary or confidential information is included.** 
All sources are publicly available and cited.

### 🎭 Composite Case Studies
The case studies in this guide are **composite illustrations** created 
for educational purposes. They:
- **Do not represent any specific company** or client engagement
- **Combine patterns** observed across multiple public sources
- **Use modified details** including scale, timelines, and specifics
- **Employ illustrative estimates** based on published industry benchmarks

Any resemblance to actual organizations is coincidental.

### 💰 Financial Estimates
All financial figures (costs, savings, ROI) are **illustrative estimates** 
based on:
- Published industry benchmarks (cited in each section)
- Back-of-envelope calculation methodology (shown transparently)
- Conservative ranges rather than point estimates

**Your actual results will vary** based on your specific context, 
implementation quality, organizational factors, and market conditions.

### 📜 No Warranty
This content is provided "as is" without warranty of any kind, express 
or implied. The authors and contributors are not liable for any damages 
arising from the use of this information.
```

### Case Study Disclaimer (Copy & Customize)

```markdown
## ⚠️ Important Notice

This case study is a **composite illustration** created for educational 
purposes. It:
- Does not represent any specific [company/organization/engagement]
- Uses financial estimates derived from **published industry benchmarks** 
  (sources cited below)
- Demonstrates common patterns observed in **public [vendor case studies/ 
  academic research/industry reports]**
- Is designed to teach [methodology/patterns/concepts], not guarantee outcomes
```

---

## 💰 ROI Methodology Template

When including financial estimates, use this transparent format:

```markdown
## 💰 ROI Estimation Methodology

**This section teaches back-of-envelope ROI calculation using public benchmarks.**

### Step 1: [Cost/Benefit Category]

```
INPUT ASSUMPTIONS (from public benchmarks):
─────────────────────────────────────────────────────────────────
[Metric 1]:                      [Value or range]
  Source: [Organization/Publication]

[Metric 2]:                      [Value or range]
  Source: [Organization/Publication]

CALCULATION:
─────────────────────────────────────────────────────────────────
[Step-by-step arithmetic]

RESULT:
─────────────────────────────────────────────────────────────────
[Outcome with range]
```

### Key Benchmark Sources

| Benchmark | Source | Link |
|-----------|--------|------|
| [Metric] | [Organization] | [URL] |

### Why We Use Ranges

All estimates use ranges rather than point values because:
1. **Organizational variance**: Every implementation differs
2. **Data quality variance**: Outcomes depend on input quality
3. **Adoption variance**: Human factors affect results
4. **Market variance**: Costs and values change over time

**Recommendation:** Use the conservative end for business cases.
```

---

## 📚 Academic References Template

```markdown
# 📚 Academic References & Research Sources

> **Peer-reviewed research and published benchmarks that inform this guide**

## 🎓 Peer-Reviewed Academic Papers

| Paper | Venue | Year | Key Contribution | Link |
|-------|-------|------|------------------|------|
| **[Title]** | [Conference/Journal] | [Year] | [1-line summary] | [arXiv/DOI link] |

## 📊 Industry Research & Benchmarks

| Source | Publication | Key Finding | Link |
|--------|-------------|-------------|------|
| **[Organization]** | [Report name] | [Key statistic] | [URL] |

## 🔗 Open Source Repositories Referenced

| Repository | Organization | License | Purpose |
|------------|--------------|---------|---------|
| [repo-name](URL) | [Org] | [License] | [Purpose] |
```

---

## ✅ Pre-Publication Checklist

### Content Review
- [ ] All claims have cited sources
- [ ] No specific client/company names
- [ ] No confidential metrics (replaced with public benchmarks)
- [ ] Case studies framed as "illustrative" and "composite"
- [ ] Financial figures shown as ranges with methodology
- [ ] Links to academic papers and industry sources work

### Disclaimers
- [ ] Main README has full disclaimer section
- [ ] Case studies have individual disclaimer boxes
- [ ] "Educational purposes only" stated clearly
- [ ] "No warranty" language included
- [ ] "Results will vary" for any estimates

### Legal/Professional
- [ ] Employment agreement reviewed for conflicts
- [ ] No NDA violations
- [ ] Employer notified/approved (if applicable)
- [ ] No proprietary methodologies exposed

### Attribution
- [ ] All open-source repos credited
- [ ] Academic papers properly cited
- [ ] Industry sources linked
- [ ] Contributors acknowledged

---

## 🎨 Positioning Language

### Safe Framing (Use These)

✅ "Curated synthesis of publicly available research"
✅ "Patterns observed in published case studies and academic literature"
✅ "Illustrative example based on industry benchmarks"
✅ "Composite scenario combining common patterns"
✅ "Estimates derived from [Organization] published data"
✅ "Educational resource for practitioners"

### Risky Framing (Avoid These)

❌ "Based on my client work"
❌ "From my experience at [Company]"
❌ "Real-world case study from..."
❌ "Actual results achieved..."
❌ "Proven methodology that delivers..."
❌ "Guaranteed to produce..."

---

## 📋 Example: Transforming Experience into Safe Content

### Original (Risky)
> "At my healthcare client, we reduced document processing time by 65% 
> and saved them $2.3M annually using our RAG implementation."

### Transformed (Safe)
> "Industry research from AHIMA suggests document processing typically 
> takes 15-20 minutes per document. Published vendor case studies 
> (ABBYY, Kofax) report 50-70% automation rates for similar workflows.
> 
> Using these benchmarks, a mid-size health system processing 10,000 
> documents monthly might see potential savings in the $500K-$1M range,
> though actual results vary significantly based on document complexity,
> data quality, and implementation factors."

### What Changed
| Aspect | Original | Transformed |
|--------|----------|-------------|
| Source | "My client" | Published benchmarks |
| Specificity | Exact figures | Ranges |
| Claim | "We achieved" | "Research suggests" |
| Guarantee | Implied | "Results vary" caveat |

---

## 🔄 Continuous Improvement

After publishing:

1. **Monitor feedback**: Update if sources become outdated
2. **Add citations**: When new research supports your content
3. **Refine disclaimers**: If edge cases emerge
4. **Credit contributors**: Acknowledge community input
5. **Version updates**: Note when benchmarks are refreshed

---

## 📖 License Recommendations

| Content Type | Recommended License | Reason |
|-------------|--------------------|----- ---|
| Code + Documentation | **MIT** | Simple, widely understood on GitHub |
| Documentation only | **CC BY 4.0** | Designed for creative content |
| Mixed | **MIT** | Covers both cleanly |

---

## 🚀 Quick Start

1. **Copy this template** to your new repository
2. **Run the risk assessment** (Step 1-3 above)
3. **Customize disclaimers** for your domain
4. **Build content** following the structure template
5. **Verify with checklist** before publishing
6. **Add to AGENTS.md** for future reference

---

*This meta prompt was developed while creating the [RAG Production Guide](https://github.com/MarioLazo/rag-production-guide) repository.*
