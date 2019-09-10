<h1 align="center">vuepress-plugin-code-gen-box</h1>

> code-gen-box plugin for vuepress.

With this plugin, you can both display demo and code via following syntax.

```md
::: demo
<div @click="onClick">Click me!</div>

<script>
export default {
  methods: {
    onClick: () => { window.alert(1) },
  },
}
</script>
:::
```

## Features
* Only one source code
* Foldable code
* Support online editing
  * ✔ Codepen
  * ✔ JSFiddle
  * ✔ CodeSandbox

## Install

* First of all, install [vuepress v1.x](https://github.com/vuejs/vuepress)

* Then install the plugin

```bash
$ npm i vuepress-plugin-code-gen-box -D
# OR
$ yarn add vuepress-plugin-code-gen-box -D
```

## Usage
Write vuepress config

```js
module.exports = {
  plugins: ['code-gen-box'],
}
```

## Options
This plugin supports the following configurations.

```js
module.exports = {
    plugins: [
        ['demo-code', {
            jsLibs: [
                // umd
                'https://unpkg.com/tua-storage/dist/TuaStorage.umd.js',
            ],
            cssLibs: [
                'https://unpkg.com/animate.css@3.7.0/animate.min.css',
            ],
            showText: 'show code',
            hideText: 'hide',
            styleStr: 'text-decoration: underline;',
            minHeight: 200,
            onlineBtns: {
                codepen: true,
                jsfiddle: true,
                codesandbox: true,
            },
            codesandbox: {
                deps: { 'lodash': 'latest' },
                json: '',
                query: '',
                embed: '',
            },
            demoCodeMark: 'demo-code',
        }]
    ],
}
```

### jsLibs
* Type: `Array`
* Default: `[]`

Js libraries for the demo.

### cssLibs
* Type: `Array`
* Default: `[]`

Css libraries for the demo.

### showText
* Type: `String`
* Default: `显示代码`

The display text of unfold code button.

### hideText
* Type: `String`
* Default: `隐藏代码`

The display text of fold code button.

### minHeight
* Type: `Number`
* Default: `0`(px)

The height of the code when it is folded.

### onlineBtns
* Type: `Object`
* Default: `{ codepen: true, jsfiddle: true, codesandbox: true }`

Display online edit buttons.

### codesandbox
* Type: `Object`
* Default: `{ deps: {}, json: '', query: 'module=App.vue'', embed: '' },`

It passes [CodeSandbox options](https://codesandbox.io/docs/importing#define-api).

> `deps` is dependencies

### demoCodeMark
* Type: `String`
* Default: `demo`

The mark of the plugin, follows the tag after `:::`.

## Related
* [vuepress-plugin-demo-block](https://github.com/xiguaxigua/vuepress-plugin-demo-block)

## License

[MIT](http://opensource.org/licenses/MIT)
