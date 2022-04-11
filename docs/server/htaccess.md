---
layout: default
title: Htaccess
nav_order: 2
parent: Server
permalink: docs/server/htaccess
---

# O que é o htaccess?

Em servidores web que utilizam Apache, o arquivo ```.htaccess``` é utilizado para aplicar configurações, renomeações, restrição de acesso, etc.

Com o htaccess, você pode criar urls mais amigáveis, retirando o sufixo .php por exemplo, fazendo com que a página fique apenas exemplo.com/blog.

Aqui são os procedimentos que podemos fazer:

- Redirecionamentos de urls
- Redirecionamentos de pastas
- Bloqueio de acesso a determinadas pastas
- Redirecionamentos quando em página de erro, para alguma personalizada.
- Solicitação de módulos e aplicações do php, para serem executadas.
- Habilitar Mod_rewrite
- Fazer chamada de uma php.ini personalizada
- Redirecionamentos para funcionamento de ferramentas e aplicações.

Veja o exemplo do htaccess do wordpress:

```

# BEGIN WordPress
# As diretrizes (linhas) entre "BEGIN WordPress" e "END WordPress" são
# geradas dinamicamente e só devem ser modificadas através de filtros do WordPress.
# Quaisquer alterações nas diretivas entre esses marcadores serão sobrescritas.
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
RewriteBase /
RewriteRule ^index\.php$ - [L]

# add a trailing slash to /wp-admin
RewriteRule ^([_0-9a-zA-Z-]+/)?wp-admin$ $1wp-admin/ [R=301,L]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^ - [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(wp-(content|admin|includes).*) $2 [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(.*\.php)$ $2 [L]
RewriteRule . index.php [L]

</IfModule>

# END WordPress

    php_value upload_max_filesize 64M
    php_value post_max_size 128M
    php_value memory_limit 256M
    php_value max_execution_time 300
    php_value max_input_time 300

```

O arquivo é redigido usando regex.