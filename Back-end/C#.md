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

### Conjuntos:
Em C#, um conjunto é uma estrutura de dados que armazena elementos únicos. Os conjuntos são implementados pela classe HashSet<T> da biblioteca padrão do .NET.

Para usar conjuntos em C#, você deve primeiro importar o namespace System.Collections.Generic. Em seguida, você pode criar um objeto HashSet<T> e adicionar elementos a ele.

Aqui está um exemplo básico de como usar conjuntos em C#:

~~~
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        // Criando um conjunto de números inteiros
        HashSet<int> conjunto = new HashSet<int>();

        // Adicionando elementos ao conjunto
        conjunto.Add(1);
        conjunto.Add(2);
        conjunto.Add(3);

        // Verificando se um elemento está presente no conjunto
        bool contem = conjunto.Contains(2);
        Console.WriteLine(contem);  // Saída: True

        // Removendo um elemento do conjunto
        conjunto.Remove(3);

        // Percorrendo os elementos do conjunto
        foreach (int elemento in conjunto)
        {
            Console.WriteLine(elemento);
        }
        // Saída: 1, 2
    }
}
~~~

Neste exemplo, criamos um conjunto de números inteiros e adicionamos alguns elementos a ele. Em seguida, verificamos se o número 2 está presente no conjunto, removemos o número 3 e percorremos os elementos restantes.

Os conjuntos em C# são úteis quando você precisa armazenar elementos únicos e não se preocupa com a ordem dos elementos. Eles são eficientes para verificar se um elemento está presente no conjunto e para remover elementos duplicados de uma lista.

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

~~~
public class Exemplo : IExemplo
{
    public void Metodo1()
    {
        // Implementação do método
    }

    public int Propriedade { get; set; }

    public event EventHandler Evento;
}
~~~

- Contrato: Uma interface define um contrato que a classe que a implementa deve cumprir. Isso significa que a classe deve fornecer implementações para todos os membros definidos na interface.

- Herança de interfaces: As interfaces também podem herdar de outras interfaces, permitindo a criação de hierarquia de interfaces. Uma classe que implementa uma interface derivada também é considerada como implementando todas as interfaces base.

~~~
public interface IInterfaceBase
{
    void MetodoBase();
}

public interface IInterfaceDerivada : IInterfaceBase
{
    void MetodoDerivado();
}

public class Exemplo : IInterfaceDerivada
{
    public void MetodoBase()
    {
        // Implementação do método da interface base
    }

    public void MetodoDerivado()
    {
        // Implementação do método da interface derivada
    }
}
~~~

- Polimorfismo de interface: O uso de interfaces permite o polimorfismo, o que significa que você pode tratar objetos de classes diferentes que implementam a mesma interface de maneira uniforme.

~~~
public void ExemploPolimorfismo(IExemplo exemplo)
{
    exemplo.Metodo1();
}
~~~

- Implementação explícita de interface: Uma classe também pode implementar uma interface de forma explícita, onde os membros da interface são implementados explicitamente, tornando-os acessíveis somente por meio da interface.

~~~
public class Exemplo : IExemplo
{
    void IExemplo.Metodo1()
    {
        // Implementação do método de forma explícita
    }
}
~~~

As interfaces são uma parte fundamental da programação orientada a objetos em C#. Elas permitem definir contratos claros, promovem a reutilização de código e facilitam a implementação de polimorfismo e extensibilidade em suas classes.

## Generics:
Generics em C# é um recurso que permite criar classes, interfaces, métodos e delegados que podem ser parametrizados com tipos específicos. Isso proporciona flexibilidade e reutilização de código, pois você pode escrever código genérico que funciona com diferentes tipos de dados, sem precisar repetir o código para cada tipo individualmente.

Aqui estão alguns conceitos importantes relacionados a generics em C#:

Declaração de uma classe genérica:
Você pode declarar uma classe genérica usando a sintaxe <T>, onde "T" é um parâmetro de tipo que representa um tipo desconhecido.

~~~
public class Exemplo<T>
{
    // Código da classe genérica
}
~~~

Uso de tipo genérico:
Dentro da classe genérica, você pode usar o tipo genérico "T" como se fosse um tipo real. Ele pode ser usado para declarar variáveis, parâmetros de método, propriedades e retornos de método.

~~~
public class Exemplo<T>
{
    private T dado;

    public Exemplo(T valor)
    {
        dado = valor;
    }

    public T GetDado()
    {
        return dado;
    }
}
~~~

Restrições de tipo:
Você pode aplicar restrições aos parâmetros de tipo genérico usando a palavra-chave where. As restrições de tipo especificam que tipo ou tipos devem ser usados para substituir o parâmetro genérico.

~~~
public class Exemplo<T> where T : IComparable
{
    // Restrição de tipo: T deve implementar a interface IComparable
}
~~~

Métodos genéricos:
Você também pode declarar métodos genéricos que recebem ou retornam tipos genéricos. Isso permite que você escreva código genérico para operações que funcionam com vários tipos.

~~~
public class Exemplo
{
    public void MetodoGeneri<|endoftext|>
~~~

### Extension methods:
Em C#, extension methods (métodos de extensão) permitem adicionar novos métodos a tipos existentes sem modificar ou herdar desses tipos. Isso é útil quando você não pode modificar a definição de uma classe, como tipos primitivos ou classes de bibliotecas de terceiros.

Para criar um extension method, você deve seguir as seguintes regras:

1. Defina uma classe estática.
2. Defina um método estático dentro da classe estática.
3. Adicione o modificador this antes do primeiro parâmetro do método. O tipo desse parâmetro será o tipo que você deseja estender.
Aqui está um exemplo de como criar e usar um extension method em C#:

~~~
using System;

public static class StringExtensions
{
    public static string Reverse(this string str)
    {
        char[] chars = str.ToCharArray();
        Array.Reverse(chars);
        return new string(chars);
    }
}

class Program
{
    static void Main(string[] args)
    {
        string texto = "Hello, World!";
        string textoReverso = texto.Reverse();

        Console.WriteLine(texto);          // Saída: Hello, World!
        Console.WriteLine(textoReverso);   // Saída: !dlroW ,olleH
    }
}
~~~

Neste exemplo, criamos um extension method chamado Reverse para a classe string. O método Reverse recebe uma string como parâmetro e retorna a string invertida. Para usar o método, basta chamar o método diretamente na instância de string desejada.

Extension methods são úteis para adicionar funcionalidades a tipos existentes sem modificar suas definições. Eles podem ser usados para melhorar a legibilidade do código e fornecer métodos personalizados para tipos primitivos ou classes de terceiros.

### Delegates:
Em C#, um delegate é um tipo que representa referências a métodos. Ele pode ser visto como um ponteiro para um método, permitindo que você passe métodos como parâmetros, armazene-os em variáveis ​​e invoque-os posteriormente.

Os delegates fornecem um mecanismo flexível e poderoso para a implementação de callbacks e eventos. Eles são amplamente utilizados em cenários como programação assíncrona, manipulação de eventos, chamada de métodos em tempo de execução com base em condições, entre outros.

A declaração de um delegate envolve especificar a assinatura do método que ele pode representar. Aqui está a sintaxe básica para declarar um delegate em C#:

~~~
delegate tipoRetorno NomeDelegate(tipoParametro1 parametro1, tipoParametro2 parametro2, ...);
~~~

Por exemplo, vamos criar um delegate chamado OperacaoMatematica que representa um método que recebe dois inteiros como parâmetros e retorna um inteiro:

~~~
delegate int OperacaoMatematica(int a, int b);
~~~

Agora, podemos usar esse delegate para referenciar diferentes métodos que correspondam à assinatura especificada. Vamos criar duas funções que correspondem a essa assinatura:

~~~
int Soma(int a, int b)
{
    return a + b;
}

int Subtracao(int a, int b)
{
    return a - b;
}
~~~

Em seguida, podemos criar uma instância do delegate OperacaoMatematica e atribuir a ela uma referência ao método Soma ou Subtracao:

~~~
OperacaoMatematica operacao = Soma;
int resultado = operacao(5, 3); // resultado = 8

operacao = Subtracao;
resultado = operacao(5, 3); // resultado = 2
~~~

Observe que podemos atribuir diferentes métodos ao mesmo delegate, desde que eles correspondam à assinatura especificada.

Além disso, os delegates também podem ser combinados usando o operador + e -=, permitindo que você tenha múltiplos métodos associados ao delegate. Quando o delegate é invocado, todos os métodos associados são chamados na ordem em que foram adicionados.

~~~
OperacaoMatematica operacao = Soma;
operacao += Subtracao;

int resultado = operacao(5, 3);
// resultado = 8 (retorno do método Soma)
// resultado = 2 (retorno do método Subtracao)
~~~

Os delegates também são frequentemente usados em combinação com os eventos. Os eventos são um mecanismo de C# para notificar outras partes do código quando algo acontece. Ao declarar um evento, você também precisa especificar o delegate que será usado para lidar com o evento.

Em resumo, os delegates em C# permitem que você trate métodos como objetos, referenciando-os, passando-os como parâmetros e invocando-os posteriormente. Eles são particularmente úteis em cenários onde é necessário implementar callbacks ou tratar eventos.

## LINQ:
LINQ (Language Integrated Query) é uma tecnologia introduzida pela Microsoft no .NET Framework que permite a consulta de dados de uma maneira unificada usando uma sintaxe similar à consulta SQL em C#.

O LINQ oferece uma maneira intuitiva e poderosa de manipular e consultar dados de diferentes fontes, como bancos de dados, coleções de objetos, serviços web e muito mais. Ele permite escrever consultas de dados diretamente no código C#, proporcionando uma abordagem declarativa para a manipulação de dados.

Existem dois principais tipos de sintaxe para usar o LINQ em C#:

1. Sintaxe de consulta (Query Syntax): A sintaxe de consulta é semelhante à sintaxe SQL e permite escrever consultas usando palavras-chave como "from", "where", "select" e "orderby". Aqui está um exemplo de consulta LINQ usando a sintaxe de consulta:

~~~
var result = from c in customers
             where c.Age > 18
             orderby c.Name
             select c;
~~~

Nesse exemplo, a variável customers representa uma coleção de objetos do tipo Customer. A consulta LINQ filtra os clientes com idade superior a 18 e, em seguida, os ordena pelo nome, retornando a lista resultante.

2. Sintaxe de método (Method Syntax): A sintaxe de método é baseada em métodos de extensão e permite encadear operações usando métodos LINQ como "Where", "OrderBy", "Select", etc. Aqui está o mesmo exemplo anterior, reescrito usando a sintaxe de método:

~~~
var result = customers
    .Where(c => c.Age > 18)
    .OrderBy(c => c.Name)
    .Select(c => c);
~~~

Nesse exemplo, a variável customers representa a mesma coleção de objetos do tipo Customer. A consulta LINQ é expressa como uma sequência de métodos encadeados, onde cada método filtra, ordena ou seleciona os elementos da coleção.

O LINQ oferece suporte a uma ampla gama de operações, como filtragem, ordenação, projeção, junção (join), agrupamento (group by) e agregação. Além disso, ele pode ser usado com vários provedores de dados, como LINQ to Objects (para consultas em coleções), LINQ to SQL (para consultas em bancos de dados SQL), LINQ to XML (para consultas em documentos XML) e assim por diante.

O uso do LINQ traz benefícios significativos, como código mais legível e expressivo, redução da quantidade de código necessário para manipular dados e maior produtividade no desenvolvimento de aplicativos. Ele se tornou uma ferramenta poderosa para os desenvolvedores C# lidarem com consultas e manipulação de dados de forma eficiente e intuitiva.

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

## Ler arquivos XML:
Para ler documentos XML em C#, você pode usar a classe XmlReader ou a classe XmlDocument. Ambas as classes fornecem funcionalidades para analisar e extrair informações de documentos XML.

Usando xmlDocument:
~~~
using System;
using System.Xml;

class Program
{
    static void Main()
    {
        // Cria um objeto XmlDocument
        XmlDocument xmlDoc = new XmlDocument();

        // Carrega o documento XML a partir do arquivo
        xmlDoc.Load("caminho_do_arquivo.xml");

        // Obtém o elemento raiz do documento
        XmlElement root = xmlDoc.DocumentElement;

        // Exibe o nome do elemento raiz
        Console.WriteLine("Elemento raiz: " + root.Name);

        // Percorre os elementos filhos do elemento raiz
        foreach (XmlNode node in root.ChildNodes)
        {
            // Verifica se é um elemento
            if (node.NodeType == XmlNodeType.Element)
            {
                // Exibe o nome do elemento
                Console.WriteLine("Elemento: " + node.Name);

                // Percorre os atributos do elemento
                foreach (XmlAttribute attribute in node.Attributes)
                {
                    // Exibe o nome e o valor do atributo
                    Console.WriteLine("Atributo: " + attribute.Name + " = " + attribute.Value);
                }

                // Verifica se possui texto
                if (node.HasChildNodes && node.FirstChild.NodeType == XmlNodeType.Text)
                {
                    // Exibe o texto
                    Console.WriteLine("Texto: " + node.FirstChild.Value);
                }
            }
        }
    }
}
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
