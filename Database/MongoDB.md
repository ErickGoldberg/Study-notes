# O que é MongoDB:
MongoDB é um banco de dados NoSQL (Not Only SQL) orientado a documentos, ou seja, ele armazena dados em documentos JSON (JavaScript Object Notation), que são estruturas de dados flexíveis e semelhantes a objetos. O MongoDB foi desenvolvido em 2007 pela empresa 10gen (atualmente MongoDB Inc.) e se tornou um dos bancos de dados mais populares entre desenvolvedores de aplicativos web e mobile.

Diferente dos bancos de dados relacionais tradicionais, o MongoDB não utiliza tabelas para armazenar dados. Em vez disso, ele armazena dados em coleções de documentos, que podem ser acessados e manipulados de forma mais flexível e escalável do que em um modelo relacional.

Algumas das principais características do MongoDB incluem:
- Suporte a consultas complexas:

O MongoDB permite consultas complexas usando uma linguagem de consulta baseada em JSON, que permite buscar documentos com base em seus valores de atributos, relacionamentos e outras características.

- Escalabilidade horizontal: 

O MongoDB foi projetado para ser escalável horizontalmente, ou seja, para distribuir dados em vários servidores, o que permite aumentar o desempenho e a capacidade de armazenamento à medida que a demanda aumenta.

- Flexibilidade de esquema: 

O MongoDB permite que os desenvolvedores trabalhem com dados não estruturados ou sem uma estrutura fixa, o que pode ser útil em casos em que os dados são dinâmicos ou não são conhecidos com antecedência.

- Alta disponibilidade: 

O MongoDB é projetado para ser altamente disponível, com recursos de replicação e failover para garantir que os dados estejam sempre acessíveis, mesmo em caso de falhas.

O MongoDB é amplamente utilizado em aplicações web e mobile de grande escala, que precisam de um banco de dados escalável e flexível para armazenar dados em formato de documentos. Ele é compatível com diversas linguagens de programação, incluindo JavaScript, Python, Ruby, Java e C#.

## restrições de criação - Database:
Por padrão, o MongoDB já vem com três bancos de dados criados, o Admin, config e local. Além desses, nós temos a liberdade de criar novos bancos de dados. Porém, precisamos seguir algumas restrições:
- Diferenciação de maiúsculas e minúsculas do nome do banco de dados

Os nomes de banco de dados diferenciam maiúsculas de minúsculas no MongoDB. Por exemplo: se o banco de dados AluraDB já existir, o MongoDB retornará um erro se você tentar criar um banco de dados chamado AluraDB.

- Restrições sobre nomes de banco de dados para Windows

Para implantações do MongoDB em sistemas operacionais Windows, os nomes de banco de dados não podem conter nenhum dos seguintes caracteres:

/. "$*<>:|?

- Restrições sobre nomes de banco de dados para sistemas Unix e Linux

Para implantações do MongoDB em em sistemas operacionais Unix e Linux, os nomes de banco de dados não podem conter nenhum dos seguintes caracteres:

/. "$

Além disso, os nomes de banco de dados não podem conter o caractere nulo.

- Comprimento dos nomes de banco de dados

Os nomes de banco de dados não podem estar vazios e devem ter menos de 64 caracteres.

## restrições de criação - Collections:
- Os nomes das coleções devem começar com um sublinhado ou um caractere de letra.

Não podem:
- Conter o $.
- Ser uma string vazia (por exemplo "", ).
- Conter o caractere nulo.
- Começar com o system.prefixo. (Reservado para uso interno).








## Principais conceitos:
### Tipos de dados
O MongoDB armazena registros de dados como documentos BSON, que é uma representação binária de documentos JSON.

O valor de um campo em um documento pode ser qualquer um dos tipos de dados BSON, incluindo outros documentos, matrizes e matrizes de documentos
- NULL: armazena valores nulos;
- Boolean: pode armazenar valores true ou falso;
- Number: número com sinal que pode ter uma notação com E exponencial;
- Inteiro: pode armazenar o tipo de dados inteiro em duas formas, inteiro assinado de 32 bits e inteiro assinado de 64 bits;
- String: uma sequência de um ou mais caracteres Unicode;
- Object: um array não ordenado com itens do tipo chave/valor, também conhecidos como documentos aninhados;
- Array: armazena uma lista ordenada de qualquer tipo, criada usando colchetes e com cada elemento separado por vírgulas;
- ObjectId: identificador único de um registro do MongoDB;
- Date(): retorna a data atual em formato de string; e
- New Date() e ISODate(): retornam um objeto de data.



### Comandos para manipulação de Banco de Dados:

- Listar os nomes de todos os banos: 'show database' ou 'show dbs'
- Selecionar um banco de dados: 'use <banco>'
- Visualizar o banco de dados em uso: 'db'
- Excluir o banco de dados em uso: 'db.dropatabae()'
- Listr os nomes das coleções: 'show collections'
- Criação de uma collection: 'db.createColection("nome_da_colecao")'  
- Listando o nome das coleções: 'show collections'
- Renomenado uma coleção: d.colecao.renameCollection("novo_nome")
-  Excluir uma coleção do DB: 'db.colecao.drop()'
- Listar os documentos de uma coleção: 'db.colecao.find()'
- Incluir um documento em uma coleção: 'db.colecao.insertOne({campo1: "dado1", campo2: "dado2", ...})'  
- Incluindo vários documentos em uma coleção: 'db.colecao.insertMany([
{campo1: "dado1"},
{campo2: "dado2"},
{...}
  ])'  
- Alterando um documento de uma coleção: 'db.colecao.updateOne({campo: "dado"}, {$set: {campo: "dado"}})'
- 
  
  
Link para download: http://www.mongodb.com
