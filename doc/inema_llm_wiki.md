# LLM Wiki / Second Brain (Resumo INEMA)

## Por que isso é importante?

- Chats de IA são efêmeros — o conhecimento se perde
- Esse método faz o conhecimento acumular como juros
- A IA passa a agir como um “colega” que lembra de tudo

---

## Simplicidade do Sistema

- Funciona em escala pessoal
- Não precisa de:
  - banco vetorial
  - embeddings
  - RAG complexo
- Stack:
  - pastas
  - Markdown
  - Obsidian
- O LLM usa `index.md` para navegar

---

## Estrutura de Arquivos

```
my-wiki/
├── raw/        → conteúdo bruto (somente leitura)
├── wiki/       → conteúdo organizado pelo LLM
│   ├── index.md
│   ├── log.md
│   ├── *.md
└── CLAUDE.md   → regras do sistema
```

---

## Benefícios

- Economia de tokens (~95% em alguns casos)
- Transformação de dados dispersos em conhecimento estruturado
- Foco em “arquivos de ideia” em vez de código
- Integração natural com agentes

---

## Passo a Passo

1. Instalar Obsidian
2. Criar um vault
3. Abrir no VS Code ou ambiente do agente
4. Colar o prompt base
5. Criar estrutura inicial:
   - raw/
   - wiki/
   - index.md
   - log.md
   - CLAUDE.md

---

## Fluxo de Uso

### Ingestão

1. Adicionar conteúdo em `raw`
2. Pedir ao LLM: “ingest this source”
3. O LLM:
   - lê
   - organiza
   - cria páginas
   - conecta
   - atualiza index e log

---

### Iteração

- Continuar adicionando conteúdo
- Repetir ingestão
- Sistema melhora continuamente

---

## Web Clipper

### Função

Capturar conteúdo direto da internet para `raw`

### Benefícios

- evita copiar e colar
- acelera o fluxo
- mantém padrão limpo

### Fluxo

1. Abrir página
2. Clicar na extensão
3. Enviar para `raw`
4. LLM processa

---

## Ideia Central

```
raw → processamento LLM → wiki organizada
```

---

## Ferramentas

- Obsidian
- Web Clipper
- VS Code (opcional)

---

## Prompt Base (EN)

You are now my LLM Wiki agent. Implement this exact idea file as my complete second brain. Guide me step-by-step: create the CLAUDE.md schema file with full rules, set up index.md and log.md, define folder conventions, and show me the first ingest example. From now on, every interaction follows the schema.

---

## Prompt Base (PT-BR)

Agora você é meu agente de Wiki com LLM. Implemente exatamente este arquivo de ideia como meu segundo cérebro completo. Me guie passo a passo: crie o arquivo de esquema CLAUDE.md com todas as regras, configure index.md e log.md, defina convenções de pastas e me mostre o primeiro exemplo de ingestão. A partir de agora, toda interação segue esse esquema.
