# Vue.Js
## Como usar:
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
