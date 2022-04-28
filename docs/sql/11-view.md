---
layout: default
title: View
nav_order: 1
parent: SQL
---

# View

Uma VIEW é uma consulta armazenada no banco de dados e ela se comporta como se fosse uma tabela virtual. Ela é utilizada principalmente quando é preciso controlar a segurança do banco, onde algumas informações de uma tabela não podem ser acessadas pelo cliente. Assim, é criada uma tabela intermediária, onde quem a cria é o banco de dados e o cliente acessa apenas a tabela intermediária.

Outro uso é para apresentar os dados sem que o cliente precise criar queryes complicadas.

Uma VIEW é uma query em tempo de execução, ou seja, quando o cliente solicita o acesso a uma view, ela irá executar o código interno e retornará a tabela.

# Materialized View

É uma View em que a query é executada sempre que as tabelas vizualizadas por ela são atualizadas. Ou seja, uma Materialized View é o resultado de uma consulta, o que torna a visualização de dados muito mais rápida, já que as consultas, cálculos, joins, já foram realizados.

## Desvantagens

A escrita no banco de dados fica mais lento, pois é necessário executar a consulta interna da Materialized View toda vez que um dado é inserido ou atualizado.

## Como escolher entre VIEW e MATERIALIZED VIEW?

Depende de qual o uso principal do banco de dados, a maior parte dos acessos será de consultas ou de escritas? Existem muitas alterações de dados?

Se você precisa de desempenho nas buscas pelos dados e não na escrita, utilize Materialized View.

Se você usa o banco muito mais para escrever e editar, utilize View.

## Como criar uma view?

```
CREATE
OR REPLACE VIEW city_a_usa AS SELECT
	city_id,
	city,
	country_id
FROM
	city_a
WHERE
	country_id = 103

```

A criação de uma Materialized View segue oo mesmo princípio, mas no Postgres, existe ainda a linha `WITH DATA` ou `WITH NO DATA`.

```
// Para o postgres utilize
CREATE MATERIALIZED VIEW city_a_usa AS SELECT
	city_id,
	city,
	country_id
FROM
	city_a
WHERE
	country_id = 103
    WITH DATA;

// Ou com WITH NO DATA
CREATE MATERIALIZED VIEW city_a_usa AS SELECT
	city_id,
	city,
	country_id
FROM
	city_a
WHERE
	country_id = 103
    WITH NO DATA;
```

A diferença é que `WITH NO DATA` precisa de um comando para sua atualização, ela não funciona de forma automática como `WITH DATA`.

```
// Comando para atualizar os dados de uma view com WITH NO DATA
REFRESH MATERIALIZED VIEW tabela
```

[Fonte](https://dicasdeprogramacao.com.br/qual-a-diferenca-entre-view-e-materialized-view/)