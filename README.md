# Skills Catalog Baseline

This repository is set up as a `skills.sh`-compatible catalog.

## Layout

- `skills/` - directory containing one subdirectory per skill
- `skills/<skill-name>/SKILL.md` - skill definition with YAML frontmatter and instructions

Current starter skill:

- `skills/my-first-skill/SKILL.md`
- `skills/bookstack-expert/SKILL.md`

## SKILL.md minimum requirements

Each skill file must include YAML frontmatter:

```md
---
name: my-first-skill
description: Brief explanation of what this skill does
---
```

Recommended content sections:

- `# <Skill Title>`
- `## When to use`
- `## Instructions`

## Authoring workflow

Create a new skill template:

```bash
npx skills init skills/<skill-name>
```

## Local verification

List skills discovered from this repo:

```bash
npx skills add . --list
```

Install from local path (project scope):

```bash
npx skills add . --skill my-first-skill
```

Install the BookStack skill from local path:

```bash
npx skills add . --skill bookstack-expert
```

List skills and confirm BookStack skill is discoverable:

```bash
npx skills add . --list
```

## Continuous improvement loop (recommended)

Use this loop to improve skill quality over time:

1. Update `skills/bookstack-expert/SKILL.md` based on real usage.
2. Keep test prompts in `evals/evals.json` current.
3. Run with-skill and baseline runs for each eval prompt.
4. Compare outputs qualitatively and quantitatively.
5. Iterate skill instructions, then re-run evals.

## Publish and share

1. Push this repo to GitHub.
2. Ask users to install with:

```bash
npx skills add <owner>/<repo>
```

Or install one skill explicitly:

```bash
npx skills add <owner>/<repo> --skill my-first-skill
```

## References

- Skills docs: https://skills.sh/docs
- CLI reference: https://skills.sh/docs/cli
- FAQ: https://skills.sh/docs/faq
- Open source CLI: https://github.com/vercel-labs/skills
