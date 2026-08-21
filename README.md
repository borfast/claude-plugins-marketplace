# claude-plugins-marketplace

A Claude Code plugin marketplace listing the plugins I publish.

The marketplace is named `borfast`, so plugins install as `<plugin>@borfast`.

## Use it

```
/plugin marketplace add borfast/claude-plugins-marketplace
/plugin install gorfast@borfast
```

Adding the marketplace is a one-time step. Everything listed below installs
with the `@borfast` suffix afterwards.

## Plugins

| Plugin | Repository | What it is |
|---|---|---|
| `gorfast` | [borfast/gorfast](https://github.com/borfast/gorfast) | Skills for building web applications in Go |

## Adding a plugin

Add an entry to `.claude-plugin/marketplace.json` pointing at the plugin's own
repository:

```json
{
  "name": "example",
  "source": { "source": "url", "url": "https://github.com/borfast/example.git" },
  "description": "..."
}
```

Entries deliberately omit `version`. It is resolved from the plugin's own
`plugin.json`, so a release means bumping one file in one repository rather
than keeping two in sync.

Validate before pushing:

```bash
claude plugin validate .
```

## Note on the name

The marketplace format (`.claude-plugin/marketplace.json`) is specific to
Claude Code, so this repository is named for it. Plugins listed here may
support other agent harnesses in their own repositories.
