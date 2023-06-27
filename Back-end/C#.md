# C#
é uma linguagem de programação orientada a objetos e orientada a componentes que é fortemente tipada. O C# permite que os desenvolvedores criem muitos tipos de aplicativos seguros e robustos que são executados no .NET. 

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

~~~

Neste exemplo, criamos um dicionário que mapeia strings para inteiros. Podemos adicionar itens ao dicionário usando o método Add, onde especificamos a chave e o valor correspondente. Podemos acessar valores no dicionário usando a sintaxe de indexação, fornecendo a chave entre colchetes. Podemos verificar se uma chave existe no dicionário usando o método ContainsKey. Para atualizar um valor, simplesmente atribuímos um novo valor à chave correspondente. E para remover um item, usamos o método Remove.

Podemos iterar sobre os pares chave-valor no dicionário usando um loop foreach. A variável par representa cada par chave-valor durante a iteração.

Os dicionários em C# são extremamente úteis quando você precisa armazenar e recuperar dados de forma eficiente usando uma chave única. Eles fornecem um acesso rápido aos valores com base nas chaves, o que os torna uma escolha comum para muitos cenários de programação.

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

## Links úteis:
- https://learn.microsoft.com/pt-br/dotnet/csharp/
- https://learn.microsoft.com/pt-br/visualstudio/get-started/csharp/?view=vs-2022
- https://learn.microsoft.com/pt-br/dotnet/framework/
