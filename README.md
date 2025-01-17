# Vue js component generator [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

CLI util for easy generate Vue js component

## Installation

```js
npm install -g vue-generate-component
```

## Usage

```bash
vgc --help
```

### Create new component

```bash
vgc footer
```

Will generate five files:

**footer.ts**

```typescript
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {},
})
export default class Footer extends Vue {}
```

**footer.spec.ts**

```typescript
import Vue from "vue";
import Footer from "./footer.vue";

describe("Footer.vue", () => {});
```

**footer.scoped.scss**

```css
.footer {
}
```

**footer.vue**

```html
<template>
  <section class="footer">
    <h1>footer Component</h1>
  </section>
</template>
<script src="./footer.ts" lang="ts"></script>
<style src="./footer.scoped.scss" scoped lang="scss"></style>
```

**footer.vue.d.ts**

```typescript
import Footer from "./footer";

export default Footer;
```

### Create new component single file

```bash
vgc -s home
```

will generate one vue file:

```javascript
<template lang="html">
  <section class="home">
    <h1>home Component</h1>
  </section>
</template>

<script lang="js">
  export default  {
    name: 'home',
    props: [],
    mounted() {

    },
    data() {
      return {

      }
    },
    methods: {

    },
    computed: {

    }
}
</script>

<style scoped lang="scss">
  .home {

  }
</style>
```

### Create new component single file inside new folder

```bash
vgc -s home --folder
```

### Create new directive

```bash
vgc -d my-directive
```

will generate:

**my-directive.directive.js**

```javascript
import Vue from "vue";

Vue.directive("my-directive", {
  bind() {},
  // When the bound element is inserted into the DOM...
  inserted(el) {
    // el.focus();
  },
  update() {},
  unbind() {},
});
```

### If you want use postfix in file name, use -- postfix

```bash
vgc footer --postfix page
```

Will generate files with postfix:

- footer.page.ts
- footer.page.scss
- footer.page.vue
- footer.page.vue.d.ts
- footer.page.spec.ts

### Change the default file types for html, style, script, and spec

```bash
sudo vgc --html jade --style less --script js --spec js
```

### Contribute

If you want to fix/improve the templates you're welcome to create a PR.
