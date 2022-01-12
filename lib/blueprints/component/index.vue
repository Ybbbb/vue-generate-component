<template>
  <section class="{{name | kebabCase}}">
    <h1>{{ name | kebabCase }} Component</h1>
  </section>
</template>
<script src="./{{name}}.{{ filesType.script }}"{% if filesType.script !="js" %} lang="{{ filesType.script }}"{% endif %}></script>
<style src="./{{name}}.scoped.{{ filesType.style }}" scoped lang="{{ filesType.style }}"></style>
