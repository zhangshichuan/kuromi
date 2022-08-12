# kuromi

> 基于 Vue3 + Typescript + NaiveUI 的基础项目配置模板

## 配置步骤

- 具体配置参考项目里面的各类文件

### Vue

```shell
 $ pnpm create vue@latest
```

### EditorConfig

```shell
 $ touch .editorconfig
```

### Prettier

```shell
 $ pnpm add prettier -D

 $ touch .prettierrc
```

### ESLint

```shell
 $ pnpm add eslint -D

 $ npx eslint --init
```

### ESLint 和 Prettier 的冲突

```shell
 $ pnpm add eslint-config-prettier -D
```

### .eslintignore 和 .prettierignore

```shell
 $ touch .eslintignore .prettierignore
```

### StyleLint

```shell
 $ pnpm add stylelint stylelint-config-standard -D

 $ touch .stylelintrc.js

 $ pnpm add stylelint-order stylelint-config-rational-order stylelint-declaration-block-no-ignored-properties -D

```

### Stylelint 和 Prettier 的冲突

```shell
 $ pnpm add stylelint-config-prettier -D
```

### Lint

```shell
 $ pnpm add lint-staged -D
```

### Husky

```shell
 $ pnpm add husky -D
```

### Commitlint

```shell
 $ pnpm add @commitlint/cli @commitlint/config-conventional -D

 $ touch .commitlintrc.js
```

### Changelog

```shell
 $ pnpm add conventional-changelog-cli -D
```

### NaiveUI

```shell
 $ pnpm add naive-ui -D

 $ pnpm add vfonts -D
```

### Others

```shell
 $ pnpm add axios lodash dayjs blueimp-md5 normalize.css
```
