# open-riff-heroes

Guitar Hero de navegador em um único arquivo HTML, com áudio direto do YouTube.

🎸 **Jogar agora:** https://felipeaguiarcode.github.io/open-riff-heroes/

## Recursos

- **Notas nas cores do Guitar Hero** (verde, vermelho, amarelo, azul), pensadas na linha de guitarra de cada música
- **Som de acerto de guitarra** sintetizado (pluck com afinação de cordas E-A-D-G por pista; palm-mute nos holds)
- **Notas longas (hold)** com rastro em perspectiva e **notas boost** (multiplicador ×2, empilha até ×10)
- **Seletor de discos**: carrossel de álbuns com vinil girando
- **Charts em JSON** (`charts/<id>.json`): link do YouTube, tempo e notas configuráveis sem tocar no código — botão ⤓ EXPORTAR JSON na seleção

## Discos e músicas

### Disco 1 — LENDAS DO ROCK

| Música | Duração | Dificuldade |
|---|---|---|
| Paint It, Black — The Rolling Stones | 3:41 | ●●●○○ |
| Welcome to the Jungle — Guns N' Roses | 4:30 | ●●●●○ |
| One — Metallica (multi-tempo 108→212 BPM) | 7:25 | ●●●●○ |
| Knights of Cydonia — Muse | 6:03 | ●●●●○ |
| Through the Fire and Flames — DragonForce | 7:18 | ●●●●● |

### Disco 2 — LET IT BEATLES

| Música | Duração | Dificuldade |
|---|---|---|
| Here Comes the Sun | 3:03 | ●●●○○ |
| Come Together | 4:14 | ●●●○○ |
| While My Guitar Gently Weeps | 4:44 | ●●●●○ |
| Twist and Shout | 2:32 | ●●●○○ |
| I Want to Hold Your Hand | 2:23 | ●●○○○ |

### Disco 3 — PIANO & ARCADE

| Música | Duração | Dificuldade |
|---|---|---|
| Moonlight Sonata (1º mov.) — Beethoven | 5:50 | ●●○○○ |
| Mickey Mouse March (Eurobeat Ver.) — DDR Disney Mix | 1:38 | ●●●●○ |

## Controles

- **D F J K** — pistas · **Espaço** — Fever · **P/Esc** — pausar · **R** — reiniciar · **Q** — sair para músicas
- **‹ ›** (setas ← →) — trocar de disco · **↑ ↓ / W S** — escolher música
- **, / .** — calibrar offset de áudio em ±25 ms (persistido por música e incluído no JSON exportado)

## Charts em JSON

Cada música é definida por `charts/<id>.json`, carregado por fetch na inicialização (com fallback para o chart embutido). Notas: `[tempo, pista]` (tap), `[tempo, pista, "h", duração]` (hold), `[tempo, pista, "b"]` (boost) — segundos relativos a `startAtSec`. O campo `youtube` aceita qualquer URL de vídeo.

Fluxo de edição: jogue → calibre com `,`/`.` → **⤓ EXPORTAR JSON** → substitua em `charts/` → commit.

> Compatibilidade: os saves (recordes/offsets) usam chaves `pianoHero.*` no localStorage — mantidas após o rename do projeto.

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
