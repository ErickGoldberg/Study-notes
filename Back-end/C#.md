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



## Links úteis:
- https://learn.microsoft.com/pt-br/dotnet/csharp/
- https://learn.microsoft.com/pt-br/visualstudio/get-started/csharp/?view=vs-2022
- https://learn.microsoft.com/pt-br/dotnet/framework/
