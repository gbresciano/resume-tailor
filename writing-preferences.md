# Generic Conventions & Style Guide

> Tone, wording, formatting, and shared conventions used by the resume-tailoring project. Generic — applies regardless of who's using the project.
>
> - Personal identity, positioning, AI scope, and cross-cutting accuracy constraints live in `personal-profile.md`.
> - Factual career data lives in `master-resume.md`.
> - Workflow, decision logic, and output sequencing live in `project-instructions.md`.
> - Visual styling (typography, colours, spacing, docx specs) lives in `resume-template.md` and `resume-style.json`.

---

## ATS Optimisation Principle

ATS systems score resumes largely on keyword overlap with the JD. To maximise the score:

- **Mirror the JD's exact terminology** when the master resume supports it. JD says "A/B testing" → write "A/B testing" (not "experimentation"). JD says "product-led growth" → use that phrase verbatim.
- **Pack the skills section with JD keywords** evidenced in the master resume — the skills section is heavily weighted by many ATS systems.
- **Use JD keywords across summary, bullets, and skills** — repetition across sections boosts match scores.
- **Truthfulness gate:** a keyword only goes in if the master resume genuinely supports it. Never invent a skill or experience to hit a keyword.

---

## Keep Tailoring Invisible

The resume should read as a polished personal document — not a one-off written for this specific JD. Mirror the JD's domain and vocabulary, but never reveal who the resume is aimed at.

- **Never name the target company or its products** anywhere in the resume (summary, bullets, skills, subtitle). E.g. ❌ "the same TypeScript/React/GCP stack [Target] runs on" → ✅ "shipped on a TypeScript/React/GCP stack".
- **Never address the target in second person.** No "your team", "your product", "what you're building".
- Mirror **domain language**, not **branding**. The reader should infer the target from emphasis and vocabulary, not from explicit mentions.

---

## Master Resume Schema

Every primary experience entry in `master-resume.md` uses the same field set in the same order. Fields are optional unless marked **required**. Empty fields are omitted.

| Field                    | Required | Purpose                                                                                                       |
| ------------------------ | :------: | ------------------------------------------------------------------------------------------------------------- |
| **Sort order**           |    ✓     | Integer — position in rendered Experience section. Lower numbers appear first.                                |
| **Role**                 |    ✓     | Canonical job title held                                                                                      |
| **Role variants**        |          | Alternative titles when a JD better fits a different framing (founder-type roles)                             |
| **Previous role**        |          | Flag (`Yes`) — collapsed render by default (see project-instructions.md)                                      |
| **Company**              |    ✓     | One-line company description                                                                                  |
| **Website**              |          | Company URL — hyperlinks the company name (see `resume-template.md`)                                          |
| **Location**             |          | Geographic location (e.g. "London, UK")                                                                       |
| **Domain tags**          |          | Pipe-separated tags: industry, audience, business model, product category (e.g. `EdTech \| B2C \| Subscription`) |
| **Core narrative**       |          | One-line punchline for founder/0→1 roles                                                                      |
| **Verified metrics**     |          | Exact verified figures only — never approximated or combined                                                  |
| **Key achievements**     |          | Top-level outcomes (3–5 items)                                                                                |
| **Responsibilities**     |    ✓     | Ongoing scope of the role                                                                                     |
| **Notable developments** |          | Specific systems, features, or technical work shipped — primary source for tailored bullets                   |
| **Tech stack**           |          | Engineering technologies used                                                                                 |
| **Tools**                |          | Analytics, PM, and ops tools used                                                                             |
| **AI scope**             |          | Honest description of AI work done, with overclaim guards                                                     |
| **Accuracy notes**       |          | Per-role truth constraints                                                                                    |

`Key achievements`, `Notable developments`, and `Verified metrics` are the highest-value fields for bullet generation. If a role only has `Responsibilities`, bullets read generically — flag in Tailoring Notes.

---

## Resume Subtitle

**Specificity tracks experience depth, not JD demand.** Be as specific as truthfully possible — but no more.

- **Deep evidence** in the JD's domain → name it explicitly in the subtitle (industry, product type, audience, growth mechanic).
- **Shallow evidence** → stay broad, don't name it. Use higher-level categories (role archetype, go-to-market, audience type). Broad-but-true beats specific-but-stretching.
- The subtitle carries JD-aligned keyword density — but only with terms the master resume supports.
- Rewrite the subtitle fresh per application.
- **Format:** each item is a complete, standalone noun phrase. Items must make sense in isolation. Single words / abbreviations / symbols without qualifiers read as filler — always expand. Concrete item examples (and fragments to avoid) live in `personal-profile.md`.
- **Separator:** use the pipe from `resume-style.json` (`separators.subtitle`). Full line: `[Resume Title] | [Item 1] | [Item 2] | [Item 3]`. Don't use `·` or other separators.

When in doubt: can you point to a specific `Notable development` or `Key achievement` in `master-resume.md` that backs this phrase? If not, broaden.

---

## Markdown Role-Header Format

When rendering Experience entries in the markdown preview, use this multi-line format (tab-stop layouts don't translate to markdown — whitespace collapses):

```
### [Role Title] · [Company]
**[Start] – [End] · [Location]**

[Optional: one-line company description]

- Bullet
- Bullet
```

If the role has a `Website` field, render the company name as a markdown link in the H3: e.g. `### Head of Product · [Loop](https://www.intheloop.io)`. The URL never appears as visible text — only as the link target.

---

## Tone

**Use:** high-agency, builder-oriented, product-minded, clear and concise, metrics-backed, practical, modern startup register.

**Avoid:** corporate jargon, inflated claims, excessive buzzwords or adjectives, specialist framing without direct experience, long paragraphs in bullets.

---

## Wording Defaults

### Action Verbs — Register Examples

Open bullets with strong, specific action verbs in this register (illustrative, not exhaustive — pick whatever fits the action and the JD's vocabulary):

Built · Designed · Led · Owned · Defined · Improved · Shipped · Launched · Conceived · Implemented · Increased · Simplified · Architected · Drove · Scaled · Migrated · Rebuilt · Established · Reduced

**Mirror JD verbs when truthful.** If the JD says "spearheaded," "championed," "delivered," "orchestrated," etc., and the underlying work supports it, use the JD's verb.

### Weak Verbs — Avoid By Default

Don't open bullets with: helped · assisted · participated · supported · worked on. If the JD uses one of these for a responsibility genuinely owned, rewrite to a stronger verb.

### Domain-Sensitive Phrasing

Some claims (AI/ML expertise, people management scope, specialised technical work) must be calibrated to actual experience. Conservative register and "never use" lists live in `personal-profile.md`.

---

## Common Mistakes To Avoid

- "Responsible for..." — rewrite as active verb
- "Worked closely with..." — rewrite as what was actually achieved
- Vague bullets like "Improved user experience" — add specifics or metrics
- Overloading the summary with adjectives rather than substance
- Listing skills not evidenced in the experience section
- Reusing the same resume structure regardless of role
- Paraphrasing `Responsibilities` when `Notable developments` / `Key achievements` would yield richer bullets
- Merging two unrelated items into one bullet for density — split them instead

---

## Length

- Single page preferred
- Two pages acceptable for senior/strategic roles
- Never pad to fill space — cut before you expand
