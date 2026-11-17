# ts7-lsp

A Claude Code plugin that gives Claude TypeScript/JavaScript code intelligence from the native
TypeScript 7 language server (`tsc --lsp --stdio`).

The official `typescript-lsp` plugin runs `typescript-language-server`, which wraps the classic
`tsserver.js`. TypeScript 7 no longer ships `tsserver.js`, so that plugin falls back to its own
bundled TypeScript and checks your code with the wrong compiler.

## Which `tsc` it runs

The project's own: `node_modules/.bin/tsc` in the project root, so the server always matches the
TypeScript version the project builds with, whatever the package manager. It never looks above the
project root. With no `tsc` there (for example Yarn Plug'n'Play, or a monorepo package opened on its
own), it uses `tsc` from your `PATH`.

That `tsc` must be TypeScript 7 or later. An older one has no `--lsp` mode and the server
won't start, so enable the plugin only in projects on TypeScript 7.

## Install

```
/plugin marketplace add KevLehman/ts7-lsp
/plugin install ts7-lsp@ts7-lsp --scope local
/plugin disable typescript-lsp@claude-plugins-official --scope local
/reload-plugins
```

`--scope local` turns it on for the current project only. The last `disable` is needed only if you
have the official plugin enabled.

## Requirements

- TypeScript 7 or later, in the project or on `PATH`
- A POSIX shell (macOS, Linux, WSL). Windows without WSL isn't supported.

## License

MIT
