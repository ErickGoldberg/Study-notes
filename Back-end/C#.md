# C#
é uma linguagem de programação orientada a objetos e orientada a componentes que é fortemente tipada. O C# permite que os desenvolvedores criem muitos tipos de aplicativos seguros e robustos que são executados no .NET. 

## Estruturação:
### Assembly:
Em C#, um assembly é um arquivo compilado que contém código executável, metadados e recursos relacionados a um programa. Um assembly pode ser uma biblioteca de classes (.dll) ou um executável (.exe). Ele é a unidade fundamental de implantação e reutilização de código em C#.

Um assembly pode ser criado a partir de um único projeto ou de vários projetos dentro de uma solução. Ele contém uma ou mais namespaces e tipos, como classes, estruturas, interfaces e assim por diante. Além disso, um assembly pode fazer referência a outros assemblies para usar seu código e recursos.

Quando você compila um programa em C#, o compilador cria um ou mais assemblies. Esses assemblies podem ser implantados em outras máquinas ou compartilhados com outros desenvolvedores para uso em seus próprios projetos. Um assembly também pode ser versionado, permitindo atualizações e correções futuras.

### Namespace:
Um namespace é uma estrutura de organização lógica que ajuda a evitar conflitos de nomes e permite agrupar tipos relacionados em uma hierarquia. Ele é usado para organizar o código em unidades lógicas e criar um escopo separado para os tipos definidos dentro dele.

Um namespace fornece um prefixo aos tipos definidos dentro dele, evitando colisões de nome com tipos definidos em outros namespaces. Isso é especialmente útil quando você está usando bibliotecas ou frameworks diferentes que podem ter tipos com o mesmo nome.

Exemplo:
~~~
namespace MeuNamespace
{
    // Definição de tipos (classes, estruturas, interfaces, etc.) aqui
}
~~~
Para usar tipos definidos em um namespace em seu código, você pode fazer referência ao namespace usando a diretiva "using". Por exemplo:
~~~
using MeuNamespace.Pasta1;

class MinhaClasse
{
    // Uso de tipos definidos em MeuNamespace.Pasta1
}
~~~
A diretiva "using" permite que você use os tipos do namespace sem ter que especificar o nome completo do namespace toda vez.

- Em resumo, o assembly é um arquivo compilado que contém código executável e recursos relacionados, enquanto o namespace é uma estrutura de organização lógica que ajuda a evitar conflitos de nome e agrupar tipos relacionados.

## Arrays:
### Unidimensional:
~~~
int[] vetor = new int[5]; // Cria um vetor de inteiros com capacidade para 5 elementos

vetor[0] = 10; // Define o valor do primeiro elemento
vetor[1] = 20; // Define o valor do segundo elemento
vetor[2] = 30; // Define o valor do terceiro elemento
vetor[3] = 40; // Define o valor do quarto elemento
vetor[4] = 50; // Define o valor do quinto elemento

Console.WriteLine(vetor[2]); // Saída: 30
~~~

### Bidimensional:
~~~
int[,] matriz = new int[3, 2]; // Cria uma matriz 3x2 (3 linhas e 2 colunas) de inteiros

matriz[0, 0] = 10; // Define o valor da primeira célula (linha 0, coluna 0)
matriz[0, 1] = 20; // Define o valor da segunda célula (linha 0, coluna 1)
matriz[1, 0] = 30; // Define o valor da terceira célula (linha 1, coluna 0)
matriz[1, 1] = 40; // Define o valor da quarta célula (linha 1, coluna 1)
matriz[2, 0] = 50; // Define o valor da quinta célula (linha 2, coluna 0)
matriz[2, 1] = 60; // Define o valor da sexta célula (linha 2, coluna 1)

Console.WriteLine(matriz[1, 1]); // Saída: 40
~~~

## Lambdas:
### Vantagens:
- Concisão: As lambdas permitem escrever código de forma mais concisa, eliminando a necessidade de definir métodos separados para funções simples.
- Legibilidade: As lambdas são mais fáceis de ler e entender, especialmente quando o critério de filtragem ou a lógica do código é curto e direto.
- Flexibilidade: As lambdas podem ser usadas em várias situações, como filtrar, ordenar, mapear ou reduzir coleções de dados. Elas permitem que você especifique a lógica do código diretamente no local onde é necessário, sem a necessidade de criar métodos adicionais.
- Encerramento de escopo: As lambdas têm acesso às variáveis do escopo em que são definidas, o que permite que você capture e utilize valores externos dentro da expressão lambda. Isso pode ser útil em casos onde você precisa fazer referência a variáveis externas dentro de um loop, por exemplo.

Exemplo: 
- Código sem usar lambda:
~~~
public int Somar(int a, int b)
{
    int resultado = a + b;
    return resultado;
}
~~~
- Mesmo código usando lambda:
~~~
public int Somar(int a, int b) => a + b;
~~~

## Dictionary:
Em C#, um dicionário é uma estrutura de dados que armazena pares chave-valor, onde cada chave é única. É uma implementação da interface genérica Dictionary<TKey, TValue> da biblioteca padrão do .NET.

Para usar um dicionário em C#, você precisa importar o namespace System.Collections.Generic. Aqui está um exemplo de como criar e usar um dicionário em C#:

~~~
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Criando um dicionário de strings
        Dictionary<string, int> dicionario = new Dictionary<string, int>();

        // Adicionando itens ao dicionário
        dicionario.Add("Maçã", 10);
        dicionario.Add("Laranja", 5);
        dicionario.Add("Banana", 7);

        // Acessando itens no dicionário
        Console.WriteLine(dicionario["Maçã"]); // Saída: 10

        // Verificando se uma chave existe no dicionário
        bool existeChave = dicionario.ContainsKey("Laranja");
        Console.WriteLine(existeChave); // Saída: True

        // Atualizando um valor no dicionário
        dicionario["Banana"] = 15;

        // Removendo um item do dicionário
        dicionario.Remove("Maçã");

        // Iterando sobre os pares chave-valor no dicionário
        foreach (KeyValuePair<string, int> par in dicionario)
        {
            Console.WriteLine(par.Key + ": " + par.Value);
        }

        // Saída:
        // Laranja: 5
        // Banana: 15
    }
}
~~~

Neste exemplo, criamos um dicionário que mapeia strings para inteiros. Podemos adicionar itens ao dicionário usando o método Add, onde especificamos a chave e o valor correspondente. Podemos acessar valores no dicionário usando a sintaxe de indexação, fornecendo a chave entre colchetes. Podemos verificar se uma chave existe no dicionário usando o método ContainsKey. Para atualizar um valor, simplesmente atribuímos um novo valor à chave correspondente. E para remover um item, usamos o método Remove.

Podemos iterar sobre os pares chave-valor no dicionário usando um loop foreach. A variável par representa cada par chave-valor durante a iteração.

Os dicionários em C# são extremamente úteis quando você precisa armazenar e recuperar dados de forma eficiente usando uma chave única. Eles fornecem um acesso rápido aos valores com base nas chaves, o que os torna uma escolha comum para muitos cenários de programação.

### Struct:
Em C#, a struct é um tipo de dado que permite agrupar diferentes tipos de variáveis relacionadas em uma única unidade. Ela é semelhante a uma classe, mas possui algumas diferenças importantes em seu comportamento e uso.

Uma struct é um tipo de valor, o que significa que, quando você atribui uma struct a outra variável ou passa uma struct como argumento para um método, uma cópia do valor da struct é criada. Isso é diferente das classes, que são tipos de referência, onde a atribuição ou passagem de uma classe para outra variável cria uma referência compartilhada ao mesmo objeto.

~~~
struct Ponto
{
    public int X;
    public int Y;
}
~~~

Neste exemplo, criamos uma struct chamada "Ponto" com duas variáveis de membro públicas: "X" e "Y". Essas variáveis representam as coordenadas x e y de um ponto no plano.

Você pode inicializar uma struct usando o construtor padrão ou especificando valores para suas variáveis de membro:

~~~
Ponto ponto1 = new Ponto(); // inicialização com construtor padrão
ponto1.X = 10;
ponto1.Y = 20;

Ponto ponto2 = new Ponto() { X = 5, Y = 15 }; // inicialização com valores específicos
~~~

As structs também podem ter métodos, propriedades e eventos, assim como as classes. No entanto, é importante observar que, diferentemente das classes, as structs não podem herdar de outras structs ou classes e não podem ser base de herança.

As structs são frequentemente usadas para representar tipos de dados pequenos e imutáveis, como pontos, coordenadas, intervalos, etc. Além disso, as structs são frequentemente utilizadas em cenários onde o desempenho é crucial, pois evitam a alocação de memória no heap.

É importante ter cuidado ao usar structs, especialmente quando são passadas como argumentos de método ou atribuídas a variáveis, para evitar cópias desnecessárias e impacto no desempenho do programa.

Em resumo, as structs em C# são tipos de dados que permitem agrupar diferentes variáveis relacionadas em uma única unidade de valor. Elas são tipos de valor, com comportamento de cópia por valor, e são úteis para representar tipos pequenos e imutáveis, comumente utilizados em cenários de alto desempenho.

### Garbage collector:
O Garbage Collector (Coletor de Lixo) em C# é um componente do tempo de execução do .NET que gerencia a memória de forma automática e ajuda a lidar com a desalocação de objetos que não estão mais em uso.

Quando você cria objetos em um programa C#, a memória é alocada para armazenar esses objetos. No entanto, em algum momento, esses objetos podem se tornar inacessíveis, ou seja, não há mais referências a eles no programa. Quando isso acontece, esses objetos não são mais necessários e ocupam espaço de memória desnecessariamente.

O trabalho do Garbage Collector é identificar esses objetos inacessíveis e liberar a memória ocupada por eles, tornando-a disponível para uso posterior. O Garbage Collector executa periodicamente em segundo plano, rastreando os objetos alocados e determinando quais deles são elegíveis para coleta.

O Garbage Collector utiliza um algoritmo chamado "marcador-e-varredor" (mark-and-sweep) para determinar quais objetos estão em uso e quais não estão. Durante a fase de marcação, o Garbage Collector percorre todas as referências a partir de um conjunto inicial de raízes (como variáveis estáticas, referências em pilha, etc.) e marca todos os objetos que estão acessíveis a partir dessas raízes. Em seguida, durante a fase de varredura, o Garbage Collector percorre toda a memória, desalocando os objetos não marcados e liberando a memória associada a eles.

## Orientação a objetos:
### Classe e método:
Exemplo:
~~~
class EscolaDoRock
{
    string Titulo;
    int AnoLancamento;

    void ExibirInformacoes()
    {
        Console.WriteLine($"Título: {Titulo}");
        Console.WriteLine($"Ano de Lançamento: {AnoLancamento}");
    }
}
~~~
Outro exemplo de método:
~~~
class Musica
{
    public void ExibirFichaTecnica()
    {
        //código...
    }
}
~~~

### Get & Set:
Utilizando o mesmo exemplo anterior:
~~~
using System;

class EscolaDoRock
{
    private string titulo;
    private int anoLancamento;

    public string Titulo
    {
        get { return titulo; }
        set { titulo = value; }
    }

    public int AnoLancamento
    {
        get { return anoLancamento; }
        set { anoLancamento = value; }
    }

    public void ExibirInformacoes()
    {
        Console.WriteLine($"Título: {Titulo}");
        Console.WriteLine($"Ano de Lançamento: {AnoLancamento}");
    }
}
~~~

### Construtor:
Obs: Não precisa declarar set se tiver construtor
~~~
public Carro(string marca, string modelo, int ano)
    {
        this.marca = marca;
        this.modelo = modelo;
        this.ano = ano;
    }
    
    
 Carro meuCarro = new Carro("Ford", "Mustang", 2021);    
~~~

## Atalhos:
- Identar: CTRL + K + D
- Renomear variavél: Ctrl +	R, Ctrl	+ R	(Ctrl +	R duas vezes).
- ctor	+	+	:	declara	um	construtor	dentro	da	classe;
- prop	+	+	:	declara	uma	propriedade	dentro	da	classe;

## Links úteis:
- https://learn.microsoft.com/pt-br/dotnet/csharp/
- https://learn.microsoft.com/pt-br/visualstudio/get-started/csharp/?view=vs-2022
- https://learn.microsoft.com/pt-br/dotnet/framework/
- https://www.caelum.com.br/apostila/apostila-csharp-orientacao-objetos.pdf
