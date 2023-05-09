# O que é SQL Server:
O SQL Server é um sistema de gerenciamento de banco de dados relacional (SGBD). O SQL Server conta também com uma ferramenta de interface gráfica chamada SQL Server Management Studio, que substitui o uso da ferramenta de linha de comando, tornando o trabalho com o banco de dados mais simples.

## Principais conceitos:
### Basic:
#### Organização da SQL:
- DQL(Linguagem de Consulta de Dados): Define o comando utilizado para que possamos consultar (SELECT) os dados armazenados no banco;
- DML(Linguagem de Manipulação de Dados): Define os comandos utilizados para manipulação de dados no banco (INSERT, UPDATE e DELETE);
- DDL(Linguagem de Definição de Dados): Define os comandos utilizados para criação (CREATE) de tabelas, views, índices, atualização dessas estruturas (ALTER), assim como a remoção (DROP);
- DCL(Linguagem de Controle de Dados):  Define os comandos utilizados para controlar o acesso aos dados do banco, adicionando (GRANT) e removendo (REVOKE) permissões de acesso;
- DTL(Linguagem de Transação de Dados): Define os comandos utilizados para gerenciar as transações executadas no banco de dados, como iniciar (BEGIN) uma transação, confirmá-la (COMMIT) ou desfazê-la (ROLLBACK).

#### Database: 
Banco de dados são onde irão ficar as tabelas para guardar registros
#### Schema: 
Os Schemas são uma coleção de objetos dentro de um determinado database (banco de dados), servem para agrupar objetos no nível de aplicação como também para simplesmente fazer divisões departamentais. Schemas são bastante utilizados em padrões de sistema de banco de dados. São muito importantes para a performance e segurança.
#### Table: 
Tabelas são objetos de banco de dados que contêm todos os dados em um banco de dados. Nas tabelas, os dados são organizados de maneira lógica em um formato de linha-e-coluna semelhante ao de uma planilha. Cada linha representa um registro exclusivo e cada coluna representa um campo no registro.

### Comandos DDL:
#### Create: 
Serve para criar um database/Schema/Table
Exemplos:
- CREATE DATABASE nome do banco de dados;
- CREATE SCHEMA nome do esquema;
- CREATE TABLE database_name  schema_name"table_name (
    pk_column data_type PRIMARY KEY,
    column_1 data_type NOT NULL,
    column_2 data_type,
    ...,
    table_constraints
);

#### Alter: 
Serve para alterar um database/Schema/Table
Exemplos:
- ALTER DATABASE database_name MODIFY NAME = new_database_name // 
- ALTER SCHEMA schema_name   
   TRANSFER  <entity_type> ::  securable_name ; 
- ALTER TABLE table_name ADD column_name {datatype};

#### Drop: 
Serve para apagar um database/Schema/Table
Exemplos:
- DROP DATABASE database_name;
- DROP SCHEMA schema_name;
- DROP TABLE table_name;


### Comandos DML:
#### Insert: 
Usado para inserir novos registros na tabela
- INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

#### Update: 
Usada para modificar os registros existentes em uma tabela
- UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

#### Delete:
Usado para deletar tabelas e colunas
- DELETE FROM table_name WHERE condition;

### Comandos DQL:
#### SELECT: 
O comando SELECT permite recuperar os dados de um objeto do banco de dados, como uma tabela, view e, em alguns casos, uma stored procedure (alguns bancos de dados permitem a criação de procedimentos que retornam valor).
- SELECT <lista_de_campos>
FROM <nome_da_tabela></nome_da_tabela></lista_de_campos>

#### Where: 
A cláusula Where permite ao comando SQL passar condições de filtragem
- SELECT CODIGO, NOME FROM CLIENTES
WHERE UF = ‘RJ’ OR (UF = ‘SP’ AND ATIVO = ‘N’)

#### Like:
O operador LIKE é empregado nas situações em que usamos como base para realizar pesquisas (ou filtros) as colunas que estão no formato caractere
Possuí o "NOT LIKE"
- SELECT CODIGO, NOME FROM CLIENTES
 WHERE NOME LIKE ‘MARIA%’

#### Order by:
A ordenação pode ser definida com o comando ORDER BY. Assim como no comando WHERE, o campo de ordenação não precisa estar listado como campo de visualização. Obs: A utilização da palavra DESC garante a ordenação invertida
- SELECT CODIGO, NOME FROM CLIENTES
ORDER BY NOME
SELECT CODIGO, NOME FROM CLIENTES
ORDER BY UF, NOME
- SELECT CODIGO, NOME FROM CLIENTES
ORDER BY NOME DESC
SELECT CODIGO, NOME FROM CLIENTES
ORDER BY UF DESC

#### Agreggation:
Existem 5 funções para agrupar
- AVG: Retorna a média do campo especificado
- SELECT AVG(VALOR) FROM PEDIDOS
- MIN/MAX/SUM: Respectivamente retorna o menor valor, o maior e o somatório de um grupo de registros:
- SELECT MIN(VALOR) FROM PEDIDOS
- SELECT MAX(VALOR) FROM PEDIDOS
- SELECT AVG(VALOR) FROM PEDIDOS
- COUNT: Retorna a quantidade de itens da seleção

#### Group by:
Um poderoso recurso do comando SELECT é o parâmetro GROUPY BY. Através dele podemos retornar informações agrupadas de um conjunto de registros, estabelecendo uma condição de agrupamento
- SELECT CODCLIENTE, MAX(VALOR)
FROM PEDIDOS
GROUP BY CODCLIENTE

#### Having:
Através do comando HAVING podemos filtrar a cláusula GROUP BY
- SELECT CODCLIENTE, COUNT(*)
FROM PEDIDOS
GROUPY BY CODCLIENTE
HAVING COUNT(*) >= 2
- SELECT CODCLIENTE, COUNT(*)
FROM PEDIDOS
WHERE DATA > ‘06/10/2002’
GROUPY BY CODCLIENTE
HAVING COUNT(*) >= 2

#### Join:
Utilizado para junar 2 tabelas na hora da visualização do SELECT e possuem 5 tipos de join:
- (INNER) JOIN: Retorna registros que possuem valores correspondentes em ambas as tabelas
- LEFT (OUTER) JOIN: Retorna todos os registros da tabela da esquerda e os registros correspondentes da tabela da direita
- RIGHT (OUTER) JOIN: Retorna todos os registros da tabela da direita e os registros correspondentes da tabela da esquerda
- FULL (OUTER) JOIN: Retorna todos os registros quando há uma correspondência na tabela esquerda ou direita
- CROSS JOIN: A cláusula CROSS JOIN retorna todas as linhas das tabelas por cruzamento, ou seja, para cada linha da tabela esquerda queremos todos os linhas da tabelas direita ou vice-versa.

Exemplos em sequência:
- SELECT <select_list>
FROM Tabela A
INNER JOIN Tabela B
ON A.Key = B.Key
- SELECT <select_list>
FROM Tabela A
LEFT JOIN Tabela B
ON A.Key = B.Key
- SELECT <select_list>
FROM Tabela A
RIGHT JOIN Tabela B
ON A.Key = B.Key
- SELECT <select_list>
FROM Tabela A
FULL JOIN Tabela B
ON A.Key = B.Key
- SELECT <select_list>
FROM Tabela A
CROSS JOIN Tabela B

#### Union:
Existe ainda uma segunda forma de juntar tabelas com o comando SELECT. Através do parâmetro UNION, é possível colar o conteúdo de duas tabelas. Por default, os registros duplicados são eliminados na cláusula UNION. Para incluir todos os registros, independente de duplicidade, utilize a palavra ALL
- SELECT CODIGO, NOME FROM CLIENTES
UNION
SELECT CODIGO. NOME FROM FUNCIONARIOS
- SELECT CODIGO, NOME FROM CLIENTES
UNION ALL
SELECT CODIGO, NOME FROM FUNCIONARIOS




#### Subqueries
Subqueries, ou subconsultas, em SQL Server são consultas internas que são incorporadas em uma consulta externa. As subconsultas são usadas para filtrar ou recuperar dados de uma tabela ou conjunto de tabelas, que é então usado como entrada para uma consulta externa.

As subconsultas em SQL Server podem ser usadas em várias cláusulas da consulta, como SELECT, FROM, WHERE, HAVING e JOIN. O resultado da subconsulta é usado como entrada para a consulta externa, que pode então ser usada para filtrar ou selecionar dados de outras tabelas.
- SELECT CustomerID, CompanyName
FROM Customers
WHERE CustomerID IN (
    SELECT DISTINCT CustomerID
    FROM Orders
    WHERE ShippedDate IS NULL
)


### T-SQL:
A linguagem Transact-SQL é uma extensão ao padrão SQL-92, sendo a linguagem utilizada por desenvolvedores na construção de aplicações que manipulam dados mantidos no SQL Server. Seus comandos podem ser classificados em quatro grupos, de acordo com sua função: DML (Linguagem de Manipulação de Dados), DDL (Linguagem de Definição de Dados), DCL (Linguagem de Controle de Dados) e DTL (Linguagem de Transação de Dados). Além dessas categorias, podemos ter também uma relacionada à consulta dos dados (DQL – Linguagem de Consulta de Dados), que possui apenas o comando SELECT. Entretanto, é mais comum encontrar esse comando como parte da DML em conjunto com os demais comandos de manipulação: INSERT, UPDATE e DELETE.

#### Identity:
O comando IDENTITY é utilizado para determinar que uma coluna da tabela será automaticamente incrementada quando um valor novo é inserido (esse campo não aceita valores nulos). Todas as tabelas possuem uma coluna ou um conjunto de colunas que identificam a linha: a primary key.
- CREATE TABLE MyTable
(
    ID INT IDENTITY(1,1) PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
)

### Function
Em SQL Server, uma função é um objeto de banco de dados que pode ser usado para encapsular uma lógica específica e ser reutilizada em diferentes partes do código SQL. As funções podem aceitar argumentos de entrada, executar operações de lógica e retornar um valor de saída.

Um exemplo de uso de função em SQL Server é para retornar a idade de uma pessoa a partir de sua data de nascimento. Você pode criar uma função chamada "GetAge" que recebe como entrada a data de nascimento e retorna a idade em anos. Aqui está um exemplo de como criar e usar uma função GetAge em SQL Server:
- CREATE FUNCTION GetAge (@birthdate DATE)
RETURNS INT
AS
BEGIN
    DECLARE @age INT
    SET @age = DATEDIFF(YEAR, @birthdate, GETDATE())
    IF (MONTH(@birthdate) > MONTH(GETDATE()) OR (MONTH(@birthdate) = MONTH(GETDATE()) AND DAY(@birthdate) > DAY(GETDATE())))
        SET @age = @age - 1
    RETURN @age
END
#### Funções de string:
- CONCAT: Esta função concatena duas ou mais cadeias de caracteres em uma única cadeia de caracteres.
- SUBSTRING: Esta função retorna uma parte de uma cadeia de caracteres, com base na posição inicial e no comprimento especificados.
- CHARINDEX: Esta função retorna a posição da primeira ocorrência de uma cadeia de caracteres especificada dentro de outra cadeia de caracteres.
- REPLACE: Esta função substitui todas as ocorrências de uma cadeia de caracteres especificada em uma cadeia de caracteres por outra cadeia de caracteres.
- UPPER/LOWER: Essas funções convertem todos os caracteres em uma cadeia de caracteres em maiúsculas ou minúsculas, respectivamente.
- LTRIM/RTRIM: Essas funções removem os espaços em branco à esquerda ou à direita de uma cadeia de caracteres, respectivamente.

#### Funções de data:
- GETDATE(): Esta função retorna a data e hora atuais do servidor.
Exemplo: 'SELECT GETDATE()' retornaria algo como '2023-05-09 12:34:56.789'
- DATEPART(): Esta função retorna uma parte específica de uma data ou hora, como ano, mês ou dia.
Exemplo: 'SELECT DATEPART(year, '2023-05-09')' retornaria '2023'
- YEAR(): Esta função retorna o ano de uma data.
Exemplo: 'SELECT YEAR('2023-05-09')' retornaria '2023'
- MONTH(): Esta função retorna o mês de uma data.
Exemplo: 'SELECT MONTH('2023-05-09')' retornaria '5'
- DAY(): Esta função retorna o dia do mês de uma data.
Exemplo: 'SELECT DAY('2023-05-09')' retornaria '9'
- DATEADD(): Esta função adiciona ou subtrai uma quantidade especificada de tempo a uma data.
Exemplo: 'SELECT DATEADD(day, 7, '2023-05-09')' retornaria '2023-05-16'
- DATEDIFF(): Esta função retorna a diferença entre duas datas em uma unidade específica, como dias, semanas ou meses.
Exemplo: 'SELECT DATEDIFF(day, '2023-05-01', '2023-05-09')' retornaria '8'

#### Funções númericas:
- SUM: Esta função retorna a soma dos valores em uma coluna.
- AVG: Esta função retorna a média dos valores em uma coluna.
- MAX: Esta função retorna o valor máximo em uma coluna.
- MIN: Esta função retorna o valor mínimo em uma coluna.
- COUNT: Esta função retorna o número de linhas em uma tabela que atendem a uma condição especificada.
- ROUND: Esta função arredonda um número para um número especificado de casas decimais.



### Stored procedures:

### Índices

### Views

### Triggers:
