# O que é linguagem funcional:
A linguagem funcional é um paradigma de programação que se baseia no conceito de funções matemáticas puras como a unidade fundamental de computação. Ao contrário de linguagens de programação imperativas, que se concentram em alterar o estado dos dados, a programação funcional enfatiza a avaliação de expressões e a manipulação de funções.

As linguagens funcionais tratam as funções como cidadãos de primeira classe, o que significa que as funções podem ser atribuídas a variáveis, passadas como argumentos para outras funções e retornadas como resultados de outras funções. Elas também possuem características como imutabilidade de dados, onde os valores não podem ser modificados após serem criados, e recursão como um mecanismo principal de repetição.

A programação funcional oferece diversos benefícios, incluindo:
- Clareza e legibilidade: As funções matemáticas puras são declarativas, o que significa que você pode descrever o que quer fazer, em vez de se preocupar com o fluxo de controle e a manipulação direta dos dados. Isso resulta em um código mais conciso e legível.
- Composição de funções: Como as funções são tratadas como valores, é possível combiná-las e encadear operações de maneira elegante e modular. Isso facilita a reutilização de código e a construção de programas complexos a partir de partes menores.
- Imutabilidade de dados: Ao evitar a modificação direta dos dados, a programação funcional reduz os efeitos colaterais indesejados e torna o código mais previsível e fácil de testar.
- Tolerância a falhas: A imutabilidade dos dados e a ênfase nas funções puras facilitam a detecção e o isolamento de erros, tornando a depuração mais simples e aumentando a robustez do software.
- Paralelismo e concorrência: A natureza declarativa e a imutabilidade de dados tornam a programação funcional mais adequada para aproveitar o paralelismo e a concorrência em sistemas modernos, onde múltiplos processadores e threads são comuns.

Algumas linguagens de programação funcionais populares incluem Haskell, Elixir, Lisp, Clojure, Erlang e F#. No entanto, muitas linguagens de programação modernas, mesmo aquelas que não são puramente funcionais, incorporam conceitos e recursos funcionais em sua sintaxe e bibliotecas para aproveitar os benefícios da programação funcional.

## Linguagem funcional VS linguagem orientada a objetos:
A escolha entre uma linguagem funcional e uma linguagem orientada a objetos depende das necessidades e características específicas do projeto. No entanto, há casos em que o uso de uma linguagem funcional pode ser vantajoso em relação a linguagens orientadas a objetos. Aqui estão alguns casos em que vale a pena considerar o uso de uma linguagem funcional:

- Processamento paralelo e concorrência: Linguagens funcionais, devido à imutabilidade dos dados e ao foco na avaliação de expressões, facilitam a criação de programas paralelos e concorrentes. A falta de efeitos colaterais e a ênfase em funções puras permitem que o código funcional seja executado de forma independente e distribuída em vários núcleos de processamento ou em sistemas distribuídos.
- Manipulação de grandes volumes de dados: Linguagens funcionais são adequadas para processar e transformar grandes volumes de dados, especialmente quando a ênfase é dada às transformações dos dados, em vez de ao estado mutável. Com funções puras e imutabilidade de dados, é possível criar pipelines de processamento de dados eficientes e fáceis de manter.
- Código conciso e expressivo: A programação funcional tende a ser mais concisa e expressiva, permitindo que você escreva menos código para realizar uma tarefa. Isso pode resultar em um código mais legível e mais fácil de entender e manter.
- Testabilidade e depuração: Linguagens funcionais tendem a ser mais fáceis de testar, pois as funções puras produzem resultados previsíveis e não têm dependências complexas. Além disso, a imutabilidade de dados facilita a depuração, pois você pode confiar que os valores não são modificados em locais inesperados.
- Programação matemática e científica: A programação funcional é especialmente adequada para problemas relacionados a cálculos matemáticos e científicos, devido à sua proximidade com a notação matemática e sua capacidade de lidar com transformações e composição de funções.
