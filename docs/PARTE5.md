# PARTE 5 - Checklist de Validação de Requisitos

## Introdução ao Checklist

Um bom SRS deve passar por rigorosa validação. Este checklist fornece **critérios objetivos** para avaliar a qualidade e conformidade de cada requisito antes da implementação.

## Critérios de Validação

### 1. CONSISTÊNCIA

#### Definição
O requisito pode ser atendido **sem entrar em conflito** com outros requisitos do sistema?

#### Como Verificar
- [ ] O requisito não contradiz outros requisitos?
- [ ] Os requisitos relacionados são compatíveis?
- [ ] Não há imposições conflitantes?

#### Contra-exemplo

**Requisito 1:** "O Sistema DEVE processar no máximo 2000 registros por hora."

**Requisito 2:** "O Sistema DEVE processar no mínimo 48.000 registros por dia."

**Problema:** Estes requisitos são **inconsistentes**. 2.000 registros/hora = máximo 48.000 registros/dia. O requisito 2 não pode ser atendido se o requisito 1 for limitante.

**Solução:** 
- Revisar requisito 1: "O Sistema DEVE processar no mínimo 3.000 registros por hora."
- Ou revisar requisito 2: "O Sistema DEVE processar no máximo 40.000 registros por dia."

#### Contra-exemplo 2

**Requisito A:** "O sistema DEVE criptografar dados com AES-256."

**Requisito B:** "O sistema DEVE processar requisições em menos de 100ms."

**Análise:** Não há conflito – é possível implementar AES-256 com boa performance.

---

### 2️⃣ AUSÊNCIA DE ERROS

#### Definição
O requisito **contém erros** técnicos, lógicos ou de especificação?

#### Como Verificar
- [ ] A especificação técnica está correta?
- [ ] Não há erros lógicos ou algorítmicos?
- [ ] A matemática/lógica está correta?
- [ ] Foram utilizados padrões e algoritmos corretos?

#### Contra-exemplo

**Requisito:** "O Sistema DEVE utilizar a função F(id) = RESTO_DA_DIVISÃO_INTEIRA(id, 2) = 1 para verificar se um número inteiro é par."

**Problema:** **ERRO LÓGICO**
- Um número é **par** se resto da divisão por 2 = **0**
- Um número é **ímpar** se resto da divisão por 2 = **1**
- O requisito especifica verificar paridade ERRADA

**Solução:**
"O Sistema DEVE utilizar a função F(id) = RESTO_DA_DIVISÃO_INTEIRA(id, 2) = 0 para verificar se um número inteiro é par."

#### Contra-exemplo 2

**Requisito:** "O Sistema DEVE utilizar hash SHA-256 para armazenar senhas."

**Validação:** Correto - SHA-256 é algoritmo apropriado para hash de senhas.

---

### 3. RASTREABILIDADE

#### Definição
A **fonte ou origem do requisito é conhecida** e pode ser referenciada através do sistema?

#### Como Verificar
- [ ] Há referência clara à origem do requisito?
- [ ] É possível vincular a documentos de origem?
- [ ] Existe rastreamento de alterações?
- [ ] A justificativa está documentada?

#### Contra-exemplo

**Requisito:** "SSS-050 - O sistema DEVE permitir análise de dados."

**Problemas:**
- Origem não está clara
- Não há referência a stakeholder ou documento
- Justificativa não existe
- Impossível validar com quem solicitou

**Solução:**

**Requisito:** "SSS-050 - O sistema DEVE permitir análise de dados estatísticos de empréstimos (origem: requisição do Bibliotecário em 15/01/2026, discussão com gerente em 20/01/2026). Vinculado à característica 'Relatórios' do documento de escopo."

#### Matriz de Rastreabilidade Exemplo

```
┌────────────┬──────────────┬──────────────┬───────────────────┐
│ Req ID     │ Origem       │ Prioridade   │ Validado com      │
├────────────┼──────────────┼──────────────┼───────────────────┤
│ RF-001     │ Entrevista   │ ALTA         │ Bibliotecário     │
│            │ Bibliotecário│              │ (05/02/2026)      │
│            │ (02/02/2026) │              │                   │
├────────────┼──────────────┼──────────────┼───────────────────┤
│ RF-002     │ Escopo       │ ALTA         │ Estudante         │
│            │ Projeto      │              │ (05/02/2026)      │
│            │ (01/02/2026) │              │                   │
├────────────┼──────────────┼──────────────┼───────────────────┤
│ RNF-001    │ Workshop     │ MÉDIA        │ TI/DevOps         │
│            │ Performance  │              │ (04/02/2026)      │
│            │ (03/02/2026) │              │                   │
└────────────┴──────────────┴──────────────┴───────────────────┘
```

---

### 4. CONCISÃO

#### Definição
O requisito é **simples e claro**? É fácil de entender sem ambiguidades?

#### Como Verificar
- [ ] O requisito é breve (1-2 linhas)?
- [ ] Usa linguagem clara e direta?
- [ ] Evita jargão desnecessário?
- [ ] Cada conceito está definido?
- [ ] Não tenta especificar múltiplas coisas?

#### Contra-exemplo

**Requisito:** "O Sistema DEVE permitir a liberação de notas sempre que as condições propícias tenham sido satisfeitas."

**Problemas:**
- "liberação de notas" não está claro
- "condições propícias" é vago e subjetivo
- Como saber quando está satisfeito?
- Como validar?

**Solução:**

**Requisito:** "O Sistema DEVE permitir que o Professor libere notas para os alunos após finalizar a correção de todas as provas da avaliação."

**Ou ainda mais específico:**

"O Sistema DEVE, quando o Professor marcar a avaliação como 'finalizada', liberar automaticamente as notas para todos os alunos da turma via email e painel."

#### Contra-exemplo 2

**Requisito:** "O sistema DEVE permitir cadastro de usuários com login e senha."

**Validação:** Claro, conciso, específico

---

### 5. CONSTRUTOR PADRÃO

#### Definição
O requisito está na **forma imperativa usando a palavra "DEVE"**? Requisitos indicando objetivos ou intenções não são imperativos.

#### Como Verificar
- [ ] Inicia com "O Sistema DEVE"?
- [ ] Usa imperativo (obrigatório)?
- [ ] Evita "pode", "talvez", "deve tentar"?
- [ ] É claro que é obrigatório?

#### Contra-exemplo - Forma Negativa

**Requisito:** "O Sistema NÃO DEVE permitir acessos não autorizados."

**Problema:** Forma **negativa** é difícil de testar. Como você testa algo que "não deve" acontecer?

**Solução (Forma Positiva):**

**Requisito:** "O Sistema DEVE impedir acessos não autorizados através de autenticação obrigatória."

Ou:

**Requisito:** "O Sistema DEVE validar credenciais do usuário antes de permitir acesso aos dados."

---

## Exemplos Completos de Análise

### Exemplo 1: Requisito Bem Estruturado

```
═══════════════════════════════════════════════════════════
Requisito: RF-003 - Registrar Empréstimo
═══════════════════════════════════════════════════════════

Especificação:
"O Sistema, quando solicitado pelo Bibliotecário, DEVE registrar 
empréstimo de livro com os seguintes dados: ID do usuário, ID do 
livro, data de empréstimo e prazo de devolução (14 dias por padrão), 
atualizando a disponibilidade do livro no acervo."

VALIDAÇÃO:

1. CONSISTÊNCIA
   ✓ Compatível com RF-001 (Cadastro de livros)
   ✓ Compatível com RF-004 (Cálculo de multa)
   ✓ Sem conflitos identificados

2. AUSÊNCIA DE ERROS
   ✓ Lógica correta (registrar + atualizar)
   ✓ Prazo padrão é realista (14 dias)
   ✓ Dados necessários estão especificados

3. RASTREABILIDADE
   ✓ Origem: Entrevista Bibliotecário (02/02/2026)
   ✓ Validado com: Stakeholder Biblioteca (05/02/2026)
   ✓ Vinculado ao caso de uso: "Emprestar Livro"

4. CONCISÃO
   ✓ Descreve uma única funcionalidade
   ✓ Linguagem clara e técnica
   ✓ Sem ambiguidades importantes

5. CONSTRUTOR PADRÃO
   ✓ Usa "O Sistema... DEVE"
   ✓ Forma imperativa
   ✓ Obrigatoriedade clara

RESULTADO: REQUISITO VÁLIDO E PRONTO PARA IMPLEMENTAÇÃO
```

### Exemplo 2: Requisito Melhorado

```
═══════════════════════════════════════════════════════════
Requisito Original (PROBLEMÁTICO):
═══════════════════════════════════════════════════════════

"O Sistema DEVE encriptar mensagens"

PROBLEMAS:
   - Vago: Quais mensagens? Todas?
   - Qual algoritmo?
   - Qual padrão?
   - Como testar?

═══════════════════════════════════════════════════════════
Requisito Melhorado (VÁLIDO):
═══════════════════════════════════════════════════════════

RNF-005 - Criptografia de Dados Sensíveis

"O Sistema DEVE criptografar, segundo o algoritmo AES (Advanced 
Encryption Standard) definido em Federal Information Processing 
Standards (FIPS) Publication 197, dados sensíveis (CPF, RG, 
informações bancárias) armazenados no banco de dados, utilizando 
chaves de 256 bits gerenciadas através de Key Management System."

VALIDAÇÃO COMPLETA:

1. CONSISTÊNCIA:
2. AUSÊNCIA DE ERROS: ✓ (FIPS 197 é padrão real)
3. RASTREABILIDADE: ✓ (Origem: Analista de Segurança)
4. CONCISÃO: ✓ (Específico mas compreensível)
5. CONSTRUTOR PADRÃO: ✓ (DEVE + imperativo)

CRITÉRIO DE ACEITAÇÃO:
- [ ] Dados sensíveis criptografados em repouso
- [ ] Algoritmo AES-256 implementado
- [ ] Chaves gerenciadas seguramente
- [ ] Desempenho não afetado significativamente
- [ ] Conformidade LGPD atingida
```

## Tabela de Verificação por Requisito

Use esta tabela para cada requisito do seu SRS:

```
┌─────────────────────────────────────────────────────────────┐
│ CHECKLIST DE VALIDAÇÃO - Requisito: _____________________ │
├─────────────────────────────────────────────────────────────┤
│ CRITÉRIO          │ SIM □ │ NÃO □ │ N/A □ │ OBSERVAÇÕES     │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Consistente       │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Sem Erros         │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Rastreável        │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Conciso           │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Padrão DEVE       │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ Verificável       │       │       │       │                 │
├───────────────────┼───────┼───────┼───────┼─────────────────┤
│ RESULTADO         │ OK │ REVISAR                      │
└─────────────────────────────────────────────────────────────┘
```

## Prioridade de Correção

Ao encontrar problemas, corrija-os nesta ordem:

1. **CRÍTICO** - Consistência e Erros lógicos
   - Podem quebrar todo o projeto
   - Devem ser corrigidos antes de apresentar

2. **IMPORTANTE** - Rastreabilidade e Padrão
   - Necessários para documentação
   - Devem ser corrigidos antes de implementar

3. **DESEJÁVEL** - Concisão
   - Melhoram clareza
   - Devem ser revistos quando possível

## Processo de Validação Recomendado

```
1. CRIAR REQUISITO
   ↓
2. VALIDAR INTERNAMENTE (próprio grupo)
   ↓
3. VALIDAR COM STAKEHOLDERS
   ↓
4. AJUSTAR COM FEEDBACK
   ↓
5. APROVAÇÃO FINAL
   ↓
6. DOCUMENTAR NO SRS
   ↓
7. ARQUIVAR RASTREABILIDADE
```

**Investir tempo na validação de requisitos economiza **meses** de desenvolvimento e retrabalho.**

---

**Lição Final:** *"Um requisito inválido descoberto cedo é facilmente corrigido. Descoberto durante desenvolvimento, custa caro. Descoberto em produção, é catastrófico."*