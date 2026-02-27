---
name: skill-from-markdown
description: >
  Create a new Agent Skill by analyzing a referenced markdown file or a folder
  containing multiple markdown files. Use when the user wants to convert
  documentation into a structured Agent Skill package following the Agent Skills
  standard.
license: MIT
metadata:
  author: coreyx
---

## Purpose

Transform one or more markdown files into a fully structured Agent Skill folder.
This includes generating:

- A valid SKILL.md with correct frontmatter fields
- A description derived from the source content
- Optional references/ files populated with the original markdown
- Optional scripts/ if the markdown describes procedures that can be automated
- Optional assets/ if the markdown includes templates or examples

## Instructions

1. **Identify the input type**
   - If the user provides a *single markdown file*, treat it as the primary source.
   - If the user provides a *folder of markdown files*, treat each file as a reference document.

2. **Extract core elements**
   - Determine the skill’s purpose from headings, summaries, or repeated themes.
   - Identify actionable steps, workflows, or procedures.
   - Identify any templates, examples, or code blocks that belong in `assets/`.

3. **Generate the SKILL.md frontmatter**
   - `name`: derive from the topic; lowercase, hyphens only.
   - `description`: concise statement of when to use the skill (≤1024 chars).
   - `license`: ask the user which license they'd like to use (e.g., MIT, Apache-2.0, proprietary). If they don't specify, omit this field.
   - `metadata.author`: ask the user for an author name (can be a personal name, team name, or company name). If they don't provide one, omit the metadata section.
   - Include other optional fields (`compatibility`) only when appropriate.

4. **Write the SKILL.md body**
   - Provide a clear, structured set of instructions based on the source markdown.
   - Keep the body focused; move long documentation into `references/`.

5. **Create folder structure**

```text
new-skill-name/
├── SKILL.md
├── references/   # include original markdown files
├── scripts/      # only if procedures can be automated
└── assets/       # templates or examples
```

6. **Populate references/**
- Copy or summarize the original markdown files.
- Preserve filenames when possible.

7. **Populate scripts/**
- Only create scripts when the markdown describes deterministic tasks.
- Scripts should be minimal, executable, and referenced from SKILL.md.

8. **Validate the result**
- Ensure the folder name of the new skill matches the `name` field.
- Ensure SKILL.md is valid markdown with correct frontmatter.
- Ensure the description clearly signals when the skill should activate.

9. **Generate a README.md**
- Create a README.md in the skill's root folder for GitHub documentation.
- Include: skill name, brief description, what it does, when to use it, installation instructions, and license.
- Keep it concise and user-friendly for developers browsing the repository.

## Examples of use

- “Create a skill from this README.md.”
- “Turn this docs/ folder into a reusable Kiro skill.”
- “Convert this workflow description into a skill with scripts.”

## Notes

- Keep SKILL.md concise; move long content into references/.
- Use progressive disclosure: only include what is needed for activation.
- Follow the Agent Skills standard for all formatting and field constraints.
