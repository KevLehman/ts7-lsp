TypeScript/JavaScript code intelligence for Claude Code from the native TypeScript 7 language server (`tsc --lsp`).

It runs the project's own `tsc`: the nearest `node_modules/.bin/tsc` above the project root, or `tsc` on `PATH` when there is none. That `tsc` must be TypeScript 7 or later, so enable the plugin only in projects on TypeScript 7.

See the [repository README](https://github.com/KevLehman/ts7-lsp#readme) for install steps and requirements.
