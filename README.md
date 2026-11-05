# NetEye Platform AI agents tools

The Claude Code plugin marketplace of the NetEye Platform team. Its name is
`neteye-platform`. It lists the plugins and mods that the team develops. Each
plugin lives in its own repository, and this repository only points to them.

## Plugins

| Plugin | Description |
| --- | --- |
| [`cc-split-diff-view`](https://github.com/neteye-platform/cc-split-diff-view) | `Edit`, `Write` and `Bash` diffs in two side-by-side columns, and `/diffsplit` to review all uncommitted changes |
| [`cc-side-session-summary`](https://github.com/neteye-platform/cc-side-session-summary) | A live side pane with the worktree, goal, progress checklist and token and cost stats |

## Add the marketplace

From a terminal:

```bash
claude plugin marketplace add neteye-platform/ai-agents-tools
```

Or from inside a Claude Code session:

```text
/plugin marketplace add neteye-platform/ai-agents-tools
```

You add the marketplace one time only. New plugins appear in it when this
repository lists them.

## Install a plugin

```bash
claude plugin install <plugin>@neteye-platform
```

For example:

```bash
claude plugin install cc-split-diff-view@neteye-platform
claude plugin install cc-side-session-summary@neteye-platform
```

Then start a new session or run `/reload-plugins`.

## Update

```bash
claude plugin marketplace update neteye-platform
claude plugin update <plugin>@neteye-platform
```

## Add a new plugin

1. Give the plugin repository a `.claude-plugin/plugin.json`. Do not add a
   `marketplace.json` to it.
2. Add an entry to `plugins` in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json):

   ```json
   {
     "name": "<plugin>",
     "description": "<one line>",
     "source": { "source": "github", "repo": "neteye-platform/<plugin>" }
   }
   ```

3. Add a row to the table in this README.
4. Check the manifest with `claude plugin validate .`.

## License

Dual-licensed under either of [Apache License 2.0](LICENSE-APACHE) or
[MIT](LICENSE-MIT), at your option.
