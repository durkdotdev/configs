# @durkdotdev/configs

Configuration files for developing with ESLint, Prettier, and TypeScript.

## Installation

```bash
npm install @durkdotdev/configs -D

# or
yarn add @durkdotdev/configs -D

# or
pnpm add @durkdotdev/configs -D

```

## Usage

### ESLint

There are two different ESLint configs in this package:

- `base.json`
- `typescript.json`

1. Install configuration file, ESLint, and ESLint plugins:

```bash
npm install @durkdotdev/configs eslint eslint-plugin-simple-import-sort eslint-plugin-unused-imports -D

# TypeScript
npm install @durkdotdev/configs @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-plugin-simple-import-sort eslint-plugin-unused-imports -D
```

2. Create a `.d-eslintrc.js` file to export the config file locally:

```js
module.exports = require("@durkdotdev/configs/eslint/base.json");

// TypeScript
module.exports = require("@durkdotdev/configs/eslint/typescript.json");
```

3. Create a `.eslintrc.js` file with the config file:

```js
module.exports = {
  extends: "./.d-eslint"
  // ...
};
```

For more on configuring ESLint, see the [ESLint Documentation](https://eslint.org/docs/latest/user-guide/configuring/).

### Prettier

1. Install configuration file and Prettier:

```bash
npm install @durkdotdev/configs prettier -D
```

2. Create a `.prettierrc.js` file to extend the config file:

```js
module.exports = {
  ...require("./packages/configs/prettier.json")
};
```

For more on configuring Prettier, see the [Prettier Documentation](https://prettier.io/docs/en/configuration.html).

#### Usage with ESLint

If using both ESLint and Prettier, it may be helpful to configure ESLint to work with Prettier.

1. Install the [`eslint-config-prettier`](https://github.com/prettier/eslint-config-prettier) package:

```bash
npm install eslint-config-prettier -D
```

2. Extend `.eslintrc.js` with Prettier:

```js
module.exports = {
  extends: ["./.d-eslint", "prettier"]
  // ...
};
```

### TypeScript

There are three different `tsconfigs` in this package:

- `base.json`
- `nextjs.json`
- `react-library.json`

1. Install configuration file and TypeScript:

```bash
npm install @durkdotdev/configs typescript -D
```

2. Create a `tsconfig.json` to extend a config file:

```json
{
  "extends": "@durkdotdev/configs/tsconfig/base.json"
}
```

For more on `tsconfig.json`, see the [TypeScript Documentation](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).
