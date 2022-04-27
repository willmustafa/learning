---
layout: default
title: Data e Hora
nav_order: 10
parent: Javascript
---

# Data e Hora

O Javascript é um pouco complicado para lidar com data e hora, por isso muitos utilizam o package `moment.js` para lidar com formatação, cálculos, etc.

## Mas como fazer sem o moment.js?

Tudo começa com a classe `new Date()`:

```
let hoje = new Date()

let diaEspecifico = new Date('2022-03-27')

```

Para inserir a data específica, ela precisa estar em um desses formatos:

- YYYY-MM-DD (`2022-03-27`)
- MMM DD YYYY (`Mar 27 2022`)
- DD MMM YYYY (`27 Mar 2022`)
- MM/DD/YYYY (`03/27/2022`)

## As variáveis de tempo

Praticamente toda linguagem segue o mesmo padrão de nomeação das variáveis de tempo:

- YYYY: ano com quatro dígitos;
- MM: mês;
- DD: dia;
- T: indicação de início das horas;
- HH: horas;
- mm: minutos;
- ss: segundos;
- s: milissegundos;
- TZD: time zone, que corresponde a +hh:mm ou -hh:mm.

## Formatando uma data

Como a classe `new Date()` irá gerar a data completa, com time zone, milissegundos, etc, você precisará limpar e separar para conseguir formatar para o que deseja.

```
const today = new Date();
const yyyy = today.getFullYear();
let mm = today.getMonth() + 1; // Months start at 0!
let dd = today.getDate();

if (dd < 10) dd = '0' + dd;
if (mm < 10) mm = '0' + mm;

const today = dd + '/' + mm + '/' + yyyy;
```

Esse era o modo antigo para se formatar uma data, mas para novos navegadores, é possível utilizar `.toLocaleString()` ou ainda mais específico `.toLocaleDateString('pt-BR')`:

```
const hoje = new Date()
console.log(hoje.toLocaleDateString('pt-BR'))

// 27/03/2022
```