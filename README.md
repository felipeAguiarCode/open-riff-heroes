# piano-hero

Jogo de ritmo estilo Guitar Hero / Rock Band em um único arquivo HTML, com áudio direto do YouTube.

🎹 **Jogar agora:** https://felipeaguiarcode.github.io/piano-hero/

## Recursos

- **Notas neon** com brilho e paleta viva (turquesa/âmbar/violeta)
- **Notas longas (hold)** com rastro em perspectiva estilo Guitar Hero — segure a tecla até o fim
- **Notas boost** em azul-choque: acerte para ativar multiplicador ×2 temporário (empilha com combo e Fever até ×10)
- **Tela inicial** estilo Rock Band + **seleção de músicas** com capas, dificuldade e recorde por música
- **Áudio via YouTube** (player oculto) com clock híbrido sincronizado a `getCurrentTime()`
- Charts determinísticos autorados por música, coerentes com a estrutura musical

## Músicas

| Música | Fonte | Duração | Dificuldade |
|---|---|---|---|
| Moonlight Sonata (1º mov.) — Beethoven | [YouTube](https://www.youtube.com/watch?v=4591dCHe_sE) | ~5:50 | ●●○○○ |
| Mickey Mouse March (Eurobeat Ver.) — DDR Disney Mix | [YouTube](https://www.youtube.com/watch?v=2IF8IdRLdAM) | ~1:38 | ●●●●○ |

## Controles

- **D F J K** — pistas · **Espaço** — ativar Fever · **P/Esc** — pausar · **R** — reiniciar · **Q** — sair para músicas
- **, / .** — calibrar offset de áudio em ±25 ms (persistido por música)

## Rodar localmente

A API do YouTube não funciona via `file://` — sirva por HTTP:

```bash
python -m http.server 8000
# http://localhost:8000
```

## Estrutura

- `index.html` — o jogo completo (HTML/CSS/JS em um único arquivo)
- `raw/GDD.md` — Game Design Document
- `raw/` — referências e materiais de apoio
