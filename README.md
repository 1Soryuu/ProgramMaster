# 🚀 ProgramMaster — Plataforma de Aprendizagem em Programação

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Projeto Integrador](https://img.shields.io/badge/Projeto%20Integrador-FATEC-blue)
![Git](https://img.shields.io/badge/Git-orange?logo=git)
![GitHub](https://img.shields.io/badge/GitHub-black?logo=github)

## 📖 Sobre o Projeto

Este projeto tem como objetivo desenvolver uma **plataforma interativa de aprendizagem de programação**, criada para auxiliar principalmente pessoas que estão iniciando sua jornada no desenvolvimento de software.

A plataforma busca transformar o aprendizado de programação em uma experiência mais **dinâmica, prática e envolvente**, combinando conteúdos educacionais, exercícios e elementos de gamificação.

---

## 🎯 Objetivo

O principal objetivo do projeto é **facilitar o aprendizado de programação para iniciantes**, proporcionando uma experiência que estimule a prática constante e mantenha o usuário motivado durante sua evolução.

A plataforma pretende:

* 🧑‍💻 Auxiliar pessoas que estão começando a programar;
* 📚 Apresentar conteúdos de forma progressiva;
* 🧩 Propor exercícios e desafios práticos;
* 📈 Permitir que o usuário acompanhe sua evolução;
* 🔥 Estimular a criação de uma rotina de estudos;
* 🏆 Criar metas, conquistas e recompensas;
* ⚡ Tornar o processo de aprendizagem mais dinâmico;

---

## 🚀 Funcionalidades Principais

### 1. Autenticação e Perfil Simples
* **Autenticação Segura:** Cadastro e login via OAuth (Google, Apple, etc.).
* **Perfil de Usuário:** Armazenamento do progresso individual diretamente na nuvem.

### 2. Trilha de Aprendizagem Linear
* **Conteúdo Estruturado:** Curso focado nos fundamentos de Python.
* **Mapa de Fases:** Interface gamificada com desbloqueio sequencial de aulas à medida que o aluno avança.
* **Lições em Pílulas (Cards):** Telas curtas com explicações objetivas e diretas, dividindo o conteúdo em micro-etapas de fácil assimilação.

### 3. Motor de Lições e Exercícios Interativos
* **Formatos de Exercícios:**
  * Múltipla escolha.
  * Ordenação de blocos de código/palavras.
  * Preenchimento de lacunas (*fill-in-the-blank*).
* **Feedback Imediato:** Retorno instantâneo de acerto ou erro com explicações curtas.

### 4. Mecânica Básica de Retenção (Gamificação)
* **Contador de Ofensiva (Streak):** Monitoramento de dias consecutivos de estudo para construção de hábitos.
* **Progresso Visual:** Barras de progresso claras por módulo e recompensas visuais ao finalizar cada lição.

---

## Diagramas de sequência e de caso de uso

```mermaid
sequenceDiagram
    autonumber
    actor U as Usuário
    participant App as App Mobile
    participant API as Back-end
    participant AI as Tutor IA

    %% 1. Início
    U->>App: Seleciona a lição
    App->>API: Busca exercícios
    API-->>App: Retorna conteúdo

    %% 2. Resolução & Dúvidas
    U->>App: Executa / Valida exercício
    opt Precisa de ajuda
        U->>App: Pede dica
        App->>AI: Solicita explicação
        AI-->>App: Envia instrução
    end

    %% 3. Conclusão
    U->>App: Conclui a lição
    App->>API: Salva progresso (XP / Streak)
    API-->>App: Confirma e libera próxima fase
```

```mermaid
flowchart LR
    %% Atores
    User(["👤 Aluno / Usuário"])
    AI(["🤖 Tutor IA"])

    subgraph ProgramMaster ["ProgramMaster App"]
        direction TB
        UC01["UC01: Autenticar no App"]
        UC02["UC02: Visualizar Perfil / XP"]
        UC03["UC03: Navegar pela Trilha"]
        UC04["UC04: Realizar Exercícios"]
        UC05["UC05: Executar Sandbox Python"]
        UC06["UC06: Solicitar Dica da IA"]
        UC07["UC07: Gerar Dica Pedagógica"]
        UC08["UC08: Registrar Progresso"]
    end

    %% Relações do Usuário
    User --> UC01
    User --> UC02
    User --> UC03
    User --> UC04

    %% Relações Internas do App
    UC04 -. include .-> UC05
    UC04 -. extend .-> UC06
    UC04 -. include .-> UC08
    UC06 -. include .-> UC07

    %% Relação da IA
    AI --> UC07
```

---

## 🎨 Diretrizes de UI/UX e Gamificação

### 1. Interface de Usuário (UI) e Ergonomia Visual
* **Protagonismo do Código:** A área de código/exercício é o elemento principal da tela, enquanto botões e instruções secundárias são diferenciados por cor e peso.
* **Minimalismo Funcional:** Design limpo e sem distrações visuais desnecessárias para evitar o cansaço mental.
* **Feedback Instantâneo:** Respostas visuais imediatas para ações do usuário (hover em botões, telas de carregamento e avisos de erro/sucesso).

### 2. Retenção de Atenção e UX de Engajamento
* **Onboarding sem Atrito:** Acesso rápido ao valor do app antes de cadastros burocráticos para evitar o abandono inicial.
* **Estado de Fluxo (Flow):** Progressão de dificuldade balanceada para manter o usuário engajado, evitando tédio ou frustração.
* **Microlearning:** Explicações teóricas divididas em blocos curtos, práticos e diretos ao ponto.
* **Lembretes Personalizados:** Notificações focadas na evolução e no progresso real do aluno.

![Dashboard de trilhas](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Dashboard%20de%20trilhas.png)
![Detalhes da fase](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Detalhe%20da%20fase.png)
![Questão de múltipla escolha](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Quest%C3%A3o%20de%20m%C3%BAltipla%20escolha.png)
![Exercício prático de código](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Exerc%C3%ADcio%20pr%C3%A1tico%20de%20c%C3%B3digo.png)
![Resposta incorreta](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Resposta%20incorreta.png)
![Resposta correta](https://github.com/1Soryuu/ProgramMaster/blob/main/PI/Design/Resposta%20correta.png)

A intenção é criar um ambiente no qual o usuário consiga **visualizar sua evolução e estabelecer objetivos**, tornando o aprendizado mais estimulante.

---

## 📚 Estrutura de Aprendizagem

O conteúdo será organizado de maneira progressiva, começando pelos conceitos fundamentais e avançando gradualmente para assuntos mais complexos.

### 🟢 Nível Iniciante

* Algoritmos;
* Lógica de programação;
* Variáveis;
* Tipos de dados;
* Operadores;
* Condicionais;
* Estruturas de repetição;
* Funções.

### 🟡 Nível Intermediário

* Estruturas de dados;
* Manipulação de arquivos;
* Programação orientada a objetos;
* Tratamento de erros;
* Modularização;
* Bibliotecas;
* Projetos práticos.

### 🔴 Nível Avançado

* Estruturas de dados avançadas;
* Algoritmos;
* Arquitetura de software;
* Padrões de projeto;
* APIs;
* Banco de dados;
* Desenvolvimento de projetos.

---

## 🛠️ Tecnologias

### **Front-end & Mobile**
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)

**React Native + Expo:** Simplificam a navegação além de permitirem a reutilização do código Web no mobile.

**JS / TS + React:** Transição suave do React (Web) para o React Native. TypeScript ajuda a evitar erros comuns de digitação em estruturas JSON.

### **Back-end & Infraestrutura**
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=for-the-badge&logo=webassembly&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase_Auth-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

**Pyodide + WebAssembly:** Pyodide permite executar o código Python diretamente no dispositivo do usuário via WebAssembly. Isso reduz o custo de servidor a quase zero e elimina riscos de segurança no Back-end.

**Node.js:** Orquestra as APIs REST de navegação, entrega as lições e chamadas para a LLM (Tutor IA).

**PostgreSQL:** Banco relacional sólido para salvar o progresso das lições, e as ofensivas (streaks).

---

## 🗓️ Roadmap do MVP

- [ ] **Milestone 1: Alinhamento, Design e Base do Projeto**  
  * Protótipo no Figma, setup da estrutura Expo/Node.js, modelagem do PostgreSQL e criação do conteúdo inicial.
- [ ] **Milestone 2: Núcleo do Aplicativo**  
  * Login com Firebase, mapa de fases e motor visual dos 3 tipos de exercícios.
- [ ] **Milestone 3: Gamificação e Sandbox Python**  
  * Contador de Streaks, barra de progresso e integração do Pyodide (WASM) para execução de código.
- [ ] **Milestone 4: Tutor IA**  
  * Engenharia de prompts e integração da LLM para suporte dinâmico no player de exercícios.
- [ ] **Milestone 5: Testes e Lançamento**  
  * Correções de bugs, polimento de UI/UX, deploy da infraestrutura e publicação da versão de teste.
  
---

## 👥 Equipe

| Integrante                       | Função    |
| -------------------------------- | --------- |
| Victor Yamada Miyashiro          | Frontend  |
| Guilherme Gotardo Santana        | Backend   |
| Pedro Vieira Lima                | UI/UX     |
| Matheus Vinicius da Silva Marigo | Backend   |
| João Vitor Maia                  | Conteúdo  |
| Bruno Henrique Viana de Souza    | Backend   |
