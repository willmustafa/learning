---
layout: default
title: SSL
nav_order: 2
parent: Server
permalink: docs/server/ssl
---

# O que é o certificado SSL?

O SSL (Secure Sockets Layer) é um certificado digital que autentica a identidade do site e possibilita uma conexão criptografada.

Existem vários tipos de SSL, verifique os tipos no site da [Kaspersky](https://www.kaspersky.com.br/resource-center/definitions/what-is-a-ssl-certificate).

## Como obter um certificado grátis?

Você pode utilizar o OpenSSL, mas recomendo utilizar o Cloudflare.

O processo no Cloudflare é simples, faça o registro, redirecione o DNS do domínio para os servidores do Cloudflare, aguarde alguns minutos a horas. Ao ser completado o redirecionamento para o Cloudflare, você pode ir em SSL e ativar a opção flexible, pronto!

Para ativar a opção FULL, você precisará criar as chaves e adicionar em sua hospedagem, veja o passo a passo:

1- No Cloudflare, entre em SSL -> Origin Server
2- Create Certificate
3- Em Hostname coloque o domínio do seu site sem 'www', caso tenha subdomínios, pode adicionar aqui também ou você pode criar um SSL para cada subdomínio
4- Clique em Create
5- Salve os códigos em um local seguro
6- Acesse sua hospedagem e vá em SSL
7- Adicione uma custom SSL keys
8- Copie os códigos gerados pelo Cloudflare
9- No Cloudflare, vá em SSL e ative a opção FULL
10- Pronto!
