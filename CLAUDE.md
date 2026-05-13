# Growth Machine — Time de Marketing

## O que é esse workspace

Workspace pessoal pra trabalhar no time de marketing da Growth Machine usando o Claude Code. Cada pessoa do time tem o seu, configurado pela sua função (editor de vídeo, design, copy, ops).

A estrutura de pastas é definida no `/setup` baseado na sua função. Os arquivos de contexto (`_contexto/`) e identidade visual (`marca/`) já vêm preenchidos com as informações da GM, pra não precisar configurar do zero.

## Sobre a Growth Machine

Consultoria B2B de vendas. Atende empresas que querem montar máquina de vendas previsível.

**CEO:** Thiago Reis. Autor de "Demanda Infinita" e "Vendas Infinitas". Host do GrowthCast.

**Posicionamento:** já atendeu milhares de empresas, gerou bilhões em receita pros clientes. Aplica Hormozi, SPIN Selling, Cold Calling 2.0 no mercado B2B brasileiro.

**Termos de marca (capitalizar sempre):** Máquina de Vendas, Playbook Validado, Arena de Crescimento, funil, cadência, CRM, previsibilidade.

## Tom de voz

Direto, data-driven, português brasileiro informal mas preciso. Sem linguagem motivacional genérica. Sem jargão excessivo. Sem travessões. Sem "mergulhe de cabeça", "no mundo dinâmico", "venha conosco". Sem emojis em conteúdo da marca.

Código sempre completo, nunca snippets parciais.

## Ferramentas conectadas

- Lovable, Supabase, Vercel, Netlify, Cloudflare
- WordPress (Elementor + Yoast)
- ClickUp, HubSpot, Hotmart
- GitHub, React
- Google Drive, Gmail, Google Calendar
- Canva

---

## Contexto do negócio

No início de toda conversa, ler os seguintes arquivos:

1. `_contexto/empresa.md` — quem é a GM, como funciona, time, clientes
2. `_contexto/preferencias.md` — tom de voz, estilo, o que evitar
3. `_contexto/estrategia.md` — foco atual da sua função, prioridades

Para qualquer tarefa visual (carrossel, slide, landing page), consultar `marca/design-guide.md` como referência de estilo.

Não é necessário listar o que foi lido nem confirmar a leitura. Apenas usar o contexto naturalmente.

---

## Fluxo de trabalho

Antes de executar qualquer tarefa, verificar se existe uma skill relevante em `.claude/skills/` ou `.claude/commands/`.
Se encontrar, seguir as instruções da skill.
Se não encontrar, executar a tarefa normalmente.

Ao concluir uma tarefa que não tinha skill mas parece repetível, perguntar:

> "Isso pode virar uma skill pra próxima vez. Quer que eu crie?"

Não perguntar pra tarefas pontuais. Só quando o padrão de repetição for claro.

---

## Aprender com correções

Quando o usuário corrigir algo, melhorar uma resposta ou dar uma instrução que parece permanente ("na verdade é assim", "não faça mais isso", "prefiro assim", "sempre que..."), perguntar:

> "Quer que eu salve isso pra não precisar repetir?"

Se sim, identificar onde salvar:

- **Sobre a GM** (processos, time, clientes, ferramentas) → `_contexto/empresa.md`
- **Preferências de tom/estilo** → `_contexto/preferencias.md`
- **Prioridade ou foco** → `_contexto/estrategia.md`
- **Regra de comportamento dessa pasta** → próprio `CLAUDE.md`
- **Mudança visual** → `marca/design-guide.md`

Salvar com linha nova clara, sem reformatar o arquivo inteiro. Confirmar o que foi salvo mostrando a linha adicionada.

Não perguntar pra correções óbvias de contexto imediato.

---

## Criação de skills

Quando o usuário pedir pra criar uma skill nova:

1. Verificar se existe template em `templates/skills/`. Se existir, usar como base
2. Perguntar: "Essa skill é específica desse workspace ou útil em qualquer projeto?"
   - Específica → salvar em `.claude/skills/nome/SKILL.md` (local)
   - Universal → salvar em `~/.claude/skills/nome/SKILL.md` (global)
3. Ler `_contexto/empresa.md` e `_contexto/preferencias.md` pra calibrar a skill ao contexto GM
4. Criar arquivo de comando correspondente em `.claude/commands/nome.md` pra `/nome` funcionar

**Formato do arquivo de comando:**

```markdown
---
name: nome-da-skill
description: Descrição curta do que faz.
---

Leia `templates/skills/nome-da-skill.md` e execute as instruções com o contexto fornecido.
```
