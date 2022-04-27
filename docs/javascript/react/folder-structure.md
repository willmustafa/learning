---
layout: default
title: Folder Structure
nav_order: 2
parent: React
grand_parent: Javascript
---

# Folder Structure

Aqui vai uma sugestão de como estruturar suas pastas no react.

src
|-Assets
|--|--Styles
|--|--Images
|-Components
|--|--Cards
|-Config
|-Layouts
|--|--Footer
|--|--Header
|--|--Main
|-Middleware
|-Pages
|--|--Dashboard
|-Routes
|-Services
|--|--Actions
|--|--Reducers
|--|--Constants
|--|--Utils

## Assets

Pasta para as imagens, estilos globais, etc.

## Components

Componentes de UI como botões, modais, inputs, etc.

Também é bom inserir um arquivo de teste junto dos componentes para automatizar os testes futuros.

## Config

Arquivos de configuração do [config-js](https://www.npmjs.com/package/config-js).

## Layout

Layouts globais, como o header, footer, navbars, ets.

## Middleware

Efeitos e outros middlewares.

## Pages

Páginas são os componentes que são puxados pelo router, podem ser inseridas dentro de pastas separadas para que se adicione o `.jsx` e o `.css`.

## Routes

Pasta para a configuração das rotas privadas, protegidas, públicas, etc.

## Services

Utilizada quando se utiliza [redux](https://redux.js.org/)