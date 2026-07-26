# piano-hero

Jogo de ritmo estilo Guitar Hero / Rock Band em um único arquivo HTML, com áudio direto do YouTube.

🎹 **Jogar agora:** https://felipeaguiarcode.github.io/piano-hero/

## Recursos

- **Notas neon nas cores do Guitar Hero** (verde, vermelho, amarelo, azul)
- **Notas longas (hold)** com rastro em perspectiva — segure a tecla até o fim
- **Notas boost** azul-choque: multiplicador ×2 temporário (empilha com combo e Fever até ×10)
- **Seletor de discos**: carrossel de álbuns com vinil girando; ‹ › troca de disco com animação
- **Charts em JSON** (`charts/<id>.json`): link do YouTube, tempo e sequência de notas configuráveis sem tocar no código — botão ⤓ EXPORTAR JSON na tela de seleção
- Clock híbrido sincronizado ao player do YouTube, com calibração de offset ao vivo

## Discos e músicas

### Disco 1 — LENDAS DO ROCK

| Música | Duração | Dificuldade |
|---|---|---|
| Paint It, Black — The Rolling Stones | 3:41 | ●●●○○ |
| Welcome to the Jungle — Guns N' Roses | 4:30 | ●●●●○ |
| One — Metallica (multi-tempo 108→212 BPM) | 7:25 | ●●●●○ |
| Knights of Cydonia — Muse | 6:03 | ●●●●○ |
| Through the Fire and Flames — DragonForce | 7:18 | ●●●●● |

### Disco 2 — PIANO & ARCADE

| Música | Duração | Dificuldade |
|---|---|---|
| Moonlight Sonata (1º mov.) — Beethoven | 5:50 | ●●○○○ |
| Mickey Mouse March (Eurobeat Ver.) — DDR Disney Mix | 1:38 | ●●●●○ |

## Controles

- **D F J K** — pistas · **Espaço** — Fever · **P/Esc** — pausar · **R** — reiniciar · **Q** — sair para músicas
- **‹ ›** (setas ← →) — trocar de disco · **↑ ↓ / W S** — escolher música
- **, / .** — calibrar offset de áudio em ±25 ms (persistido por música e incluído no JSON exportado)

## Charts em JSON

Cada música é definida por `charts/<id>.json`, carregado por fetch na inicialização (com fallback para o chart embutido). Formato das notas: `[tempo, pista]` (tap), `[tempo, pista, "h", duração]` (hold), `[tempo, pista, "b"]` (boost) — tempos em segundos relativos a `startAtSec`. O campo `youtube` aceita qualquer URL de vídeo do YouTube.

Fluxo de edição: jogue → calibre com `,`/`.` → **⤓ EXPORTAR JSON** → substitua o arquivo em `charts/` → commit.

## Rodar localmente

A API do YouTube e o fetch dos charts não funcionam via `file://` — sirva por HTTP:

```bash
python -m http.server 8000
# http://localhost:8000
```

## Estrutura

- `index.html` — o jogo completo (HTML/CSS/JS em um único arquivo)
- `charts/*.json` — definição configurável de cada música (link, tempo, notas)
- `raw/GDD.md` — Game Design Document
