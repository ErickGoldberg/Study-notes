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

## restrições de criação - Documentos:
- O nome do campo _id é reservado para uso como chave primária. Seu valor deve ser único na coleção, é imutável e pode ser de qualquer tipo que não seja um array.
- Os nomes dos campos não podem conter o caractere NULL.
- O tamanho máximo de um documento BSON é 16 megabytes.

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
Listar os nomes de todos os banos: 
- 'show database' ou 'show dbs'

Selecionar um banco de dados:
-  'use <banco>'
  
Visualizar o banco de dados em uso:  
-  'db'
  
Excluir o banco de dados em uso:
-  'db.dropatabae()'
  
Listar os nomes das coleções:
- 'show collections'
  
Criação de uma collection:
- 'db.createColection("nome_da_colecao")'  
  
Listando o nome das coleções:
-  'show collections'
  
Renomenado uma coleção:
- d.colecao.renameCollection("novo_nome")
  
Excluir uma coleção do DB:
-   'db.colecao.drop()'
  
Listar os documentos de uma coleção:
-  'db.colecao.find()'
  
Incluir um documento em uma coleção:
-  'db.colecao.insertOne({campo1: "dado1", campo2: "dado2", ...})'  
 
Incluindo vários documentos em uma coleção:  
-  'db.colecao.insertMany([
{campo1: "dado1"},
{campo2: "dado2"},
{...}
  ])'  
  
Alterando um documento de uma coleção:
-  'db.colecao.updateOne({campo: "dado"}, {$set: {campo: "dado"}})'
-   db.collection.replaceOne( <filter>, <replacement> )
  
Alterando vários documentos de uma coleção:
- 'db.coleção.updateMany({campo: "dado"}, {$set: {campo: "dado"}})'
  
Alterando todos documentos de uma coleção:
-  'db.colecao.updateMany({}, {$set: {campo: "dado"}})'
  
Excluindo um documento de uma coleção:
- 'db.colecao.deleteOne({campo: "dado"})'
  
Excluindo vários documentos de uma coleção:
-  'db.colecao.deleteMany({campo: "dado"})'
  
Excluindo todos os documentos de uma coleção:
-  'db.colecao.deleteMany({})'

## Método find:
### Pela interface:
FILTER:
  - Utilizado para especificar qual será a condição que os documentos devem atender para serem retornados na busca.  

PROJECT:
-  Utilizado para especificar quais campos serão ou não retornados na consulta.
- Ao Informar o nome do campo e informar 0, todos os campos, exceto os campos especificados no campo project, são retornados. Se o campo receber o valor de 1, ele será retornado na consulta. O campo _id é retornado por padrão, a menos que este seja especificado no campo project e definido como 0.
  
SORT: 
- Especifica a ordem de classificação dos documentos retornados.
- Para especificar a ordem crescente de um campo, defina o campo como 1.
- db.pessoal.find().sort( { nome: 1 } )
- Para especificar a ordem decrescente de um campo, defina o campo como -1.
- db.pessoal.find().sort( { nome: -1 } )  
  
MAX TIME MS: 
 - Define o limite de tempo cumulativo em milissegundos para processar as operações da barra de consulta. Se o limite de tempo for atingido antes da conclusão da operação, o Compass interrompe a operação.
  
COLLATION: 
 - Utilizado para especificar regras específicas do idioma para comparação de textos, como regras para letras maiúsculas ou minúsculas, acentos, entre outros. 
  
SKIP:
 - Especifica quantos documentos devem ser ignorados antes de retornar o conjunto de resultados.
 - db.pessoal.find().skip( 2 ) 
  
LIMIT: 
 - Especifica o número máximo de documentos a serem retornados.
  
COUNT:
- O método count é utilizado para contar o numero de documentos.
- db.pessoal.count()
- O método count pode ser utilizado para contar o numero de documentos que satisfaçam determinadas condições.  
- db.pessoal.count({sexo: "M"})
  
PRETTY:
- O método pretty apresenta os campos do documento em blocos.
- db.pessoal.find().pretty()  
  
### Pela linha de código:  
- Para consultar dados em uma coleção
utilizamos o método find(). Se a condição
não for fornecida, todos os documentos
serão mostrados.
- db.pessoal.find( ) 
- db.pessoal.find( { } )
- db.pessoal.find( { }, { nome: 1, sexo: 1 } )
  
## Operadores lógicos:
### $eq:  
- O operador $eq (equal) compara dois valores e retorna true se forem iguais e false se forem diferentes.
- db.pessoal.find( { sexo: { $eq: "F" } } )
  
### $ne:
- O operador $ne (not equal) compara dois valores e retorna true se forem diferentes e false se forem iguais.  
- db.pessoal.find( { sexo: { $ne: "F" } } )
  
### $gt:
- O operador $gt (greater than) compara se os valores de um campo são maiores que o valor informado. Devolverá true, se o valor do campo for maior que o valor fornecido.  
- db.pessoal.find( { salario: { $gt: 16000 } } )
  
### $gte: 
- O operador $gte (greater than or equal) compara se os valores de um campo são maiores ou iguais ao valor informado. Devolverá true, se o valor do campo for maior ou igual ao valor fornecido.  
- db.pessoal.find( { salario: { $gte: 16000 } } )
    
### $lt:
- O operador $lt (less than) compara se os valores de um campo são menores que o valor informado. Devolverá true, se o valor do campo for menor que o valor fornecido.  
- db.pessoal.find( { salario: { $lt: 16000 } } )  
  
### $lte:
- O operador $lte (less than or equal) compara se os valores de um campo são menores ou iguais ao valor informado. Devolverá true, se o valor for menor ou igual ao valor fornecido.
- db.pessoal.find( { salario: { $lte: 16000 } } )  
  
### $and:
- O operador $and é utilizando para especificar mais de uma condição dentro de um array. Todas as condições têm que ser verdadeiras para que o resultado seja verdadeiro.  
- db.pessoal.find( { $and: [ {sexo: "F" } , { idade: 30 } ] } )  

### $or:
- O operador $or é utilizado para verificar mais de uma condição passada em um array. Basta que uma das condições seja verdadeira para que o resultado seja verdadeiro.  
- db.pessoal.find( { $or: [ {sexo: "F" } , { idade: 30 } ] } )
  
### $nor:
- O operador $nor (not or) é utilizado para verificar a não ocorrência de mais de uma condição passada em um array. As condições devem ser falsas para que o resultado seja verdadeiro.  
- db.pessoal.find( { $nor: [ {sexo: "F" } , { idade: 30 } ] } )  
  
### $not:
-  O operador $not é utilizando para negar uma condição.
-  db.pessoal.find( { sexo: { $not: { $eq: "F" } } } )
  
### $in:
- O operador $in (interval) é utilizando para verificar se um valor coincide com um dos valores de um array fornecido. Se o valor for encontrado, será retornado true, caso contrário, false.
- db.pessoal.find( { idade: { $in: [ 25, 29, 30 ] } } )
  
### $nin: 
- O operador $nin (not interval) é utilizando para verificar se um valor não coincide com nenhum dos valores de um array fornecido. Se o valor não for encontrado, será retornado true, caso contrário, false.
- db.pessoal.find( { idade: { $nin: [ 25, 29, 30 ] } } )
  
### $all:
- O operador $all é utilizando para verificar se existe todas as ocorrências informadas em um campo multivalorado. O resultado será satisfatório se existir as ocorrências, independentemente da ordem em que os parâmetros foram fornecidos.
- db.pessoal.find( { lazer: { $all: [ "Cinema", "Futebol" ] } } )
  
### $exists:
- O operador $exists é utilizando para verificar se um campo existe, ou não, em determinados documentos. Se o valor passado for true, devolverá os documentos que possuem o campo. Caso false, devolverá os documentos que não possuem o campo informado.
-  db.pessoal.find( { obs: { $exists: true } } )
  
### $search:
- O operador $search é utilizado para fazer busca textual indexada em um campo específico. Antes de utilizar o operador, devemos criar um índice com o campo a ser consultado.  
-  db.pessoal.createIndex({profissao: "text"})
- db.pessoal.find( { $text: { $search: "Engenheiro" } } )
  
### $regex:
- O operador regex permite a utilização de expressões regulares em consultas.
- db.pessoal.find( { profissao: { $regex: /Eng/ } } )
- db.pessoal.find( { profissao: /Eng/ } )  
  
## Validação de Schema:
A validação de esquema permite criar regras de validação para seus campos, como tipos de dados permitidos e intervalos de valores.

O MongoDB usa um modelo de esquema flexível, o que significa que os documentos em uma coleção não precisam ter os mesmos campos ou tipos de dados por padrão. Depois de estabelecer um esquema de aplicativo, você pode usar a validação de esquema para garantir que não haja alterações de esquema não intencionais ou tipos de dados impróprios.

### Quando usar a validação de esquema:  
Suas necessidades de validação de esquema dependem de como os usuários usam seu aplicativo. Quando seu aplicativo está nos estágios iniciais de desenvolvimento, a validação do esquema pode impor restrições inúteis porque você não sabe como deseja organizar seus dados. Especificamente, os campos em suas coleções podem mudar com o tempo.

A validação de esquema é mais útil para um aplicativo estabelecido onde você tem uma boa noção de como organizar seus dados. Você pode usar a validação de esquema nos seguintes cenários:
- Para uma coleção de usuários, certifique-se de que o passwordcampo seja armazenado apenas como uma string. Essa validação impede que os usuários salvem suas senhas como um tipo de dados inesperado, como uma imagem.
- Para uma coleção de vendas, verifique se o itemcampo pertence a uma lista de itens que sua loja vende. Essa validação evita que um usuário digite incorretamente um nome de item acidentalmente ao inserir dados de vendas.
- Para uma coleção de alunos, certifique-se de que o gpacampo seja sempre um número positivo. Essa validação detecta erros de digitação durante a entrada de dados.
  
### O que acontece quando um documento falha na validação:
Por padrão, quando uma operação de inserção ou atualização resultaria em um documento inválido, o MongoDB rejeita a operação e não grava o documento na coleção.

Como alternativa, você pode configurar o MongoDB para permitir documentos inválidos e registrar avisos quando ocorrerem violações de esquema.
  
  
  
  
  
  
  
  
  
  
  
  
  
Link para download: http://www.mongodb.com
