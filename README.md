# vue2-ace

A Vue2 component for including the [ace editor](https://ace.c9.io/).

### Installation

```
npm install -save vue2-ace
```

### How to use

Import the component, the mode and the theme in `<script>`.

```
import editor from 'vue2-ace'
import 'brace/mode/javascript'
import 'brace/theme/chrome'
```

Register the component in the Vue options.

```
components: {
  editor
}
```

Use the component in your `template`. Make sure to change `variable` to a string
the editor should start with (it can be an empty string too).

```
<editor :content="variable"></editor>
```


The content-prop is required, the other props have the following defaults:

```
lang: javascript
theme: chrome
height: 300px
width: 100%
```

If you want to change any of these defaults, just include them when you use the
component in the template.

```
<editor :content="variable" :height="'500px'"></editor>

<editor :content="variable" :width="'50%'"></editor>

<editor :content="variable" :lang="'html'"></editor>

<editor :content="variable" :theme="'github'"></editor>
```

If you want to use another lang or theme, don't forget to import it.

Last but not least listen on the `editor-update`. Make sure to replace
`vm.function` with the function you want to execute.

```
mounted () {
  const vm = this;
  vm.$on('editor-update', vm.function);
}
```