Aqui está uma proposta de **README.md** elegante e detalhada, projetada para refletir a estética minimalista e "espacial" do seu jogo **LUMINO**.

O arquivo destaca as mecânicas únicas (como a geração determinística de fases) e as funcionalidades de debug incluídas no código.

-----

# 💡 LUMINO - Puzzle Diário

**LUMINO** é um jogo de quebra-cabeça lógico minimalista inspirado no clássico "Lights Out". O objetivo é simples: acender todas as luzes do tabuleiro. O jogo apresenta um sistema de progressão diária, onde novas fases são desbloqueadas a cada 24 horas, criando uma experiência de hábito para o jogador.

 

## 🎮 Como Jogar

1.  **O Objetivo:** Transforme todos os quadrados escuros em quadrados **Azuis Brilhantes (Acesos)**.
2.  **A Mecânica:** Ao tocar em um quadrado, ele e seus vizinhos diretos (cima, baixo, esquerda, direita) invertem o estado (de aceso para apagado, e vice-versa).
3.  **O Desafio:** Encontre a sequência correta de toques para iluminar o tabuleiro completo.

## ✨ Funcionalidades Principais

  * **📅 Progressão Diária (Time-Gating):** O jogo calcula quantos dias se passaram desde o "lançamento" para liberar novas fases progressivamente.
  * **🎲 Geração Determinística (Seeded RNG):** Utiliza um algoritmo de números pseudo-aleatórios com "sementes". Isso garante que a **Fase 5** seja idêntica para todos os jogadores do mundo, mas diferente da Fase 4.
  * **🧠 Solubilidade Garantida:** O algoritmo de geração começa com o tabuleiro resolvido e aplica movimentos aleatórios para embaralhá-lo. Isso garante matematicamente que todo puzzle tem solução.
  * **📱 Mobile First:** Layout responsivo, prevenção de zoom/scroll elástico e feedback tátil (vibração) em dispositivos suportados.
  * **💾 Save Automático:** O progresso do jogador é salvo localmente no navegador (`localStorage`).

## 🛠️ Tecnologias Utilizadas

O projeto é um **Monólito Front-end** (Single File Component), ideal para hospedagem simples (GitHub Pages, Vercel, Netlify).

  * **HTML5:** Estrutura semântica.
  * **Tailwind CSS (CDN):** Estilização utilitária para o design "Dark Mode" e efeitos de brilho (Glow).
  * **JavaScript (Vanilla):** Lógica do jogo, manipulação de datas e renderização do grid.
  * **Canvas Confetti:** Biblioteca leve para o efeito de vitória.

## 🚀 Como Executar

Não é necessária instalação ou servidor Node.js.

1.  Baixe o arquivo `index.html`.
2.  Abra-o em qualquer navegador moderno (Chrome, Edge, Safari, Firefox).
3.  Jogue\!

## 🔧 Ferramentas de Debug (Desenvolvedor)

O código inclui um painel de controle oculto no menu principal para facilitar testes:

  * **Slider de Tempo:** Localizado abaixo da lista de fases.
      * Permite "viajar no tempo" simulando a passagem de dias.
      * Arraste para desbloquear fases futuras instantaneamente (ex: simular que estamos no dia 30 para testar a fase 30).

## 🧩 Estrutura do Código

  * `state`: Objeto global que gerencia o dia atual, progresso do usuário e estado do tabuleiro.
  * `class SeededRNG`: O motor matemático que garante que os puzzles sejam consistentes baseados no número do nível.
  * `toggleLogic()`: A lógica central do estilo "Lights Out" (inverte o alvo e a cruz adjacente).
  * `generateBoard()`: Cria o nível aplicando engenharia reversa (começa ganho e bagunça).

## 🎨 Personalização

Para alterar a dificuldade ou a quantidade de fases, edite as constantes no início da tag `<script>`:

```javascript
const TOTAL_LEVELS = 60; // Quantidade total de fases
// Ajuste a dificuldade mudando o tamanho do grid na função startLevel:
// state.gridSize = 3 (3x3), 4 (4x4) ou 5 (5x5)
```

-----

*Desenvolvido com foco em estética e lógica.*
