# Portfólio — Luis Filipe Rezende

Página de apresentação dos meus projetos, publicada com GitHub Pages. Em português e
inglês, com seletor de idioma no topo.

O projeto apresentado é o **Fatura Social**: dívidas entre amigos, contas divididas e
cobranças por Pix. Uma API em ASP.NET Core (.NET 8) atende um app Android (.NET MAUI
Blazor) e um app Windows (WPF), com JWT, SignalR, push pelo Firebase e 492 testes em
xUnit.

## Estrutura

```
index.html                  página inteira, autocontida (ver abaixo)
assets/fatura/              imagens da galeria em tamanho real, abertas ao clicar
assets/curriculo-*.pdf      currículo oferecido para download na página
assets/prints/              capturas reais do app Windows, da versão anterior da
                            página; não são usadas pela página atual
```

O `index.html` é um export autocontido do design Nocturne: template, design system,
React, fontes, imagens e o texto vêm embutidos, comprimidos em gzip, e um script de
carregamento os desempacota no navegador. Não faz nenhuma requisição externa, mas
precisa de JavaScript e de um navegador atual (usa `DecompressionStream`).

Os únicos arquivos que ele busca fora de si são os de `assets/fatura/` e o currículo,
então esses precisam ficar ao lado do `index.html`.

## Editar o texto

Todo o texto da página fica em um recurso embutido, o `portfolio-content.js`
(`window.PF`, com as versões `pt` e `en`). No manifesto do `index.html`
(`<script type="__bundler/manifest">`) ele é a entrada
`192ad1ac-efd5-4a44-bdae-022a36ad3627`, guardada em gzip + base64.

O caminho mais simples é editar no próprio design e exportar de novo. Para editar à
mão: decodificar o base64, descomprimir, alterar, comprimir em gzip, codificar em
base64 e substituir o campo `data` dessa entrada — o carregador não confere hash.

## Publicar

No GitHub, em **Settings › Pages**, escolher a branch `main` e a pasta `/ (root)`.
