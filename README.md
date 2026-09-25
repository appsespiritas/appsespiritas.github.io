# appsespiritas.github.io

Site do Apps Espíritas. Estático, gerado pelo Jekyll, servido pelo GitHub Pages
em <https://appsespiritas.github.io>.

## Estrutura

```
_apps/          uma aplicação por ficheiro — é daqui que sai tudo o resto
privacidade/    uma política por aplicação
_layouts/       default, page (páginas de texto), app (páginas de aplicação)
_includes/      head, header, footer, cartão de aplicação
assets/css/     uma folha de estilos, sem dependências
imagens/        logótipos dos centros, servidos à app Centros Espíritas
```

A página inicial, o rodapé, o índice de privacidade e a lista «outras
aplicações» são todos gerados a partir de `_apps/`. Não há listas escritas à
mão em lado nenhum.

## Adicionar uma aplicação

Cria um ficheiro em `_apps/`. O nome do ficheiro é o endereço:
`_apps/obras-kardec.md` fica em `/apps/obras-kardec/`.

```yaml
---
titulo: "Nome da aplicação"        # título grande na página
title: "Nome da aplicação"         # <title> e redes sociais
description: "Uma frase para os resultados de pesquisa."
ordem: 4                           # posição na listagem
resumo: "Uma linha para o cartão da página inicial."
icone: https://play-lh.googleusercontent.com/...=s512
etiquetas: [Palavra, Outra]
idiomas: [Português]

android:
  estado: publicada                # publicada | preparacao | nao_previsto
  package: "pt.appsespiritas.nome" # gera o link do Google Play
  categoria: "Educação"
  classificacao: "3+"
  requisitos: "Android 6.0 ou superior"   # opcional
  capturas:
    - https://play-lh.googleusercontent.com/...=w720

ios:
  estado: publicada
  id: "6812376884"                 # Apple ID; gera o link da App Store
  categoria: "Referência"
  classificacao: "17+"
  requisitos: "iOS 18.0 ou superior"
  capturas:
    - https://is1-ssl.mzstatic.com/...626x0w.png

funcionalidades:
  - "Uma frase por funcionalidade"
---

O texto descritivo vai aqui, em Markdown.
```

Depois cria a política em `privacidade/obras-kardec.md`, com
`permalink: /apps/obras-kardec/privacidade/`.

### Estados de plataforma

| `estado` | O que acontece na página |
|---|---|
| `publicada` | Botão de descarga para essa loja |
| `preparacao` | Nota «em preparação» |
| `nao_previsto` | Mostra o texto do campo `nota:` |
| ausente | A plataforma não é mencionada |

Se uma plataforma usa um endereço que não segue o padrão, põe-no em `url:`
dentro do bloco dessa plataforma, e esse ganha ao `package`/`id`.

### Capturas de ecrã

Quando uma aplicação tem capturas nas duas plataformas, a página mostra
separadores Android/iPhone. São feitos só com CSS, sem JavaScript. Com uma só
plataforma, as capturas aparecem sem separadores.

## Onde vivem as imagens

Os ícones e as capturas são servidos pelos CDN das lojas, com os endereços que
aparecem nas fichas. Se substituíres as imagens numa loja, os endereços mudam e
o site fica com imagens partidas — nessa altura atualiza os campos `icone:` e
`capturas:`.

Os endereços da App Store vêm da API pública:
`https://itunes.apple.com/lookup?id=<AppleID>&country=pt`. O tamanho no fim do
endereço (`626x0w.png`) pode ser trocado.

Para usar ficheiros locais, guarda-os em `assets/img/apps/` e escreve o caminho
começado por `/assets/`. Os templates aceitam as duas formas.

## Publicar

Empurra para `main`. O GitHub compila o Jekyll sozinho, sem GitHub Actions.

Em **Settings → Pages**: *Deploy from a branch*, ramo `main`, pasta `/ (root)`.

O ficheiro `google44ea2454d0574442.html` é a verificação do Search Console.
Não o apagues nem o edites.

## Endereços nas lojas

Os que devem estar configuradas na Play Console e no App Store Connect:

| | |
|---|---|
| Website | `https://appsespiritas.github.io/apps/<nome-da-app>/` |
| Política de privacidade | `https://appsespiritas.github.io/apps/<nome-da-app>/privacidade/` |

## Trabalhar localmente

```bash
bundle install
bundle exec jekyll serve
```

Fica em `http://localhost:4000`.
