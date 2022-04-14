---
layout: default
title: Best Practices - CSS
nav_order: 3
parent: HTML e CSS
permalink: docs/htmlcss/bestpractices-css
---

# Melhores práticas para CSS

## Estrutura

Agrupe o código seguindo o ITCSS (Inverted Triangle CSS), que agrupa e organiza os estilos em 8 camadas:

- Settings: as variáveis do projeto
- Tools: Mixins e funções
- Generic: Base zero (normalize, resets)
- Base ou Elements: Elementos HTML sem classe
- Objects: Seletores de classes comuns
- Components: Estilos específicos de componentes, como footer, header, etc
- Utilities: Classes imutáveis (com propriedades !important)

## BEM

Block Element Modifier, sempre recomendado mas nunca vejo realmente em ação.

Basicamente é a imposição de um método de nomeação de classes como pode ser visto [aqui](http://getbem.com/naming/)

## Dependência

Não utilize estilos dependentes de outros estilos ou de uma cadeia, apenas em casos isolados.

```
// Good
.context {
  border: 1rem solid #ccc;
}
.aside--context {
  padding-bottom: 3rem;
}

// Bad
.context {
  border: 1rem solid #ccc;
  .aside {
    padding-bottom: 3rem;
  }
}
```

## Nomenclatura

Nomeie seletores de acordo com seu papel e não semanticamente. Isso garante que caso um elemento mude de cor, por exemplo, a classe ainda faça sentido.

```
// Good
.title-primary {
  font-family: 'Helvetica';
  font-size: 2rem;
  color: black;
}

// Bad
.title-black {
  font-family: 'Helvetica';
  font-size: 2rem;
  color: black;
}

// Good
@border-primary: 1rem solid green;

// Bad
@green-border: 1rem solid green;
```

## Dimensões e tamanhos

### Unidades

- Use `px` para bordas
- Use `sem unidade` para altura de linha
- Use `em` para media queries
- Use `rem` para todo o resto (fonte, espaçamento, etc)
- Use `%`, `vh`, `vw` para colunas, width, etc

## Z-index

Use variáveis ou mapas para organizar z-index, nomeados semanticamente, como `z-index-modal`. Valores devem ser idealmente sequenciais, como `1, 2, 3, 4` e não devem ser arbitrários como `9999` ou ter `!important`.

[Fonte: Punkave](https://github.com/punkave/best-practices/blob/main/css.md)