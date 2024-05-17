# VS Code import issue

## Steps to reproduce

1. Open `index.mjs` (and close all other files).
2. Type the word `namedExport`. VS Code will suggest an import from the `example` package, as expected. ✅
3. Type the word `defaultExport`. In this case, VS Code will suggest an import from a nested path (`example/dist/nested/module`) instead of from `example`. ❌

## Explanation

The `node_modules` directory contains an `example` package, which re-exports the two functions `defaultExport` and `namedExport` and their type definitions from a nested directory. If a type definition for a default export is re-exported in a package, VS Code incorrectly suggest a longer import path.
