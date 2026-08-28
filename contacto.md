---
layout: page
titulo: "Como se sugere uma aplicação nova?"
title: "Contacto"
numero: 4
permalink: /contacto/
---

Preenchendo o formulário aqui em baixo. Serve para tudo: propor uma
aplicação, apontar um erro numa das que existem, corrigir os dados de um
centro espírita ou simplesmente dizer o que está a faltar.

Todas as mensagens são lidas. Nem todas terão resposta rápida — isto é feito
em tempo livre — mas nenhuma se perde.

{% if site.formulario_google and site.formulario_google != "" %}
<div class="formulario">
  <iframe
    src="{{ site.formulario_google }}"
    title="Formulário de contacto do Apps Espíritas"
    width="100%" height="900" frameborder="0"
    marginheight="0" marginwidth="0">A carregar o formulário…</iframe>
</div>
{% else %}
<div class="aviso aviso--bloco">
  <p><strong>O formulário ainda não está ligado.</strong></p>
  <p>
    Crie o formulário no Google Forms, copie o endereço que aparece em
    <em>Enviar &rarr; Incorporar HTML</em> e coloque-o em
    <code>_config.yml</code>, no campo <code>formulario_google</code>.
  </p>
</div>
{% endif %}

{% if site.contacto_email and site.contacto_email != "" %}
## Por email

Se preferir, escreva para <a href="mailto:{{ site.contacto_email }}">{{ site.contacto_email }}</a>.
{% endif %}
