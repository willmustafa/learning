---
layout: default
title: Web Scrapping
nav_order: 2
parent: Node
grand_parent: Javascript
---

# Puppeteer

O [puppeteer](https://github.com/puppeteer/puppeteer) é mantido pelo Google e tem mais capacidades que o cheerio.

```
npm i puppeteer
```

Para iniciar use:

```
    const browser = await puppeteer.launch({
        headless: true, // false faz com que ele mostre a janela
        defaultViewport: {
            width: 1800,
            height: 800,
            deviceScaleFactor: 1
        }
    });
    const page = await browser.newPage();
    await page.goto('http://exemplo.com.br');
  
    
    await browser.close();
```

O `defaultViewport` define o tamanho do browser que será usado, utilize um valor alto para que o site não entre pelo modo mobile.

## Selecionando algo

Para ler alguma informação na tela, utilize `$eval`

```
    await page.waitForSelector('.pagination__total')
    let value = await page.$eval('.pagination__total', el => el.textContent)
```

## Acelerando o processo

Caso a intenção seja apenas pegar os dados escritos na página, é uma boa prática bloquear o carregamento de imagens e do css para acelerar o processo.

```
    const browser = await puppeteer.launch({
        headless: false,
        defaultViewport: {
            width: 1800,
            height: 800,
            deviceScaleFactor: 1
        }
    });

    // remove timeout
    const page = await browser.newPage();
    await page.setDefaultNavigationTimeout(0);


    // Blocking images, css and font on page to speed up
    await page.setRequestInterception(true);
    page.on('request', (req) => {
        if (req.resourceType() == 'stylesheet' || req.resourceType() == 'font' || req.resourceType() == 'image') {
            req.abort();
        } else {
            req.continue();
        }
    });
```