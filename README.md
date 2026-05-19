# Resume Tailoring — Claude Project Setup Guide

This folder contains everything you need to set up a Claude Project that
generates ATS-optimised, tailored resumes from a single source of truth.

---

## Architecture: Generic vs. Personal Layer

The project is split into two layers so it can be adapted for different people without rewriting the prompt logic:

- **Generic layer** (works for anyone): `project-instructions.md`, `writing-preferences.md`, `resume-template.md`
- **Personal layer** (one person's identity + history): `personal-profile.md`, `master-resume.md`

To adapt this project for a different person, edit only the **Personal layer**. The generic layer references the personal layer through soft references (e.g. "see `personal-profile.md` for the resume title set") and works as-is.

---

## Files In This Package

| File                      | What It Is                                                                  | Layer    | Upload To Project                    |
| ------------------------- | --------------------------------------------------------------------------- | -------- | ------------------------------------ |
| `project-instructions.md` | The Claude Project system prompt                                            | Generic  | ✅ Paste into "Project Instructions" |
| `writing-preferences.md`  | Editorial style guide — tone, verb register, format, common mistakes        | Generic  | ✅ Upload as project file            |
| `resume-template.md`      | Structural layout + visual styling rules                                    | Generic  | ✅ Upload as project file            |
| `resume-style.json`       | Concrete styling parameters — font, colours, sizes, spacing                 | Generic  | ✅ Upload as project file            |
| `personal-profile.md`     | Identity, positioning, resume title set, cross-cutting accuracy constraints | Personal | ✅ Upload as project file            |
| `master-resume.md`        | Verified career data — experience, metrics, skills                          | Personal | ✅ Upload as project file            |
| `README.md`               | This file — setup guide                                                     | —        | ❌ Keep locally                      |

---

## Setup Steps

### 1. Create a new Claude Project

Go to [claude.ai](https://claude.ai) → **Projects** → **New Project**.
Name it something like: `Resume Tailoring — [Your Name]`

### 2. Add the Project Instructions

- Open the project → **Edit Project Instructions**
- Open `project-instructions.md` and paste the entire contents in
- Save

### 3. Upload the five knowledge files

Inside the project, click **Add content** (or the paperclip/upload icon):

- Upload `master-resume.md` — verified career data
- Upload `personal-profile.md` — identity, positioning, accuracy constraints
- Upload `writing-preferences.md` — tone, verbs, format
- Upload `resume-template.md` — structural scaffold + styling rules
- Upload `resume-style.json` — concrete styling parameters

Claude will have persistent access to all five files across every conversation in this project.

---

## How To Use The Project

### Basic usage

Start a new chat inside the project and paste in a job description:

> "Here's a JD for a Senior PM role at Notion. Can you tailor my resume for it?"

Claude will:

1. Analyse the JD, extract the keyword list, and assess fit
2. State the positioning angle it's using
3. Generate a complete tailored resume (ready to download as `.docx`)
4. Provide tailoring notes — targeted keywords, ATS match estimate, decisions

### Iterating on a resume

After the first output, you can refine:

- "Make the summary shorter and more direct"
- "Emphasise the engineering side more — this is a founding role"
- "Remove the ASOS entry and give Crikle more space"
- "The JD mentions Figma a lot — can you surface the design skills more?"

### Checking fit before tailoring

You can also ask Claude to assess fit before generating a full resume:

- "Read this JD and tell me how strong a fit I am before we write anything"

---

## Forking For Your Own Use

To adapt this project for a different person:

1. **Replace `master-resume.md`** with the new person's career data. Keep the same structure (per-role `Responsibilities`, `Notable developments`, `Key achievements`, `Verified metrics`, `AI scope`, `Accuracy note` where applicable).
2. **Rewrite `personal-profile.md`** for the new person:
   - **Core Positioning Statement** — one sentence describing how they pitch themselves
   - **What You Are NOT** — framings to refuse even when invited (e.g. for an IC engineer who isn't a manager, list "people leader" here)
   - **Resume Title — Fixed Set** — the canonical titles they're willing to use (e.g. a designer might use "Senior Product Designer / Staff Product Designer / Design Lead")
   - **AI Scope — Conservative Register** — only if they have _some_ AI exposure that's been overclaimed by past resumes; otherwise remove this section
   - **Cross-Cutting Accuracy Constraints** — domain-specific overclaim guards (e.g. "no full-stack claims if the experience was frontend-only")
3. **Leave the generic files alone** — `project-instructions.md`, `writing-preferences.md`, and `resume-template.md` work as-is.
4. **Update `resume-template.md` contact line** with the new person's contact info.
5. **Optionally tweak `resume-style.json`** if you want a different accent colour, font, or sizing. The defaults match a clean, ATS-friendly style

The generic files reference the personal files by name. As long as the personal files exist and follow the same section structure, the prompt logic continues to work.

---

## Keeping The Source of Truth Up To Date

Files have different update cadences — treat them separately:

**`master-resume.md`** — update when career facts change: new role, confirmed metric, new tech used, new responsibility. Rare and deliberate.

**`personal-profile.md`** — update when positioning evolves: a new "what you are not" framing surfaces, AI scope expands, you decide to drop a title from the fixed set. Occasional.

**`writing-preferences.md`** — update if your editorial preferences drift (verb register, common mistakes you keep noticing). Rare.

**`resume-template.md`** — update if the _layout structure_ changes (new section, different ordering). Rare.

**`resume-style.json`** — update for visual parameter changes (accent colour, font family, sizes, margins, spacing). One-line edits, no prompt changes needed.

To update any file: edit it locally, delete the old version from the Claude Project, and re-upload. Changes made only inside a conversation do not persist.

---

## Tips For Best Results

- **Paste the full JD**, not just the title. The more signal Claude has, the better the keyword extraction and tailoring.
- **Include the company name** — Claude may use it to frame industry context.
- **Tell Claude the seniority level** if it's unclear from the JD — it drives the title pick from the fixed set.
- **Ask for a cover letter** in the same conversation — Claude will use the same tailoring decisions consistently.
