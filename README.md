# 2i-REDES-M4-FP01-14733 - Projeto de Cancelas Automáticas (Arduino)

## Descrição Geral

Este repositório contém o código e os ficheiros de suporte para um projeto de **Cancela Automática de Estacionamento** implementado com Arduino.

O projeto demonstra o controlo de um servo motor através de um botão, simulando a abertura e fecho de uma cancela de estacionamento.

## Funcionalidades Principais

*   **Controlo de Cancela:** Utiliza um servo motor para simular a abertura e fecho da cancela.
*   **Acionamento por Botão:** A cancela é acionada (aberta) quando um botão é pressionado, simulando a passagem de um veículo.
*   **Temporização:** A cancela permanece aberta por 3 segundos antes de fechar automaticamente.
*   **Feedback Serial:** Mensagens de status são enviadas para a porta serial para monitorização.

## Componentes Necessários

Para replicar este projeto, serão necessários os seguintes componentes:

| Componente | Descrição |
| :--- | :--- |
| **Arduino** | Qualquer placa compatível (e.g., Uno, Nano) |
| **Servo Motor** | Servo motor padrão (conectado ao pino digital 9) |
| **Botão (Push Button)** | Botão de pressão (conectado ao pino digital 2) |
| **Fios e Protoboard** | Para as ligações elétricas |

## Estrutura do Projeto (Website de Apresentação)

O projeto inclui um website estático de demonstração para apresentar o projeto e a equipa.

| Ficheiro/Diretório | Descrição |
| :--- | :--- |
| `projetos.html` | Contém a descrição detalhada do projeto da cancela automática. |
| `index.html` | Página de "Equipa de Projeto" (possívelmente a página principal do website de apresentação). |
| `contacto.html` | Página de contactos. |
| `css/style.css` | Ficheiro de estilos CSS. |
| `js/script.js` | Ficheiro JavaScript (atualmente vazio). |
| `images/` | Contém imagens de membros da equipa e de projetos. |

### Detalhes do Código HTML e CSS

O website é construído com ficheiros HTML simples e uma estrutura modular, conforme a descrição original do projeto:

*   **Estrutura Modular:** Cada página (`index.html`, `projetos.html`, `contacto.html`) segue uma estrutura bem definida com secções de **cabeçalho (`<header>`)**, **conteúdo principal (`<main>`)** e **rodapé (`<footer>`)**.
*   **Estilização:** O estilo CSS é aplicado de forma mista:
    *   **CSS Incorporado:** A maior parte do CSS está incorporada diretamente na *tag* `<style>` dentro dos ficheiros HTML.
    *   **Design Responsivo Básico:** É utilizada a propriedade `grid-template-columns: repeat(auto-fit, minmax(220px, 1fr))` para garantir uma adaptação básica a diferentes tamanhos de ecrã (design responsivo).
*   **Navegação:** Todas as páginas contam com uma barra de navegação consistente no cabeçalho, ligando as páginas de "Início", "Projetos" e "Contacto".

## Como Usar (Simulação Arduino)

A lógica de funcionamento está descrita no `projetos.html`:

1.  **Incluir a Biblioteca:** O código utiliza a biblioteca `Servo.h`.
2.  **Conexões:**
    *   Servo Motor → Pino Digital 9
    *   Botão → Pino Digital 2
3.  **Lógica:**
    *   No `setup()`, o servo é inicializado a 0 graus (fechado) e o pino do botão como `INPUT`.
    *   No `loop()`, o Arduino monitoriza o estado do botão:
        *   Se o botão for pressionado, o servo gira para 90 graus (abre).
        *   Aguarda 3 segundos (`delay(3000)`).
        *   O servo retorna para 0 graus (fecha).
        *   Mensagens de status são enviadas via Serial.
