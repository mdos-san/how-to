# How to Typescript

## How to create Typescript package

### Create 2 tsconfig for each js module

#### CJS module

```
{
  "extends": "./tsconfig.base.json",
  "compilerOptions": {
    "module": "commonjs",
    "outDir": "./build/cjs"
  }
}
```

#### ESM module

```
{
  "extends": "./tsconfig.base.json",
  "compilerOptions": {
    "module": "es6",
    "outDir": "./build/esm"
  }
}
```

### Add .npmignore

```
*.tgz
.git
.storybook
css
postcss.config.js
src
tsconfig.base.json
tsconfig.cjs.json
tsconfig.esm.json
```

### Add `prepack` in package.json to build the project

### Add `main`, `module` and `types` fileds in package.json

```
{
  ...,
  "main": "build/cjs/index.js",
  "module": "build/esm/index.js",
  "types": "build/types/index.d.ts",
}
```
