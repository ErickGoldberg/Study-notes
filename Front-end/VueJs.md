# Vue.Js
## Estruturação:
- Template: o código HTML;
- Script: a lógica do componente, com código JavaScript/TypeScript;
- Style: o estilo do componente, em que as definições podem ser limitadas ao escopo.

Exemplo de botão:
~~~
<template>
  <button :title="titulo" @click="aoClicar">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "Botao",
  props: {
    titulo: String,
    aoClicar: Function,
  },
};
</script>

<style>
</style>
~~~
