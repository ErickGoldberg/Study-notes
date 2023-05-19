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
  
DISTINCT:
- A função distinct() no MongoDB é usada para retornar uma lista de valores únicos encontrados em um campo específico de uma coleção. Ela retorna os valores distintos presentes no campo especificado, eliminando quaisquer duplicatas.  
- db.collection.distinct("campo")

AGGREGATE:
- O método aggregate() no MongoDB é usado para realizar operações de agregação em documentos de uma coleção. A agregação permite que você processe e transforme dados de maneira flexível, executando várias etapas em sequência para realizar operações como filtrar, agrupar, projetar, ordenar e calcular valores agregados.  
- db.collection.aggregate([ etapa1, etapa2, ... ])
  
LOOKUP:
- A etapa $lookup no MongoDB é usada durante a agregação para realizar operações de junção entre várias coleções. Ela permite que você combine documentos de uma coleção com documentos de outra coleção com base em campos relacionados.  
- {
  $lookup: {
    from: <coleção_destino>,
    localField: <campo_local>,
    foreignField: <campo_destino>,
    as: <nome_do_campo>
  }
}
- A etapa $lookup é útil quando você precisa combinar informações de diferentes coleções com base em campos relacionados. Isso permite que você obtenha dados relacionados em uma única consulta e realize análises e consultas mais complexas envolvendo várias coleções no MongoDB.
  
COUNT:
- O método count é utilizado para contar o numero de documentos.
- db.pessoal.count()
- O método count pode ser utilizado para contar o numero de documentos que satisfaçam determinadas condições.  
- db.pessoal.count({sexo: "M"})
  
PRETTY:
- O método pretty apresenta os campos do documento em blocos.
- db.pessoal.find().pretty()  
  
OUTROS:
- findAndModify: Modifica e retorna um único documento de acordo com o filtro especificado na consulta.
- findOneAndUpdate: Atualiza um único documento com base nos critérios especificados no filtro da consulta.
- findOneAndReplace: Substitui um único documento de acordo com o filtro especificado na consulta.
- findOneAndDelete: Exclui um único documento com base nos critérios especificados na consulta e retorna como resultado o documento excluído.
  
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
  
### $slice:
- O operador $slice no MongoDB é usado para retornar uma parte de um array em um documento. Ele permite que você selecione um subconjunto dos elementos de um array com base em uma posição de início e uma quantidade específica de elementos a serem retornados.
- O operador $slice pode ser usado em conjunto com a projeção em uma consulta ou com o operador de atualização $set em uma operação de atualização.  
- { campo: { $slice: [ <número>, <quantidade> ] } }
- db.collection.find({}, { arrayField: { $slice: -3 } })  
  
### $group:
A etapa $group no MongoDB é usada durante a agregação para agrupar documentos por um ou mais campos e realizar operações de agregação nos grupos resultantes. Essa etapa é uma das etapas fundamentais para a análise e resumos de dados em uma coleção. 
- { $group: { _id: <expressão>, <campo1>: { <operador1>: <expressão1> }, ... } }
- db.sales.aggregate([
  { $group: { _id: "$product", totalSales: { $sum: "$quantity" } } }
])
- O resultado da operação $group será um conjunto de documentos agrupados, onde cada documento representa um grupo exclusivo identificado pelo valor do campo _id especificado.  
  
### $unionWith:
Com o operador $unionWith é possível realizar consultas complexas que recuperam dados de várias coleções em uma única consulta, além de retornar os resultados combinados. Isso é útil quando se deseja realizar uma análise mais ampla dos dados, pois nem sempre os dados são armazenados fisicamente em uma única coleção dentro do banco de dados.

Ao usar o operador $unionWith, é importante que as coleções envolvidas tenham esquemas semelhantes. Se as coleções tiverem campos ou campos com tipos de dados diferentes, pode ser necessário converter ou transformar os dados antes de executar a operação de união. Este operador também suporta outras opções que podem ser usadas para ajustar o comportamento da operação. Algumas dessas opções incluem:
- pipeline: permite que você especifique um pipeline de agregação para ser aplicado aos resultados combinados.
- collation: permite especificar uma regra de ordem de classificação para a união.  
- db.coleção.aggregate( [
   { $project: { _id: 0 } },
   { $unionWith: {<coleção>} }
])
  
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
  
### Operadores de avaliação:
####  $expr:
Permite o uso de expressões de agregação na linguagem de consulta
- { $expr: { <expression> } }
- db.monthlyBudget.find( { $expr: { $gt: [ "$spent" , "$budget" ] } } )  
  
####  $mod:
Executa uma operação de um módulo no valor de um campo e seleciona documentos com um resultado especificado
- { field: { $mod: [ divisor, remainder ] } }
- db.inventory.find( { qty: { $mod: [ 4.0, 0 ] } } )
  
#### $regex:
- O operador regex permite a utilização de expressões regulares em consultas.
- db.pessoal.find( { profissao: { $regex: /Eng/ } } )
- db.pessoal.find( { profissao: /Eng/ } ) 
  
####  $text:
Executa a pesquisa de texto:  
- db.articles.createIndex( { subject: "text" } )
- {
  $text:
    {
      $search: <string>,
      $language: <string>,
      $caseSensitive: <boolean>,
      $diacriticSensitive: <boolean>
    }
}
  
#### $where:
Corresponde a documentos que atendem a uma expressão JavaScript
- { $where: <string|JavaScript Code> }
- db.players.find( { $where: function() {
   return (hex_md5(this.name) == "9b53e667f30cd329dca1ec9e6a83e994")
} } );
  
#### $jsonSchema:
Valide documentos em relação ao esquema JSON fornecido
- { $jsonSchema: <JSON Schema object> }
- {
  $jsonSchema: {
     required: [ "name", "major", "gpa", "address" ],
     properties: {
        name: {
           bsonType: "string",
           description: "must be a string and is required"
        },
        address: {
           bsonType: "object",
           required: [ "zipcode" ],
           properties: {
               "street": { bsonType: "string" },
               "zipcode": { bsonType: "string" }
           }
        }
     }
  }
}
  
### Como verificar regras de validação:  
O método getCollectionInfo é usado para obter informações sobre uma coleção específica em um banco de dados. Ele retorna um documento que descreve várias propriedades da coleção, como seu nome, tamanho, índices existentes, opções de criação e muito mais.
- db.getCollectionInfo({ options })
- db.getCollectionInfos( { name: "contas" } )  

o comando runCommand é usado para executar comandos específicos do MongoDB em um banco de dados. Ele permite executar operações avançadas ou comandos internos que não estão disponíveis diretamente como métodos no shell do MongoDB.
- db.runCommand({ command })
- db.runCommand ( { listCollections: 1, filter: { name: "contas" } } )
  
### Mudar uma regra de validação:
O comando collMod no MongoDB é usado para modificar as opções de uma coleção existente. Ele permite alterar várias propriedades da coleção, como tamanho máximo, número máximo de documentos, índices e muito mais.
- db.runCommand({ collMod: "<nome_da_colecao>", <opcoes> })
- db.runCommand({ collMod: "minhaColecao", size: 100000000, capped: true })

### Níveis de validação:
  No MongoDB, existem diferentes níveis de validação que podem ser aplicados aos documentos em uma coleção. Esses níveis de validação determinam quando e como a validação dos dados ocorre.

Existem três níveis de validação disponíveis:
- Nível de validação estrita (strict): Neste nível, a validação é aplicada durante as operações de gravação (insert/update) e impede a gravação de qualquer documento que não atenda à regra de validação definida. Se um documento não atender aos critérios de validação, um erro será retornado e a gravação será rejeitada. Esse é o nível de validação padrão.
- Nível de validação moderada (moderate): Neste nível, a validação é aplicada durante as operações de gravação (insert/update), mas permite a gravação de documentos que não atendem à regra de validação definida. No entanto, um aviso será gerado para cada documento inválido. A gravação ainda será concluída, mas os documentos inválidos serão marcados como inválidos.
- Nível de validação off: Neste nível, a validação é desativada e nenhum documento é validado durante as operações de gravação. Isso permite que qualquer documento seja inserido ou atualizado na coleção sem restrições de validação.
  
Obs: Lembre-se de que, independentemente do nível de validação definido, a validação no MongoDB ocorre apenas durante as operações de gravação (insert/update). As operações de leitura (query) não aplicam a validação.

É importante considerar cuidadosamente o nível de validação a ser usado com base nos requisitos do seu aplicativo e no equilíbrio entre consistência e flexibilidade dos dados.  
  
### Tratando documentos inválidos:
A opção validationAction é usada para especificar a ação a ser tomada em relação aos documentos que não atendem à regra de validação durante as operações de gravação (insert/update).  
  
- "error": Essa é a ação padrão. Quando um documento não atende à regra de validação, um erro é retornado e a operação de gravação é rejeitada. O documento inválido não é inserido ou atualizado na coleção.
- "warn": Com essa opção, um aviso é gerado para cada documento inválido, mas a operação de gravação é concluída. Os documentos inválidos são inseridos ou atualizados na coleção, mas são marcados como inválidos. O aviso pode ser visualizado nos logs do MongoDB.
- "off": Essa opção desativa a ação de validação. Nenhum erro ou aviso é gerado e os documentos são inseridos ou atualizados na coleção, independentemente de atenderem ou não à regra de validação. É importante ter cuidado ao desativar completamente a validação, pois isso pode permitir a gravação de dados inválidos na coleção.  
  
É importante considerar cuidadosamente a ação de validação a ser usada com base nos requisitos do seu aplicativo e na importância de garantir a integridade dos dados. A opção validationAction permite que você controle como os documentos inválidos são tratados durante as operações de gravação.  
  
## Variáveis:
Para criar uma variável, você pode utilizar o comando let:
- let nome_variavel = $jsonSchema
  
OBS.: Para realizar a criação de uma variável, é necessário utilizar a linha de comando.

Após executar o comando e criar a variável, você pode utilizá-la como um filtro para buscar, modificar e remover documentos das coleções.
  
## Transações ACID:
No MongoDB, as transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade) estão disponíveis desde a versão 4.0 do banco de dados. As transações ACID fornecem uma maneira de garantir a integridade dos dados em operações que envolvem múltiplas coleções ou documentos.

Aqui estão os principais conceitos relacionados às transações ACID no MongoDB:
- Atomicidade: As transações ACID garantem que todas as operações em uma transação sejam tratadas como uma unidade atômica. Isso significa que todas as operações são executadas com sucesso ou nenhuma delas é aplicada. Se uma operação falhar, todas as alterações feitas pela transação são revertidas.
- Consistência: As transações ACID garantem que os dados estejam em um estado consistente antes e depois da transação. As operações dentro de uma transação devem atender às regras de validação definidas e preservar a integridade dos dados.
- Isolamento: O isolamento garante que as operações em uma transação sejam executadas em um ambiente isolado. Isso significa que as alterações feitas por uma transação não são visíveis para outras transações até que a transação seja confirmada.
- Durabilidade: A durabilidade garante que as alterações feitas por uma transação sejam permanentes, mesmo em caso de falha do sistema. Depois que uma transação é confirmada, suas alterações são armazenadas de forma durável no disco e permanecem mesmo em caso de reinicialização do servidor.  
  
Obs: Lembre-se de que nem todas as operações suportam transações ACID, e apenas replicações de conjuntos de réplicas (replica sets) e grupos de servidores (sharded clusters) podem ser usados com transações.    
  
## Dados incorporados VS referências:
No MongoDB, existem duas abordagens principais para modelar relacionamentos entre documentos: dados incorporados (embedded) e referências.
  
- Dados Incorporados (Embedded): Nessa abordagem, os dados relacionados são incorporados diretamente em um único documento. Isso significa que os campos do documento contêm os dados de outros documentos relacionados. Os dados incorporados são adequados quando você tem relacionamentos "um para um" ou "um para poucos" entre entidades.  
- Referências: Nessa abordagem, os documentos relacionados são armazenados separadamente e referenciados uns aos outros por meio de um campo que contém uma referência ao documento relacionado. Esse campo geralmente contém o _id do documento relacionado. As referências são adequadas para relacionamentos "muitos para muitos" ou quando você precisa de uma separação clara entre entidades.
  
A escolha entre dados incorporados e referências depende das características específicas do seu domínio e dos requisitos de consulta e manipulação de dados. Cada abordagem tem suas vantagens e considerações a serem levadas em conta, como desempenho, consistência e escala.  
  
## DBRefs:

DBRefs (Database References) são um mecanismo opcional fornecido pelo MongoDB para modelar relacionamentos entre documentos em diferentes coleções.

Uma DBRef é uma referência a um documento em outra coleção do MongoDB e consiste em três campos principais:

- $ref: O nome da coleção que contém o documento referenciado.
- $id: O valor do _id do documento referenciado.
- $db: O nome do banco de dados (opcional) que contém a coleção referenciada.
  
DBRefs são frequentemente utilizadas para estabelecer relacionamentos "um para muitos" ou "muitos para muitos" entre documentos.
  
Obs: É importante notar que as DBRefs não são uma funcionalidade nativa do MongoDB, mas sim uma convenção de estruturação de dados que pode ser seguida por aplicativos para estabelecer relacionamentos entre documentos. O MongoDB não realiza automaticamente o carregamento ou resolução das DBRefs, sendo necessário que a aplicação realize as consultas adicionais para obter os documentos referenciados, se necessário. 
  
## Dados hierárquicos:  
### Parent References:
db.Pai.insertMany([
  
    {_id:"Colaborador01" , parent:"Supervisor02"},
  
    {_id:"Colaborador02" , parent:"Supervisor02"},
  
    {_id:"Supervisor02", parent:"Gerente"},
  
    {_id:"Supervisor01", parent:"Gerente"},
  
    {_id:"Gerente", parent:"Gerente geral"},
  
    {_id:"Gerente geral", parent: null}
  
])  
  
###  Child references:
db.Filho.insertMany([
    {_id:"Colaborador01" , children:[]},
  
    {_id:"Colaborador02" , children:[]},
  
    {_id:"Supervisor01", children:[]},
  
    {_id:"Supervisor02", children:["Colaborador01", "Colaborador02"]},
  
    {_id:"Gerente", children:["Supervisor01", "Supervisor02"]},
  
    {_id:"Gerente geral", children:["Gerente"]}
  
])  
  
Obs: Enquanto o parent references armazena o "NÓ" e o ID pai, o children reference armazena  o "NÓ" e o ID dos filhos
  
###  Array of ancestors:
Neste padrão, armazenamos em um documento o nó e todos os seus ancestrais.  
  
db.Ancestrais.insertMany([
  
    {_id:"Colaborador01", ancestors:["Gerente geral", "Gerente", "Supervisor02"], parent:"Supervisor02"},
  
    {_id:"Colaborador02", ancestors:["Gerente geral", "Gerente", "Supervisor02"], parent:"Supervisor02"},
  
    {_id:"Supervisor02", ancestors:["Gerente geral", "Gerente"], parent:"Gerente"},
  
    {_id:"Supervisor01", ancestors:["Gerente geral", "Gerente"], parent:"Gerente"},
  
    {_id:"Gerente", ancestors:["Gerente geral"], parent:"Gerente geral"},
  
    {_id:"Gerente geral", ancestors:[], parent:null}
  
])  
  
### Materialized paths:
Neste padrão, armazenamos no documento o nó e o id de seus ancestrais ou o caminho do nó.  
  
db.Materializados.insertMany([
  
    {_id:"Gerente geral", path:null},
  
    {_id:"Gerente", path:"Gerente geral"},
  
    {_id:"Supervisor02", path:"Gerente geral,Gerente"},
  
    {_id:"Supervisor01", path:"Gerente geral,Gerente"},
  
    {_id:"Colaborador01", path:"Gerente geral,Gerente,Supervisor02"},
  
    {_id:"Colaborador02", path:"Gerente geral,Gerente,Supervisor02"}
  
])  
  
## Condicionais:
O MongoDB não possui construções de controle de fluxo, como if e switch, diretamente nas consultas. No entanto, você pode alcançar resultados semelhantes usando as etapas de agregação.

Para simular um if em uma consulta do MongoDB, você pode usar a etapa $cond na agregação. O $cond permite que você avalie uma condição e retorne um valor com base nessa condição. Aqui está um exemplo:
  
db.collection.aggregate([{
  
    $project: {
  
      field: {
  
        $cond: {
  
          if: { $eq: ["$someField", "someValue"] },
  
          then: "Value if true",
  
          else: "Value if false"
  
        }}}}])
  
  Para simular um switch em uma consulta do MongoDB, você pode encadear várias etapas $cond. Cada etapa $cond representa um caso no switch, e você pode fornecer uma condição para cada caso. Aqui está um exemplo:
  
 db.collection.aggregate([{
  
    $project: {
  
      field: {
  
        $switch: {
  
          branches: [
  
            { case: { $eq: ["$someField", "value1"] }, then: "Result 1" },
  
            { case: { $eq: ["$someField", "value2"] }, then: "Result 2" },
  
            { case: { $eq: ["$someField", "value3"] }, then: "Result 3" },
  
            // ...
  
          ],
  
          default: "Default Result"
  
        }}}}])
 
  
  
  
  
  
  
  
  
  
  
  
  ___
#### Links para download:
- Mongo Compass: http://www.mongodb.com
- NoSQLBooster: https://nosqlbooster.com/downloads
