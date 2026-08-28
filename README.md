# appsespiritas.github.io

Site do Apps Espíritas. Estático, gerado pelo Jekyll, servido pelo GitHub Pages.

## Publicar

1. O repositório tem de se chamar **exatamente** `appsespiritas.github.io`.
2. Empurra este conteúdo para o ramo `main`.
3. Em **Settings → Pages**, escolhe *Deploy from a branch*, ramo `main`, pasta `/ (root)`.

O GitHub compila o Jekyll sozinho a cada push. Não é preciso GitHub Actions
nem enviar HTML compilado.

## Depois de estar no ar

O site antigo (`appsespiritas.wixsite.com/apps-esp-ritas`) fica substituído por
este. No Google Play Console, para cada uma das três apps, trocar os endereços
que hoje apontam para lá:

| Campo | Novo endereço |
|---|---|
| Website | `https://appsespiritas.github.io` |
| Política de Privacidade (Centros) | `https://appsespiritas.github.io/apps/centros-espiritas-de-portugal/privacidade/` |
| Política de Privacidade (Faq) | `https://appsespiritas.github.io/apps/faq-espirita/privacidade/` |
| Política de Privacidade (Escala) | `https://appsespiritas.github.io/apps/escala-espirita/privacidade/` |

## Falta preencher

| Onde | O quê |
|---|---|
| `_config.yml` → `formulario_google` | O endereço `src` do iframe do Google Forms (Enviar → Incorporar HTML) |
| `privacidade/faq-espirita.md` | Verificar a lista de dados campo a campo; é a única app com contas |
| `privacidade/*.md` | Pôr a data em `Última atualização` e apagar os avisos amarelos |
| `assets/img/apps/` | Opcional: guardar aqui cópias locais dos ícones e capturas |

## Ícones e capturas de ecrã

Estão a ser servidos a partir do CDN do Google Play, com os endereços que
aparecem na ficha de cada app. Funciona e poupa trabalho, mas os endereços
mudam se substituíres os ficheiros na Play Store — nessa altura o site fica com
imagens partidas.

Se preferires ficheiros locais, descarrega-os para `assets/img/apps/` e troca os
campos `icone:` e `capturas:` por caminhos do género `/assets/img/apps/nome.png`.
Os templates aceitam as duas formas.

## Adicionar uma aplicação nova

Cria um ficheiro em `_apps/`. O nome do ficheiro é o endereço:
`_apps/obras-kardec.md` fica em `/apps/obras-kardec/`.

```yaml
---
titulo: "Nome da aplicação"
ordem: 4                        # posição na listagem
estado: publicada               # ou: brevemente
resumo: "Uma linha que aparece no cartão da página inicial."
icone: https://play-lh.googleusercontent.com/...=s512
package: "pt.appsespiritas.nome"
play: ""                        # só se o endereço não seguir o padrão
plataformas: [Android]
ios: true                       # mostra "versão para iPhone em preparação"
nota_ios: ""                    # texto alternativo, quando ios: false
etiquetas: [Palavra, Outra]
categoria: "Educação"
classificacao: "3+"
requisitos: ""                  # opcional, ex.: "Android 6.0 ou superior"
idiomas: [Português]
funcionalidades:
  - "Uma frase por funcionalidade"
capturas: []
---

O texto descritivo vai aqui, em Markdown.
```

Depois cria a política de privacidade em `privacidade/obras-kardec.md`, com:

```yaml
permalink: /apps/obras-kardec/privacidade/
```

Mais nada. A página inicial, o rodapé, o índice de privacidade e a lista
"outras aplicações" atualizam-se sozinhos.

## Trabalhar localmente

Precisas de Ruby.

```bash
bundle install
bundle exec jekyll serve
```

Fica em `http://localhost:4000`.

## Estrutura

```
_apps/          uma aplicação por ficheiro
privacidade/    uma política por aplicação
_layouts/       default, page (páginas de texto), app (páginas de aplicação)
_includes/      head, header, footer, cartão de aplicação
assets/css/     uma folha de estilos, sem dependências
assets/img/     favicon; ícones e capturas locais, se optares por eles
```
