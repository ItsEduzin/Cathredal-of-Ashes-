# 🏛️ Cathedral of Ashes 

## Visão Geral e Estética do Projeto 
O jogo transporta dois jogadores para o interior de uma catedral profanada e coberta de cinzas. A direção de arte adota uma paleta estritamente sombria sendo o foco principal do tema do jogo:

**Preto (#0A0A0A)**: Domina os fundos e a escuridão dos cenários, trazendo o tom de isolamento.

**Cinza (#2A2A2A / #8C8C8C)**: Representa as pedras góticas da catedral, as bordas das cartas e elementos de interface.

**Vermelho (#8B0000 / #FF2400)**: Destaca pontos críticos do combate, como vida (HP), efeitos de dano, rituais de ataque e ativação de habilidades ativas.

## ⚜️ Classes, Equilíbrio e Mecânicas de Combate
O jogo possui 6 classes jogáveis, cada uma com sua ilustração única em alto contraste e um ciclo fechado de Vantagens (+30% de dano ou redução) e Desvantagens:
| **Classe** | **Vantagem Contra** | **Desvantagem Contra** | **Passiva Especial (Lado 9 do d9)** |
| :--- | :--- | :--- | :--- |
| Vampiro | Cavaleiro | Clérigo | Duplica roubo de vida no próximo ataque. |
| Clérigo | Vampiro, Necromante | Bárbaro | Cria um escudo que anula 100% do dano. |
| Cavaleiro | Lobisomem, Bárbaro | Vampiro | Contra-ataque automático (50% do dano). |

 ## 🎲 A Mecânica do Dado d9 (Dado de 9 Lados)
A cada turno, além de jogar uma carta da mão, o jogador realiza a rolagem de um dado de 9 lados (com valores de 1 a 9). Se o dado resultar no número 9, a Passiva Especial da classe é ativada instantaneamente, alterando o rumo da partida.

## Arquitetura de Sistemas Distribuídos
O projeto foi construído sob uma arquitetura Cliente-Servidor em Tempo Real, preparada para suportar a execução simultânea em duas máquinas conectadas em rede (ou em abas separadas na mesma máquina):

**[ Front-end: PC 1 ]**  <--- WebSockets (STOMP / SockJS) --->  [ Back-end: Java / Spring Boot ]  <--->  [ PostgreSQL ]

**[ Front-end: PC 2 ]**  <-----------------------------------------------+

## Principais Conceitos Aplicados:
- Servidor Central Autoritativo: O Back-end em Java/Spring Boot controla o estado global do jogo (GameState), processa rolagens do d9, valida regras de cartas, aplica bônus de classe e calcula a vida dos jogadores.

- Comunicação Event-Driven via WebSockets: As jogadas tomadas na Máquina 1 são enviadas ao servidor e transmitidas instantaneamente para a Máquina 2 sem recarregar a página (page refresh).

- Camada de Persistência: O banco de dados PostgreSQL registra partidas, histórico de duelos e dados dos jogadores.

## 💻 Tecnologias Utilizadas
- Back-end: Java 17+, Spring Boot, Spring WebSocket (STOMP), Spring Data JPA.

- Front-end: HTML5, CSS3 (Theme Darkwood em Preto, Cinza e Vermelho), JavaScript ES6+, SockJS & STOMP Client.

- Banco de Dados: PostgreSQL.

- Controle de Versão: Git & GitHub.
