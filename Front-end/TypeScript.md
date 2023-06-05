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
