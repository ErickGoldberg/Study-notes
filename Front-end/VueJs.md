# Vue.Js
## Como usar:
### CDN:
Etapa 1: Preparação do arquivo HTML
Crie um novo arquivo HTML em seu editor de texto preferido. Por exemplo, você pode nomeá-lo como index.html. Dentro desse arquivo HTML, você precisará incluir as referências para o Vue.js e seus scripts relacionados.
~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Meu Projeto Vue.js</title>
  <!-- Inclua o Vue.js -->
  <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <!-- Conteúdo do seu aplicativo Vue.js -->
  </div>

  <!-- Inclua seus scripts personalizados do Vue.js -->
  <script src="seu-script.js"></script>
</body>
</html>
~~~
Etapa 2: Desenvolvimento do código Vue.js
Crie um novo arquivo JavaScript em seu editor de texto e salve-o com o nome "seu-script.js" (ou o nome que você especificou na etapa anterior). Dentro deste arquivo, você pode escrever seu código Vue.js.
~~~
new Vue({
  el: '#app',
  data: {
    message: 'Olá, Vue.js!'
  }
});
~~~

#### Usando a compilação global:
~~~
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
~~~
O link acima carrega a compilação global do Vue, onde todas as APIs de nível superior são expostas como propriedades no Vueobjeto global. Aqui está um exemplo completo usando a compilação global:
~~~
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<div id="app">{{ message }}</div>

<script>
  const { createApp, ref } = Vue

  createApp({
    setup() {
      const message = ref('Hello vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
~~~

Documentação oficial: https://vuejs.org/guide/quick-start.html#using-vue-from-cdn

### NPM:
Passo 1: Instalação do Vue CLI
O Vue CLI (Interface de Linha de Comando) é uma ferramenta oficial para criar, configurar e gerenciar projetos Vue.js. Para instalá-lo, abra o terminal e execute o seguinte comando:
~~~
npm install -g @vue/cli
~~~
Obs: Este comando só precisa ser usado na primeira vez(instala globalmente e todos os diretórios podem ver)

Passo 2: Criação de um novo projeto
Depois de instalar o Vue CLI, você pode criar um novo projeto Vue.js. Navegue para o diretório onde deseja criar o projeto e execute o seguinte comando:
~~~
vue create nome-do-projeto
~~~

Passo 3: Instalação das dependências
Após a criação do projeto, navegue para o diretório do projeto usando o comando:
~~~
cd nome-do-projeto

npm install
~~~

Passo 4: Execução do servidor de desenvolvimento
Agora que o projeto está configurado, você pode iniciar o servidor de desenvolvimento para visualizar sua aplicação. Use o seguinte comando:
~~~
npm run serve
~~~

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



### Links úteis:
- https://vuejs.org/
- https://www.vuemastery.com/courses/intro-to-vue-3/intro-to-vue3/
- https://cursos.alura.com.br/formacao-vuejs3
