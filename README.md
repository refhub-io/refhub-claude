# refhub-marketplace

> // claude_code_plugin_registry for [refhub.io](https://refhub.io)

plugin marketplace for claude code. lists all first-party refhub agent integrations — skills, mcp servers, and tooling.

---

## // install

```sh
claude plugin marketplace add refhub-io/refhub-marketplace
```

then install any plugin from the registry:

```sh
claude plugin install refhub-skill@refhub-marketplace
```

---

## // plugins

| plugin | description | version |
|--------|-------------|---------|
| [`refhub-skill`](https://github.com/refhub-io/refhub-skill) | agent skill for operating refhub through its public api v2 | `0.1.0` |

---

## // structure

```
.claude-plugin/
  marketplace.json   ← plugin registry manifest
```

the manifest lists plugin sources. claude code reads this to discover and install plugins. adding a plugin here makes it available to any user who has registered this marketplace.

---

## // adding a plugin

edit `.claude-plugin/marketplace.json` and add an entry:

```json
{
  "name": "your-plugin-name",
  "description": "...",
  "source": { "source": "github", "repo": "refhub-io/your-plugin-repo" },
  "version": "x.x.x"
}
```

the plugin repo must have `.claude-plugin/plugin.json` and a `skills/` directory at its root.

---

## // related

- [refhub-skill](https://github.com/refhub-io/refhub-skill) — agent skill covering the full refhub api v2: vault and item management, import, search, export, audit, semantic scholar metadata enrichment, and pdf upload to google drive
- [refhub.io](https://refhub.io) — the platform
