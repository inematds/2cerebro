# LLM Knowledge Bases e “Second Brain” com IA

## Visão Geral
O conceito apresentado gira em torno de usar modelos de linguagem (LLMs) para construir uma base de conhecimento pessoal (um “second brain”). A ideia é transformar informações brutas em um sistema estruturado e interconectado que pode ser consultado por agentes de IA.

---

## Arquitetura Principal

A estrutura funciona de forma semelhante a um compilador de código:

### 1. Entrada (Raw Data)
- Artigos, papers, transcrições, etc.
- Armazenados como Markdown (ex: pasta `raw` no Obsidian)

### 2. Processamento (Compiler)
- Um LLM processa os dados
- Gera:
  - Resumos
  - Conexões entre conteúdos
  - Estrutura organizada

### 3. Saída (Wiki)
- Base de conhecimento estruturada
- Conteúdo interligado (backlinks)
- Navegação via grafo (ex: Obsidian Graph View)

### 4. Validação (Health Checks)
- Detecta:
  - Dados desatualizados
  - Links quebrados
  - Lacunas de informação
- Mantém integridade do sistema

### 5. Execução (Query)
- Agente consulta a base
- Usa um arquivo de índice (`index`) como ponto de partida
- Não depende necessariamente de RAG ou banco vetorial

---

## Estrutura de Pastas

```
/raw              → dados brutos
/wiki             → conhecimento processado
/index.mmd        → mapa geral do sistema
/agents.mmd       → regras e contexto para o agente
/daily_logs       → histórico de interações
```

---

## Funcionamento do Sistema

### Fluxo de Dados

1. Dados são coletados (ex: web clipper)
2. Armazenados como Markdown bruto
3. LLM transforma em conhecimento estruturado
4. Conteúdo é interligado
5. Sistema é validado automaticamente
6. Agente consulta e usa esse conhecimento

---

## Versão com Memória Interna (Claude Code)

Uma evolução do sistema usa **dados internos (logs de interação)** em vez de dados externos.

### Como funciona:

- Cada sessão gera logs automáticos
- Hooks capturam interações:
  - Início da sessão
  - Fim da sessão
  - Compactação de memória

### Hooks principais:

- **Session Start**
  - Carrega regras (`agents.mmd`)
  - Carrega índice (`index.mmd`)

- **Session End / Pre-compact**
  - Resume a conversa
  - Salva no log diário

- **Flush diário**
  - Extrai:
    - Conceitos
    - Conexões
  - Atualiza a base de conhecimento

---

## Estrutura de Logs

Cada sessão gera:

- Decisões tomadas
- Lições aprendidas
- Ações futuras
- Contexto técnico

Esses dados são posteriormente promovidos para a base principal (wiki).

---

## Benefícios

- Memória evolutiva do projeto
- Respostas mais rápidas e precisas
- Redução de análise manual de código
- Aprendizado contínuo do agente
- Sistema auto-organizado

---

## Loop de Aprendizado Contínuo

1. Usuário faz uma pergunta
2. Agente consulta a base
3. Gera resposta
4. Resposta vira novo conhecimento
5. Sistema melhora com o tempo

---

## Diferencial

- Não depende de RAG complexo
- Usa Markdown como base
- Navegação via estrutura e índice
- Simples, escalável e eficiente

---

## Conclusão

Esse modelo transforma interações e dados em um sistema vivo de conhecimento, permitindo que agentes de IA se tornem progressivamente mais inteligentes e úteis dentro de um projeto ou contexto específico.
