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

## Sobre este formulário

O formulário é do Google Forms e está incorporado nesta página. Isso significa
que, ao abri-la, o seu navegador contacta servidores da Google, que podem
registar esse acesso segundo as regras de privacidade da própria Google. É a
única página do site onde isso acontece.

O que escrever no formulário chega a uma folha de cálculo à qual só o Apps
Espíritas tem acesso. Não é usado para mais nada e não é partilhado com
ninguém.

{% if site.contacto_email and site.contacto_email != "" %}
Se preferir evitar o formulário, escreva diretamente para
<a href="mailto:{{ site.contacto_email }}">{{ site.contacto_email }}</a>.
{% endif %}