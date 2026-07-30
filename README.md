# Example Agent Skill

This repository is a small, generic example of an agent skill. It demonstrates
how to give an agent focused instructions for reviewing a repository without
depending on a specific product or service.

## Files

- `SKILL.md` - the skill definition and repository review procedure.
- `README.md` - this overview and usage guidance.
- `LICENSE` - the MIT license.

## Structure

```text
.
|-- README.md
|-- SKILL.md
`-- LICENSE
```

## How an agent should use the skill

1. Read `SKILL.md`, including its frontmatter, before starting a repository
   review.
2. Use the skill when the task is to inspect a repository and report risks or
   recommend a small, safe change.
3. Follow its review steps and keep the review limited to the requested scope.
4. Return the concise response format defined by the skill. State what was
   checked and do not claim that an unrun validation command passed.

The skill is intentionally generic. It can be adapted to different
repositories and workflows without assuming a particular product integration.

## License

This repository is licensed under the MIT License. See `LICENSE` for the full
license text.
