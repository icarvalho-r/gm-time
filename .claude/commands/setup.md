---
name: setup
description: >
  Configura o workspace pra você usar no dia a dia do time de marketing da Growth Machine.
  Pergunta seu nome e sua função, cria as pastas certas e injeta seu nome em _contexto/empresa.md.
  O contexto da GM e a identidade visual já vêm prontos.
  Use quando chamar /setup ou na primeira vez que abrir o workspace.
---

# /setup — Configuração inicial (time GM)

## Verificação inicial

Antes de qualquer coisa, verifica se `_contexto/empresa.md` já tem o nome de uma pessoa preenchido na seção "Sobre você".

- Se **já tem nome**: avisa "Esse workspace já foi configurado pra [nome]. Quer refazer ou só atualizar a função?"
- Se **não tem nome**: inicia o onboarding abaixo.

---

## Onboarding (primeira vez)

Mensagem de boas-vindas, curta:

> "Vou configurar o Claude pra você usar no dia a dia do time de marketing da GM. Duas perguntas rápidas — em menos de um minuto tá pronto."

Faz as perguntas em sequência, uma por vez. Espera a resposta de cada uma.

### Pergunta 1
"Qual seu nome?"

### Pergunta 2
"Qual sua função no time de marketing da GM?"

Apresenta as opções em conversa, não como lista formal:

> "É editor de vídeo, design, copy, ops/ClickUp, ou outra coisa?"

Se a pessoa responder algo fora dessas quatro (ex: "tráfego", "social media"), confirma a função em texto livre e cria estrutura híbrida ou personalizada.

### Pergunta 3 (opcional)
"O que tá na sua mesa esse mês? Algum projeto, lançamento ou prazo que eu já devo saber?"

Resposta vaga ou "nada específico" tá ok. Se responder algo concreto, salva em `_contexto/estrategia.md`.

---

## Processamento

Com nome e função, executa em sequência:

### 1. Lê o template da função

Lê o arquivo correspondente em `templates/funcoes/`:

- `editor-video` → `templates/funcoes/editor-video.md`
- `design` → `templates/funcoes/design.md`
- `copy` → `templates/funcoes/copy.md`
- `ops/ClickUp` ou `operações` → `templates/funcoes/ops-clickup.md`
- **outra** → criar estrutura mínima (`projetos/`, `tarefas.md`) e perguntar quais pastas adicionar

O template lista: pastas a criar + skills relevantes daquela função.

### 2. Cria as pastas

Cria todas as pastas listadas no template da função na raiz do workspace.

### 3. Preenche `_contexto/empresa.md`

Substitui a seção "Sobre você" no final do arquivo:

```markdown
## Sobre você

**Nome:** [nome]
**Função no time:** [função detectada]
**Responsabilidades:** [extraído do template da função]
```

Não toca no resto do arquivo (todo o contexto da GM tem que ficar preservado).

### 4. Preenche `_contexto/estrategia.md` (se houve resposta na Pergunta 3)

Substitui o campo "Função no time" pelo valor real.
Se a pessoa mencionou projetos/prazos na Pergunta 3, preenche "Foco principal agora" e "Prazos e eventos relevantes".

### 5. Copia skills relevantes pra `.claude/commands/`

Pra cada skill listada no template da função, cria o arquivo de comando em `.claude/commands/[nome-da-skill].md` com este conteúdo:

```markdown
---
name: nome-da-skill
description: [descrição extraída do template da skill]
---

Leia `templates/skills/nome-da-skill.md` e execute as instruções com o contexto e argumentos fornecidos pelo usuário.
```

### 6. Mensagem final

Mensagem curta:

> "[Nome], tá configurado.
>
> Criei as pastas da sua função ([função]):
> [lista das pastas]
>
> Skills disponíveis:
> [lista das skills com / na frente]
>
> Pra começar, roda `/iniciar` toda vez que abrir o workspace — ele puxa o contexto da GM e do seu foco atual.
>
> Pra salvar seu trabalho no GitHub, roda `/syncar` (configura na primeira vez)."

---

## Regras

- Tom direto, sem excesso de boas-vindas
- Não lista CLAUDE.md, contexto da GM, design-guide na mensagem final (já vinham prontos, não é "novidade")
- Se a pessoa errar a função e quiser trocar depois, é só rodar `/setup` de novo
- Não cria pastas que já existem
- Não sobrescreve `_contexto/empresa.md` inteiro — só a seção "Sobre você"
