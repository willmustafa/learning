---
layout: default
title: Insert
nav_order: 5
parent: SQL
---

# Insert

O comando `INSERT INTO` é utilizado para adicionar linhas ao banco de dados, simplesmente nomeando as colunas e os valores desejados:

```
INSERT INTO frutas (nome) VALUES ("laranja")
```

Mas isso pode ficar complicado quando é necessário fazer inserts junto com select, joins, condições de existência, etc.

## INSERT com FOREIGN KEY

Quando uma tabela possui uma chave externa, é preciso dar um SELECT em seu valor para inseri-lo.

```
INSERT INTO comidas (nome, vegetal_principal) VALUES (
    "salada de batata",
    SELECT id FROM vegetais WHERE vegetal = 'batata'
)
```

Assim, você linka os dados das tabelas e economiza espaço em disco.

## INSERT com ON CONFLICT

Quando está inserindo todos valores de uma linha, é possível adicionar o comando `ON CONFLICT`, que dará 2 alternativas para caso encontre os mesmos dados já inseridos, sendo eles o `DO NOTHING` e `UPDATE`. - Este comando funciona para o Postgres.

## INSERT com valores já existentes

Quando se faz um web scrapper, muitas vezes os valores dos produtos não se alteraram desde a última consulta, por isso, você pode não querer inserir essa mesma informação novamente no banco de dados, para isso, é preciso combinar o comando `INSERT INTO` com `SELECT`:

```
INSERT INTO tabela (coluna1, coluna2, coluna3)
SELECT * FROM (
    SELECT valor1, valor2, valor3
) AS temp
WHERE NOT EXISTS (
    SELECT (coluna2, coluna3) FROM tabela WHERE coluna2 = valor2 AND coluna3 = valor3
) LIMIT 1
```

Exemplo de uso:

```
INSERT INTO historico (link, titulo, pix_price, marca_id, modelo_id, loja)
SELECT * FROM (SELECT 'https://www.kabum.com.br/produto/133028/placa-de-video-asus-rog-strix-nvidia-geforce-rtx-3090-24gb-gddr6-rog-strix-rtx3090-o24g-white', 
			   'Placa de Vídeo Asus Rog Strix NVIDIA GeForce RTX 3090, 24GB, GDDR6 - ROG-STRIX-RTX3090-O24G-WHITE', 
			   19999.90,
			  3,
			  2,
			  'kabum') AS tmp
WHERE NOT EXISTS (
    SELECT (link, titulo, pix_price, marca_id, modelo_id, loja) FROM historico WHERE link = 'https://www.kabum.com.br/produto/133028/placa-de-video-asus-rog-strix-nvidia-geforce-rtx-3090-24gb-gddr6-rog-strix-rtx3090-o24g-white'
	AND titulo = 'Placa de Vídeo Asus Rog Strix NVIDIA GeForce RTX 3090, 24GB, GDDR6 - ROG-STRIX-RTX3090-O24G-WHITE' 
	AND pix_price = 19999.90
	AND marca_id = 3
	AND modelo_id = 2
	AND loja = 'kabum'
) LIMIT 1;
```

