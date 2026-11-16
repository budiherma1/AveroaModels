<h1 align="center">@averoa/models</h1>

<p align="center">
  <img src="https://img.shields.io/badge/status-deprecated-red.svg" alt="Deprecated">
  <a href="https://www.npmjs.com/package/@averoa/models"><img src="https://img.shields.io/npm/v/@averoa/models?color=cb3837&logo=npm" alt="npm version"></a>
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License: MIT">
</p>

<p align="center">
  ⚠️ <b>Deprecated since AveroaJS 2.0.</b> Do not add this package to new apps.<br>
  Use the <code>#models</code> subpath import of the
  <a href="https://github.com/budiherma1/averoajs">AveroaJS boilerplate</a> instead.
</p>

---

This package only re-exported your app's `app/Models/index.js` through a fixed
relative path (`./../../../app/Models/index.js`). That only works when the package is
installed at exactly `node_modules/@averoa/models`, and it breaks with pnpm,
npm workspaces, symlinked installs and monorepos.

## Migrating to AveroaJS 2.0

Add a subpath import to your app's `package.json` (the 2.0 boilerplate already has it):

```json
{
  "imports": {
    "#models": "./app/Models/index.js"
  }
}
```

Then replace

```js
import { Something } from '@averoa/models';
```

with

```js
import { Something } from '#models';
```

and remove `@averoa/models` from your dependencies.

Apps still on AveroaJS 1.x can keep using this package unchanged.
