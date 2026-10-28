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

## ⚔️ Sistema de Vantagens e Desvantagens (Combat Matrix)

A dinâmica de combate do **Cathedral of Ashes** segue um ciclo tático fundamentado na *lore* de cada classe. Atacar uma classe vulnerável concede bônus de dano e anulação de efeitos passivos.

---

### 📊 Tabela Geral de Conflitos

| Classe | 🟢 Vantagem Contra (+Dano / Anula Efeito) | 🔴 Desvantagem Contra (Recebe +Dano / Efeito Anulado) |
| :--- | :--- | :--- |
| **Necromante** | **Clérigo** *(Mestria Profana)* | **Bárbaro** *(Olho Místico)* |
| **Bárbaro** | **Necromante**, **Cavaleiro** | **Lobisomem** *(Agilidade Bestial)* |
| **Cavaleiro** | **Vampiro** *(Armadura Espectral)* | **Clérigo**, **Bárbaro** |
| **Lobisomem** | **Bárbaro**, **Clérigo** | **Vampiro** *(Dreno de Sangue)* |
| **Clérigo** | **Cavaleiro** *(Purificação/Selamento)* | **Necromante**, **Lobisomem** |
| **Vampiro** | **Lobisomem** *(Regeneração de Sangue)* | **Cavaleiro** *(Sem Sangue Vital)* |

---

### 📜 Justificativa Tática da Lore

#### 1. Necromante
* **Vantagem contra Clérigo:** Por ser filho de Dragon e criador da magia negra original, sua feitiçaria sobrepõe os rituais da igreja, corrompendo as barreiras mágicas do Clérigo.
* **Desvantagem contra Bárbaro:** O olho místico do Bárbaro enxerga a aura de seus feitiços e ilude sua furtividade, deixando o Necromante exposto a ataques físicos devastadores.

#### 2. Bárbaro
* **Vantagem contra Necromante e Cavaleiro:** Seu olho mágico anula as ilusões do Necromante, e sua força bruta com o machado quebra a postura e esmaga as placas da armadura do Cavaleiro.
* **Desvantagem contra Lobisomem:** Sem armadura pesada ou esquiva suficiente, o Bárbaro não consegue conter a velocidade brutal e os acertos críticos do Lobisomem.

#### 3. Cavaleiro
* **Vantagem contra Vampiro:** Como um fantasma selado em uma armadura de ferro sem sangue vital, o Cavaleiro torna a mecânica de dreno e cura do Vampiro completamente inútil.
* **Desvantagem contra Clérigo e Bárbaro:** Sendo uma alma espectral presa, o Cavaleiro é altamente vulnerável aos milagres de selamento do Clérigo e aos golpes pesados do Bárbaro.

#### 4. Lobisomem
* **Vantagem contra Bárbaro e Clérigo:** Sua velocidade sobrenatural supera a defesa física do Bárbaro. Contra o Clérigo, movido pelo ódio à Catedral, o Lobisomem rompe a linha sacerdotal antes do lançamento dos feitiços.
* **Desvantagem contra Vampiro:** O abundante sangue da besta serve como a fonte perfeita para alimentar a praga do Vampiro, que se regenera rapidamente em combates prolongados.

#### 5. Clérigo
* **Vantagem contra Cavaleiro:** Domina os rituais de canalização de almas e magia sagrada, sendo capaz de selar ou banir a névoa fantasmagórica que prende o Cavaleiro à armadura.
* **Desvantagem contra Necromante e Lobisomem:** Fisicamente frágil, o Clérigo é facilmente emboscado pela agilidade do Lobisomem e dominado pela autoridade arcana do Necromante.

#### 6. Vampiro
* **Vantagem contra Lobisomem:** Alimentado pelo sangue alheio devido à maldição das 10 primaveras, ele utiliza a vitalidade da fera para se regenerar no combate.
* **Desvantagem contra Cavaleiro:** Não consegue drenar vida de um guerreiro que não possui sangue em suas veias.

---

### Ciclo de Combate

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
