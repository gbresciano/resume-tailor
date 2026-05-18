# Resume Tailoring — Claude Project Setup Guide

This folder contains everything you need to set up a Claude Project that
generates tailored resumes from a single source of truth.

---

## Files In This Package

| File | What It Is | Upload To Project |
|---|---|---|
| `project-instructions.md` | The Claude Project system prompt | ✅ Paste into "Project Instructions" |
| `master-resume.md` | Verified career data — experience, metrics, skills | ✅ Upload as project file |
| `writing-preferences.md` | Tone, wording rules, positioning, fit guidance | ✅ Upload as project file |
| `resume-template.md` | Structural layout scaffold | ✅ Upload as project file |
| `tailoring-playbook.md` | Role-type tailoring rules | ✅ Upload as project file |
| `README.md` | This file — setup guide | ❌ Keep locally |

---

## Setup Steps

### 1. Create a new Claude Project
Go to [claude.ai](https://claude.ai) → **Projects** → **New Project**.
Name it something like: `Resume Tailoring — Guillo Bresciano`

### 2. Add the Project Instructions
- Open the project → **Edit Project Instructions**
- Open `project-instructions.md` and paste the entire contents in
- Save

### 3. Upload the four knowledge files
Inside the project, click **Add content** (or the paperclip/upload icon):
- Upload `master-resume.md` — verified career data
- Upload `writing-preferences.md` — tone, positioning, and fit guidance
- Upload `resume-template.md` — structural scaffold
- Upload `tailoring-playbook.md` — role-type tailoring rules

Claude will have persistent access to all three files across every conversation
in this project.

---

## How To Use The Project

### Basic usage
Start a new chat inside the project and paste in a job description:

> "Here's a JD for a Senior PM role at Notion. Can you tailor my resume for it?"

Claude will:
1. Analyse the JD and assess fit
2. State the positioning angle it's using
3. Generate a complete tailored resume (ready to copy into Google Docs)
4. Provide tailoring notes explaining every decision

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

## Keeping The Source of Truth Up To Date

The two knowledge files have different update cadences — treat them separately:

**`master-resume.md`** — update when career facts change: new role, confirmed
metric, new tech used, new responsibility. This should be rare and deliberate.

**`writing-preferences.md`** — update when preferences evolve: new tone
direction, refined positioning, updated fit judgements, new safe/unsafe wording.
This may change more frequently as you refine your approach.

To update either file: edit it locally, delete the old version from the Claude
Project, and re-upload. Changes made only inside a conversation do not persist.

---

## Tips For Best Results

- **Paste the full JD**, not just the title. The more signal Claude has, the
  better the tailoring.
- **Include the company name** — Claude may use it to frame industry context.
- **Tell Claude the seniority level** if it's unclear from the JD.
- **Ask for a cover letter** in the same conversation — Claude will use the same
  tailoring decisions consistently.
- **Copy the resume output into Google Docs** and apply the formatting from the
  Google Docs notes in `resume-template.md`.
