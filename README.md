# ⚔️ Delta Trigger — RPG Textual em Java

**Delta Trigger** é um jogo de RPG em modo texto (console/terminal) desenvolvido em Java, aplicando princípios sólidos de **Programação Orientada a Objetos (POO)** e organização em arquitetura **MVC (Model-View-Controller)**.

## 🎮 Sobre o Jogo

Em **Delta Trigger**, o jogador explora diferentes cenários, gerencia atributos e equipamentos, interage na cidade e enfrenta inimigos em combates estratégicos por turnos diretamente pelo terminal, com suporte a cores ANSI e sistema de salvamento de progresso.

### ✨ Principais Funcionalidades
* **Classes e Personagens:** Diferentes perfis jogáveis (`Guerreiro`, `Elyra`, `Suporte`) herdando comportamentos base de `Personagem`, cada um com seus próprios `Atributos`.
* **Sistema de Batalha por Turnos:** Combates dinâmicos (`Batalha`) com múltiplas ações, cálculo de dano e enfrentamento contra inimigos (`Inimigo`, `Fenrok`, `LoboFactory`).
* **Exploração de Cenários:** Navegação entre diferentes ambientes do mundo (`Cidade`, `Campo`, `Caverna`) baseados na estrutura de `Cenario`.
* **Inventário e Equipamentos:** Gerenciamento de itens consumíveis e equipamentos (`Inventario`, `Item`, `Equipamento`).
* **Sistema de Save:** Persistência de dados do jogador (`SaveService`) para salvar e carregar o progresso da aventura.
* **Interface no Terminal:** Menus interativos (`MenuView`, `CidadeView`), textos externos (`TextoService` / `data/textos.txt`) e estilização com cores (`Cores`).

## 🏗️ Arquitetura e Estrutura do Projeto

O código está organizado seguindo o padrão **MVC** e pacotes utilitários:

```text
├── data/
│   └── textos.txt          # Diálogos e textos narrativos do jogo
├── src/
│   ├── Main.java           # Ponto de entrada da aplicação
│   ├── controller/
│   │   └── JogoController.java  # Controle do fluxo principal e regras do jogo
│   ├── model/
│   │   ├── Personagem.java      # Classe base dos personagens
│   │   ├── Guerreiro.java       # Especialização de classe jogável
│   │   ├── Elyra.java           # Especialização de classe jogável
│   │   ├── Suporte.java         # Especialização de classe jogável
│   │   ├── Inimigo.java         # Estrutura dos inimigos e chefes (Fenrok, LoboFactory)
│   │   ├── Batalha.java         # Lógica de combate por turnos
│   │   ├── Cenario.java         # Base para Cidade, Campo e Caverna
│   │   ├── Inventario.java      # Gerenciamento de Item e Equipamento
│   │   └── Atributos.java       # Status e evolução dos personagens
│   ├── view/
│   │   ├── MenuView.java        # Telas e menus principais no console
│   │   └── CidadeView.java      # Interface de interação na cidade
│   └── util/
│       ├── SaveService.java     # Salvamento e carregamento de progresso
│       └── TextoService.java    # Leitura dos arquivos de texto
```

## 💻 Como Executar

### Pré-requisitos
* Ter o **Java JDK** (versão 8 ou superior) instalado.
* Recomenda-se executar em um terminal com suporte a cores ANSI (como Windows Terminal, Git Bash, VS Code ou terminal Linux/macOS).

### Passo a passo
1. Clone este repositório:
   ```bash
   git clone https://github.com
   ```
2. Acesse a pasta do projeto:
   ```bash
   cd delta-trigger-rpg-java
   ```
3. Compile os arquivos Java para a pasta `out`:
   ```bash
   javac -d out src/Main.java src/controller/*.java src/model/*.java src/view/*.java src/util/*.java
   ```
4. Execute o jogo:
   ```bash
   java -cp out Main
   ```

## 🛠️ Tecnologias e Conceitos Aplicados
* **Java (JDK)**
* **Programação Orientada a Objetos:** Herança, Polimorfismo, Encapsulamento e Padrão Factory (`LoboFactory`).
* **Arquitetura MVC:** Separação clara entre regras de negócio (`model`), exibição no console (`view`) e controle de fluxo (`controller`).
* **Manipulação de Arquivos:** Leitura de roteiro (`textos.txt`) e serialização/persistência de estado (`SaveService`).
