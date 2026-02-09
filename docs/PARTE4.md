# PARTE 4 - Exercício Prático: Sistema de Gerenciamento de Biblioteca

## Dinâmica em Sala de Aula

### Objetivo Geral

Construir um SRS completo para um **Sistema de Gerenciamento de Biblioteca** através de colaboração entre stakeholders e analistas, simulando um projeto real.

## Objetivos Específicos

1. Praticar a análise e documentação de requisitos de software
2. Simular colaboração entre stakeholders e equipe de desenvolvimento
3. Construir um SRS estruturado
4. Exercitar técnicas de elicitação de requisitos
5. Desenvolver habilidades de comunicação técnica

## Estrutura de Grupos

### Composição
- **5 a 6 pessoas por grupo**
- Todos os papéis devem ser representados

### Papéis e Responsabilidades

#### 1. **Facilitador**
- **Responsabilidade:** Coordena a discussão e garante que todos participem
- **Atividades:**
  - Distribui tempo equitativamente
  - Certifica que todos têm voz
  - Mantém foco nos objetivos
  - Documenta decisões importantes
  - Resolve conflitos construtivamente

#### 2. **Stakeholders** (2 pessoas)
- **Responsabilidade:** Representam os usuários do sistema (bibliotecários, estudantes, professores)
- **Perspectivas:**

**Bibliotecário:**
- Precisa gerenciar acervo
- Controlar empréstimos e devoluções
- Cobrar multas
- Manter informações de usuários
- Gerar relatórios de uso

**Estudante:**
- Precisa encontrar livros
- Renovar empréstimos online
- Verificar multas pendentes
- Acessar histórico de leituras
- Reservar livros

**Professor:**
- Precisa de lista de leituras obrigatória
- Acesso rápido a materiais
- Relatório de uso em turmas

#### 3. **Analistas de Requisitos** (2 pessoas)
- **Responsabilidade:** Elicitar e documentar os requisitos
- **Atividades:**
  - Fazer perguntas esclarecedoras
  - Traduzir necessidades em requisitos
  - Classificar em funcionais e não-funcionais
  - Priorizar
  - Documentar no template

## Cronograma da Dinâmica (~60 minutos)

### **Parte 1: Preparação** (~5 minutos)
- Divisão em grupos
- Atribuição de papéis
- Distribuição de materiais (MIRO board, post-its virtuais)
- Leitura rápida do propósito

### **Parte 2: Levantamento de Requisitos** (~20 minutos)

#### Fase A: Stakeholders Falam (10 min)
Os stakeholders **listam suas necessidades e expectativas** para o sistema.

**Exemplos de Necessidades por Stakeholder:**

**Bibliotecário:**
- "Preciso cadastrar novos livros com agilidade"
- "Preciso controlar empréstimos e devoluções"
- "Preciso saber quem tem livros vencidos"
- "Preciso gerar relatórios de acervo"
- "Preciso bloquear usuários com multas"

**Estudante:**
- "Quero buscar livros por vários critérios"
- "Quero renovar empréstimos online"
- "Quero saber se tem livro disponível"
- "Quero ver meu histórico de leituras"
- "Quero receber notificações de vencimento"

**Professor:**
- "Quero criar listas de leituras obrigatórias"
- "Quero que meus alunos encontrem fácil os livros"
- "Quero relatório de quem pegou os livros"

#### Fase B: Analistas Fazem Perguntas (10 min)
Os **analistas de requisitos fazem perguntas** para esclarecer as necessidades.

**Exemplos de Perguntas:**

Para o Bibliotecário:
- "Quais informações são necessárias para cadastrar um livro?"
  - Respostas esperadas: código, título, autor, ISBN, data de publicação, editora, quantidade, localização na prateleira
- "Como o sistema deve lidar com livros duplicados?"
- "Como o sistema deve calcular multas por atraso?"
- "Qual é o prazo máximo de empréstimo?"

Para o Estudante:
- "Por quais critérios você quer buscar livros?"
  - Respostas esperadas: título, autor, ISBN, palavra-chave, categoria
- "Como você quer renovar empréstimos?"
- "Com quanto tempo antes você quer notificação?"

Para o Professor:
- "Como você quer estruturar a lista de leituras?"
- "Quem pode ver suas listas de leitura?"
- "Como você quer acompanhar o uso?"

**Use post-its (virtuais) para anotar cada requisito identificado.**

### **Parte 3: Classificação e Priorização** (~10 minutos)

#### Passo 1: Classificar (5 min)

Organize os requisitos em:

**Requisitos Funcionais (O QUE):**
- "O sistema DEVE permitir cadastro de livros"
- "O sistema DEVE permitir busca por autor"
- "O sistema DEVE registrar empréstimos"
- "O sistema DEVE calcular multas"
- "O sistema DEVE renovar empréstimos online"

**Requisitos Não-Funcionais (COMO):**
- "O sistema DEVE processar buscas em menos de 2 segundos"
- "O sistema DEVE criptografar dados de login"
- "A interface DEVE ser simples e intuitiva"
- "O sistema DEVE funcionar em navegador web"
- "O sistema DEVE estar disponível 24/7"

**Restrições:**
- "Deve ser desenvolvido em Java"
- "Orçamento máximo: R$ 50.000"
- "Deve estar pronto em 6 meses"
- "Deve estar em conformidade com LGPD"

#### Passo 2: Priorizar (5 min)

Use escala simples:

| Nível | Descrição | Exemplos |
|-------|-----------|----------|
| **ALTA** | Crítico para operação | Cadastro, empréstimo, devolução |
| **MÉDIA** | Importante mas não crítico | Renovação, relatórios |
| **BAIXA** | Nice-to-have | Notificações, recomendações |

**Matriz de Priorização:**

```
┌─────────────────────────────────────┬──────────┐
│ Requisito                           │ Prioridade│
├─────────────────────────────────────┼──────────┤
│ Cadastro de livros                  │ ALTA     │
│ Empréstimo                          │ ALTA     │
│ Devolução                           │ ALTA     │
│ Búsqueda de livros                  │ ALTA     │
│ Cálculo de multas                   │ MÉDIA    │
│ Renovação online                    │ MÉDIA    │
│ Relatórios estatísticos             │ BAIXA    │
│ Notificações automáticas            │ BAIXA    │
└─────────────────────────────────────┴──────────┘
```

### **Parte 4: Documentação no SRS** (~10 minutos)

Organize os requisitos no **template simplificado do MIRO:**

```
SISTEMA DE GERENCIAMENTO DE BIBLIOTECA
Data: 04/02/2026
Grupo: [Nome do Grupo]

═══════════════════════════════════════════════════════════

REQUISITOS FUNCIONAIS

RF-001: Cadastro de Livros
├─ Prioridade: ALTA
├─ Descrição: O sistema DEVE permitir cadastro de novos livros com os seguintes campos obrigatórios: código, título, autor, ISBN
├─ Ator: Bibliotecário
└─ Caso de Uso: Cadastrar Livro

RF-002: Busca de Livros
├─ Prioridade: ALTA
├─ Descrição: O sistema DEVE permitir busca de livros por título, autor, ISBN ou palavra-chave
├─ Ator: Estudante, Professor
└─ Critério de Aceitação: Resultado em menos de 2 segundos

RF-003: Registrar Empréstimo
├─ Prioridade: ALTA
├─ Descrição: O sistema DEVE registrar empréstimos com data de empréstimo e prazo de devolução
├─ Ator: Bibliotecário
└─ Restrição: Máximo 5 livros por usuário

RF-004: Calcular Multa
├─ Prioridade: MÉDIA
├─ Descrição: O sistema DEVE calcular multa diária de R$ 2,00 por dia de atraso
├─ Ator: Sistema (automático)
└─ Pós-condição: Multa vinculada ao usuário

═══════════════════════════════════════════════════════════

REQUISITOS NÃO-FUNCIONAIS

RNF-001: Performance
├─ Descrição: O sistema DEVE processar operações de busca em menos de 2 segundos
└─ Métrica: Tempo de resposta < 2s para 95% das requisições

RNF-002: Segurança
├─ Descrição: O sistema DEVE autenticar usuários com login e senha
└─ Implementação: Criptografia SHA-256 para senhas

RNF-003: Disponibilidade
├─ Descrição: O sistema DEVE estar disponível 24/7 com máximo 1 hora de downtime por mês
└─ SLA: 99.5% de disponibilidade

═══════════════════════════════════════════════════════════

RESTRIÇÕES

REST-001: Tecnologia
├─ Descrição: Deve ser desenvolvido em Java 11 ou superior
└─ Justificativa: Padrão da empresa

REST-002: Prazo
├─ Descrição: Sistema deve estar pronto em 6 meses
└─ Data Limite: 04/08/2026

REST-003: Conformidade
├─ Descrição: Deve estar em conformidade com LGPD
└─ Validação: Auditoria externa
```

### **Parte 5: Apresentação e Feedback** (~15 minutos)

#### Apresentação (8 min)
Cada grupo apresenta:
1. **Stakeholders representados** (Quem fez as solicitações?)
2. **Requisitos funcionais coletados** (Principais 3-5)
3. **Requisitos não-funcionais** (Restrições identificadas)
4. **Priorização** (O que é crítico?)
5. **Desafios encontrados** (O que foi difícil?)

#### Feedback (7 min)
**Professor e demais grupos fornecem feedback:**
- "Vocês consideraram requisitos de segurança?"
- "Todos os requisitos são verificáveis?"
- "Há conflitos entre requisitos?"
- "A priorização faz sentido?"
- "Faltou pensar em algo?"

## Exemplo de Resultado Final

### Requisitos Coletados - Grupo A

**Funcionalidades Críticas:**
- Cadastro de livros (código, título, autor, ISBN, categoria, quantidade)
- Empréstimo com prazo máximo de 14 dias
- Devolução e cálculo automático de multa (R$ 2/dia)
- Busca avançada (por autor, título, categoria)
- Renovação online (máximo 2x, se sem multa)

**Não-Funcionais:**
- Performance: Resposta em < 2 segundos
- Segurança: Senha criptografada, LGPD
- Dados: Backup diário automatizado
- 📱 Interface: Web-based, responsiva

## 🎓 Aprendizados Esperados

1. **Elicitação de Requisitos:** Como fazer boas perguntas
2. **Comunicação Técnica:** Traduzir necessidades em linguagem técnica
3. **Priorização:** O que é realmente importante
4. **Documentação:** Como deixar claro para a equipe técnica
5. **Colaboração:** Diferentes perspectivas enriquecem soluções

---

**Reflexão Final:** *"O sucesso de um projeto começa com a compreensão clara do que precisa ser feito."*
