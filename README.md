# TechTown Skills

A collection of reusable agent skills for TechTown projects.

## Available Skills

| Skill                                                         | Description                                 |
| ------------------------------------------------------------- | ------------------------------------------- |
| [techtown-brand-guidelines](skills/techtown-brand-guidelines) | TechTown brand and design system guidelines |

## Installation

Install skills using the [skills CLI](https://github.com/vercel-labs/skills):

```bash
# Install all skills
npx skills add techtown-fr/skills

# Install a specific skill
npx skills add techtown-fr/skills --skill techtown-brand-guidelines

# Install to a specific agent (e.g., GitHub Copilot)
npx skills add techtown-fr/skills -a github-copilot

# List available skills without installing
npx skills add techtown-fr/skills --list
```

## Creating a New Skill

1. Create a directory under `skills/`:

   ```bash
   mkdir skills/my-new-skill
   ```

2. Add a `SKILL.md` file with YAML frontmatter:

   ```markdown
   ---
   name: my-new-skill
   description: Brief description of what this skill does
   metadata:
     author: techtown
     version: "1.0"
   license: MIT
   ---

   # My New Skill

   Instructions for the agent...
   ```

3. Add any supporting assets or reference files as needed.

## License

Each skill has its own license. See the individual skill directories for details.

## Related Links

- [Agent Skills Specification](https://agentskills.io/)
- [Skills CLI](https://github.com/vercel-labs/skills)
- [Skills Directory](https://skills.sh/)
