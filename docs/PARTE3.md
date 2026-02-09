# PARTE 3 - SRS e Artefatos de Software

## O Artefato SRS

### Software Requirements Specification (SRS)

**Definição:** Documento que especifica de forma clara, detalhada e estruturada os requisitos do sistema, servindo como um **contrato entre os stakeholders** (clientes, usuários, desenvolvedores, etc.) e a equipe de desenvolvimento.

## Propósito do SRS

O SRS deve:

### 1. **Especificar**
- O QUE o sistema deve fazer
- Requisitos Funcionais
- Funcionalidades detalhadas

### 2. **Definir**
- COMO o sistema deve fazer (restrições e propriedades)
- Requisitos Não-Funcionais
- Limitações e conformidades

### 3. **Ser Completo**
- Conter todas as funcionalidades necessárias
- Não deixar lacunas críticas
- Cobrir todos os casos de uso

### 4. **Ser Consistente**
- Sem conflitos entre requisitos
- Sem ambiguidades
- Linguagem padronizada

### 5. **Ser Verificável**
- Cada requisito deve ser testável
- Deve ser possível validar se foi atendido
- Critérios de aceitação claros

### 6. **Ser Modular**
- Organizado logicamente
- Separado por funcionalidades ou componentes
- Fácil navegação

### 7. **Ser Rastreável**
- Cada requisito tem origem identificada
- Possível vincular a documentos de origem
- Manutenção de histórico

## Fluxo de Artefatos em Engenharia de Software

```
┌──────────────────────────────────────────────────┐
│          ARTEFATOS DE ENTRADA                    │
└──────────────────────────────────────────────────┘
                      ↓
┌──────────────────────────────────────────────────┐
│  SICD (System Interface Control Document)       │
│  SSDD (Software System Design Document)         │
│  OCD (Operational Concept Document)             │
│  SSS (Software System Specification)            │
└──────────────────────────────────────────────────┘
                      ↓
          ┌───────────────────┐
          │ FLOWDOWN DE       │
          │ REQUISITOS        │
          └───────────────────┘
          ↙      ↓       ↖
    ┌──────────────────────────────┐
    │  Requisitos do               │
    │  Subsistema 1...N            │
    └──────────────────────────────┘
          ↓
    ┌──────────────────────────────┐
    │  ANÁLISE DE SOFTWARE         │
    │  • TSR (Technical System...)  │
    │  • IDD (Interface Design...)  │
    │  • SRS (Software Requirements)
    └──────────────────────────────┘
          ↓
    ┌──────────────────────────────┐
    │  DI (CSCI) DO SUBSISTEMA     │
    │  • Design do Software         │
    │  • Componentes Técnicas       │
    └──────────────────────────────┘
```

## Estrutura de um SRS

### Seção 1: Introdução
- Propósito do documento
- Escopo do sistema
- Definições, acrônimos e abreviações

### Seção 2: Descrição Geral
- Perspectiva do produto
- Funcionalidades do produto
- Características do usuário
- Restrições gerais

### Seção 3: Requisitos Específicos
- **Requisitos Funcionais:** Organizados por caso de uso ou funcionalidade
- **Requisitos Não-Funcionais:** Desempenho, segurança, usabilidade, etc.
- **Restrições:** Padrões, conformidades, tecnologias

### Seção 4: Apêndices
- Modelos UML
- Prototipagem
- Referências

## Exemplo: Sistema de Gerenciamento de Biblioteca

### Estrutura de Requisitos Funcionais

```
SSS01 - Cadastro e Gestão de Produtos/Livros
├── C01 - O sistema DEVE permitir cadastro de livros
│   └── Campos obrigatórios: código, nome, descrição
├── C02 - O sistema DEVE permitir consulta de livros
│   └── Por código, nome, autor ou categoria
└── C03 - O sistema DEVE permitir alteração de livros
    └── Apenas administrador pode alterar

SSS02 - Gerenciamento de Empréstimos
├── E01 - O sistema DEVE registrar empréstimos
├── E02 - O sistema DEVE permitir renovação
└── E03 - O sistema DEVE calcular multas por atraso

SSS03 - Gerenciamento de Usuários
├── U01 - O sistema DEVE permitir cadastro de usuários
├── U02 - O sistema DEVE autenticar usuários
└── U03 - O sistema DEVE manter histórico de empréstimos

SSS04 - Relatórios
├── R01 - O sistema DEVE gerar relatório de utilizações
├── R02 - O sistema DEVE gerar relatório de multas
└── R03 - O sistema DEVE gerar relatório de acervo
```

## Requisitos Não-Funcionais do Sistema

### Desempenho
- O sistema DEVE processar cadastro de livro em menos de 2 segundos
- O sistema DEVE suportar até 1000 usuários simultâneos

### Segurança
- O sistema DEVE autenticar usuários com login e senha
- O sistema DEVE criptografar dados sensíveis com AES-256
- O sistema DEVE fazer backup automático diário

### Usabilidade
- A interface DEVE ser intuitiva para usuários não-técnicos
- O sistema DEVE estar disponível em português e inglês
- Cada operação DEVE ser completada em no máximo 3 cliques

### Confiabilidade
- O sistema DEVE ter disponibilidade de 99.5%
- O sistema DEVE ter tempo de recuperação após falha de 1 hora
- O sistema DEVE manter integridade referencial dos dados

### Manutenibilidade
- O código DEVE seguir padrões de codificação Java
- O sistema DEVE estar documentado completamente
- O sistema DEVE suportar atualizações com mínimo downtime

## Rastreabilidade de Requisitos

### Matriz de Rastreabilidade

```
┌──────────────────┬──────────┬──────────────┬────────────┐
│ ID do Requisito  │ Origem   │ Status       │ Validação  │
├──────────────────┼──────────┼──────────────┼────────────┤
│ SSS01            │ Cliente  │ Aprovado     │ Testável   │
│ C01              │ SSS01    │ Implementado │ Testável   │
│ C02              │ SSS01    │ Em Teste     │ Testável   │
│ C03              │ SSS01    │ Pendente     │ Testável   │
│ E01              │ Cliente  │ Aprovado     │ Testável   │
│ ...              │ ...      │ ...          │ ...        │
└──────────────────┴──────────┴──────────────┴────────────┘
```

## Checklist para um SRS de Qualidade

- [ ] Todos os requisitos são claros e compreensíveis?
- [ ] Cada requisito é verificável e testável?
- [ ] Há conflitos entre requisitos?
- [ ] Todos os requisitos têm origem rastreável?
- [ ] O documento está bem organizado?
- [ ] Há modelos UML para complexidades significativas?
- [ ] As restrições são realistas e alcançáveis?
- [ ] Os stakeholders aprovaram o documento?

## Próxima Etapa

Na **PARTE 4**, aplicaremos todos esses conceitos em um **exercício prático** onde desenvolveremos um SRS completo para um **Sistema de Gerenciamento de Biblioteca**.

---

**Princípio Fundamental:** *"Um SRS bem estruturado é a base sólida para um projeto de software bem-sucedido."*
