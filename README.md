# Portfólio — Luis Filipe Rezende

Página de apresentação dos meus projetos, publicada com GitHub Pages.

- **Fatura Social** — app de finanças pessoais focado no dinheiro que circula entre
  amigos: pendências por pessoa, cobrança por Pix e ciclo de fatura automático.
  C# · .NET 8 · WPF · ASP.NET Core · SQLite.
- **Mesa do Mestre** — ferramenta de mesa para mestres de RPG: ficha que calcula os
  espaços de magia pelas regras do PHB 2024, iniciativa por aventura e barra de
  dados. C# · .NET 8 · WPF · MVVM · EF Core · SQLite.

## Estrutura

```
index.html            página inteira (HTML + CSS + JS inline, sem build)
assets/prints/        capturas dos aplicativos rodando
assets/dados/         ícones de dado em pixel art, vindos da Mesa do Mestre
assets/curriculo-*.pdf  currículo oferecido para download na página
```

Seções: início, sobre, experiência, habilidades, projetos, formação e contato.

Sem dependências e sem etapa de build: abrir o `index.html` no navegador já mostra
o resultado final. As únicas requisições externas são as fontes do Google Fonts.

## Capturas

Os prints em `assets/prints/` foram tirados dos aplicativos rodando de verdade no
Windows. Para atualizá-los, basta substituir os arquivos mantendo os nomes:

| Arquivo | Tela |
|---------|------|
| `fatura-claro.png` | Fatura Social · Lançamentos, tema claro |
| `fatura-escuro.png` | Fatura Social · Lançamentos, tema escuro |
| `fatura-conexoes.png` | Fatura Social · Conexões |
| `mesa-do-mestre.png` | Mesa do Mestre · Aventura ativa |

Os dois primeiros alimentam o seletor de tema da página, então precisam ser da
mesma tela e do mesmo tamanho.

## Publicar

No GitHub, em **Settings › Pages**, escolher a branch `main` e a pasta `/ (root)`.
