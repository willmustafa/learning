---
layout: default
title: Atividade 3 - Teste Funcional
nav_order: 15
parent: Teste de Software
grand_parent: Engenharia de Software
---

# Atividade 3 - Teste Funcional

Aluno: Willian Felipe Mustafa

Disciplina: Teste de Software

## 1.1 Descrição do Problema

Um hospital fornece no levantamento de requisitos, as informações para a resolução
do problema de registro de pacientes na entrada de um hospital privado. A ferramenta
auxiliará no controle dos pacientes que são atendidos no cotidiano. Realize um teste de
caixa-preta usando o critério de classes de equivalência e um conjunto de casos de teste
para o módulo da especificação fornecida a seguir:

- Em primeiro momento, o usuário do sistema, fornece ao programa o nome do
paciente a ser atendido. O nome não pode conter números e pode conter no
máximo 50 caracteres.
- A segunda entrada fornecida ao sistema é o CPF do paciente. O CPF não pode
ser maior que 11 caracteres.
- Um outro item fornecido ao sistema é a idade do paciente. A idade necessariamente
é um valor inteiro maior que zero e menor 100. Para ocasionais fins estatísticos
o sistema classifica a idade dos pacientes da seguinte forma: de 0 - 3 anos como
bebês, de 4 - 12 como crian ̧cas, de 13 - 18 como adolescentes, de 19 -59 como
adultos e 60 - 99 como idosos.
- Em seguida, se existente, o plano de saúde do paciente também é fornecido. Planos
privados são classificados como aceitos e planos públicos como não aceitos, dadas
as circunstâncias burocráticas do local.
- Por último, um texto descrevendo os sintomas do paciente é fornecido ao programa.
O programa aceita somente texto maiores que 20 caracteres e menores que 200.

Identificar as entradas e saídas do programa. Gerar a tabela com as classes de
equivalência. Gerar os casos de teste para cada classe de equivalência definida.

## 2.0 Classe de Equivalência

### 2.0.1 Primeira entrada

- Em primeiro momento, o usuário do sistema, fornece ao programa o nome do
paciente a ser atendido. O nome não pode conter números e pode conter no
máximo 50 caracteres.

| Variável de Entrada | CE Válidas         | CE Inválidas   |
|---------------------|--------------------|----------------|
| Tamanho da entrada  | T <= 50            | T > 50         |
| Conteúdo da entrada | Não conter números | Conter Números |

### 2.0.2 Segunda Entrada

- A segunda entrada fornecida ao sistema é o CPF do paciente. O CPF não pode
ser maior que 11 caracteres.

| Variável de Entrada | CE Válidas | CE Inválidas |
|---------------------|------------|--------------|
| Tamanho da entrada  | T <= 11    | T > 11       |

### 2.0.3 Terceira Entrada

- Um outro item fornecido ao sistema é a idade do paciente. A idade necessariamente
é um valor inteiro maior que zero e menor 100. Para ocasionais fins estatísticos
o sistema classifica a idade dos pacientes da seguinte forma: de 0 - 3 anos como
bebês, de 4 - 12 como crianças, de 13 - 18 como adolescentes, de 19 -59 como
adultos e 60 - 99 como idosos.

| Variável de Entrada    | CE Válidas               | CE Inválidas                  |
|------------------------|--------------------------|-------------------------------|
| Tamanho da entrada     | 0 <= T <= 100            | T > 100 && T < 0              |
| Classificação da idade | Faixa etária pertencente | Faixa etária não classificada |

### 2.0.4 Quarta Entrada

- Em seguida, se existente, o plano de saúde do paciente também é fornecido. Planos
privados são classificados como aceitos e planos públicos como não aceitos, dadas
as circunstâncias burocráticas do local.

| Variável de Entrada    | CE Válidas    | CE Inválidas  |
|------------------------|---------------|---------------|
| Possuí Plano Privado?  | SIM           | Não           |

### 2.0.5 Quinta Entrada

- Por último, um texto descrevendo os sintomas do paciente é fornecido ao programa.
O programa aceita somente texto maiores que 20 caracteres e menores que 200.

| Variável de Entrada | CE Válidas     | CE Inválidas      |
|---------------------|----------------|-------------------|
| Tamanho da entrada  | 20 >= T <= 200 | T < 20 && T > 200 |

## 2.1 Conjunto de testes

### 2.1.1 Primeira entrada

| T                                                 | W | C | O | Output                                    |
|---------------------------------------------------|---|---|---|-------------------------------------------|
| Uma frase grande com mais de cinquenta caracteres |   |   |   | Insira um nome com menos de 50 caracteres |
| Carlos2                                           |   |   |   | O nome não pode conter números            |

### 2.1.2 Segunda entrada

| T            | W | C | O | Output                                    |
|--------------|---|---|---|-------------------------------------------|
| 123456789123 |   |   |   | O CPF precisa ter menos que 11 caracteres |

### 2.1.3 Terceira entrada

| T   | W | C | O | Output                            |
|-----|---|---|---|-----------------------------------|
| -1  |   |   |   | A idade precisa ser entre 0 a 100 |
| 120 |   |   |   | A idade precisa ser entre 0 a 100 |
| 40  |   |   |   | adulto                            |

### 2.1.4 Quarta Entrada

| T | W | C | O | Output                     |
|---|---|---|---|----------------------------|
|   |   |   | N | Plano público não é aceito |
|   |   |   | S | Plano privado aceito       |

### 2.1.5 Quinta Entrada

| T                                  | W | C | O | Output                                                          |
|------------------------------------|---|---|---|-----------------------------------------------------------------|
| Texto                              |   |   |   | O texto é muito pequeno, precisa conter mais que 20 caracteres  |
| (texto com mais de 200 caracteres) |   |   |   | O texto é muito grande, precisa conter menos que 200 caracteres |