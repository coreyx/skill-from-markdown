# Skill from Markdown

A Kiro Agent Skill that transforms markdown documentation into fully structured Agent Skills.

## What it does

This skill helps you convert existing markdown files or documentation folders into properly formatted Kiro Agent Skills. It analyzes your content and generates:

- Valid SKILL.md with correct frontmatter
- Organized folder structure (references/, scripts/, assets/)
- Extracted procedures and templates
- Proper metadata and descriptions

## When to use it

- "Create a skill from this README.md"
- "Turn this docs/ folder into a reusable Kiro skill"
- "Convert this workflow description into a skill with scripts"

## How it works

The skill analyzes your markdown content to:

1. Extract the core purpose and actionable steps
2. Generate appropriate frontmatter (name, description, license, metadata)
3. Create the proper folder structure
4. Organize content into SKILL.md, references/, scripts/, and assets/
5. Validate the result follows Agent Skills standards

## Installation

Place the `skill-from-markdown` folder in your Kiro skills directory:

- User-level: `~/.kiro/skills/`
- Workspace-level: `.kiro/skills/`

## License

MIT
