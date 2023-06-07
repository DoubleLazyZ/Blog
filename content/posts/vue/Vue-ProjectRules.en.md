---
title: 'Vue-專案的規範'
date: 2022-07-24
tags: ['Vue']
categories: ['Vue']
---

# Vue-專案的規範

建立 Vue Project 的一些規範

<!--more-->

### prettier

```
pnpm install prettier
```

.prettierrc

```json
{
  "useTabs": false,
  "tabWidth": 2,
  "printWidth": 80,
  "singleQuote": false,
  "trailingComma": "none",
  "semi": true
}
```

.prttierignore

```
/dist/*
.local
.output.js
/node_modules/**

**/*.svg
**/*.sh

/public/*

```

### eslint

```
pnpm install eslint-plugin-prettier eslint-config-prettier -D
```

.eslintrc.js

```js
module.exports = {
  root: true,
  env: {
    node: true,
  },
  extends: ['plugin:vue/vue3-essential', 'eslint:recommended', '@vue/typescript/recommended', 'plugin:prettier/recommended'],
  parserOptions: {
    ecmaVersion: 2020,
  },
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
  },
}
```

### husky

```javascript
pnpm dlx husky-init && pnpm install
auto-install-peers=true
```

### commitizen、commitlint

1.1 下載 pnpm

```
pnpm add -D commitizen cz-conventional-changelog
```

1.2 在 root 建立.czrc 對 commitizen 進行設定

```
{
  "path": "cz-conventional-changelog"
}

```

1.3 下載 commitlint

```bash
pnpm install --save-dev @commitlint/config-conventional @commitlint/cli
```

1.4 進行 commitlint 設定
commitlint.config.js

```
module.exports = {
  extends: ['@commitlint/config-conventional']
}
```

1.5 增加 husky 檢查使用者提交是否符合 commitlint 使用 commitizen

```bash=
npx husky add .husky/commit-msg "npx --no-install commitlint --edit $1"
```

### Vue-router

```bash=
pnpm add vue-router@next
```

### Vuex

```bash=
pnpm add vuex@next
```
