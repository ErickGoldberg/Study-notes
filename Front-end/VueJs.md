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

## Principais funcionalidades:
### Binding de dados bidirecional: 
O Vue.js permite a ligação de dados bidirecional entre a camada de visualização e o modelo de dados subjacente, facilitando a atualização automática da interface do usuário quando os dados são modificados.

### Diretivas: 
As diretivas são recursos especiais do Vue.js que permitem adicionar comportamento reativo aos elementos HTML. Alguns exemplos populares de diretivas são v-bind, v-if, v-for e v-on.

### Sistema de componentes: 
O Vue.js oferece um sistema de componentes robusto, permitindo a criação de componentes personalizados reutilizáveis. Os componentes encapsulam a estrutura HTML, a lógica e o estilo, facilitando a manutenção e organização do código.

### Renderização condicional: 
O Vue.js oferece suporte à renderização condicional, permitindo mostrar ou ocultar elementos com base em condições definidas. Isso é útil para exibir ou ocultar partes da interface do usuário com base no estado do aplicativo.

### Gestão de estado:
O Vue.js fornece uma maneira conveniente de gerenciar o estado do aplicativo usando a biblioteca Vuex. O Vuex oferece uma arquitetura de gerenciamento de estado centralizada e reativa, que ajuda a lidar com a complexidade de aplicativos grandes.

### Animações e transições: 
O Vue.js facilita a adição de animações e transições elegantes aos elementos da interface do usuário. Ele fornece classes e ganchos especiais para criar efeitos de transição suaves ao adicionar, remover ou atualizar elementos.

### Roteamento: 
O Vue.js tem um roteador oficial chamado Vue Router, que permite criar aplicativos de página única (SPA) com navegação por rotas. O Vue Router simplifica a criação de rotas e a navegação entre diferentes páginas ou componentes em seu aplicativo.

### Ferramentas de desenvolvimento:
O ecossistema Vue.js inclui várias ferramentas úteis para facilitar o desenvolvimento, como a extensão Vue DevTools para navegador, que oferece recursos avançados de depuração e inspeção de componentes.

## Sintaxe:
### Diretivas: 
- v-if: A diretiva v-if é usada para renderização condicional de elementos. Ela permite que você mostre ou oculte elementos com base em uma expressão condicional. Por exemplo:
~~~
<div v-if="showMessage">
  {{ message }}
</div>
~~~
- v-for: A diretiva v-for é usada para renderização de listas ou iteração de arrays. Ela permite que você itere sobre uma coleção e crie elementos repetidos com base nos itens dessa coleção. Por exemplo:
~~~
<ul>
  <li v-for="item in items" :key="item.id">
    {{ item.name }}
  </li>
</ul>
~~~
- v-on: A diretiva v-on (ou @) é usada para lidar com eventos e associar manipuladores de eventos a elementos. Ela permite que você reaja a eventos do DOM e execute métodos ou expressões quando esses eventos ocorrem. Por exemplo:
~~~
<button v-on:click="handleClick">Clique aqui</button>
~~~
~~~
<button @click="counter++">Clique aqui</button>
~~~
- v-bind: A diretiva v-bind é usada para ligação de atributos HTML a expressões no modelo de dados. Ela permite que você associe dinamicamente valores de atributos com base nos dados do componente. Por exemplo:
~~~
<img v-bind:src="imageUrl">
~~~
- v-model: Essa diretiva é usada para criar uma ligação bidirecional entre um elemento de formulário e uma propriedade no modelo de dados. Ela permite que você vincule o valor do elemento do formulário a uma variável do Vue.js e sincronize automaticamente as alterações de ambos os lados.
- v-text: Essa diretiva é usada para definir o conteúdo de um elemento como o valor de uma expressão no modelo de dados. É semelhante a usar {{ }}, mas evita interpolação e, em vez disso, define o conteúdo diretamente.
- v-html: Essa diretiva é usada para renderizar conteúdo HTML dinâmico no elemento. É útil quando você deseja exibir HTML gerado dinamicamente, mas tenha cuidado ao usá-lo para evitar vulnerabilidades de segurança.

### Methods:
No Vue.js, a seção methods é usada para definir métodos no objeto Vue. Esses métodos são chamados a partir de eventos, diretivas ou outros métodos dentro do componente Vue. A seção methods permite que você defina a lógica de manipulação de eventos e outras funcionalidades no componente. Exemplo:
~~~
<div id="app">
  <button v-on:click="incrementCounter">Clique para aumentar</button>
  <p>Contador: {{ counter }}</p>
</div>

<script>
new Vue({
  el: '#app',
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    incrementCounter() {
      this.counter++;
    }
  }
});
</script>
~~~
Neste exemplo, temos um botão que, quando clicado, chama o método incrementCounter definido na seção methods do componente Vue. Esse método incrementa o valor da propriedade counter no objeto de dados usando this.counter++.

Os métodos definidos na seção methods podem receber argumentos e realizar várias tarefas, como manipular dados, fazer chamadas de API, atualizar o estado do componente, interagir com outros componentes, entre outras ações.

Ao definir métodos no objeto Vue, eles se tornam acessíveis dentro do escopo do componente e podem ser referenciados em várias partes do componente, como eventos, diretivas ou mesmo em outros métodos.

Usar a seção methods ajuda a manter seu código organizado e facilita a reutilização de lógica em seu componente Vue. É uma parte essencial do Vue.js para adicionar interatividade e funcionalidade aos componentes.

### Emits:
Em Vue.js, a funcionalidade emits é usada para criar e gerenciar eventos personalizados em um componente. Por meio dos eventos emits, um componente pode notificar outros componentes pai ou escutar eventos personalizados emitidos por outros componentes.

Ao definir a opção emits em um componente, você especifica uma lista de eventos que o componente pode emitir. Isso serve como uma documentação dos eventos que o componente é capaz de emitir e permite que o Vue.js faça a validação dos eventos emitidos, fornecendo erros em tempo de execução quando um evento não especificado é emitido.

Aqui está um exemplo de como usar a opção emits em um componente Vue:
~~~
<template>
  <button @click="incrementCounter">Incrementar</button>
</template>

<script>
  export default {
    emits: ['increment'],
    methods: {
      incrementCounter() {
        this.$emit('increment');
      }
    }
  };
</script>
~~~
Neste exemplo, temos um componente de botão que, quando clicado, emite um evento personalizado chamado "increment". A opção emits é definida com um array contendo o nome do evento personalizado ("increment").

Ao emitir o evento usando this.$emit('increment'), o componente notifica os componentes pais que o evento "increment" ocorreu. Os componentes pais podem então ouvir esse evento usando a sintaxe @increment ou v-on:increment em seu template e executar ações apropriadas em resposta a ele.

Para ouvir eventos personalizados emitidos por um componente, você pode usar a diretiva v-on (ou seu atalho @) no template do componente pai. Aqui está um exemplo de como ouvir o evento "increment" emitido pelo componente de botão:
~~~
<template>
  <div>
    <Button @increment="handleIncrement" />
  </div>
</template>

<script>
  import Button from './Button.vue';

  export default {
    components: {
      Button
    },
    methods: {
      handleIncrement() {
        // Lógica a ser executada quando o evento "increment" for emitido
      }
    }
  };
</script>
~~~
Neste exemplo, o componente pai importa e usa o componente de botão e ouve o evento "increment" usando @increment="handleIncrement". O método handleIncrement será chamado sempre que o evento "increment" for emitido pelo componente de botão.

Os emits fornecem uma maneira clara e controlada de definir e usar eventos personalizados em componentes Vue. Eles facilitam a comunicação entre componentes e permitem a criação de componentes mais reutilizáveis e modularizados.

### Computed:
Em Vue.js, a propriedade computed é usada para definir propriedades calculadas em um componente. As propriedades calculadas são propriedades que são derivadas de outras propriedades no componente, e seu valor é calculado dinamicamente com base nas dependências definidas.

As propriedades calculadas são úteis quando você precisa realizar cálculos complexos, transformações ou filtragens de dados com base em outras propriedades no componente, mas deseja tratá-las como propriedades reativas. Em vez de chamar um método a cada vez que você precisa acessar o valor calculado, você pode usar uma propriedade calculada, que é atualizada automaticamente sempre que suas dependências mudam.

Aqui está um exemplo de como usar a propriedade computed em um componente Vue:
~~~
<template>
  <div>
    <p>Valor: {{ valor }}</p>
    <p>Dobro: {{ dobro }}</p>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        valor: 5
      };
    },
    computed: {
      dobro() {
        return this.valor * 2;
      }
    }
  };
</script>
~~~
da propriedade calculada sempre que a propriedade valor for modificada.

Uma característica importante das propriedades calculadas é que elas são armazenadas em cache e só são recalculadas quando suas dependências mudam. Isso melhora o desempenho, evitando cálculos desnecessários.

As propriedades calculadas podem ser usadas em expressões, interpoladas em templates e até mesmo em outras propriedades calculadas. Isso permite uma composição e reutilização de lógica complexa de forma limpa e declarativa.

Em resumo, a propriedade computed é usada para definir propriedades calculadas em um componente Vue, permitindo a criação de lógica de cálculo dinâmica baseada em outras propriedades reativas.

### Slots:
Em Vue.js, os slots são uma funcionalidade poderosa que permitem a criação de componentes reutilizáveis e flexíveis, permitindo que você injete conteúdo personalizado dentro desses componentes. Os slots permitem que você defina áreas de conteúdo em um componente que podem ser preenchidas com conteúdo específico quando o componente é usado.

Existem dois tipos principais de slots em Vue.js: slots nomeados (named slots) e slots padrão (default slots).
- Slots nomeados: 
Os slots nomeados permitem que você defina áreas de conteúdo específicas em um componente, que podem ser preenchidas com conteúdo personalizado ao usar o componente. Para criar um slot nomeado, você usa a sintaxe <slot> com um atributo name especificando o nome do slot. Aqui está um exemplo:
```
<!-- Componente "Card" com um slot nomeado "header" -->
<template>
  <div class="card">
    <div class="card-header">
      <slot name="header"></slot>
    </div>
    <div class="card-body">
      <slot></slot> <!-- Slot padrão -->
    </div>
  </div>
</template>
```
- Slots padrão: 
Os slots padrão são usados para definir o conteúdo padrão que será inserido em um componente caso nenhum conteúdo específico seja fornecido. Eles são definidos usando a sintaxe <slot></slot> diretamente no corpo do componente. Aqui está um exemplo:
~~~
  <!-- Componente "Button" com um slot padrão -->
<template>
  <button class="btn">
    <slot>Texto Padrão</slot>
  </button>
</template>
~~~
Os slots permitem que você crie componentes flexíveis e reutilizáveis, pois permitem que o usuário do componente insira conteúdo personalizado onde for necessário. Com slots, você pode personalizar a aparência e o comportamento dos componentes sem a necessidade de modificá-los diretamente, promovendo a reutilização de código e a modularidade em seu aplicativo Vue.js.  

## Roteamento: 
Em Vue.js, o roteamento é usado para criar aplicativos de página única (SPA) com navegação entre diferentes páginas ou componentes. O roteamento permite que você defina diferentes rotas, associando-as a componentes específicos que serão renderizados quando a rota correspondente for acessada.

O Vue Router é a biblioteca oficial de roteamento para Vue.js e fornece um conjunto de recursos para gerenciar o roteamento em um aplicativo Vue.

Para começar a usar o Vue Router, você precisa instalar a biblioteca e configurar suas rotas. Aqui está um exemplo básico de como fazer isso:

Passo 1: Instalar o Vue Router via CDN:
~~~
<!-- index.html -->
<body>
  <div id="app">
    <!-- O conteúdo do aplicativo será renderizado aqui -->
  </div>

  <script src="https://unpkg.com/vue@2.6.14"></script>
  <script src="https://unpkg.com/vue-router@3.5.3"></script>
  <script src="app.js"></script>
</body>
~~~
Passo 2: Criar os componentes para as rotas:
~~~
<!-- components/Home.vue -->
<template>
  <div>
    <h1>Página Inicial</h1>
    <!-- Conteúdo da página inicial -->
  </div>
</template>

<!-- components/About.vue -->
<template>
  <div>
    <h1>Sobre</h1>
    <!-- Conteúdo da página "Sobre" -->
  </div>
</template>
~~~
Passo 3: Configurar as rotas e inicializar o Vue Router:
~~~
// app.js
const Home = { template: '<home></home>' };
const About = { template: '<about></about>' };

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About }
];

const router = new VueRouter({
  routes
});

new Vue({
  el: '#app',
  router
});
~~~
Neste exemplo, criamos dois componentes Vue: Home e About. Esses componentes serão renderizados quando a rota correspondente for acessada.

Em seguida, definimos um array routes que contém as configurações das rotas. Cada objeto de rota possui uma propriedade path que especifica o caminho da rota e uma propriedade component que define o componente a ser renderizado.

Depois, criamos uma instância do Vue Router, passando o array routes para a configuração das rotas.

Finalmente, criamos uma instância do Vue e vinculamos o Vue Router a ela usando a opção router.

Agora você pode adicionar links de navegação em seu aplicativo para acessar as rotas definidas. Por exemplo, para criar links de navegação para a página inicial e a página "Sobre", você pode usar a diretiva router-link fornecida pelo Vue Router:
~~~
<!-- App.vue -->
<template>
  <div>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>

    <router-view></router-view>
  </div>
</template>
~~~

Em Vue.js, o roteamento é usado para criar aplicativos de página única (SPA) com navegação entre diferentes páginas ou componentes. O roteamento permite que você defina diferentes rotas, associando-as a componentes específicos que serão renderizados quando a rota correspondente for acessada.

O Vue Router é a biblioteca oficial de roteamento para Vue.js e fornece um conjunto de recursos para gerenciar o roteamento em um aplicativo Vue.

Para começar a usar o Vue Router, você precisa instalar a biblioteca e configurar suas rotas. Aqui está um exemplo básico de como fazer isso:

Passo 1: Instalar o Vue Router via CDN:

~~~
<!-- index.html -->
<body>
  <div id="app">
    <!-- O conteúdo do aplicativo será renderizado aqui -->
  </div>

  <script src="https://unpkg.com/vue@2.6.14"></script>
  <script src="https://unpkg.com/vue-router@3.5.3"></script>
  <script src="app.js"></script>
</body>
~~~

Passo 2: Criar os componentes para as rotas:

~~~
<!-- components/Home.vue -->
<template>
  <div>
    <h1>Página Inicial</h1>
    <!-- Conteúdo da página inicial -->
  </div>
</template>

<!-- components/About.vue -->
<template>
  <div>
    <h1>Sobre</h1>
    <!-- Conteúdo da página "Sobre" -->
  </div>
</template>
~~~

Passo 3: Configurar as rotas e inicializar o Vue Router:

~~~
// app.js
const Home = { template: '<home></home>' };
const About = { template: '<about></about>' };

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About }
];

const router = new VueRouter({
  routes
});

new Vue({
  el: '#app',
  router
});
~~~
Neste exemplo, criamos dois componentes Vue: Home e About. Esses componentes serão renderizados quando a rota correspondente for acessada.

Em seguida, definimos um array routes que contém as configurações das rotas. Cada objeto de rota possui uma propriedade path que especifica o caminho da rota e uma propriedade component que define o componente a ser renderizado.

Depois, criamos uma instância do Vue Router, passando o array routes para a configuração das rotas.

Finalmente, criamos uma instância do Vue e vinculamos o Vue Router a ela usando a opção router.

Agora você pode adicionar links de navegação em seu aplicativo para acessar as rotas definidas. Por exemplo, para criar links de navegação para a página inicial e a página "Sobre", você pode usar a diretiva router-link fornecida pelo Vue Router:

~~~
<!-- App.vue -->
<template>
  <div>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>

    <router-view></router-view>
  </div>
</template>
~~~
A diretiva router-link cria links de navegação que alteram a URL e renderizam o componente correspondente à rota definida.

O componente <router-view> é usado para renderizar o componente correspondente à rota atualmente acessada.

Dessa forma, você pode navegar entre as diferentes páginas/componentes do seu aplicativo Vue usando os links de navegação fornecidos pelo Vue Router.

Este é um exemplo básico de como configurar rotas usando o Vue Router. O Vue Router oferece muitos recursos adicionais, como rotas aninhadas, passagem de parâmetros, navegação programática, entre outros. Você pode consultar a documentação oficial do Vue Router para obter mais informações sobre esses recursos.

Espero que isso ajude a entender o conceito de roteamento em Vue.js e como implementá-lo em seu aplicativo

### Roteamento via CDN:
Exemplo:
~~~
<!DOCTYPE html>
<html>
<head>
  <!-- Incluir os arquivos do Vue.js e Vue Router via CDN -->
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/vue-router/dist/vue-router.js"></script>
</head>
<body>
  <div id="app">
    <!-- Definir o router-view -->
    <router-view></router-view>
  </div>

  <script>
    // Criar instância do Vue Router e definir rotas
    const router = new VueRouter({
      routes: [
        { path: '/', component: HomeComponent },
        { path: '/about', component: AboutComponent },
        // ...definir outras rotas
      ]
    });

    // Criar instância do Vue e vincular ao elemento #app
    new Vue({
      el: '#app',
      router: router
    });
  </script>
</body>
</html>
~~~

## Vuex:
O Vuex é um padrão de gerenciamento de estado para aplicativos Vue.js. Ele é usado para gerenciar o estado centralizado em uma aplicação Vue de grande escala. O Vuex funciona como uma "store" centralizada para os dados do aplicativo, permitindo que os componentes acessem e modifiquem o estado de forma previsível e consistente.

O principal objetivo do Vuex é resolver o problema da comunicação entre componentes em um aplicativo Vue complexo. À medida que um aplicativo cresce, pode se tornar difícil rastrear e manter o estado compartilhado entre vários componentes. O Vuex fornece uma solução para esse problema, permitindo que você defina um estado global e use getters, mutations e actions para interagir com ele.

Aqui estão os principais conceitos do Vuex:

- State (Estado): O estado é um objeto reativo que contém os dados compartilhados do aplicativo. É a fonte única de verdade para todo o aplicativo.
- Getters: Os getters são métodos computados que fornecem acesso aos dados do estado. Eles permitem que você filtre, calcule ou formate os dados do estado de maneira consistente.
- Mutations: As mutações são responsáveis por modificar o estado do Vuex. Elas são funções síncronas que recebem o estado como parâmetro e podem ser chamadas pelos componentes para atualizar o estado.
- Actions: As actions são semelhantes às mutações, mas são assíncronas. Elas são usadas para realizar operações assíncronas, como chamadas de API, antes de chamar as mutações para atualizar o estado.
- Modules (Módulos): Os módulos permitem que você divida a store do Vuex em módulos menores e independentes. Cada módulo tem seu próprio estado, getters, mutations e actions, facilitando o gerenciamento do estado em aplicativos maiores.

O uso do Vuex é recomendado em aplicativos Vue.js de médio a grande porte, nos quais o gerenciamento de estado se torna complexo. Ele promove um fluxo de dados unidirecional e organizado, tornando o código mais previsível, testável e escalável.

Para usar o Vuex em seu aplicativo Vue.js, você precisa instalar a biblioteca do Vuex, criar uma store, definir o estado e usar getters, mutations e actions conforme necessário.
  
## Links úteis:
- https://vuejs.org/
- https://www.vuemastery.com/courses/intro-to-vue-3/intro-to-vue3/
- https://cursos.alura.com.br/formacao-vuejs3
