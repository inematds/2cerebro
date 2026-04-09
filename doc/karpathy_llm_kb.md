# LLM Knowledge Bases (Karpathy)

## Ideia Central

Ao invés de usar RAG tradicional (buscar trechos de documentos a cada pergunta), a proposta é diferente:

> O LLM constrói e mantém uma wiki persistente.

- O conhecimento **não é reconstruído toda vez**
- Ele é **compilado, organizado e atualizado continuamente**
- A base cresce e melhora com o tempo

---

## Diferença para RAG

### RAG tradicional
- Busca dados brutos a cada query
- Não acumula conhecimento
- Sempre “reaprende” do zero

### LLM Wiki (proposta)
- Conhecimento é **pré-compilado**
- Conexões já existem
- Contradições já foram analisadas
- Sistema melhora continuamente

---

## Conceito-chave

- O LLM atua como um **bibliotecário + compilador**
- O usuário:
  - Escolhe fontes
  - Faz perguntas
- O LLM:
  - Resume
  - Conecta
  - Atualiza
  - Organiza tudo

---

## Arquitetura

### 1. Raw Sources (dados brutos)
- Artigos
- Papers
- Dados
- Imagens

Características:
- Imutáveis
- Fonte da verdade
- Nunca editados pelo LLM

---

### 2. Wiki (base compilada)

- Arquivos Markdown interligados
- Contém:
  - Resumos
  - Conceitos
  - Entidades
  - Comparações
  - Sínteses

Função:
- É a **base de conhecimento real**
- O LLM escreve e mantém tudo

---

### 3. Schema (regras do sistema)

Arquivo tipo:
- `AGENTS.md` ou `CLAUDE.md`

Define:
- Estrutura da wiki
- Convenções
- Fluxos de trabalho

Função:
- Transformar o LLM em um **agente disciplinado**

---

## Operações do Sistema

### 1. Ingest (ingestão)

Fluxo:
1. Adiciona novo documento no raw/
2. LLM lê o conteúdo
3. Gera:
   - resumo
   - páginas novas
   - atualizações em páginas existentes
4. Atualiza index
5. Registra no log

Impacto:
- Um único documento pode atualizar várias páginas

---

### 2. Query (consulta)

Fluxo:
1. LLM lê o index
2. Encontra páginas relevantes
3. Lê essas páginas
4. Gera resposta

Formato de saída:
- Markdown
- Tabela
- Slides
- Gráficos

Importante:
- Respostas podem virar novas páginas

---

### 3. Lint (manutenção)

O LLM faz auditorias:

- Detecta contradições
- Identifica dados desatualizados
- Encontra páginas órfãs
- Sugere novas conexões
- Identifica lacunas de conhecimento

---

## Arquivos Especiais

### index.md
- Catálogo da wiki
- Contém:
  - links
  - resumos curtos
  - organização por categoria

Função:
- Ponto inicial para queries

---

### log.md
- Histórico cronológico

Registra:
- ingestões
- queries
- manutenções

Função:
- Linha do tempo da evolução do conhecimento

---

## Propriedades do Sistema

- Persistente (não perde contexto)
- Incremental (cresce com o tempo)
- Auditável (Markdown legível)
- Interligado (grafo de conhecimento)
- Auto-mantido (LLM atualiza tudo)

---

## Ferramentas Sugeridas

- Obsidian (interface)
- Web Clipper (captura conteúdo)
- Scripts de busca (opcional)
- CLI tools (para escala)

---

## Insight Principal

> O conhecimento vira um artefato compilado.

- Não é só consulta
- É construção contínua

---

## Casos de Uso

- Pesquisa profunda
- Estudo de livros
- Base de conhecimento pessoal
- Times e empresas
- Projetos de longo prazo
- Planejamento e análise

---

## Loop de Crescimento

1. Adiciona informação
2. LLM compila
3. Usuário pergunta
4. Resposta vira conhecimento
5. Sistema melhora

---

## Analogia

- Obsidian = IDE
- Wiki = código
- LLM = programador

---

## Conclusão

Esse modelo transforma o LLM de um chatbot stateless em:

→ um sistema de memória persistente  
→ um motor de conhecimento evolutivo  
→ um “second brain” real
