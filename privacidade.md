---
layout: page
titulo: "Que dados é que as aplicações recolhem?"
title: "Privacidade"
numero: 5
permalink: /privacidade/
---

O princípio é curto: as aplicações do Apps Espíritas não têm publicidade, não
têm rastreadores e não vendem nem cedem dados a ninguém.

Duas das três não recolhem nada. A terceira tem contas de utilizador, e por
isso guarda o que é preciso para essas contas funcionarem.

Cada aplicação tem a sua política, porque cada loja exige um endereço próprio:

<ul class="lista-privacidade">
{%- assign lista = site.apps | sort: "ordem" -%}
{%- for app in lista -%}
  <li><a href="{{ app.url | append: 'privacidade/' | relative_url }}">{{ app.titulo }}</a></li>
{%- endfor -%}
</ul>

## Notas guardadas no telemóvel

Quando uma aplicação permite guardar notas ou marcar a posição de leitura,
esses dados ficam apenas no dispositivo. Não são enviados para lado nenhum e
desaparecem se a aplicação for desinstalada.
