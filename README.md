# Js Editor


> Simple js editor with syntax highlighting and line numbers.

## Features

- Code Editing ^^
- Syntax highlighting
- Undo / Redo
- Copy / Paste
- The spaces/tabs of the previous line is preserved when a new line is added
- Works on mobile (thanks to contenteditable)
- Resize to parent width and height <sup>new</sup>
- Support for line numbers <sup>new</sup>
- Support for autosizing the editor <sup>new</sup>
- Autostyling the linenumbers(optional) <sup>new</sup>

## Use Case

The goal of this project is to have a simple code editor. You can use to make small changes of some content or you just need a textarea with syntax highlighting. That's what it's good for. If you need an advanced code editor use Codemirror or Monaco Editor.

## Install

```sh
npm install vue-js-editor
```

or

```sh
yarn add vue-js-editor
```

## Usage

Register the component locally and use it (recommended)

```html
<template>
  <vue-js-editor :code="code" language="js"></vue-js-editor>
</template>

<script>
import VueJsEditor from 'vue-js-editor'
export default {
  components: {
    JsEditor
  }
}
</script>
```

## Prismjs

This package won't install Prismjs. If you use Prismjs already skip this step. If not you need to load Prismjs somewhere in your app:

```js
// yarn add prismjs
import "prismjs";
import "prismjs/themes/prism.css";
```

OR:

```html
<link rel="stylesheet" href="https://unpkg.com/prismjs/themes/prism.css" />
<script src="https://unpkg.com/prismjs"></script>
```

## Props

| Name                 | Type      | Default | Options                              | Description                                           |
| -------------------- | --------- | ------- | ------------------------------------ | ----------------------------------------------------- |
| v-model              | `string`  | -       | -                                    | for the `code` prop below                             |
| code                 | `string`  | `""`    | -                                    | the code                                              |
| language             | `String`  | `"js"`  | `vue,html,md,ts` + Js Languages | language of the code                                  |
| lineNumbers          | `Boolean` | `false` | -                                    | Whether to show line numbers or not                   |
| readonly             | `Boolean` | `false` | -                                    | Indicates if the editor is read only or not.          |
| emitEvents           | `Boolean` | `false` | -                                    | Indicates if the editor should emit events.           |
| autoStyleLineNumbers | `Boolean` | `true`  | -                                    | Allow the line number to be styled by this component. |

## Events

| Name   | Parameters | Description                     |
| ------ | ---------- | ------------------------------- |
| change | `(code)`   | Fires when the code is changed. |

The events below won't be fired unless you set the `emitEvents` prop to `true`.

| Name         | Parameters | Description                                                                 |
| ------------ | ---------- | --------------------------------------------------------------------------- |
| keydown      | `(event)`  | This event is emitted when a keydown event happens in editor                |
| keyup        | `(event)`  | This event is emitted when a keyup event happens in editor                  |
| editor-click | `(event)`  | This event is emitted  when clicking anywhere in the contenteditable editor |

## Thanks

inspired by [react-live](https://github.com/FormidableLabs/react-live).

## License

MIT
