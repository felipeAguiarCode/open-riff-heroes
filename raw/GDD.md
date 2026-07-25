# PIANO HERO — GAME DESIGN DOCUMENT

**Arquivo:** `gdd.md`  
**Versão:** 0.1 — Documento-base  
**Status:** Pré-produção / definição conceitual  
**Plataforma principal:** Navegador desktop  
**Gênero:** Ritmo musical + Roguelite  
**Modelo de controle:** Teclado físico / Button Quick Time Event  
**Princípio de produção:** IA como acelerador de desenvolvimento, não como substituta da direção de design

---

## 0. COMO LER ESTE DOCUMENTO

Este GDD possui três tipos de decisão:

- **Confirmado:** informação definida no conceito original.
- **Proposto:** decisão adicionada para tornar o jogo prototipável e testável.
- **Em aberto:** decisão que ainda precisa de validação.

As decisões propostas devem ser tratadas como hipóteses de design. Elas existem para permitir a construção de um primeiro protótipo funcional, mas podem ser alteradas após playtests.

---

# 1. VISÃO DO JOGO

## 1.1 High Concept

**Piano Hero** é um jogo de ritmo musical para navegador em que notas descem pela tela em direção a uma zona de execução. Cada nota corresponde a uma tecla do teclado físico do jogador.

O jogador precisa pressionar a tecla correta no momento correto para tocar a música, construir combos, carregar o sistema de **Fever** e sobreviver a uma sequência de fases com estrutura roguelite.

Entre músicas, o jogador escolhe melhorias temporárias que alteram pontuação, tolerância de erro, velocidade, recuperação, Fever e comportamento das notas. Cada partida deve produzir uma combinação diferente de bônus, riscos e decisões.

## 1.2 Elevator Pitch

> Guitar Hero encontra um piano digital e uma estrutura roguelite: acerte as teclas no ritmo, construa sua combinação de melhorias e sobreviva até o final da apresentação.

## 1.3 Fantasia Central

O jogador deve sentir que está:

- executando uma música com precisão;
- dominando progressivamente o teclado;
- entrando em um estado de fluxo;
- construindo uma performance cada vez mais poderosa;
- criando uma “build musical” diferente a cada partida;
- transformando uma apresentação simples em um espetáculo visual e mecânico.

## 1.4 Diferencial Principal

A principal distinção de Piano Hero não deve ser apenas “notas caindo”.

O diferencial será a combinação de:

1. **Ritmo com teclado físico**;
2. **Sistema de Fever progressivo**;
3. **Escolhas roguelite entre músicas**;
4. **Runs curtas e rejogáveis**;
5. **Modificadores que mudam a forma de tocar**;
6. **IA utilizada para acelerar criação, validação e balanceamento de conteúdo**.

---

# 2. PILARES DE DESIGN

## 2.1 Leitura Imediata

O jogador deve entender rapidamente:

- qual tecla pressionar;
- quando pressionar;
- se acertou;
- qual foi a qualidade do acerto;
- quanto falta para ativar o Fever;
- se está perto de vencer ou perder.

A interface não deve competir visualmente com as notas.

## 2.2 Ritmo Antes de Complexidade

A sensação de tocar no tempo é mais importante que a quantidade de sistemas.

O núcleo do jogo precisa ser divertido antes da inclusão de:

- upgrades;
- raridades;
- progressão permanente;
- chefes;
- efeitos especiais;
- eventos aleatórios.

## 2.3 Falha Justa

O jogador deve compreender por que errou.

Toda falha precisa ter feedback visual e sonoro claro, diferenciando:

- tecla errada;
- tecla correta pressionada cedo;
- tecla correta pressionada tarde;
- nota ignorada;
- input não reconhecido;
- perda por desempenho mínimo insuficiente.

## 2.4 Crescimento Durante a Run

Cada música vencida deve tornar a run mais interessante.

O jogador deve sentir que sua build está:

- ficando mais eficiente;
- criando sinergias;
- abrindo novas possibilidades;
- também aumentando riscos ou exigências.

## 2.5 Partidas Rejogáveis

Uma run não deve ser idêntica à anterior.

A variação pode vir de:

- ordem das músicas;
- padrões de notas;
- upgrades;
- eventos;
- modificadores de fase;
- chefes;
- recompensas;
- dificuldade escalável.

---

# 3. OBJETIVOS DE EXPERIÊNCIA

## 3.1 Emoções Pretendidas

Durante uma música:

- concentração;
- urgência;
- prazer por sincronização;
- satisfação por combos;
- tensão próxima de uma falha;
- euforia ao ativar Fever.

Entre músicas:

- alívio;
- curiosidade;
- planejamento;
- sensação de crescimento;
- expectativa pela próxima escolha.

Ao concluir uma run:

- domínio;
- orgulho;
- vontade de testar outra build;
- desejo de superar a própria pontuação.

## 3.2 Duração Proposta

### Sessão rápida

- 5 a 10 minutos;
- uma música isolada;
- modo de treino ou desafio diário.

### Run padrão

- 20 a 35 minutos;
- de 5 a 8 músicas;
- escolhas de melhoria entre as fases;
- pelo menos um confronto final ou música-chefe.

### Música individual

- 90 segundos a 4 minutos;
- duração variável conforme dificuldade e modo.

**Status:** Proposto.

---

# 4. PÚBLICO-ALVO

## 4.1 Público Primário

- jogadores de títulos musicais;
- pessoas que gostam de Guitar Hero, Piano Tiles, osu!mania e jogos de ritmo baseados em lanes;
- jogadores de roguelites que valorizam builds e runs curtas;
- usuários de computador familiarizados com teclado físico;
- jogadores casuais que procuram sessões rápidas.

## 4.2 Público Secundário

- estudantes de música;
- pessoas interessadas em percepção rítmica;
- criadores de conteúdo;
- jogadores que gostam de competir por pontuação;
- jogadores interessados em experiências acessíveis diretamente pelo navegador.

## 4.3 Classificação Indicativa Pretendida

Livre, desde que o repertório, os elementos visuais e qualquer monetização mantenham conteúdo apropriado.

---

# 5. PLATAFORMA E PREMISSAS

## 5.1 Plataforma Principal

**Navegador desktop.**

Navegadores-alvo propostos:

- Google Chrome;
- Microsoft Edge;
- Mozilla Firefox;
- Safari em macOS, mediante validação de latência e áudio.

## 5.2 Dispositivos de Entrada

### MVP

- teclado físico;
- mouse apenas para menus.

### Pós-MVP

- gamepad;
- teclado MIDI;
- controles customizados;
- dispositivos móveis com interface adaptada.

## 5.3 Orientação de Tela

**Proposta principal:** paisagem 16:9.

A pista de notas ocupa o centro da tela, com HUD distribuído nas laterais e na parte superior.

## 5.4 Requisitos de Sessão

O jogo deve:

- carregar rapidamente;
- funcionar sem instalação;
- manter baixa latência de input;
- pausar ao perder foco, caso o modo permita;
- detectar quedas severas de performance;
- permitir calibração de áudio e vídeo.

---

# 6. ESTRUTURA MACRO DO JOGO

## 6.1 Fluxo Principal

```text
ABERTURA
  ↓
MENU PRINCIPAL
  ↓
SELEÇÃO DE MODO
  ↓
SELEÇÃO DE PERSONAGEM/INSTRUMENTO/BUILD INICIAL
  ↓
INÍCIO DA RUN
  ↓
SELEÇÃO DE ROTA OU PRÓXIMA MÚSICA
  ↓
GAMEPLAY MUSICAL
  ↓
RESULTADO DA MÚSICA
  ↓
RECOMPENSA / ESCOLHA DE UPGRADE
  ↓
PRÓXIMA FASE
  ↓
MÚSICA-CHEFE
  ↓
VITÓRIA DA RUN OU GAME OVER
  ↓
PROGRESSÃO / ESTATÍSTICAS / NOVA RUN
```

## 6.2 Estados Principais

1. Inicialização;
2. Menu principal;
3. Configurações;
4. Calibração;
5. Seleção de modo;
6. Seleção de run;
7. Mapa ou sequência de músicas;
8. Preparação da música;
9. Gameplay;
10. Pausa;
11. Resultado;
12. Escolha de recompensa;
13. Evento roguelite;
14. Vitória;
15. Derrota;
16. Tela de estatísticas;
17. Créditos.

---

# 7. CORE LOOP

## 7.1 Loop de Momento a Momento

```text
LER A NOTA
  ↓
IDENTIFICAR A TECLA
  ↓
ANTECIPAR O TEMPO
  ↓
PRESSIONAR A TECLA
  ↓
RECEBER FEEDBACK
  ↓
AUMENTAR COMBO/PONTUAÇÃO/FEVER
  ↓
PREPARAR A PRÓXIMA NOTA
```

## 7.2 Loop de Música

```text
INICIAR MÚSICA
  ↓
ACERTAR NOTAS
  ↓
CONSTRUIR COMBO
  ↓
CARREGAR FEVER
  ↓
ATIVAR FEVER
  ↓
MAXIMIZAR PONTUAÇÃO
  ↓
ATINGIR O CRITÉRIO MÍNIMO
  ↓
VENCER A MÚSICA
```

## 7.3 Loop de Run

```text
VENCER MÚSICA
  ↓
RECEBER RECOMPENSA
  ↓
ESCOLHER UPGRADE
  ↓
CRIAR SINERGIA
  ↓
ENFRENTAR MÚSICA MAIS DIFÍCIL
  ↓
ADAPTAR A BUILD
  ↓
DERROTAR O CHEFE
```

## 7.4 Loop de Longo Prazo

```text
CONCLUIR OU PERDER UMA RUN
  ↓
RECEBER PROGRESSO PERMANENTE
  ↓
DESBLOQUEAR CONTEÚDO
  ↓
TESTAR NOVAS BUILDS
  ↓
AUMENTAR DIFICULDADE
  ↓
BUSCAR MELHORES RANKINGS E CONQUISTAS
```

**Observação:** progressão permanente ainda é uma decisão em aberto.

---

# 8. GAMEPLAY MUSICAL

## 8.1 Conceito Base

As notas surgem na parte superior da pista e descem em direção à **Linha de Execução**.

Cada nota exibe uma tecla correspondente do teclado.

Quando a nota alcança a Linha de Execução, o jogador deve pressionar a tecla indicada.

## 8.2 Pista de Notas

### Estrutura proposta

- pista vertical;
- de 4 a 8 lanes, conforme dificuldade;
- cada lane representa uma tecla fixa ou uma região do teclado;
- notas descem de cima para baixo;
- a Linha de Execução fica próxima da parte inferior;
- a velocidade de descida é configurável dentro de limites seguros.

## 8.3 Modelos Possíveis de Mapeamento

### Modelo A — Teclas fixas por lane

Exemplo:

```text
Lane 1 = A
Lane 2 = S
Lane 3 = D
Lane 4 = F
Lane 5 = J
Lane 6 = K
Lane 7 = L
Lane 8 = ;
```

Vantagens:

- previsibilidade;
- ergonomia;
- fácil aprendizagem;
- compatibilidade com padrões tradicionais de jogos de ritmo.

### Modelo B — Letras variáveis em qualquer lane

Cada nota apresenta uma tecla que pode mudar.

Vantagens:

- maior variedade;
- aproximação de Quick Time Events;
- permite trabalhar reconhecimento visual.

Riscos:

- leitura mais difícil;
- menor associação entre lane e mão;
- maior carga cognitiva.

### Modelo C — Híbrido

- cada lane possui uma tecla-base;
- efeitos roguelite podem alterar temporariamente o mapeamento;
- fases especiais podem usar teclas variáveis.

**Recomendação inicial:** Modelo A no MVP.

## 8.4 Tipos de Nota

### Nota simples — MVP

- exige um toque;
- desaparece após julgamento;
- representa o elemento central do jogo.

### Nota sustentada — Pós-MVP

- exige pressionar e manter;
- pontua enquanto estiver segurada;
- pode terminar com soltura precisa.

### Acorde — Pós-MVP

- duas ou mais teclas simultâneas;
- exige coordenação;
- pode carregar Fever mais rapidamente.

### Nota fantasma — Opcional

- parece uma nota comum, mas não deve ser pressionada;
- recomendada apenas para dificuldades avançadas ou modificadores específicos.

### Nota de sequência — Opcional

- pequeno grupo de notas encadeadas;
- recompensa execução completa.

### Nota de risco — Roguelite

- concede recompensa superior;
- aplica penalidade adicional em caso de erro.

---

# 9. INPUT E JULGAMENTO DE TEMPO

## 9.1 Princípio

A precisão deve ser calculada pela diferença entre:

- o momento ideal da nota;
- o momento real do input;
- o offset de calibração do jogador.

## 9.2 Janelas de Acerto Propostas

| Julgamento | Janela proposta | Pontuação-base | Efeito |
|---|---:|---:|---|
| Perfect | até ±50 ms | 100% | maior ganho de Fever |
| Great | até ±90 ms | 80% | mantém combo |
| Good | até ±140 ms | 50% | mantém ou reduz combo, conforme balanceamento |
| Miss | acima de ±140 ms | 0% | quebra combo e aplica penalidade |

**Status:** Proposto.  
Esses valores precisam ser testados em diferentes navegadores, monitores, teclados e dispositivos de áudio.

## 9.3 Early e Late

O feedback deve informar quando o jogador pressionou:

- cedo demais;
- tarde demais;
- dentro da janela perfeita.

Exemplo visual:

```text
PERFECT
GREAT — EARLY
GOOD — LATE
MISS
```

## 9.4 Inputs Extras

Pressionar uma tecla sem nota correspondente pode:

- não causar penalidade no modo Casual;
- reduzir a pontuação no modo Normal;
- quebrar o combo no modo Difícil;
- causar dano em modificadores específicos.

**Status:** Proposto.

## 9.5 Anti-Repetição

O sistema não deve contar múltiplos eventos do sistema operacional gerados ao manter uma tecla pressionada, exceto em notas sustentadas.

## 9.6 Teclas Simultâneas

A arquitetura deve aceitar múltiplos inputs no mesmo frame para suportar acordes futuramente.

---

# 10. PONTUAÇÃO

## 10.1 Fórmula Base Proposta

```text
Pontuação da nota =
Valor-base da nota
× Qualidade do julgamento
× Multiplicador de combo
× Multiplicador de Fever
× Modificadores da build
```

## 10.2 Valor-base

Proposta inicial:

```text
Nota simples = 100 pontos
Nota sustentada = 100 pontos + ticks de sustentação
Acorde = 100 pontos por tecla + bônus de acordo completo
Nota de risco = 150 a 300 pontos
```

## 10.3 Precisão da Música

```text
Precisão =
Pontos de julgamento obtidos
÷
Pontos máximos de julgamento
× 100
```

A precisão não deve ser calculada apenas pela quantidade de notas tocadas. Ela deve considerar a qualidade dos julgamentos.

## 10.4 Rank de Resultado

| Rank | Precisão proposta |
|---|---:|
| S+ | 99% ou mais |
| S | 95% a 98,99% |
| A | 90% a 94,99% |
| B | 80% a 89,99% |
| C | 70% a 79,99% |
| D | abaixo de 70% |

**Status:** Proposto.

## 10.5 Bônus Adicionais

- Full Combo;
- All Perfect;
- nenhuma tecla extra;
- Fever máximo;
- conclusão com modificador de risco;
- execução de notas especiais;
- conclusão sem recurso defensivo;
- velocidade elevada.

---

# 11. COMBO

## 11.1 Funcionamento

O combo aumenta a cada nota acertada.

Proposta:

- Perfect: +1 combo;
- Great: +1 combo;
- Good: +1 combo ou mantém combo;
- Miss: quebra o combo;
- tecla errada: comportamento depende da dificuldade.

## 11.2 Multiplicador de Combo Proposto

| Combo | Multiplicador |
|---:|---:|
| 0–9 | ×1,0 |
| 10–24 | ×1,25 |
| 25–49 | ×1,5 |
| 50–99 | ×2,0 |
| 100+ | ×2,5 |

O multiplicador pode ser alterado por upgrades.

## 11.3 Feedback

O combo deve:

- crescer visualmente sem cobrir a pista;
- mudar de escala em marcos importantes;
- produzir feedback sonoro sutil;
- ter animação especial ao ser quebrado em valores elevados.

---

# 12. SISTEMA DE FEVER

## 12.1 Conceito Confirmado

Conforme o jogador acerta notas, uma barra de multiplicador chamada **Fever** é preenchida.

O Fever representa o ápice da performance.

## 12.2 Ganho de Fever Proposto

| Evento | Ganho |
|---|---:|
| Perfect | alto |
| Great | médio |
| Good | baixo |
| Miss | perda parcial |
| Combo milestone | bônus |
| Nota especial | bônus elevado |

## 12.3 Ativação

Existem três modelos possíveis:

### Automática

O Fever é ativado ao atingir 100%.

Vantagem:

- simples;
- mantém foco no ritmo.

### Manual

O jogador pressiona uma tecla dedicada.

Vantagem:

- cria decisão estratégica;
- permite guardar Fever para partes difíceis ou valiosas.

### Híbrida

O jogador pode ativar manualmente; caso não ative, o sistema dispara automaticamente antes do término da música.

**Recomendação:** ativação manual no modo roguelite e automática no modo casual.

## 12.4 Efeitos Propostos do Fever

Durante o Fever:

- multiplicador de pontuação aumentado;
- feedback visual intensificado;
- erros leves podem não quebrar o combo;
- notas podem conceder mais recurso;
- a música pode receber uma camada sonora adicional;
- a pista pode reagir ao ritmo;
- upgrades podem alterar sua duração ou efeito.

## 12.5 Duração Proposta

- barra cheia: 8 segundos;
- upgrades podem aumentar a duração;
- Perfects durante Fever podem desacelerar a drenagem;
- Fever termina quando a barra chega a zero.

## 12.6 Multiplicador Proposto

```text
Fever padrão = ×2
Fever aprimorado = até ×4
```

## 12.7 Risco de Legibilidade

Os efeitos do Fever nunca devem:

- ocultar notas;
- alterar o contraste das teclas;
- movimentar a Linha de Execução;
- introduzir flashes excessivos;
- prejudicar jogadores fotossensíveis.

---

# 13. CONDIÇÕES DE VITÓRIA E DERROTA

## 13.1 Definição Original

A definição inicial informa:

- vitória ao acertar mais de 15% das notas;
- derrota ao não acertar 15% das notas.

## 13.2 Interpretação Provisória

Para tornar a regra consistente:

```text
Vitória:
precisão final igual ou superior ao requisito da fase.

Derrota:
precisão final inferior ao requisito da fase.
```

## 13.3 Ponto Crítico

O valor de **15%** parece muito baixo para um jogo de ritmo convencional.

Ele pode significar uma destas interpretações:

1. o jogador precisa acertar pelo menos 15% das notas;
2. o jogador pode errar no máximo 15% das notas;
3. o jogador precisa acertar mais de 85% das notas;
4. a fase possui uma barra de sobrevivência, e perder 15% das notas causa derrota;
5. 15% é apenas um valor de protótipo.

Esta decisão deve ser confirmada antes do balanceamento.

## 13.4 Modelo Recomendado

Para o MVP:

```text
Casual: 50% de precisão mínima
Normal: 70% de precisão mínima
Difícil: 80% de precisão mínima
Expert: 90% de precisão mínima
```

Uma alternativa é utilizar uma **Barra de Performance**, em vez de avaliar somente no final.

## 13.5 Barra de Performance — Proposta

- começa em 50%;
- acertos aumentam a barra;
- erros reduzem a barra;
- chegar a 0% encerra a música;
- terminar acima do limite mínimo concede vitória.

Esse modelo cria tensão durante toda a música.

---

# 14. DIFICULDADE

## 14.1 Variáveis de Dificuldade

A dificuldade pode ser controlada por:

- número de lanes;
- quantidade de teclas;
- velocidade das notas;
- densidade de notas;
- presença de acordes;
- presença de notas sustentadas;
- largura das janelas de acerto;
- penalidade por tecla errada;
- exigência mínima de precisão;
- intensidade dos modificadores;
- padrões polirrítmicos;
- mudanças de BPM;
- duração da música.

## 14.2 Níveis Propostos

### Iniciante

- 4 lanes;
- notas simples;
- baixa densidade;
- janela de tempo ampla;
- sem penalidade por tecla extra.

### Normal

- 4 a 6 lanes;
- notas simples e sustentadas;
- densidade moderada;
- penalidade leve.

### Difícil

- 6 a 8 lanes;
- acordes;
- sequências rápidas;
- janela menor;
- penalidade por input extra.

### Expert

- 8 lanes;
- padrões complexos;
- mudanças de velocidade;
- notas especiais;
- modificadores severos.

## 14.3 Curva Durante a Run

Cada etapa deve aumentar ao menos uma dimensão de dificuldade, mas não todas simultaneamente.

Exemplo:

```text
Fase 1: leitura
Fase 2: velocidade
Fase 3: densidade
Fase 4: acordes
Fase 5: modificador especial
Chefe: combinação controlada dos elementos anteriores
```

---

# 15. ESTRUTURA ROGUELITE

## 15.1 Definição

Uma run é composta por uma sequência de músicas e eventos.

O jogador começa com:

- atributos-base;
- nenhuma ou uma melhoria inicial;
- uma quantidade definida de recursos defensivos;
- um repertório inicial.

Ao vencer uma fase, escolhe uma recompensa que vale até o fim da run.

## 15.2 Estrutura Proposta de Run

```text
ATO 1
- 2 músicas
- 1 evento
- 1 mini-chefe

ATO 2
- 2 músicas
- 1 loja ou evento
- 1 mini-chefe

ATO 3
- 1 música de preparação
- 1 chefe final
```

Total proposto:

- 6 a 8 músicas;
- 2 a 4 eventos;
- 1 ou 2 mini-chefes;
- 1 chefe final.

## 15.3 Seleção de Rota

Após algumas fases, o jogador pode escolher entre caminhos.

Exemplo:

```text
CAMINHO SEGURO
Música mais fácil
Recompensa comum

CAMINHO TÉCNICO
Música com notas sustentadas
Recompensa focada em precisão

CAMINHO DE RISCO
Música mais difícil
Recompensa rara
```

## 15.4 Recompensas

Após uma vitória:

- apresentar três melhorias;
- o jogador escolhe uma;
- as demais são descartadas;
- rerolls podem existir como recurso limitado.

## 15.5 Categorias de Build

### Virtuoso

Foco em precisão.

Exemplos:

- Perfects valem mais;
- janelas de Perfect levemente maiores;
- sequência de Perfects concede bônus;
- Good deixa de conceder combo.

### Showman

Foco em Fever.

Exemplos:

- Fever carrega mais rápido;
- Fever dura mais;
- Fever pode acumular cargas;
- ativação cria uma onda que melhora notas próximas.

### Improvisador

Foco em risco e adaptação.

Exemplos:

- notas aleatórias valem mais;
- teclas podem mudar;
- recompensas aumentam conforme a complexidade;
- erros custam mais.

### Sobrevivente

Foco em segurança.

Exemplos:

- primeiro Miss não quebra combo;
- recuperação de Barra de Performance;
- escudo contra falha;
- cura entre músicas.

### Maestro

Foco em controle da pista.

Exemplos:

- redução temporária de velocidade;
- visualização antecipada;
- conversão de acordes em arpejos;
- reorganização de lanes.

## 15.6 Raridades Propostas

- Comum;
- Incomum;
- Raro;
- Épico;
- Lendário.

A raridade não deve significar apenas “número maior”. Upgrades raros devem mudar decisões ou regras.

## 15.7 Sinergias

Exemplo:

```text
Pulso Perfeito
Perfects geram +10% de Fever.

Encore
Ativar Fever aumenta a janela de Perfect durante 3 segundos.

Apoteose
Cada Perfect durante Fever prolonga o Fever em 0,1 segundo.
```

As três melhorias formam uma build coerente.

## 15.8 Upgrades com Trade-off

Exemplos:

### Mãos Velozes

- notas descem 15% mais rápido;
- pontuação total aumenta 25%.

### Palco Escuro

- a pista fica parcialmente oculta;
- Perfects geram o dobro de Fever.

### Sem Segunda Chance

- Miss causa penalidade elevada;
- Full Combo concede recompensa lendária.

---

# 16. MÚSICAS-CHEFE

## 16.1 Objetivo

Chefes são músicas que alteram regras, e não apenas músicas mais rápidas.

## 16.2 Exemplos de Mecânicas

### O Metrônomo

- altera o BPM em blocos;
- testa adaptação de tempo.

### O Dissonante

- muda temporariamente o mapeamento visual;
- exige leitura atenta.

### A Maestrina

- alterna entre mãos esquerda e direita;
- cria padrões de resposta.

### O Silêncio

- remove parte do feedback sonoro;
- exige confiança visual e memória rítmica.

## 16.3 Regras de Justiça

Toda mecânica de chefe deve:

- ser apresentada antes de causar punição severa;
- ter feedback antecipado;
- possuir versão simplificada em fase anterior;
- respeitar acessibilidade;
- não depender de informação invisível.

---

# 17. EVENTOS ROGUELITE

## 17.1 Tipos de Evento

- escolha narrativa curta;
- troca de recurso por upgrade;
- cura;
- loja;
- treino;
- desafio de precisão;
- aposta de pontuação;
- remix de música;
- alteração de rota.

## 17.2 Exemplo

### Afinador Misterioso

> Um afinador antigo promete corrigir qualquer execução, mas exige que você abandone parte de sua energia de palco.

Escolhas:

- ampliar a janela de Great, mas reduzir ganhos de Fever;
- manter a build;
- arriscar uma recompensa aleatória.

---

# 18. RECURSOS DA RUN

## 18.1 Barra de Performance

Representa a capacidade de continuar tocando.

## 18.2 Moeda Temporária

Nome provisório: **Aplausos**.

Obtida por:

- concluir músicas;
- atingir ranks;
- cumprir desafios;
- escolher rotas arriscadas.

Utilizada em:

- lojas;
- rerolls;
- cura;
- remoção de penalidades;
- compra de upgrades.

## 18.3 Recurso de Reroll

Nome provisório: **Encore**.

Permite trocar as opções de recompensa após uma fase.

## 18.4 Escudos ou Vidas

Decisão em aberto:

- a run termina ao perder uma música;
- ou o jogador possui uma quantidade limitada de chances.

**Recomendação inicial:** uma derrota encerra a run, mas upgrades podem oferecer uma única recuperação.

---

# 19. PROGRESSÃO PERMANENTE

## 19.1 Possibilidades

A progressão permanente pode desbloquear:

- novas músicas;
- novos personagens;
- novos estilos visuais;
- novos conjuntos de upgrades;
- novos modificadores;
- novos níveis de dificuldade;
- novas rotas;
- modos de desafio;
- cosméticos.

## 19.2 Princípio de Balanceamento

A progressão permanente não deve transformar habilidade em irrelevância.

Priorizar:

- variedade;
- novas opções;
- novos estilos;
- conteúdo;
- conveniência.

Evitar:

- bônus permanentes excessivos de pontuação;
- aumento permanente de janelas de tempo;
- vantagens que invalidem rankings competitivos.

## 19.3 Perfis ou Arquétipos

O jogador pode selecionar um perfil inicial.

Exemplos:

- Virtuoso: melhor precisão;
- Showman: Fever inicial;
- Improvisador: recompensa extra por risco;
- Maestro: controle de pista.

**Status:** Opcional.

---

# 20. MODOS DE JOGO

## 20.1 Run Roguelite

Modo principal.

- sequência de músicas;
- melhorias temporárias;
- derrota encerra a run;
- chefe final;
- progressão e estatísticas.

## 20.2 Música Livre

- escolha direta de música;
- escolha de dificuldade;
- sem upgrades roguelite;
- foco em pontuação e treino.

## 20.3 Treino

- velocidade ajustável;
- repetição de trechos;
- visualização de Early/Late;
- sem derrota;
- metrônomo opcional.

## 20.4 Desafio Diário

- seed fixa;
- mesma sequência para todos;
- ranking diário;
- build e músicas predefinidas.

## 20.5 Modo Infinito

- músicas e padrões contínuos;
- dificuldade crescente;
- objetivo de sobrevivência.

## 20.6 Editor de Fases

Pós-MVP.

- importar ou selecionar música;
- posicionar notas;
- validar BPM;
- testar chart;
- exportar chart;
- compartilhar código ou arquivo.

---

# 21. CONTEÚDO MUSICAL

## 21.1 Fonte das Músicas

Decisão obrigatória em aberto.

Possibilidades:

1. trilhas originais;
2. biblioteca royalty-free;
3. músicas licenciadas;
4. músicas geradas ou assistidas por IA;
5. upload local pelo jogador;
6. catálogo híbrido.

## 21.2 Requisitos de Cada Música

Cada faixa deve possuir:

- identificador;
- título;
- artista;
- duração;
- BPM;
- compassos;
- offset inicial;
- arquivo de áudio;
- chart por dificuldade;
- intensidade;
- tags;
- prévia;
- imagem de capa;
- licença e origem;
- volume normalizado.

## 21.3 Estrutura de Chart Conceitual

```json
{
  "songId": "song_001",
  "difficulty": "normal",
  "bpm": 120,
  "offsetMs": 350,
  "notes": [
    {
      "timeMs": 1250,
      "lane": 0,
      "key": "A",
      "type": "tap"
    }
  ]
}
```

Este exemplo é conceitual, não uma decisão final de arquitetura.

## 21.4 Geração de Charts

### Manual

- maior controle;
- melhor qualidade;
- custo de produção maior.

### Automática

- análise de batidas;
- geração por intensidade;
- criação rápida de variações.

### Híbrida — Recomendada

```text
IA/algoritmo gera rascunho
  ↓
ferramenta valida BPM e sincronização
  ↓
designer revisa padrões
  ↓
playtest humano
  ↓
publicação
```

---

# 22. IA COMO ACELERADOR

## 22.1 Princípio

A IA deve acelerar tarefas de produção sem substituir:

- direção criativa;
- validação humana;
- playtest;
- licenciamento;
- decisão final de balanceamento;
- responsabilidade sobre conteúdo.

## 22.2 Usos Recomendados

### Design

- gerar alternativas de upgrades;
- detectar redundâncias;
- sugerir sinergias;
- criar matrizes de balanceamento;
- revisar clareza de regras.

### Conteúdo Musical

- auxiliar na detecção de BPM;
- identificar batidas e seções;
- gerar charts preliminares;
- criar versões por dificuldade;
- apontar trechos inconsistentes.

### Arte e UX

- explorar direções visuais;
- gerar referências;
- criar variações de ícones;
- revisar contraste e legibilidade;
- auxiliar na produção de placeholders.

### Desenvolvimento

- implementar protótipos;
- gerar testes automatizados;
- revisar código;
- documentar sistemas;
- criar ferramentas internas;
- acelerar refactors controlados.

### QA

- simular padrões de input;
- testar charts;
- detectar notas impossíveis;
- identificar picos de dificuldade;
- gerar relatórios de consistência.

### Balanceamento

- analisar telemetria;
- comparar taxa de falha;
- identificar upgrades dominantes;
- sugerir ajustes;
- agrupar perfis de jogadores.

## 22.3 Limites

O jogo não deve depender de uma chamada de IA em tempo real para:

- reconhecer inputs;
- julgar notas;
- calcular pontuação;
- manter sincronização;
- validar vitória;
- funcionar no núcleo da partida.

O core deve ser determinístico e reproduzível.

## 22.4 Rastreabilidade

Toda saída de IA utilizada em conteúdo publicado deve registrar:

- ferramenta ou modelo;
- finalidade;
- versão;
- revisão humana;
- licença;
- data;
- responsável pela aprovação.

---

# 23. INTERFACE E HUD

## 23.1 HUD Durante a Música

Elementos obrigatórios:

- pista de notas;
- Linha de Execução;
- teclas/lanes;
- feedback de julgamento;
- combo atual;
- multiplicador;
- barra de Fever;
- Barra de Performance ou indicador de condição;
- progresso da música;
- pausa;
- acessibilidade visual ativa, quando aplicável.

## 23.2 Hierarquia Visual

Ordem de prioridade:

1. nota atual;
2. Linha de Execução;
3. próxima sequência;
4. feedback de acerto;
5. Barra de Performance;
6. Fever;
7. combo;
8. pontuação;
9. efeitos cosméticos.

## 23.3 Tela de Resultado

Deve exibir:

- vitória ou derrota;
- pontuação;
- precisão;
- rank;
- Perfects;
- Greats;
- Goods;
- Misses;
- combo máximo;
- Fever ativado;
- bônus;
- recorde anterior;
- gráfico Early/Late;
- recompensa recebida.

## 23.4 Tela de Recompensa

- três cartas de upgrade;
- nome;
- ícone;
- descrição;
- raridade;
- categoria;
- impacto numérico;
- sinergias existentes;
- comparação com build atual;
- opção de reroll, caso disponível.

---

# 24. DIREÇÃO VISUAL

## 24.1 Objetivo

A estética deve unir:

- piano;
- palco;
- música;
- energia de arcade;
- clareza funcional;
- elementos de fantasia roguelite.

## 24.2 Direções Possíveis

### Arcade Neon

- alto contraste;
- cores pulsantes;
- visual contemporâneo;
- fácil associação com ritmo.

### Teatro Mágico

- piano como artefato;
- palco vivo;
- upgrades como partituras encantadas;
- chefes musicais.

### Minimalismo Gráfico

- fundo limpo;
- notas muito legíveis;
- efeitos precisos;
- baixo custo de produção.

**Direção ainda em aberto.**

## 24.3 Regras Visuais

- cada lane deve possuir identidade clara;
- letras devem ser legíveis em movimento;
- notas não devem depender apenas de cor;
- efeitos precisam respeitar a pista;
- o jogador deve poder reduzir partículas;
- o Fever deve intensificar a cena sem comprometer leitura.

---

# 25. DIREÇÃO DE ÁUDIO

## 25.1 Camadas

- música principal;
- efeitos de acerto;
- efeitos de erro;
- feedback de combo;
- ativação de Fever;
- interface;
- ambiência;
- voz do apresentador, caso exista.

## 25.2 Feedback de Acerto

O feedback sonoro precisa ser:

- curto;
- sincronizado;
- ajustável;
- opcional;
- não conflitante com a música.

## 25.3 Mixagem

Controles separados:

- volume master;
- música;
- efeitos;
- interface;
- voz;
- metrônomo.

## 25.4 Latência

A reprodução deve utilizar agendamento de áudio adequado para navegador.

A lógica de notas deve ser sincronizada ao relógio de áudio, e não depender exclusivamente do frame visual.

---

# 26. CALIBRAÇÃO

## 26.1 Objetivo

Compensar diferenças entre:

- dispositivo de áudio;
- monitor;
- navegador;
- sistema operacional;
- teclado;
- percepção individual.

## 26.2 Fluxo Proposto

1. tocar pulsos sonoros;
2. solicitar que o jogador pressione uma tecla no ritmo;
3. repetir várias vezes;
4. calcular média;
5. separar offset de áudio e offset visual, quando possível;
6. salvar configuração;
7. permitir ajuste manual.

## 26.3 Configurações

- offset global;
- velocidade visual;
- tamanho das notas;
- posição da Linha de Execução;
- intensidade de efeitos;
- volume de feedback.

---

# 27. ACESSIBILIDADE

## 27.1 Visual

- modo para daltonismo;
- símbolos além de cores;
- alto contraste;
- tamanho ajustável de notas;
- redução de flashes;
- redução de partículas;
- fundo simplificado;
- opção de desativar movimento de câmera;
- fontes legíveis.

## 27.2 Motora

- remapeamento completo de teclas;
- modos com menos lanes;
- tolerância ajustável;
- modo sem penalidade por tecla extra;
- ativação automática de Fever;
- possibilidade de usar apenas uma mão.

## 27.3 Auditiva

- pista visual completa;
- metrônomo visual;
- pulsos de tela opcionais;
- representação visual de batida;
- nenhuma informação crítica exclusivamente sonora.

## 27.4 Cognitiva

- tutorial progressivo;
- instruções curtas;
- previsibilidade de ícones;
- modo treino;
- redução de elementos do HUD;
- velocidade ajustável.

## 27.5 Fotossensibilidade

- limitar flashes;
- oferecer modo seguro;
- evitar padrões pulsantes agressivos;
- apresentar aviso quando necessário.

---

# 28. TUTORIAL

## 28.1 Objetivo

Ensinar jogando, não por blocos extensos de texto.

## 28.2 Sequência Proposta

### Etapa 1 — Uma tecla

- apresentar uma lane;
- ensinar timing;
- mostrar Perfect, Great e Miss.

### Etapa 2 — Quatro teclas

- introduzir mão esquerda e direita;
- ensinar leitura da pista.

### Etapa 3 — Combo

- explicar multiplicador;
- demonstrar quebra de combo.

### Etapa 4 — Fever

- preencher barra;
- ativar;
- mostrar aumento de pontuação.

### Etapa 5 — Roguelite

- concluir música;
- selecionar uma melhoria;
- jogar pequeno trecho alterado pela melhoria.

## 28.3 Critério de Conclusão

O tutorial deve validar que o jogador:

- acertou uma sequência;
- entendeu Early/Late;
- ativou Fever;
- escolheu um upgrade;
- concluiu uma pequena música.

---

# 29. RETENÇÃO E REJOGABILIDADE

## 29.1 Sistemas Possíveis

- desafio diário;
- conquistas;
- rankings;
- seeds;
- histórico de runs;
- coleção de músicas;
- desbloqueio de skins;
- missões;
- recordes por chart;
- modo semanal;
- modificadores rotativos.

## 29.2 Evitar

- obrigação de login para primeiro uso;
- punição por não jogar diariamente;
- sistemas de energia;
- FOMO excessivo;
- progressão artificialmente lenta.

---

# 30. MONETIZAÇÃO

## 30.1 Status

Em aberto.

## 30.2 Modelos Possíveis

### Gratuito

- jogo completo;
- financiamento externo;
- adequado para portfólio ou aquisição de audiência.

### Premium

- compra única;
- sem anúncios;
- acesso completo ao catálogo base.

### Expansões

- pacotes de músicas;
- novos atos;
- temas visuais;
- personagens.

### Cosméticos

- skins de pista;
- efeitos de nota;
- pianos;
- palcos;
- avatares.

## 30.3 Restrições Recomendadas

Nunca vender:

- janelas de acerto maiores para ranking competitivo;
- multiplicadores de pontuação;
- revives ilimitados;
- vantagens que invalidem habilidade.

---

# 31. PERSISTÊNCIA

## 31.1 Dados Locais

Para o MVP, salvar localmente:

- configurações;
- calibração;
- recordes;
- músicas desbloqueadas;
- conquistas;
- histórico resumido;
- progresso;
- preferências de acessibilidade.

## 31.2 Conta Online

Pós-MVP, caso necessária para:

- ranking;
- sincronização;
- desafios diários;
- compartilhamento;
- recuperação de progresso.

## 31.3 Princípio

O primeiro acesso deve ser jogável sem cadastro.

---

# 32. REQUISITOS TÉCNICOS DE GAME DESIGN

Esta seção não substitui um documento de arquitetura.

## 32.1 Determinismo

Com a mesma:

- seed;
- música;
- chart;
- build;
- sequência de inputs;

o resultado deve ser reproduzível.

## 32.2 Sincronização

- usar o relógio de áudio como fonte principal;
- separar simulação lógica de renderização;
- evitar lógica crítica baseada apenas em FPS;
- registrar timestamps de input;
- suportar compensação de offset.

## 32.3 Performance

Meta proposta:

- 60 FPS em hardware desktop comum;
- resposta de input consistente;
- sem alocação excessiva durante a música;
- pré-carregamento de áudio e chart;
- degradação visual antes de degradação lógica.

## 32.4 Resolução

- layout responsivo;
- suporte primário a 1280×720 ou superior;
- pista central preservada em diferentes proporções;
- modo tela cheia opcional.

## 32.5 Pausa e Foco

Ao perder foco:

- modo solo pode pausar automaticamente;
- ranking competitivo pode invalidar a tentativa;
- áudio deve ser interrompido com segurança;
- retorno deve exigir confirmação.

---

# 33. TELEMETRIA

## 33.1 Objetivo

Medir dificuldade, clareza e balanceamento.

## 33.2 Eventos Importantes

- início da música;
- conclusão;
- abandono;
- derrota;
- julgamento por nota;
- Early/Late;
- quebra de combo;
- ativação de Fever;
- upgrade escolhido;
- upgrade ignorado;
- rota escolhida;
- morte por fase;
- duração da run;
- erro de carregamento;
- queda de FPS;
- offset de calibração.

## 33.3 Métricas

- taxa de conclusão por música;
- precisão média;
- taxa de derrota por trecho;
- distribuição Early/Late;
- uso de Fever;
- upgrades mais escolhidos;
- win rate por build;
- duração média de run;
- taxa de abandono;
- retenção;
- charts com picos anormais.

## 33.4 Privacidade

- coletar apenas o necessário;
- informar o jogador;
- permitir recusa;
- anonimizar dados;
- respeitar legislação aplicável.

---

# 34. MVP

## 34.1 Objetivo do MVP

Provar que o núcleo de Piano Hero é:

- responsivo;
- legível;
- divertido;
- sincronizado;
- capaz de sustentar uma pequena run.

## 34.2 Escopo do MVP

### Conteúdo

- 3 músicas originais ou liberadas;
- 2 dificuldades;
- 4 lanes;
- 1 pista visual;
- 1 tema;
- 1 música-chefe simples.

### Mecânicas

- notas simples;
- julgamento Perfect/Great/Good/Miss;
- combo;
- pontuação;
- Fever;
- precisão;
- vitória e derrota;
- pausa;
- calibração básica.

### Roguelite

- run de 3 músicas;
- escolha de 1 entre 3 upgrades;
- 12 upgrades;
- 3 categorias de build;
- 1 evento simples;
- derrota encerra run.

### Interface

- menu principal;
- configurações;
- tutorial;
- HUD;
- resultado;
- recompensa;
- vitória;
- derrota.

### Persistência

- configurações;
- calibração;
- recordes locais;
- histórico simples.

## 34.3 Fora do MVP

- login;
- multiplayer;
- ranking online;
- editor;
- upload de música;
- gamepad;
- MIDI;
- monetização;
- mobile;
- acordes complexos;
- progressão narrativa extensa;
- grande quantidade de cosméticos;
- IA em tempo real.

---

# 35. ROADMAP PROPOSTO

## Gate 0 — Validação do Ritmo

Entregáveis:

- uma música;
- uma lane;
- input;
- sincronização;
- feedback de julgamento;
- ferramenta de offset.

Critério:

> O jogador percebe os acertos como sincronizados e justos.

## Gate 1 — Vertical Slice Musical

Entregáveis:

- quatro lanes;
- uma música completa;
- combo;
- score;
- Fever;
- resultado.

Critério:

> A música é divertida sem sistemas roguelite.

## Gate 2 — Mini-Run

Entregáveis:

- três músicas;
- upgrades;
- progressão entre fases;
- vitória e derrota;
- persistência local.

Critério:

> As escolhas alteram perceptivelmente a forma de jogar.

## Gate 3 — Conteúdo e Balanceamento

Entregáveis:

- charts por dificuldade;
- categorias de build;
- chefe;
- eventos;
- telemetria.

Critério:

> Não existe uma única build claramente dominante.

## Gate 4 — Polimento

Entregáveis:

- arte final;
- áudio final;
- acessibilidade;
- tutorial;
- performance;
- compatibilidade de navegador.

Critério:

> O jogo está pronto para teste público.

---

# 36. CRITÉRIOS DE ACEITAÇÃO DO CORE

## 36.1 Sincronização

- a mesma nota deve ser julgada consistentemente;
- o resultado não pode variar por queda visual de frame;
- calibração deve alterar o julgamento;
- inputs devem registrar timestamp próprio.

## 36.2 Legibilidade

- jogador identifica a tecla antes da Linha de Execução;
- letras permanecem legíveis em velocidade padrão;
- Fever não encobre notas;
- contraste atende ao padrão definido.

## 36.3 Pontuação

- cada nota é julgada uma única vez;
- Miss quebra combo conforme regra;
- Fever multiplica somente eventos válidos;
- resultado total corresponde ao log da partida.

## 36.4 Roguelite

- upgrades são aplicados imediatamente;
- efeitos acumulados são visíveis;
- escolhas não oferecidas não afetam a run;
- seed reproduz a mesma sequência de recompensas.

## 36.5 Persistência

- calibração permanece após recarregar;
- recorde é atualizado corretamente;
- dados corrompidos não impedem o jogo de iniciar.

---

# 37. RISCOS DE DESIGN

## 37.1 Latência de Navegador

**Risco:** sensação de injustiça.

**Mitigação:**

- Web Audio;
- calibração;
- testes multi-browser;
- timestamps;
- tolerâncias ajustáveis;
- telemetria de offset.

## 37.2 Confusão entre Digitação e Ritmo

**Risco:** o jogo parecer um teste de teclado, e não uma performance musical.

**Mitigação:**

- lanes fixas;
- padrões associados à música;
- feedback sonoro;
- charts desenhados musicalmente;
- redução de letras variáveis no MVP.

## 37.3 Roguelite Desconectado do Core

**Risco:** upgrades aumentarem apenas números.

**Mitigação:**

- upgrades que mudam regras;
- categorias de build;
- trade-offs;
- chefes que valorizam builds distintas.

## 37.4 Efeitos Prejudicando Leitura

**Risco:** Fever tornar o jogo pior.

**Mitigação:**

- efeitos atrás da pista;
- modo reduzido;
- testes de contraste;
- limites de partículas.

## 37.5 Direitos Autorais

**Risco:** uso indevido de músicas.

**Mitigação:**

- trilhas originais;
- biblioteca licenciada;
- controle de origem;
- registro de licença;
- política clara para conteúdo do usuário.

## 37.6 Charts Gerados sem Qualidade

**Risco:** notas tecnicamente sincronizadas, mas musicalmente ruins.

**Mitigação:**

- geração híbrida;
- revisão humana;
- validação automática;
- playtests;
- métricas por trecho.

---

# 38. RISCOS DE ESCOPO

Evitar incluir cedo demais:

- multiplayer;
- editor público;
- upload irrestrito;
- IA generativa em tempo real;
- dezenas de tipos de notas;
- narrativa extensa;
- marketplace;
- mobile;
- integração MIDI;
- ranking competitivo antes de resolver latência e anti-cheat.

---

# 39. BACKLOG INICIAL DE UPGRADES

## 39.1 Precisão

### Toque de Seda — Comum

Aumenta levemente a janela de Great.

### Ouvido Absoluto — Raro

A cada cinco Perfects consecutivos, o próximo Great conta como Perfect.

### Técnica Impecável — Épico

Perfects valem mais, mas Goods quebram o combo.

## 39.2 Fever

### Palco Aquecido — Comum

Fever carrega mais rapidamente.

### Solo Estendido — Raro

Fever dura mais dois segundos.

### Bis — Lendário

A primeira ativação de Fever em cada música não consome a barra imediatamente por dois segundos.

## 39.3 Combo

### Ritmo Crescente — Comum

O multiplicador aumenta um estágio mais cedo.

### Não Pare Agora — Raro

O primeiro Miss acima de 50 combo não quebra completamente a sequência.

### Perfeccionista — Épico

Combo cresce duas vezes mais rápido com Perfects, mas não cresce com Goods.

## 39.4 Sobrevivência

### Fôlego — Comum

Recupera pequena quantidade de Performance após a música.

### Segunda Chance — Raro

Uma vez por run, sobreviva a uma falha com Performance mínima.

### Última Nota — Épico

Ao chegar perto da derrota, a velocidade visual diminui por alguns segundos. O áudio permanece normal.

## 39.5 Risco

### Dobro ou Nada — Raro

Aumenta pontuação e penalidade de Miss.

### Partitura Oculta — Épico

Notas aparecem mais tarde, mas valem mais.

### Concerto Impossível — Lendário

A dificuldade da próxima música aumenta e sua recompensa será obrigatoriamente rara ou superior.

---

# 40. EXEMPLO DE RUN

## Início

O jogador seleciona o arquétipo **Showman**:

- Fever começa 10% carregado.

## Música 1

- dificuldade baixa;
- foco em leitura;
- jogador vence com rank B.

Escolha:

- Palco Aquecido;
- Toque de Seda;
- Fôlego.

O jogador escolhe **Palco Aquecido**.

## Música 2

- maior densidade;
- Fever ativa duas vezes.

Recompensa:

- Solo Estendido;
- Ritmo Crescente;
- Dobro ou Nada.

O jogador escolhe **Solo Estendido**.

## Evento

O Afinador Misterioso oferece:

- ampliar a janela de Great;
- reduzir ganho de Fever.

O jogador recusa para proteger a build.

## Chefe

O chefe possui uma seção longa de alto valor.

O jogador guarda Fever para essa seção, ativa no momento estratégico e maximiza pontuação.

Esse exemplo demonstra que o Fever deixa de ser apenas um bônus automático e se torna uma decisão de run.

---

# 41. IDENTIDADE E NOMENCLATURA PROVISÓRIA

| Elemento | Nome provisório |
|---|---|
| Jogo | Piano Hero |
| Barra de multiplicador | Fever |
| Moeda de run | Aplausos |
| Reroll | Encore |
| Vida/desempenho | Barra de Performance |
| Upgrades | Talentos, Técnicas ou Partituras |
| Chefes | Maestros, Virtuoses ou Ícones |
| Run | Concerto, Turnê ou Apresentação |
| Fase | Música, Palco ou Ato |

A nomenclatura final deve seguir a direção narrativa e visual.

---

# 42. DECISÕES CONFIRMADAS

- o jogo se chama **Piano Hero**;
- será executado em navegador;
- o gênero combina ritmo musical e roguelite;
- o core utiliza Button Quick Time Event;
- notas descem pela tela;
- cada nota corresponde a uma tecla do teclado;
- acertar no ritmo gera pontuação;
- acertos preenchem uma barra de Fever;
- Fever está relacionado a multiplicador;
- existe condição de vitória e derrota baseada em desempenho;
- IA deve atuar como acelerador do processo de criação.

---

# 43. DECISÕES PROVISÓRIAS

- pista com lanes fixas;
- quatro lanes no MVP;
- quatro julgamentos;
- Fever manual no roguelite;
- run de três músicas no MVP;
- escolha de um entre três upgrades;
- Barra de Performance;
- uma derrota encerra a run;
- progressão local sem login;
- músicas originais ou licenciadas;
- IA não participa do core em tempo real;
- dificuldade mínima acima de 15%, até confirmação.

---

# 44. LACUNAS CRÍTICAS

As seguintes decisões bloqueiam o fechamento da versão 1.0 do GDD:

1. interpretação correta dos 15%;
2. modelo de lanes e teclas;
3. forma de ativação do Fever;
4. condição exata de derrota;
5. estrutura da run;
6. origem das músicas;
7. progressão permanente;
8. direção visual;
9. modo principal de pontuação ou sobrevivência;
10. papel exato da IA na produção;
11. público e dificuldade inicial;
12. modelo de monetização;
13. presença de narrativa ou personagens;
14. suporte futuro a mobile, gamepad ou MIDI;
15. necessidade de ranking online.

---

# 45. GLOSSÁRIO

**BPM:** batidas por minuto.  
**Chart:** mapa temporal de notas de uma música.  
**Combo:** sequência de acertos sem falha.  
**Fever:** estado temporário de multiplicador e intensificação.  
**Input:** ação realizada pelo jogador em um dispositivo de controle.  
**Judgement/Julgamento:** avaliação temporal de um input.  
**Lane:** faixa vertical pela qual as notas descem.  
**Offset:** compensação de tempo entre áudio, vídeo e input.  
**QTE:** evento que exige uma ação específica em uma janela de tempo.  
**Roguelite:** estrutura de partidas com progressão por run, aleatoriedade e repetição.  
**Run:** tentativa completa do início até vitória ou derrota.  
**Seed:** valor usado para reproduzir uma sequência procedural.  
**Telemetria:** dados coletados para compreender uso, falhas e balanceamento.

---

# 46. RESUMO DE PRODUÇÃO

A prioridade de Piano Hero deve ser:

```text
SINCRONIZAÇÃO
  ↓
SENSAÇÃO DE ACERTO
  ↓
LEGIBILIDADE
  ↓
PONTUAÇÃO E FEVER
  ↓
MÚSICA COMPLETA
  ↓
UPGRADES
  ↓
RUN ROGUELITE
  ↓
CONTEÚDO
  ↓
POLIMENTO
```

Nenhum sistema roguelite deve ser considerado concluído antes de o gameplay musical isolado ser divertido, justo e tecnicamente consistente.

---

# 47. PERGUNTAS PARA FECHAR O GDD

## Regras fundamentais

1. Quando você escreveu **15%**, quis dizer que o jogador precisa acertar pelo menos 15% das notas, que pode errar no máximo 15%, ou que precisa acertar pelo menos 85%?
2. A derrota acontece apenas no final da música ou pode acontecer durante a execução quando uma barra chega a zero?
3. Uma derrota encerra toda a run ou o jogador possui vidas/tentativas?
4. O objetivo principal deve ser sobreviver, atingir uma nota mínima ou buscar a maior pontuação?

## Controles e notas

5. Cada lane terá sempre a mesma tecla, como `A S D F J K L ;`, ou as letras mudarão a cada nota?
6. Quantas teclas você imagina no jogo-base: 4, 6, 8 ou uma região maior do teclado?
7. O jogo terá apenas notas de toque ou também notas sustentadas, acordes e sequências?
8. O Fever será ativado automaticamente ou o jogador escolherá o momento de ativar?

## Estrutura roguelite

9. Quantas músicas devem formar uma run completa?
10. O jogador escolherá caminhos em um mapa ou seguirá uma sequência linear?
11. Os upgrades devem durar somente durante a run ou existirão melhorias permanentes?
12. Você quer personagens/arquétipos com vantagens iniciais?
13. O jogo terá chefes musicais com regras próprias?

## Música e conteúdo

14. As músicas serão originais, licenciadas, royalty-free, geradas com IA ou enviadas pelo jogador?
15. Você pretende permitir que o jogador importe uma música própria?
16. Os charts serão feitos manualmente, gerados por IA/algoritmo ou produzidos de forma híbrida?
17. O jogo deve ensinar noções reais de piano/música ou apenas utilizar a fantasia de tocar piano?

## Identidade

18. Qual direção visual você imagina: arcade neon, piano clássico, teatro mágico, desenho cartunesco, minimalismo ou outra?
19. Existe protagonista, banda, rival, maestro ou narrativa?
20. O tom deve ser competitivo, divertido, épico, aconchegante ou cômico?

## Produto

21. O jogo será gratuito, premium ou terá expansões?
22. Precisa funcionar offline depois do primeiro carregamento?
23. Haverá login, ranking, desafio diário ou compartilhamento de resultados?
24. O foco inicial é desktop com teclado ou você já quer considerar mobile, gamepad e teclado MIDI?
25. Qual é a duração ideal de uma música e de uma run completa?

---

**Fim do documento — versão 0.1**
