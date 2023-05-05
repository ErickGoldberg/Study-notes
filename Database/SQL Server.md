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
#### Create: Serve para criar um database/Schema/Table
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

#### Alter: Serve para alterar um database/Schema/Table
Exemplos:
- ALTER DATABASE database_name MODIFY NAME = new_database_name // 
- ALTER SCHEMA schema_name   
   TRANSFER  <entity_type> ::  securable_name ; 
- ALTER TABLE table_name ADD column_name {datatype};

#### Drop: Serve para apagar um database/Schema/Table
Exemplos:
- DROP DATABASE database_name;
- DROP SCHEMA schema_name;
- DROP TABLE table_name;


### Comandos DML:
#### Insert: usado para inserir novos registros na tabela
- INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

#### Update: Usada para modificar os registros existentes em uma tabela
- UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

#### Delete: Usado para deletar tabelas e colunas
- DELETE FROM table_name WHERE condition;

### Comandos DQL:
#### SELECT:

##### Where:

##### Order by:

##### Group by:

##### Having:

##### Agreggation:
SUM, AVG, MAX, MIN

##### Join:

##### Union:

##### Subqueries




### Function

### Stored procedures:

### Índices

### Views

### T-SQL

### Triggers:

###

###

###
