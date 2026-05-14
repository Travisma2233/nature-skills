# `nature-paper-writing` skill

A research-writing skill for drafting, restructuring, and self-reviewing Nature-family and high-impact ML/CV/NLP-style manuscripts.

It focuses on manuscript architecture rather than sentence polishing alone: section roles, paragraph flow, claim-evidence alignment, reviewer-facing framing, figure/table presentation, and end-of-draft adversarial review.

## Important Attribution

Most writing knowledge and methodology in this repository comes from Prof. Peng Sida (彭思达)'s open study notes:
[https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e](https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e)

Prof. Peng's original repository:
[https://github.com/pengsida/learning_research](https://github.com/pengsida/learning_research)

I sincerely thank Prof. Peng for openly sharing these valuable experiences. My contribution is organization, structured adaptation, and packaging as reusable Skills.

## What it does

- turns rough notes or draft sections into reviewer-readable manuscript prose
- builds compact outlines before drafting
- rewrites Abstract, Introduction, Related Work, Method, Experiments, and Conclusion sections with section-specific logic
- checks every major claim against available evidence
- audits paragraph flow with reverse outlining
- reviews figures, tables, teaser figures, and pipeline figures as part of the paper argument
- runs a final five-dimension self-review before submission

## When to use

- drafting a new paper section from notes
- revising an unclear Introduction, Abstract, Method, Results/Experiments, Related Work, or Conclusion
- checking whether paragraph flow is readable to an external reviewer
- weakening unsupported claims before submission
- aligning figures and tables with the manuscript's central argument
- doing an adversarial final pass before journal or conference submission

## File structure

```text
nature-paper-writing/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── abstract.md
    ├── conclusion.md
    ├── does-my-writing-flow-source.md
    ├── experiments.md
    ├── introduction.md
    ├── method.md
    ├── paper-review.md
    ├── related-work.md
    └── examples/
        ├── abstract-examples.md
        ├── index.md
        ├── introduction-examples.md
        └── method-examples.md
```

## Reference map

| File | Use when |
|---|---|
| `references/abstract.md` | You need a compact problem-method-result-implication abstract |
| `references/introduction.md` | You need gap framing, positioning, motivation, and contribution logic |
| `references/related-work.md` | You need synthesis rather than a paper-by-paper list |
| `references/method.md` | You need motivation, design rationale, and technical advantage |
| `references/experiments.md` | You need evaluation logic, ablations, metrics, and result claims |
| `references/conclusion.md` | You need a bounded final contribution statement |
| `references/paper-review.md` | You need final adversarial review before submission |
| `references/does-my-writing-flow-source.md` | You need paragraph flow and reverse-outline checks |
| `references/examples/` | You need examples for Abstract, Introduction, or Method writing |

## Output contract

When drafting or rewriting sections, the skill should return:

1. a compact section outline with three to seven bullets
2. revised paragraphs with explicit paragraph roles such as opening, challenge, method, advantage, evidence, or limitation
3. a short self-review checklist for clarity, flow, terminology, unsupported claims, and missing evidence
4. a claim-evidence map for each major claim, using `Claim: ... | Evidence: ... | Status: supported/needs evidence`

## Design intent

The skill should help authors make the paper easier to review without inventing scientific content. It should expose weak argument structure, unsupported claims, missing evidence, and unclear paragraph flow before polishing surface language.

It complements `nature-polishing`: use `nature-paper-writing` when the paper's argument or section logic needs work, and use `nature-polishing` when the argument is already stable and the user needs publication-quality wording.
