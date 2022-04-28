---
layout: default
title: Funções
nav_order: 1
parent: SQL
---

# Funções

Assim como em uma linguagem qualquer, no SQL você também pode criar funções com parâmetros e retornos para serem utilizados em suas queryes.

```
CREATE FUNCTION east_or_west (
	@long DECIMAL(9,6)
)
RETURNS CHAR(4) AS
BEGIN
	DECLARE @return_value CHAR(4);
	SET @return_value = 'same';
    IF (@long > 0.00) SET @return_value = 'east';
    IF (@long < 0.00) SET @return_value = 'west';
 
    RETURN @return_value
END;
```

Agora você pode chamar a função em sua consulta sql.

```
SELECT east_or_west(10.543)
```

No Postgres a variável passada na função é um pouco diferente.

```
CREATE FUNCTION public.teste(IN texto_input text)
    RETURNS pg_tables
    LANGUAGE 'sql'
    LEAKPROOF 
AS $BODY$
SELECT * FROM tabela WHERE texto = texto_input
$BODY$;
```