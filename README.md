# gm-time — Workspace pro time de marketing da GM

Kit pra você usar o Claude Code no seu dia a dia no time de marketing da Growth Machine. Já vem com o contexto da empresa, tom de voz e identidade visual preenchidos. Você só precisa rodar `/setup` pra dizer quem você é e qual sua função no time.

---

## Como instalar

### Opção 1 — Via prompt (mais fácil)

Com o Claude Code aberto em qualquer pasta, copie e cole esse prompt:

```
Instala pra mim o repositório https://github.com/icarvalho-r/gm-time.git na pasta atual, abre ela e roda /setup
```

O Claude faz tudo: clona o repo, entra na pasta e inicia a configuração.

### Opção 2 — Via terminal

```bash
git clone https://github.com/icarvalho-r/gm-time.git
cd gm-time
code .
```

Abre o terminal integrado no VS Code (Ctrl + ` / Cmd + `) e roda:

```bash
claude
```

Depois, dentro do Claude:

```
/setup
```

---

## O que o /setup pergunta

Duas coisas:

1. Seu nome
2. Sua função no time: **editor de vídeo, design, copy, ops/ClickUp** ou outra

Baseado na função, ele cria as pastas certas. Nada além disso. O contexto da GM, o tom de voz e a identidade visual já vêm prontos — você não precisa explicar o que a empresa faz nem como o time escreve.

Leva menos de um minuto.

---

## Comandos disponíveis

**Sempre disponíveis:**
- `/setup` — configura a primeira vez ou refaz se sua função mudar
- `/iniciar` — carrega o contexto no começo de cada sessão de trabalho
- `/syncar` — salva o trabalho no GitHub (configura na primeira vez)
- `/atualizar` — varre o projeto e atualiza os arquivos de contexto desatualizados
- `/mapear` — entrevista sobre seus processos repetitivos e cria skills personalizadas
- `/novo-projeto` — cria pasta de projeto novo com CLAUDE.md dedicado

**Conteúdo:**
- `/roteiro-post` — ideia ou texto em roteiro de post ou vídeo
- `/carrossel-gm` — carrossel pro Instagram da GM com identidade visual
- `/slide` — slide ou card visual pra apresentação
- `/email-profissional` — email profissional a partir de contexto livre

**Copy avançado:**
- `/copy-decoder` — decompõe uma copy de referência (estrutura, ganchos, padrões)
- `/hormozi` — framework Hormozi (Value Equation, Grand Slam Offer, headlines)
- `/derick-vsl` — framework de VSL do Derick Howell
- `/perpetuo-white` — estrutura de carta de venda longa
- `/gold-finder` — ângulos de venda escondidos a partir de pesquisa
- `/niche-scout` — pesquisa de nicho (dores, concorrentes, oportunidades)
- `/meta-ads-criativos` — criativos pra Meta Ads (hook, ângulo, copy)
- `/squad-creator-pro` — workflow de criação de conteúdo em squad multi-agente

**Operação:**
- `/proposta-comercial` — proposta em HTML a partir de briefing
- `/publicar-site` — publica HTML no ar via Cloudflare Pages
- `/analisar-dados` — analisa CSV/XLSX/PDF e gera resumo executivo

**Pesquisa e descoberta (instaladas via skills.sh):**
- `/find-skills` — busca e instala skills novas do catálogo skills.sh
- `/firecrawl-search` — busca na web
- `/firecrawl-scrape` — raspa o conteúdo de uma página

**Marketing/Conteúdo (instaladas via skills.sh):**
- `/copywriting` — redação persuasiva
- `/social-content` — conteúdo pra redes sociais
- `/content-strategy` — estratégia e planejamento editorial
- `/email-sequence` — sequências de email (boas-vindas, nutrição, lançamento)
- `/cold-email` — email frio pra prospecção
- `/copy-editing` — edição/revisão de copy
- `/ad-creative` — criativos pra anúncios

**SEO/Análise (instaladas via skills.sh):**
- `/seo-audit` — auditoria de SEO em um site
- `/programmatic-seo` — estratégia de páginas em escala pra long-tail
- `/ai-seo` — SEO pra aparecer em ChatGPT, Perplexity, Google AI Overviews
- `/schema-markup` — gera schema/JSON-LD pra rich snippets
- `/analytics-tracking` — plano de eventos GA4/pixel
- `/competitor-alternatives` — análise de concorrentes e comparativos
- `/audit-website` — auditoria geral (performance, UX, técnico)

---

## O que já vem pré-configurado

- `CLAUDE.md` — Claude já sabe quem é a GM, como o time trabalha, o tom de voz
- `_contexto/empresa.md` — Growth Machine, Thiago Reis, projetos do time
- `_contexto/preferencias.md` — regras de escrita (sem travessão, sem cara de IA)
- `marca/design-guide.md` — identidade visual GM (laranja #fb6500, Manrope, dark)
- `templates/ferramentas/catalogo.md` — APIs e MCPs disponíveis pra usar em skills

**Pasta `dados/`:** drop zone pra arquivos que você quer analisar (CSV, XLSX, PDF). Use com `/analisar-dados dados/seu-arquivo.csv`.

---

## Mudou de função?

Roda `/setup` de novo. Ele detecta que já tem configuração, pergunta se quer só atualizar a função, e cria as pastas da nova função.

---

## Dúvidas?

Fala com a Isa.
