---
layout: default
title: CRUD
nav_order: 3
parent: SQL
---

# CRUD (Create, Read, Update, Delete) 

O CRUD é um acrônimo das 4 operações básicas de um SQL, Criar, Ler, Atualizar e Deletar.
Segue abaixo como utilizá-los:

## CREATE

**CREATE** é justamente o termo usado para criar tabelas, esquemas, triggers, index, etc.
O mais utilizado seria justamente o de criar tabelas e esquemas.

```
// Criar um esquema chamado MERCADO
CREATE SCHEMA mercado;

// Criar tabela CLIENTES no esquema mercado com as colunas ID e NOME
CREATE TABLE mercado.clientes (
    id INT PRIMARY KEY,
    nome VARCHAR(200) NOT NULL
)
```

## READ

Para ler um dado, deve-se utilizar **SELECT**, você também pode utilizá-lo com condicionantes como **WHERE** e **BETWEEN**.

```
// Seleciona os dados de toda a tabela
SELECT * FROM clientes;

// Seleciona o id do cliente com nome Willian
SELECT id FROM clientes WHERE nome = 'Willian'
```

## UPDATE

Para atualizar uma linha no banco de dados, utilizamos **UPDATE**;

```
// Muda o nome do cliente GABRIEL no ID = 2 da tabela CLIENTES
UPDATE clientes SET nome = 'Gabriel' WHERE id = 2
```

## DELETE

O comando **DELETE** pode ser usado para apagar uma linha ou todo o conteúdo da tabela.

```
// Deleta a linha onde o nome é GABRIEL
DELETE FROM clientes WHERE nome = 'Gabriel'

// Deleta todo o conteúdo da tabela 
DELETE FROM clientes

*Esse comando pode dar erro de SAFE MODE, caso não queira desativar o modo seguro do banco de dados, utilize a condicional WHERE com uma condição genérica como WHERE id > 0
```

## Simples que pode complicar

Aparentemente é uma tarefa simples utilizar um banco de dados, correto? Errado!

Para pequenas aplicações, sem conexões entre tabelas ou iterações, o CRUD é realmente simples, SELECT, DELETE, etc. O problema é quando o sistema cresce, tabelas possuem diversas foreign keys ou a consulta depende de multiplos parâmetros, dispostos em multiplas tabelas e o retorno deve ser uma combinação de colunas entre tabelas. Para isso, é necessário utilizar diversas outras medidas e combinações para resolver o problema.