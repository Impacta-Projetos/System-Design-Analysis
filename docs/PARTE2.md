# PARTE 2 - Engenharia de Requisitos

## 📖 Fundamentos da Engenharia de Requisitos

### O que é Engenharia de Requisitos?

Engenharia de Requisitos é um conjunto de processos e técnicas para **identificar, analisar, especificar e validar as necessidades** que um sistema de software deve atender.

É fundamentalmente uma **atividade colaborativa** entre:
- **Stakeholders:** Representam as partes interessadas (usuários, clientes)
- **Analistas de Requisitos:** Responsáveis por elicitar e documentar os requisitos
- **Equipes Técnicas:** Implementarão as soluções

## 🎯 Diferenças Fundamentais

### Requisitos de Sistema

**Definição:** Descrições claras e detalhadas das necessidades, funcionalidades, restrições e comportamentos que um sistema deve possuir para atender aos objetivos dos stakeholders.

**Características:**
- Nível mais alto de abstração
- Visão holística do sistema completo
- Inclui aspectos não-técnicos
- Foco em objetivos de negócio

**Exemplos:**
- "O sistema deve gerenciar a biblioteca"
- "Deve suportar múltiplos usuários simultaneamente"

### Requisitos de Software

**Definição:** Descrições específicas das necessidades e restrições do software em si, focando em como o sistema de software realizará os requisitos do sistema.

**São divididos em três categorias:**

#### 1. Requisitos Funcionais
**O QUE o software deve fazer**

- Descrevem as funcionalidades do sistema
- Ações e operações que o software deve realizar
- Ligadas diretamente aos casos de uso

**Exemplos:**
- "O software DEVE permitir cadastro de usuários"
- "O software DEVE permitir empréstimo de livros"
- "O software DEVE gerar relatórios mensais"

#### 2. Requisitos Não-Funcionais
**COMO o software deve fazer**

- Desempenho e velocidade
- Segurança e autenticação
- Usabilidade e interface
- Confiabilidade e disponibilidade
- Manutenibilidade e escalabilidade
- Portabilidade e compatibilidade

**Exemplos:**
- "O sistema DEVE processar requisitos em menos de 2 segundos"
- "O sistema DEVE estar disponível 99.9% do tempo"
- "O sistema DEVE criptografar dados sensíveis"
- "A interface DEVE ser acessível para usuários com deficiência visual"

#### 3. Restrições
**Limitações, imposições ou condições específicas**

- Limitações tecnológicas
- Restrições de orçamento
- Conformidade regulatória
- Padrões e protocolos obrigatórios
- Integração com sistemas legados

**Exemplos:**
- "O sistema DEVE ser desenvolvido em Java"
- "O sistema DEVE estar em conformidade com LGPD"
- "O sistema DEVE integrar-se com o ERP existente"

## 📋 Casos de Uso (Use Cases)

### Definição

**Técnica da UML para identificar e detalhar as funcionalidades de um sistema do ponto de vista de quem irá interagir com este sistema.**

### Características

- Focam na perspectiva do usuário (ator)
- Descrevem sequências de interações
- Capturam fluxos principais e alternativos
- Facilitam comunicação com stakeholders

### Estrutura Básica

```
Caso de Uso: [Nome do Caso]
Ator: [Quem interage]
Pré-condição: [Estado antes da execução]
Fluxo Principal:
  1. Ator faz ação
  2. Sistema responde
  3. ...
Fluxo Alternativo:
  2a. [Condição] → [Ação alternativa]
Pós-condição: [Estado após conclusão]
```

### Exemplo: Sistema de Biblioteca

**Caso de Uso: Emprestar Livro**

- **Ator:** Estudante
- **Pré-condição:** Estudante autenticado, livro disponível
- **Fluxo Principal:**
  1. Estudante seleciona livro
  2. Sistema verifica disponibilidade
  3. Sistema registra empréstimo
  4. Sistema atualiza prazo de devolução
  5. Sistema confirma operação
- **Fluxo Alternativo:**
  2a. Livro não disponível → Sistema mostra data prevista de devolução
  3a. Estudante com multas pendentes → Sistema bloqueia empréstimo
- **Pós-condição:** Livro registrado como emprestado

## 🔗 Relacionamento entre os Requisitos

```
┌─────────────────────────────────────────────────────┐
│   REQUISITOS DE SISTEMA (Visão Holística)          │
│                                                      │
│  ┌────────────────────────────────────────────────┐ │
│  │ REQUISITOS DE SOFTWARE                         │ │
│  │                                                 │ │
│  │ ┌──────────────┐  ┌──────────────────────────┐ │ │
│  │ │ FUNCIONAIS   │  │ NÃO-FUNCIONAIS          │ │ │
│  │ │              │  │                         │ │ │
│  │ │ • Cadastro   │  │ • Performance           │ │ │
│  │ │ • Empréstimo │  │ • Segurança             │ │ │
│  │ │ • Devolução  │  │ • Usabilidade           │ │ │
│  │ └──────────────┘  └──────────────────────────┘ │ │
│  │                                                 │ │
│  │ ┌──────────────────────────────────────────────┐ │ │
│  │ │ RESTRIÇÕES                                   │ │ │
│  │ │ • Tecnologia, Orçamento, Conformidade      │ │ │
│  │ └──────────────────────────────────────────────┘ │ │
│  └────────────────────────────────────────────────┘ │
│                                                      │
│  ┌────────────────────────────────────────────────┐ │
│  │ CASOS DE USO (Perspectiva do Usuário)        │ │
│  └────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────┘
```

## ✅ Processo de Engenharia de Requisitos

### 1. Elicitação
- Coleta de necessidades junto aos stakeholders
- Entrevistas, workshops, observação
- Documentação inicial de ideias

### 2. Análise
- Refinamento das necessidades coletadas
- Resolução de conflitos
- Classificação e estruturação

### 3. Especificação
- Documentação formal e clara
- Criação de artefatos (SRS, modelos UML)
- Rastreamento de origem

### 4. Validação
- Verificação com stakeholders
- Checklist de qualidade
- Aprovação formal

### 5. Gerenciamento
- Rastreamento de mudanças
- Manutenção da documentação
- Comunicação de alterações

## 🎯 Próxima Etapa

Na **PARTE 3**, aprenderemos sobre o **SRS (Software Requirements Specification)** e como estruturar e documentar todos esses requisitos de forma profissional e verificável.

---

**Lição Chave:** *"Um requisito bem definido é aquele que é claro, conciso, verificável e aceito por todos os stakeholders."*
