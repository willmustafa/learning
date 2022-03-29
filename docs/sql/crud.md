---
layout: default
title: CRUD
nav_order: 2
parent: SQL
permalink: docs/sql/crud
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

Para ler um dado, deve-se utilizar **SELECT**, você também pode utilizá-lo com condicionantes como **WHERE**.

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