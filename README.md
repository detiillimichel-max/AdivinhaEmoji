# 🎯 AdivinhaEmoji

PWA de adivinhação onde a IA gera sequências de emojis representando filmes, séries, músicas, games e livros. O jogador tenta adivinhar o título.

## Funcionalidades

- 🤖 Emojis gerados dinamicamente pela IA (Claude) — nunca repete
- 🏆 Sistema de pontos com bônus por acertar sem dicas e sequência de acertos
- 💡 Até 3 dicas progressivas por rodada
- ⏭ Opção de pular e ver a resposta
- 🎬📺🎵🎮📚 5 categorias toggleáveis
- 🎉 Confetti animado ao acertar
- 📱 PWA instalável (offline para o shell, IA requer conexão)

## Estrutura

```
/
├── index.html       ← jogo completo
├── manifest.json    ← PWA manifest
├── sw.js            ← Service Worker (cache + offline shell)
├── README.md
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## Deploy no GitHub Pages

1. Renomeie `emoji-game.html` → `index.html`
2. Adicione os ícones em `/icons/` (192×192 e 512×512 px)
3. Registre o SW no `index.html` antes de `</body>`:

```html
<script>
  if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('/sw.js');
  }
</script>
```

4. Adicione o manifest no `<head>` do `index.html`:

```html
<link rel="manifest" href="/manifest.json">
<meta name="theme-color" content="#A855F7">
```

5. Faça push para a branch `main` (ou `gh-pages`) e ative o GitHub Pages nas configurações do repositório.

> **Atenção:** A IA requer conexão com a internet (chama a API Anthropic). O Service Worker faz cache apenas do shell do app.

## Ícones

Gere os ícones em [favicon.io](https://favicon.io) ou similar usando o emoji 🎯 como base, exportando nos tamanhos 192×192 e 512×512 px.

## Licença

MIT
