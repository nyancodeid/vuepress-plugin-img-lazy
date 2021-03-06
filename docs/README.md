## Introduction

> a vuepress plugin to better supporting image lazy loading

**The plugin will preferentially use native image [lazy-loading](https://caniuse.com/#feat=loading-lazy-attr), if the browser does not support it, it will be implemented through lozad**

base on [markdown-it-img-lazy](https://github.com/tolking/markdown-it-img-lazy) and [markdown-it-imsize](https://github.com/tatsy/markdown-it-imsize) and [lozad](https://github.com/ApoorvSaxena/lozad.js)

---

## Installation

``` sh
yarn add vuepress-plugin-img-lazy
# or
npm i vuepress-plugin-img-lazy
```

## Usage

``` js
module.exports = {
  plugins: [
    'img-lazy'
  ]
}
```

``` md
![img](img.jpg)
<!-- or -->
![img](img.jpg =500x300) <!-- better -->
<!-- or -->
<img data-src="img.jpg" loading="lazy" class="lazy">
```

## Use in theme <Badge text="^1.0.1"/>

- registered as global components

``` js
// enhanceAppFile.js
import ImgLazy from 'vuepress-plugin-img-lazy/ImgLazy'

export default ({ Vue }) => {
  Vue.component(ImgLazy.name, ImgLazy)
}
```

- or registered as components

``` js
import ImgLazy from 'vuepress-plugin-img-lazy/ImgLazy'

export default {
  components: { ImgLazy }
}
```

- use

``` vue
<template>
  <img-lazy src="img.jpg" />
</template>
```

## Options

### useLoading
- Type: `Boolben`
- Default: `true`

Use the native image lazy-loading for the web

### selector
- Type: `string`
- Default: `lazy`

Default class name for image
