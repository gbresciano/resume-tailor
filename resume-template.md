# Resume Template

> **How to use this file:** Structural and visual scaffold for the generated resume. Claude fills it in when tailoring — edit the _generated output_, not this file. Contact info placeholders should be replaced with the user's real details when adopting this project for a new person.

---

## Layout

Single-column, top-to-bottom, with **vertical spacing** (not horizontal rules) separating sections.

```
[NAME IN ALL CAPS]
[Resume Title] | [Subtitle]

[Phone]  •  [Email]  •  [Website]
[Location]


SUMMARY

[3–5 lines, written fresh for the specific role.]


EXPERIENCE

[Role Title]                                        [Start] – [End]
[Company]  •  [URL]                                       [Location]
[Optional: one-line company description]

• Bullet
• Bullet
• Bullet


[Role Title]                                        [Start] – [End]
[Company]  •  [URL]                                       [Location]
[Optional: one-line company description]

• Bullet
• Bullet


EARLIER EXPERIENCE

[Role]  •  [Company]  •  [Dates]
[Role]  •  [Company]  •  [Dates]


SKILLS

[Group]: skill • skill • skill • skill
[Group]: skill • skill • skill • skill
[Group]: skill • skill • skill • skill
```

---

## Visual Styling — Keep It Consistent and Simple

The goal is a clean, low-noise document. Achieve this with **just three typography levels** and **one accent colour**. Don't add a fourth weight, a second accent, or any decoration that isn't on this page.

**All concrete parameters — font family, sizes, colours, spacing values, margins — live in `resume-style.json`.** Read that file for exact values. The rules below define _how_ those parameters are applied, not the values themselves.

### Typography — only three levels

| Level    | Used for                                                | Weight in `resume-style.json`                                                                                                       |
| -------- | ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **H1**   | Name                                                    | `typography.name`                                                                                                                   |
| **H2**   | Section titles, Role titles                             | `typography.section_title` (for section headings) and `typography.role_title` (for role headings — same size/weight, accent colour) |
| **Body** | Everything else (company, description, bullets, skills) | `typography.body`                                                                                                                   |

The line under the name contains both the **Resume Title** (from the fixed set in `personal-profile.md`) and the **Subtitle** (specificity-tracks-depth rule in `project-instructions.md`), separated by `|`. Both parts share the same styling — they use `typography.resume_title` in `resume-style.json`. This is **not** a fourth typography level; it sits directly under the name with normal styling.

**Always include both title and subtitle.** If only the title appears, the resume is missing the subtitle.

### Colour — only two

The two colours are defined in `resume-style.json` under `colors.body` and `colors.accent`. The accent colour is used **only** on the Name and Role titles. Never apply it to bullets, separators, body text, etc. Links use the accent colour without underline (see `links` in the JSON).

### Section breaks — no rules, only spacing

**No horizontal rules.** No `━━━`, no thin lines, no decorative separators. Sections are visually broken by:

- The bold ALL CAPS section title (sufficient on its own)
- Vertical spacing above each section title (see `spacing.before_section_title_pt` in the JSON)

### Alignment

- **Role line:** Role title left, dates right — same line, achieved via tab stop (not a table)
- **Company line:** Company + URL left, location right — same line, same way
- **Everything else:** Left-aligned, full-width

### Bullets

- Simple round bullets — character defined in `bullets.character` in the JSON
- Standard indent
- Bullet colour matches body (never accent)
- No custom markers, no nested bullets

### Spacing

Spacing values are in `resume-style.json` under `spacing`:

- `between_bullets_pt` — within a role
- `between_roles_pt` — between roles
- `before_section_title_pt` — above each section heading
- `line_height` — for body text

Apply these values consistently across the whole document — same gap pattern for every section, every role.

### Font

One sans-serif family applied **everywhere**: see `font.primary` in the JSON (with `font.fallbacks` if the primary isn't available). Don't mix fonts.

### Italics, underlines, photos — avoid

- No italics
- No underlines (links inherit the accent colour — never underlined)
- **No profile photo.** Photos hurt ATS parseability — most parsers skip or break on the image region. Omit even if a sample shows one. Re-add manually for non-ATS submissions if desired.
- No background colours or shading
- No icons next to contact info — plain text only

### Decorative elements that must NOT appear

- Horizontal rules between sections
- More than one accent colour
- More than three typography levels
- Italics
- Underlines (including auto-styled hyperlinks)
- Tables for layout (use tab stops)
- Multi-column layouts
- Profile photos
- Page borders
- Shaded boxes

---

## Docx Export Specs

- Single column (see `layout.columns` in the JSON)
- Margins from `spacing.margins_cm` in the JSON
- One sans-serif font family throughout (from `font.primary`)
- Body size from `typography.body.size_pt`
- Hyperlinks: accent colour, no underline (per `links` in the JSON)
- Export to PDF before submitting to verify ATS parseability

**To change any visual parameter** (e.g. swap the accent colour, increase body size, tighten margins): edit `resume-style.json` and re-upload. No prompt changes needed.
