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

### Funções para string:
- Formatar: ToLower(), ToUpper(), Trim()
- Buscar: IndexOf, LastIndexOf
- Recortar: Substring(inicio), Substring(inicio, tamanho)
- Substituir: Replace(char, char), Replace(string, string)
- String.IsNullOrEmpty(str), String.IsNullOrWhiteSpace(str)
- str.Split(' ')
- Conversão para numero: int x = int.Parse(str), int x =Convert.ToInt32(str)
- Conversão de número: str = x.ToString(), str = x.ToString("C"), str =
x.ToString("C3"), str = x.ToString("F2")

### Garbage collector:
O Garbage Collector (Coletor de Lixo) em C# é um componente do tempo de execução do .NET que gerencia a memória de forma automática e ajuda a lidar com a desalocação de objetos que não estão mais em uso.

Quando você cria objetos em um programa C#, a memória é alocada para armazenar esses objetos. No entanto, em algum momento, esses objetos podem se tornar inacessíveis, ou seja, não há mais referências a eles no programa. Quando isso acontece, esses objetos não são mais necessários e ocupam espaço de memória desnecessariamente.

O trabalho do Garbage Collector é identificar esses objetos inacessíveis e liberar a memória ocupada por eles, tornando-a disponível para uso posterior. O Garbage Collector executa periodicamente em segundo plano, rastreando os objetos alocados e determinando quais deles são elegíveis para coleta.

O Garbage Collector utiliza um algoritmo chamado "marcador-e-varredor" (mark-and-sweep) para determinar quais objetos estão em uso e quais não estão. Durante a fase de marcação, o Garbage Collector percorre todas as referências a partir de um conjunto inicial de raízes (como variáveis estáticas, referências em pilha, etc.) e marca todos os objetos que estão acessíveis a partir dessas raízes. Em seguida, durante a fase de varredura, o Garbage Collector percorre toda a memória, desalocando os objetos não marcados e liberando a memória associada a eles.

É importante ressaltar que o desenvolvedor não precisa se preocupar explicitamente em liberar a memória alocada para objetos. O Garbage Collector cuida dessa tarefa de forma transparente. No entanto, é possível influenciar o comportamento do Garbage Collector por meio de técnicas como a liberação explícita de recursos não gerenciados usando o método Dispose(), implementando a interface IDisposable ou usando construções como using.

O uso do Garbage Collector em C# facilita a programação, reduzindo a necessidade de gerenciamento manual de memória e evitando problemas comuns, como vazamentos de memória. No entanto, é importante entender como o Garbage Collector funciona para escrever um código eficiente e evitar práticas que possam afetar negativamente o desempenho, como o uso excessivo de objetos temporários ou referências a objetos que permanecem vivos por um tempo prolongado.

Em resumo, o Garbage Collector em C# é um componente do tempo de execução do .NET que gerencia a memória automaticamente, identificando e liberando objetos que não estão mais em uso. Ele utiliza um algoritmo de marcação e varredura para rastrear os objetos alocados e desalocar a memória associada a eles. O Garbage Collector simplifica a programação ao eliminar a necessidade de gerenciamento manual de memória, ajudando a evitar vazamentos de memória e facilitando o desenvolvimento de aplicativos mais robustos.

### Nullable:
Em C#, o tipo nullable é usado para permitir que variáveis de tipos de valor armazenem um valor adicional: null. Normalmente, os tipos de valor, como int, double, bool, etc., não podem ser atribuídos a null, pois são considerados tipos de valor não anuláveis, o que significa que eles devem ter um valor válido.

No entanto, com o tipo nullable, você pode declarar uma variável de tipo de valor que pode armazenar um valor válido do tipo subjacente ou o valor null. Isso é útil quando você precisa representar a ausência de um valor ou quando precisa diferenciar entre um valor nulo e um valor padrão do tipo subjacente.

Para criar uma variável nullable em C#, você adiciona o símbolo de interrogação (?) após o tipo de valor. Aqui está um exemplo:
~~~
int? numero = null;
~~~
~~~
numero = 10; // atribui um valor inteiro válido
numero = null; // atribui o valor null
~~~
Você pode verificar se uma variável nullable tem um valor definido usando a propriedade HasValue. Além disso, para acessar o valor subjacente de uma variável nullable, você pode usar a propriedade Value, mas é necessário ter cuidado, pois, se a variável for null, ocorrerá uma exceção InvalidOperationException. Para evitar a exceção, é recomendável verificar se a variável tem um valor usando HasValue antes de acessar o Value.

Aqui está um exemplo que demonstra o uso dessas propriedades:
~~~
int? numero = 10;

if (numero.HasValue)
{
    Console.WriteLine("O número tem um valor: " + numero.Value);
}
else
{
    Console.WriteLine("O número é nulo.");
}
~~~
O tipo nullable é especialmente útil quando se trabalha com bancos de dados, onde colunas podem ter valores nulos, ou ao lidar com dados opcionais ou valores padrão em APIs.

Em resumo, o tipo nullable em C# permite que variáveis de tipos de valor armazenem um valor válido do tipo subjacente ou o valor null. Isso é útil quando você precisa representar a ausência de um valor ou quando precisa diferenciar entre um valor nulo e um valor padrão do tipo subjacente. O tipo nullable é criado adicionando o símbolo de interrogação (?) após o tipo de valor e oferece propriedades como HasValue e Value para verificar e acessar os valores.

### Coalescência nula:
A coalescência nula, também conhecida como operador de fusão nula ou operador de coalescência nula, é um recurso do C# que permite atribuir um valor padrão a uma expressão que possa resultar em null. Ela é representada pelo operador ??.

O operador de coalescência nula tem a seguinte sintaxe:
~~~
expressao1 ?? expressao2
~~~
A expressão1 representa a expressão que será avaliada e pode resultar em null. A expressão2 representa o valor padrão que será atribuído caso a expressão1 seja null.

O operador de coalescência nula funciona da seguinte maneira:

- Se a expressão1 não for null, o valor da expressão1 será retornado.
- Se a expressão1 for null, o valor da expressão2 será retornado.
Aqui está um exemplo simples:
~~~
string nome = null;
string nomeCompleto = nome ?? "Nome não disponível";

Console.WriteLine(nomeCompleto); // Saída: "Nome não disponível"
~~~

### Lista:
Em C#, as listas são uma estrutura de dados fornecida pela biblioteca padrão do .NET Framework que permite armazenar e manipular uma coleção de elementos de forma dinâmica. A lista é uma implementação da interface List<T> e oferece várias operações convenientes para adicionar, remover, pesquisar e acessar elementos da coleção.

Aqui estão algumas características e vantagens das listas em C#:

- Dinamicidade: As listas têm tamanho dinâmico, o que significa que você pode adicionar e remover elementos facilmente sem se preocupar com o redimensionamento manual da coleção.
- Acesso por índice: As listas permitem acessar elementos com base em seus índices. Isso facilita a recuperação rápida de elementos específicos.
- Operações de adição e remoção: As listas fornecem métodos para adicionar elementos no final da lista (Add), inserir elementos em uma posição específica (Insert), remover elementos (Remove), remover elementos em uma posição específica (RemoveAt), remover todos os elementos (Clear), entre outras operações úteis.
- Iteração simplificada: As listas podem ser facilmente percorridas usando um loop foreach, o que torna a iteração sobre os elementos da lista muito conveniente.
- Tipagem forte: As listas em C# são tipadas, o que significa que você pode especificar o tipo de elementos que a lista pode conter. Isso oferece segurança de tipo durante a compilação e evita erros de tipo em tempo de execução.
- Métodos e propriedades auxiliares: As listas fornecem métodos e propriedades úteis, como Count (para obter o número de elementos na lista), Contains (para verificar se a lista contém um elemento específico), Sort (para classificar os elementos da lista) e muito mais.

No entanto, as listas também têm algumas desvantagens:

- Inserção e remoção em posições intermediárias: Embora as listas permitam a inserção e a remoção de elementos em posições específicas, essas operações podem ser mais lentas quando comparadas com estruturas de dados como LinkedList ou ArrayList.
- Consumo de memória: As listas alocam um bloco contíguo de memória para armazenar seus elementos, o que pode resultar em desperdício de memória se a lista for redimensionada frequentemente ou se o tamanho estimado da lista for significativamente maior do que o número real de elementos.

Aqui está um exemplo básico de como usar uma lista em C#:
~~~
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> nomes = new List<string>();

        nomes.Add("João");
        nomes.Add("Maria");
        nomes.Add("José");

        Console.WriteLine("Elementos da lista:");

        foreach (string nome in nomes)
        {
            Console.WriteLine(nome);
        }
    }
}
~~~

Em resumo, as listas em C# são estruturas de dados flexíveis e convenientes que oferecem operações poderosas para manipular coleções de elementos. Elas têm tamanho dinâmico, permitem acesso por índice, fornecem métodos úteis e são tipadas. No entanto, a inserção e remoção em posições intermediárias podem ser mais lentas e o consumo de memória pode ser uma preocupação em determinados casos.

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

### Override:
A palavra-chave "override" é usada para indicar que um método em uma classe derivada está substituindo (ou "sobrescrevendo") um método de mesma assinatura na classe base. Ao usar "override", você está modificando o comportamento padrão do método na classe base e fornecendo uma implementação específica para a classe derivada.
Para usar "override", você precisa seguir algumas regras:

- O método na classe derivada deve ter a mesma assinatura (nome, tipo e ordem dos parâmetros) do método na classe base.
- O método na classe base deve ser declarado como "virtual", "abstract" ou "override" (se já for uma substituição de outro método).
- O modificador de acesso do método na classe derivada não pode ser menos acessível do que o modificador de acesso do método na classe base.

Aqui está um exemplo de como usar o "override" em C#:
~~~
class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("The animal makes a sound.");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("The dog barks.");
    }
}

class Program
{
    static void Main()
    {
        Animal animal = new Animal();
        animal.MakeSound();  // Output: The animal makes a sound.

        Dog dog = new Dog();
        dog.MakeSound();  // Output: The dog barks.
    }
}
~~~

### Base:
A palavra-chave "base" é usada em uma classe derivada para acessar membros da classe base, como métodos, propriedades ou construtores. Você pode usar "base" para chamar a implementação do método da classe base antes de fazer modificações adicionais ou para acessar propriedades e campos da classe base.

Aqui está um exemplo de como usar o "base" em C#:
~~~
class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("The animal makes a sound.");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        base.MakeSound();  // Chama o método MakeSound() da classe base.
        Console.WriteLine("The dog barks.");
    }
}

class Program
{
    static void Main()
    {
        Dog dog = new Dog();
        dog.MakeSound();
        /* 
        Output:
        The animal makes a sound.
        The dog barks.
        */
    }
}
~~~

### Interface:

Em C#, uma interface é uma estrutura que define um contrato entre duas entidades: uma classe e a entidade que a utiliza. Ela define um conjunto de membros (métodos, propriedades, eventos e indexadores) que a classe que implementa a interface deve fornecer.

Aqui estão algumas características e conceitos importantes relacionados a interfaces em C#:

Declaração: Uma interface é declarada usando a palavra-chave interface seguida pelo nome da interface. Por convenção, o nome da interface começa com uma letra "I" maiúscula.

~~~
public interface IExemplo
{
    void Metodo1();
    int Propriedade { get; set; }
    event EventHandler Evento;
}
~~~

- Implementação: Uma classe pode implementar uma ou mais interfaces. Isso é feito usando a palavra-chave class seguida pelo nome da classe e uma lista separada por vírgulas de interfaces que a classe implementa.

## Arquivos e diretórios:
Em C#, existem várias classes e conceitos relacionados a arquivos e diretórios que facilitam a manipulação de operações de leitura e gravação de arquivos. Vou explicar brevemente alguns deles:

1. File: A classe File fornece métodos estáticos para criar, copiar, excluir, mover e realizar outras operações em arquivos. Ela é útil para operações básicas de manipulação de arquivos, como leitura e gravação.

2. FileInfo: A classe FileInfo fornece uma representação de alto nível de um arquivo existente no sistema de arquivos. Ela permite acessar informações sobre o arquivo, como nome, tamanho, data de criação, entre outros. Também fornece métodos para manipular o arquivo, como copiar, mover, renomear, excluir, ler e gravar.

3. FileStream: A classe FileStream permite a leitura e gravação de dados brutos em um arquivo. Ela fornece um fluxo de bytes para ler e gravar dados em um arquivo de maneira eficiente.

4. StreamReader: A classe StreamReader é usada para ler caracteres de um fluxo de bytes, como um arquivo. Ela facilita a leitura de texto de um arquivo, permitindo a leitura de linhas ou caracteres individuais.

5. StreamWriter: A classe StreamWriter é usada para gravar caracteres em um fluxo de bytes, como um arquivo. Ela facilita a gravação de texto em um arquivo, permitindo a escrita de linhas ou caracteres individuais.

6. Bloco using: O bloco using é usado para garantir que os recursos sejam liberados corretamente após o uso. Ele permite que você trabalhe com recursos como arquivos, streams, etc., dentro do escopo do bloco using e, assim que sair do escopo, esses recursos serão automaticamente liberados.

7. Directory: A classe Directory fornece métodos estáticos para criar, mover, renomear e realizar outras operações em diretórios. Ela permite a manipulação de diretórios no sistema de arquivos.

8. DirectoryInfo: A classe DirectoryInfo fornece uma representação de alto nível de um diretório existente no sistema de arquivos. Ela permite acessar informações sobre o diretório, como nome, data de criação, arquivos contidos, entre outros. Também fornece métodos para manipular o diretório, como criar, renomear e excluir.

9. Path: A classe Path fornece métodos estáticos para manipular caminhos de arquivo e diretório. Ela permite combinar, extrair informações e realizar outras operações em caminhos de arquivos e diretórios.

10. IOException: A IOException é uma exceção que é lançada quando ocorre um erro de E/S (entrada/saída) ao trabalhar com arquivos, como falha na leitura ou gravação. Ela permite tratar exceções relacionadas a operações de arquivo.

Esses são apenas alguns conceitos relacionados a arquivos e diretórios em C#. O .NET Framework oferece uma ampla gama de classes e recursos para facilitar a manipulação de operações de E/S em arquivos e diretórios.  

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
