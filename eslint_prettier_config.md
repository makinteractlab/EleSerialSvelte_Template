# To configure ESLINT and PRETTIER

## ESSLINT

1. npm i -D eslint eslint-plugin-svelte3

2. npx eslint --init
   -> choose airbnd for default style

3. Change

```
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: ['airbnb-base'],
  parserOptions: {
    ecmaVersion: 2019,
    sourceType: 'module',
  },
  plugins: ['svelte3'],
  overrides: [
    {
      files: ['*.svelte'],
      processor: 'svelte3/svelte3',
    },
  ],
  rules: {
    'comma-dangle': 0,
    'no-console': 0,
    'import/prefer-default-export': 0,
    'import/no-mutable-exports': 0,
  },
};
```

4. create .eslintignore

```
rollup.config.js
```

## PRETTIER

1. npm i -D prettier prettier-plugin-svelte

2. .prettierrc

```
{
  "tabWidth": 2,
  "trailingComma": "all",
  "semi": true,
  "singleQuote": true
}
```

3. Task file (open workspace settings)

```
{
  "files.associations": {
    "*.svelte": "html"
  },
  "eslint.validate": ["javascript", "javascriptreact", "html"],
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

4. Optionally add to package.json

```
  "scripts": {
    "fix": "npx eslint --fix \"{,!(node_modules|public)/**/}*.{js,svelte}\"",
    "format": "npx prettier --write \"{,!(node_modules|public)/**/}*.{js,svelte}\""
  }
```

with this you can run `npm run format`
