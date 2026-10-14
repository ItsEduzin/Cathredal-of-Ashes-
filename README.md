# 🏛️ Cathedral of Ashes — Dark Fantasy Card Game

> **Cathedral of Ashes** é um jogo de duelo tático de cartas em tempo real (1v1), ambientado num universo *dark fantasy* soturno fortemente inspirado pela atmosfera sufocante de **Darkwood**. Com uma identidade visual marcante focada nas cores **preto, cinza e vermelho sangrento**, o projeto foi projetado e implementado como requisito prático para a disciplina de **Sistemas Distribuídos**.

---

## 🟢 1. O Que Já Foi Definido e Estipulado

### 👁️ Visão Geral e Estética
* **Estilo Visual:** Monocromático em alto contraste (Preto e Cinza) com destaques em Vermelho Sangrento para HP, efeitos e ações de combate.
* **Cenário:** Interior de uma catedral em ruínas coberta de cinzas.
* **Modo de Jogo:** Duelo PvP em tempo real para 2 jogadores (100 HP cada).

### 🎲 Tabela Oficial de Regras do Dado (d9)
O dado de 9 lados ($d9$) atua como o motor de dinamismo e multiplicador de jogadas da partida:

| Dado (d9) | Efeito no Turno | Regras e Condições de Aplicação |
| :--- | :--- | :--- |
| **1 ou 2** | **Azar Extremo (Perde a Vez)** | O jogador é consumido pelas sombras. **Não pode jogar nenhuma carta** no turno e passa a vez imediatamente. |
| **3, 4 ou 5** | **Turno Normal** | Permissão padrão para jogar **1 carta comum** da mão (aplica o dano/efeito base, sem multiplicadores). |
| **6 ou 7** | **Ataque Fortalecido ($\times 2$)** | Permite jogar 1 carta comum, **multiplicando o dano/efeito por 2** ($\times 2$) no resultado final da jogada. |
| **8** | **Gatilho de Carta Bônus / Fortalecido** | • **Se TIVER Carta Bônus na mão:** É a oportunidade de ativá-la! O jogador pode jogar a **Carta Bônus**.<br>• **Se NÃO tiver Carta Bônus:** Pode jogar 1 carta comum com **dano/efeito multiplicado por 2** ($\times 2$). |
| **9** | **Coringa Adaptativo (Regra Especial)** | O efeito adapta-se ao inventário do jogador:<br><br>• **Com 2 Cartas Bônus na mão (Limite Máximo):** Funciona como o **8** (libera o uso de 1 Carta Bônus).<br>• **Com 0 Cartas Bônus na mão:** O jogador joga 1 carta comum e seu **dano/efeito é multiplicado por 3** ($\times 3$).<br>• **Com 1 Carta Bônus na mão (Caindo 2x no 9):** Na primeira ocorrência o jogador pode **usar a Carta Bônus**; na segunda ocorrência (ou se optar por não gastar a bônus), joga 1 carta comum com **dano/efeito multiplicado por 3** ($\times 3$). |

> **Nota de Inventário:** Cada jogador pode ter no máximo **2 Cartas Bônus em mãos** por partida.

### ⚜️ Classes Confirmadas (6)
* Vampiro
* Clérigo
* Cavaleiro
* Lobisomem
* Bárbaro
* Necromante

### 🛠️ Arquitetura e Tecnologias
* **Estrutura:** Monorepo no GitHub (`Cathedral-of-Ashes`).
* **Back-end:** Java 17+, Spring Boot, Spring WebSocket (STOMP), Spring Data JPA.
* **Front-end:** HTML5, CSS3, JavaScript ES6+ (alocado em `src/main/resources/static/`).
* **Banco de Dados:** PostgreSQL.

---

## 🟡 2. O Que Falta Definir (Próximos Passos)

Para avançar para a codificação completa do jogo, os seguintes tópicos precisam ser especificados:

### 📄 A. Catálogo de Cartas Comuns e Cartas Bônus
* Definir os nomes, imagens e valores base das **Cartas Comuns** (ex: *Ataque*, *Defesa/Escudo*, *Cura/Dreno*).
* Definir o efeito especial e o valor exato da **Carta Bônus de cada uma das 6 Classes**.

### ⚔️ B. Regra Prática da Matriz de Vantagens
* Estipular como a vantagem/desvantagem entre as classes será calculada em código (ex: $+50\%$ de dano extra ou alteração no HP inicial do jogador).

### 🗄️ C. Modelagem do Banco de Dados PostgreSQL
* Criar o script SQL (`schema.sql`) com as tabelas de jogadores (`tb_player`) e histórico de partidas (`tb_match`).

### 📡 D. Protocolo WebSocket e Interface
* Estruturar o objeto JSON (`GameState`) transmitido pelo servidor Spring Boot para atualização da interface dos dois clientes em tempo real.
* Desenhar os componentes da interface em HTML/CSS (mesa da catedral, mãos de cartas, dado e contadores de HP).
