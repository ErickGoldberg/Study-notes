# TypeScript:
## Qual é a diferença entre JavaScript e TypeScript?
São duas linguagens de programação diferentes, porém uma é o superconjunto de outra. TypeScript é esse superconjunto, possibilitando que você use absolutamente tudo do JavaScript de forma válida. isto é, todo seu código JavaScript é válido em TypeScript (mas não o contrário). A principal diferença vai ser em relação a tipagem de dados, ao uso de classes, aos mecanismos de abstração, que são bem mais fortes.


## Vantagens:
- Feedback mais rápido de erros;
- Processo de refatoração mais fácil;
- Autocomplete da linguagem, muito boa no vscode;
- Poder adotar gradualmente typescript em uma base de código;

## Principais funcionalidades:
- É possível usar o modificador de acesso private para restringir o acesso a membros de uma classe. Quando um membro é declarado como private, ele só pode ser acessado dentro da própria classe em que foi declarado.
- Podem ter o tipo do dado para ter uma certa "validação", como: number, string, date... Ex:
~~~
let nome: string = "João";
let idade: number = 25;
let numeros: Array<number>;
let numeros: Array<number> = [1, 2, 3, 4, 5];
~~~
- Pode ser configurado para o tipo do dado não aceitar "any" (obrigatório dizer o tipo do dado). Ex: 
~~~
{
  "compilerOptions": {
    "noImplicitAny": true
  }
}
~~~
- É possível declarar um array que não disponibiliza a remoção ou inclusão de novos items. Ex:
~~~
const nomes: ReadonlyArray<string> = ['a', 'b', 'c'];
~~~

### Union Types:
Union Types(Tipos de União) permitem que você defina uma variável, parâmetro de função ou retorno de função que pode ter mais de um tipo possível. Isso permite que você trabalhe com valores que podem ter diferentes tipos, aumentando a flexibilidade e expressividade do sistema de tipos.

Para criar um tipo de união, você utiliza o operador de pipe (|) para separar os tipos que a variável pode assumir. Por exemplo:
~~~
let age: number | string;
age = 25; // válido, age é do tipo number
age = "vinte e cinco"; // válido, age é do tipo string
~~~
No exemplo acima, a variável age pode ter um valor do tipo number ou do tipo string. Isso significa que você pode atribuir tanto um valor numérico quanto um valor de texto a essa variável.

Os tipos de união são uma ferramenta poderosa para modelar situações em que um valor pode ter diferentes tipos possíveis. Eles permitem que você escreva código mais flexível e expressivo, enquanto ainda se beneficia do sistema de tipos do TypeScript para evitar erros comuns.

### Strict Null Checks:
Strict Null Checks(Verificações Estritas de Nulos) é uma configuração no TypeScript que ajuda a evitar erros relacionados a valores nulos ou indefinidos (null e undefined). Quando habilitado, o compilador do TypeScript impõe regras mais rigorosas para lidar com valores potencialmente nulos ou indefinidos.

Por padrão, o TypeScript permite que você atribua null ou undefined a qualquer variável, mesmo que ela tenha um tipo específico. Isso pode levar a erros difíceis de depurar, pois o TypeScript não faz verificações estritas sobre esses valores.

No entanto, com as "Strict Null Checks" habilitadas, o TypeScript força você a ser mais explícito ao lidar com valores nulos ou indefinidos, evitando que esses valores sejam atribuídos acidentalmente a variáveis que não foram explicitamente marcadas como opcionais.

A habilitação das "Strict Null Checks" traz os seguintes benefícios:
- Identificação de valores nulos e indefinidos: Com as verificações estritas, o TypeScript consegue detectar quando você está tentando atribuir ou usar um valor potencialmente nulo ou indefinido sem tratá-lo adequadamente.
- Maior segurança durante a execução: Ao lidar com valores nulos ou indefinidos de forma explícita, você evita erros relacionados a acessos inválidos ou propriedades indefinidas durante a execução do código.
- Melhor qualidade do código: As "Strict Null Checks" incentivam boas práticas de programação, como a verificação de nulos e indefinidos antes de usá-los e o uso de tipos opcionais de forma adequada.

Para habilitar as "Strict Null Checks" em um projeto TypeScript, você precisa configurar a opção strictNullChecks para true no arquivo tsconfig.json do seu projeto:
~~~
{
  "compilerOptions": {
    "strictNullChecks": true
  }
}
~~~
Ao ativar essa opção, o compilador do TypeScript realizará verificações mais rigorosas e emitirá erros e avisos sempre que houver um risco de valores nulos ou indefinidos não tratados. Isso ajuda a melhorar a segurança e a robustez do seu código TypeScript.

### Decorators:
Decorators são uma funcionalidade que permite adicionar metadados e comportamentos extras a classes, métodos, propriedades e parâmetros de função. Eles são anexados usando a sintaxe @nomeDoDecorator imediatamente antes do elemento ao qual estão sendo aplicados.

Os Decorators são amplamente utilizados em frameworks e bibliotecas populares, como Angular, NestJS e TypeORM, para adicionar funcionalidades extras aos componentes, rotas, serviços e entidades. Eles desempenham um papel fundamental na programação orientada a aspectos (AOP) ao permitir a separação de preocupações (conhecida como "aspectos") do código principal.

Os Decorators podem ser usados para uma variedade de finalidades, incluindo:
- Modificar comportamentos: Você pode usar decorators para adicionar comportamentos extras a classes, métodos ou propriedades. Por exemplo, um decorator pode adicionar validações, cache, autenticação, tratamento de erros, entre outros.
- Anotações e metadados: Decorators permitem adicionar metadados aos elementos decorados. Esses metadados podem ser usados ​​em tempo de execução ou durante o processo de construção, fornecendo informações adicionais sobre a estrutura do código.
- Extensão de funcionalidade: Os decorators podem estender a funcionalidade de bibliotecas e frameworks, permitindo que você crie suas próprias extensões personalizadas para atender às suas necessidades específicas.
- Logging e monitoramento: Decorators podem ser usados para registrar informações de log, monitorar o desempenho e rastrear o comportamento do código em tempo de execução.

É importante mencionar que o uso de decorators requer suporte da versão do ECMAScript (ES) que está sendo usada. No TypeScript, é possível habilitar o suporte a decorators adicionando a opção "experimentalDecorators": true ao arquivo tsconfig.json do seu projeto.
