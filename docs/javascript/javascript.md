---
layout: default
title: Javascript
nav_order: 4
has_children: true
permalink: docs/javascript
---

# Javascript
{: .no_toc }

O JavaScript, ou JS, é uma linguagem leve e simples de se implementar. Sua simplicidade de aprendizado para implementar em projetos simples a complicados são refletidos na quantidade de usuários utilizando-o. Segundo o [StackOverflow](https://insights.stackoverflow.com/survey/2020#technology-programming-scripting-and-markup-languages-all-respondents), o Javascript é utilizado por 67,7% dos programadores ficando muito a frente de outras linguagens como Java (40,2%) e C# (31,4%). Não confunda **Java** com **Javascript**, são linguagens diferentes.

Ele é muito utilizado para dar dinamismo para páginas web, fazendo adição de classes a um elemento, validando um form, mudando informações na página conforme a escolha do usuário, etc. Mas alguns frameworks como Angular e React abriram um novo leque de aplicações no front-end usando javascript. No back-end, a implementação do nodejs tornou o javascript uma linguagem poderosa e leve para diversas funcionalidades em servidores.

Após se tornar popular a linguagem passou a evoluir seguindo algumas padronizações segundo o Ecma International (European Computer Manufacturers Association), trazendo versões ao javascript com a sigla ECMAScript ou ES#.

## Meus projetos usando Javascript

Aqui estão alguns repositórios que criei utilizando javascript:

### [Calculadora de Investimentos](https://github.com/willmustafa/Calculadora-Investimentos)
![](https://github.com/willmustafa/Calculadora-Investimentos/raw/main/images/screenshot.png?raw=true)

Calculadora de juros compostos utilizando 3 perguntas simples para o usuário, podendo escolher entre investimento único, aplicações mensais e aposentadoria. Neste projeto o javascript é utilizado para o dinamismo na troca de páginas, na validação dos dados e no cálculo final.

### [Money Controle Financeiro](https://github.com/willmustafa/money-controle-financeiro)
![](https://github.com/willmustafa/money-controle-financeiro/raw/master/resources/planilha.png?raw=true)

Planilha do Google Sheets com integração com uma interface HTML para inserção dos dados na planilha através do Google App Scripts. O javascript é responsável pela validação, requisições e inserção dos dados.

### [Valor dos Produtos no Mercado - WebScrapping](https://github.com/willmustafa/ValorMercado-WebScraping)

Nesse projeto, o usuário passa uma série de produtos ou links de supermercados para fazer a coleta de dados. As informações coletadas são então destrinchadas e inseridas em um banco de dados PostgreSQL, onde pode ser consultadas futuramente. Esse projeto utiliza o NodeJs e o Puppeteer para fazer a coleta de dados. Front-end criado com React.js.

### Monitora GPU

Projeto visando o monitoramento dos preços das placas de vídeo nas principais lojas de informática do Brasil. Além disso, disponibilizar uma API com acesso ao banco de dados dos preços, variações, benchmarks, relação custo/benefício, variação comparada ao dólar, etc.

### [Louvre Collection - WebScrapping e Data Analysis](https://github.com/willmustafa/LouvreCollection-DataAnalysis)

Projeto para coletar os dados de todas as obras de arte na coleção do Museu do Louvre. Com posse das informações cedidas pelo web scrapping no site do museu, o projeto visa criar uma análise de dados sobre as artes como: o uso de cores em relação ao ano da pintura, posseções de artes e contestações por outros países, etc.

## [NagaStudios - VUE.js](https://github.com/willmustafa/NagaStudio-VUE)

Site de teste para aprendizado no framework Vue.js. Acesse o site no link [https://nagastudio.pages.dev/](https://nagastudio.pages.dev/)

## [Thaila Nagazawa - Vue.js com Wordpress API](https://thailanagazawa.com.br/)

Site que utiliza o framework Vue.js e o Wordpress API para as postagens. Por limitação do servidor de hospedagem, o Wordpress foi instalado em um subdiretório e o site principal ficou com apenas o Vue (que faz a coleta de dados através da API do wordpress no subdiretório), melhorando a performance do site.