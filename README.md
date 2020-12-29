# element-theme
[![Build Status](https://travis-ci.org/ElementUI/element-theme.svg?branch=master)](https://travis-ci.org/ElementUI/element-theme)
[![npm](https://img.shields.io/npm/v/element-theme.svg)](https://www.npmjs.com/package/element-theme)

> Theme generator cli tool for Element.

![](./media/element.gif)

> The current version is compatible with element-ui@2.x. For element-ui@1.x, please check out the legacy branch.

## Installation
install local or global
```shell
npm i element-theme -D
```

install `theme-chalk`
```shell
npm i element-theme-chalk -D
# or from github
npm i https://github.com/ElementUI/theme-chalk -D
```

## CLI
```shell
# init variables file
et --init [file path]

# watch then build
et --watch [--config variable file path] [--out theme path]

# build
et [--config variable file path] [--out theme path] [--minimize]
```

## Node API
```javascript
var et = require('element-theme')

// watch mode
et.watch({
  config: 'variables/path',
  out: 'output/path',
  vue3: true,
})

// build
et.run({
  config: 'variables/path',
  out: 'output/path',
  minimize: true,
  vue3: true,
})
```

## Options
### config
Variable file path, default `./element-variables.css`.

### out
Theme output path, default `./theme`.

### minimize
Compressed file.

### vue3
Build theme for vue3, set it to `true` to append `el-` prefix to style files. If your Vue3 project failed to compile showing `Module not found: Error: Can't resolve ... theme/el-XXX.css`, this is the solution. By default, it builds for vue2.

### browsers
set browsers, default `['ie > 9', 'last 2 versions']`.

### watch
watch variable file changes then build.

### components
A lists of components that you want to generate themes for.  All by default.

## Config
You can configure some options in `element-theme` by putting it in package.json:
```json
{
  "element-theme": {
    "browsers": ["ie > 9", "last 2 versions"],
    "out": "./theme",
    "config": "./element-variables.css",
    "theme": "element-theme-chalk",
    "minimize": false,
    "vue3": true,
    "components": ["button", "input"]
  }
}
```

## License
MIT
