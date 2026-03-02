# FOR9TEVE-O: A Deep-Dive into Building an Awesome Smart Contract Analysis Tools List

*Your personal breakdown of every decision, tradeoff, and lesson from this project — written so you walk away smarter.*

---

## Step 1: What Approach Did I Take, and Why?

**The starting point:** The moment I looked at this repository, I saw a problem that a lot of security-focused developers face — too many tools, no map.

Imagine you're new to town and want to find the best coffee shop. You *could* Google every café individually, read every Yelp review, and compare opening hours. Or someone could hand you a well-organised, locally-trusted list. That's what this repository is: the well-organised list.

**The reasoning:**

The approach I took was **curation over creation**. Rather than building a new tool, the goal was to become the most reliable *guide* to existing tools. This matters because:

1. **The field moves fast.** New smart contract security tools appear monthly. Researchers publish, auditing firms build internal tools and open-source them, and the community iterates. Any static snapshot goes stale fast.
2. **The existing academic literature was already outdated.** The two anchor papers (the 2022 IEEE Access survey by Kushwaha et al. and the 2019 DAPPCON survey by di Angelo and Salzer) were comprehensive *at the time*, but they referenced tools that have since been deprecated, archived, or superseded. There was a genuine gap.
3. **Organisation by technique matters.** Lumping all tools together would be like a library that organises books by the colour of their spine. Instead, the list was structured by *what kind of analysis* each tool does: static analysis, symbolic execution, fuzzing, formal verification, or a mix. This helps you pick the right tool for the right job.

**Starting point:** I began with the two reference papers to build a baseline list, then cross-checked GitHub activity, deprecation notices, and newer research to add and flag tools accordingly.

---

## Step 2: What Other Approaches Did I Consider — and Reject?

Here's where most guides skip the honest part. Let me not do that.

### Rejected Approach 1: Build a Tool Comparison Table

A natural instinct is to add a big comparison table — columns for "language support," "detection types," "last commit date," "stars." Wikipedia-style.

**Why I rejected it:** Maintenance hell. A table like that goes stale within weeks. One tool releases a new version that adds Vyper support; now your table is wrong. The cognitive overhead of keeping it accurate is enormous, and an *inaccurate* table is worse than no table — it actively misleads people.

**The analogy:** It's like publishing a train timetable without a "last updated" date. A wrong timetable is worse than no timetable.

### Rejected Approach 2: Include Every Tool Ever Mentioned in Any Paper

The temptation when doing a survey is completeness. "If it was published, include it."

**Why I rejected it:** Quality over quantity. Including deprecated or abandoned tools (some are flagged with "Archived" in this list — e.g., FEther and SolAnalyzer) without clear labels would send users down dead ends. If someone spends a day trying to install a tool that was last updated in 2018, that's a real cost.

**The compromise:** Keep the archived tools *with a clear label*, because they still have historical and educational value. But don't bury live tools alongside dead ones without distinction.

### Rejected Approach 3: Separate Repos by Blockchain (Ethereum, Solana, etc.)

The field is expanding beyond Ethereum. Solana, Cosmos, Polkadot — each has its own smart contract model.

**Why I rejected it (for now):** The vast majority of existing analysis tooling targets Ethereum and Solidity/EVM bytecode. Splitting too early creates fragmentation and dilutes the value of each sub-list. Better to start deep on one ecosystem and expand later with proper structure.

---

## Step 3: How Do the Parts Connect?

Think of the repository like a well-designed hardware store, not a landfill.

```
README.md
│
├── Context Section (Why this list exists)
│   └── Reference to the two anchor papers — sets academic credibility
│
├── Tools Section (The core of the list)
│   ├── Static Analysis     — Fast, no execution needed. Your first line of defence.
│   ├── Symbolic Execution  — Explores all possible code paths mathematically.
│   ├── Fuzzing Tools       — Throws random/crafted inputs at contracts to find crashes.
│   ├── Formal Verification — Mathematical proof that code behaves as specified.
│   └── Mix                 — Tools that combine multiple techniques.
│
├── Research Section
│   └── Academic papers — the "why it works" behind the tools above.
│
└── CONTRIBUTION.md
    └── How to add to this list without breaking its quality.
```

**Why this order?**

Static analysis comes first because it's the most accessible and widely used. Symbolic execution and fuzzing require more setup and understanding. Formal verification is the most rigorous and hardest to use. This ordering mirrors the learning curve — a beginner can start at the top and work their way toward more advanced techniques as they grow.

The Research section is deliberately *after* the tools, not before, because most users want to use a tool first and understand the theory later. If they're curious why something works, the papers are there. But the list doesn't force them through 20 research papers before they can install Slither.

---

## Step 4: What Tools, Methods, and Frameworks Did I Use?

### The Curation Framework

**Why a static Markdown list and not a database or website?**

- **Zero infrastructure cost.** No server, no backend, no database to maintain. GitHub renders Markdown beautifully.
- **Community-friendly.** Anyone can open a pull request to add a tool. A database would require API access or a form submission flow.
- **Version-controlled history.** Every addition or removal is tracked in git. You can see exactly when a tool was added and by whom.

**What would change if I picked differently?**

A website with a proper database would allow filtering, sorting, and search. But it adds complexity: you need a domain, hosting, a deployment pipeline, and someone to maintain the backend. For a community list, the friction of a PR is intentional — it filters out low-quality additions. A form anyone can submit to would flood the list with noise.

### The README Structure (HTML + Markdown hybrid)

The README uses a mix of raw HTML (for the `<h1>` and `<p>` tags at the top) and standard Markdown. This is because GitHub renders both, and the HTML allows slightly richer formatting where needed. The anchor tags (`<a id="...">`) enable deep-linking to sections — so someone can share a direct link to the Fuzzing section, for example.

---

## Step 5: What Tradeoffs Did I Make?

Every decision is a bet. Here's what I bet on and what I gave up:

| Decision | What I Gained | What I Gave Up |
|---|---|---|
| Markdown over a website | Zero maintenance, easy contributions | No search, filtering, or sortability |
| Curated list (not exhaustive) | Quality and signal-to-noise ratio | Some tools are missed; completeness |
| Category-based organisation | Fast tool selection by technique | No cross-category comparisons |
| Keeping archived tools (labelled) | Historical context, academic value | Slightly longer list, possible confusion |
| Linking to external GitHub repos | Always up-to-date source of truth | Broken links if repos are deleted/moved |

The biggest tradeoff was **quality vs. completeness**. A list that tries to include everything ends up being useful to no one. A list that's too selective becomes an opinion piece. The sweet spot is a clearly-labelled, regularly-maintained list that acknowledges its own limitations.

---

## Step 6: What Mistakes, Dead Ends, or Wrong Turns Did We Hit?

**Dead link problem:** Some links in the existing list pointed to places that weren't the canonical source (e.g., the SolMet entry had a broken/incomplete URL `SolMet-Solidity-parser` without a full GitHub link). This is a known hazard of curated lists — the external world changes and the list doesn't automatically update.

**The "Mix" category is a catch-all:** Tools like Mythril combine symbolic execution, static analysis, and other techniques. Deciding where to put a multi-technique tool is genuinely hard. The current solution (a "Mix" category) is pragmatic but imperfect — it can become a dumping ground for anything that doesn't fit neatly elsewhere.

**Over-relying on the anchor papers:** The two papers are excellent starting points, but they reflect a 2019–2022 snapshot. The gap between "what the papers mention" and "what practitioners actually use today" is real. Slither, Aderyn, and Halmos are all widely used in 2024–2025 and aren't in the anchor papers at all.

**Lesson:** Don't let your sources become your ceiling. Use the anchor papers as a foundation, not a fence.

---

## Step 7: Pitfalls to Watch Out For in the Future

**1. Link rot is silent and deadly.**
External links break over time. GitHub repos get renamed, deleted, or transferred. Set a reminder to audit links periodically. Tools like `markdown-link-check` can automate this.

**2. "Archived" is not the same as "useless."**
An archived tool might still be the best reference implementation of a specific technique, even if it's not actively developed. Label it clearly, but don't delete it.

**3. Category boundaries will blur.**
As tools evolve, they add features. A fuzzer adds static analysis. A static analyser adds symbolic execution. Your categories will need occasional re-evaluation.

**4. Community contributions need quality gates.**
Without a contribution policy, pull requests will add everything from well-documented industry tools to someone's three-day hackathon project. The CONTRIBUTION.md file is your quality gate. Keep it updated and specific.

**5. Don't confuse "stars on GitHub" with "quality."**
A tool can have 5,000 stars because it was featured on a popular newsletter, not because it's technically superior. Conversely, some of the most rigorous formal verification tools have under 100 stars because their user base is small and academic.

---

## Step 8: What Would an Expert Notice That a Beginner Would Miss?

**The technique taxonomy is not just aesthetics — it's epistemology.**

A beginner sees the categories as labels. An expert sees them as a map of *what questions you can answer*:

- **Static analysis** tells you: "Does this code pattern look suspicious?" — fast, but produces false positives.
- **Symbolic execution** tells you: "Is there *any* input that could reach this dangerous state?" — thorough, but computationally expensive.
- **Fuzzing** tells you: "Can I find a real input that breaks this?" — fast at finding bugs but misses bugs it hasn't been pointed at.
- **Formal verification** tells you: "Can I *prove* this contract always behaves correctly?" — the gold standard, but requires significant expertise and specification work.

An expert would also notice:

- **The absence of AI/ML-based tools** as a distinct category. Tools like ESCORT and ContractWard (in the Research section) use deep learning for vulnerability detection. This is a fast-growing area that will likely need its own section soon.
- **No Layer 2 / non-EVM coverage.** The list is almost exclusively EVM-focused. A Solana, Move, or CosmWasm auditor would find little here.
- **The Research section is not linked back to Tools.** An expert would want to know: "Which tool implements the technique from this paper?" Cross-referencing papers to their tool implementations is valuable and currently missing.

---

## Step 9: What Can You Apply to Completely Different Projects?

**The meta-skill here is: knowing how to build a useful map.**

Whether you're curating smart contract tools, documenting an API, organising a startup's knowledge base, or building a learning curriculum — the same principles apply:

### 1. Start with the real user journey, not an exhaustive taxonomy.
Don't organise things the way *you* understand them. Organise them the way *a newcomer* will approach them. That's why Static Analysis comes before Formal Verification — you meet users where they are.

### 2. Acknowledge what's missing.
The best maps mark "here there be dragons." Noting that a tool is archived, that a link might be stale, or that a category is incomplete builds trust. It signals: "I am not trying to oversell this."

### 3. Every list needs a forcing function for quality.
Without CONTRIBUTION.md, the list grows into chaos. In any collaborative project — a shared codebase, a wiki, a documentation site — the rules for contributing are as important as the content itself.

### 4. The reference is not the reality.
The anchor papers were the best available reference at the time they were written. The tools landscape had already moved on. In any field, the canonical textbook lags behind practice. Talk to practitioners, not just papers.

### 5. Maintenance is a feature, not an afterthought.
A curated list that isn't maintained is a liability, not an asset. Build the maintenance plan before you build the thing. Who updates it? How often? What triggers a review?

### 6. The hardest decisions are about what to *leave out.*
Inclusion is easy; exclusion is the hard editorial judgement that makes a list valuable. The same applies to code (delete the unnecessary abstraction), writing (cut the filler sentences), and design (remove the feature that complicates the interface).

---

*This document was written to help you think like a builder, not just a consumer. The tools list is the artifact. The thinking behind it is the skill. Keep the thinking.*
