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

##### Where: 
A cláusula Where permite ao comando SQL passar condições de filtragem
- SELECT CODIGO, NOME FROM CLIENTES
WHERE UF = ‘RJ’ OR (UF = ‘SP’ AND ATIVO = ‘N’)

##### Like:
O operador LIKE é empregado nas situações em que usamos como base para realizar pesquisas (ou filtros) as colunas que estão no formato caractere
Possuí o "NOT LIKE"
- SELECT CODIGO, NOME FROM CLIENTES
 WHERE NOME LIKE ‘MARIA%’

##### Order by:
A ordenação pode ser definida com o comando ORDER BY. Assim como no comando WHERE, o campo de ordenação não precisa estar listado como campo de visualização. Obs: A utilização da palavra DESC garante a ordenação invertida
- SELECT CODIGO, NOME FROM CLIENTES
ORDER BY NOME
SELECT CODIGO, NOME FROM CLIENTES
ORDER BY UF, NOME
- SELECT CODIGO, NOME FROM CLIENTES
ORDER BY NOME DESC
SELECT CODIGO, NOME FROM CLIENTES
ORDER BY UF DESC

##### Agreggation:
Existem 5 funções para agrupar
- AVG: Retorna a média do campo especificado
- SELECT AVG(VALOR) FROM PEDIDOS
- MIN/MAX/SUM: Respectivamente retorna o menor valor, o maior e o somatório de um grupo de registros:
- SELECT MIN(VALOR) FROM PEDIDOS
- SELECT MAX(VALOR) FROM PEDIDOS
- SELECT AVG(VALOR) FROM PEDIDOS
- COUNT: Retorna a quantidade de itens da seleção

##### Group by:
Um poderoso recurso do comando SELECT é o parâmetro GROUPY BY. Através dele podemos retornar informações agrupadas de um conjunto de registros, estabelecendo uma condição de agrupamento
- SELECT CODCLIENTE, MAX(VALOR)
FROM PEDIDOS
GROUP BY CODCLIENTE

##### Having:
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

##### Join:
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

##### Union:
Existe ainda uma segunda forma de juntar tabelas com o comando SELECT. Através do parâmetro UNION, é possível colar o conteúdo de duas tabelas. Por default, os registros duplicados são eliminados na cláusula UNION. Para incluir todos os registros, independente de duplicidade, utilize a palavra ALL
- SELECT CODIGO, NOME FROM CLIENTES
UNION
SELECT CODIGO. NOME FROM FUNCIONARIOS
- SELECT CODIGO, NOME FROM CLIENTES
UNION ALL
SELECT CODIGO, NOME FROM FUNCIONARIOS





### Subqueries

### Function

### Stored procedures:

### Índices

### Views

### T-SQL

### Triggers:

###

###

###
