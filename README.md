# bake-claude-md-files

Claude Code skill - converts CLAUDE.md rules into automated checks (eslint, phpstan, pint, CI, etc.), freeing up agent context.

Inspired by [Matthieu Napoli's tweet](https://x.com/matthieunapoli/status/2024507469394039057). We extended the original prompt into a proper Claude Code skill with tooling-first priorities.

## Install

### Via skills.sh

```bash
npx skills add publicala/bake-claude-md-files
```

### Via Plugin Marketplace

```
/plugin marketplace add publicala/bake-claude-md-files
/plugin install bake-claude-md-files@publicala
```

### Manual

Copy `skills/bake/SKILL.md` into your skills directory:

```bash
# Global (all projects)
mkdir -p ~/.claude/skills/bake-claude-md-files
cp skills/bake/SKILL.md ~/.claude/skills/bake-claude-md-files/

# Project-level
mkdir -p .claude/skills/bake-claude-md-files
cp skills/bake/SKILL.md .claude/skills/bake-claude-md-files/
```

## Usage

```
/bake-claude-md-files
```

When installed as a plugin:

```
/bake-claude-md-files:bake
```

## Resources

- [CLAUDE.md Guide](https://github.com/publicala/claude-md-guide) - Presentation slides about CLAUDE.md files
- [CLAUDE.md docs](https://docs.anthropic.com/en/docs/claude-code/memory) - Official documentation
- [Matthieu Napoli's tweet](https://x.com/matthieunapoli/status/2024507469394039057) - Original inspiration

## License

MIT
