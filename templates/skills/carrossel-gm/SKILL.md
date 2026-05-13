---
name: carrossel-gm
description: >
  Cria carrosséis completos para Instagram da Growth Machine.
  Gera o texto dos slides no tom do Thiago Reis, cria os HTMLs com a identidade visual
  da GM (dark, laranja #fb6500, Manrope), renderiza em PNG via Playwright e pergunta
  se quer versão TikTok/Stories.
  Use quando pedir "carrossel da GM", "carrossel pro Thiago", "carrossel Growth Machine",
  ou rodar /carrossel-gm.
---

# /carrossel-gm — Carrossel Growth Machine

## Identidade visual (fixo — não perguntar)

- **Fundo:** `#0a0a0a`
- **Destaque / CTA:** `#fb6500` (laranja)
- **Texto:** `#ffffff`
- **Cards / fundo alternativo:** `#111111` ou `#1a1a1a`
- **Fonte:** Manrope (Google Fonts) — títulos 700–800, corpo 400–500
- **Border-radius:** 8–12px
- **Proibido:** fundo branco, múltiplas cores de destaque, tipografia serifada

## Tom de voz (fixo — não perguntar)

- Voz do Thiago Reis: direto, data-driven, B2B brasileiro, informal mas preciso
- Sem linguagem motivacional genérica, sem jargão excessivo
- Frases longas e naturais (2-4 por slide), nunca bullet points picotados
- Sem travessões (—)
- Preservar capitalização: Máquina de Vendas, Playbook Validado, Arena de Crescimento, funil, cadência, CRM, previsibilidade
- Referências do universo do Thiago: Hormozi, SPIN Selling, Cold Calling 2.0

## Padrão real dos carrosséis do Thiago (observado no perfil)

Os carrosséis recentes seguem um formato específico — não são slides graficamente elaborados, são posts com 1 imagem de impacto + análise densa no caption.

**Hook da capa:** sempre uma afirmação provocadora sobre empresa famosa ou dado de mercado
- Exemplos reais: "O Mercado Livre está investindo PESADO no Brasil: R$ 57 BILHÕES em 2026"
- "Esse gráfico sobre falências no Brasil é MENTIROSO!!!"
- "O McDonald's está passando A MAIOR DIFICULDADE de toda a sua história"

**Estrutura do caption:** 3-5 parágrafos curtos, análise com opinião clara, termina com CTA
- CTA padrão: "Comente X aqui embaixo que eu te envio o link direto na sua DM"

**Visual dos slides projetados (para quando o formato for multi-slide gráfico):**
- Thumbnails escuros com foto do Thiago em palco + texto bold branco/laranja sobreposto
- Palavras-chave em maiúsculas: "ESTRATÉGIA", "PRODUTO NÃO VENDE SOZINHO", "VOCÊ PRECISA SER RESILIENTE"

## Input

- Tema, texto livre, link ou arquivo de referência
- Número do episódio/série (se aplicável)
- Foto pra capa (opcional)
- Perguntar: formato hook + caption longo (1 slide) ou carrossel multi-slide gráfico?

---

## Workflow em 3 Fases

### Fase 1 — Texto

1. Se o input for um link, usar WebFetch pra buscar o conteúdo
2. Definir o ângulo: educacional, oportunidade, contrário, provocativo ou inspiracional
3. Escrever 8-10 slides no seguinte fluxo:
   - **Slide 1 (Capa):** 3 opções de título (máx 8 palavras) + subtítulo — usuário escolhe antes de continuar
   - **Slides 2-3 (Contexto):** o que é / por que importa
   - **Slides 4-7 (Desenvolvimento):** um insight por slide, opinião clara
   - **Slides 8-9 (Implicação):** o que isso muda pra quem tá lendo
   - **Slide final (CTA):** chamada pra ação + menção à Growth Machine

**Regras de escrita:**
- Frases longas e naturais, não bullet points disfarçados
- Curiosity gap entre slides, mas cada slide deve fluir por conta própria
- Sem travessões, sem emojis, sem entusiasmo vazio

4. Salvar texto em `growth-machine/conteudo/carrosseis/[tema]/carousel-text.md`

**CHECKPOINT:** mostrar texto completo + 3 opções de capa. Aguardar escolha e aprovação antes da Fase 2.

---

### Fase 2 — Visual (HTMLs + PNGs)

Criar HTMLs com as seguintes especificações:

**Dimensão:** 1080x1350px  
**Dependência externa:** apenas Google Fonts (Manrope)  
**CSS:** inline, sem frameworks

**Layout dos slides:**
- Fundo `#0a0a0a`, texto `#ffffff`, destaque `#fb6500`
- Usar pelo menos 2 layouts diferentes (ex: texto simples, número grande em destaque, card com borda laranja, citação em destaque)
- Slide 1 (capa): título grande, subtítulo menor, logo ou nome "Growth Machine" no rodapé
- Slides intermediários: texto corrido com destaque em palavras-chave (cor laranja ou peso 800)
- Slide final: branding, CTA direto, sem texto longo

**Estrutura HTML base de cada slide:**
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;700;800&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      width: 1080px; height: 1350px;
      background: #0a0a0a;
      font-family: 'Manrope', sans-serif;
      color: #ffffff;
      display: flex; align-items: center; justify-content: center;
    }
  </style>
</head>
<body>
  <!-- conteúdo do slide -->
</body>
</html>
```

**Passos:**
1. Criar HTMLs em `growth-machine/conteudo/carrosseis/[tema]/instagram/`
2. Renderizar slide 1 primeiro:
   ```bash
   npx playwright screenshot --viewport-size=1080,1350 --full-page "file:///caminho/absoluto/slide-01.html" "slide-01.png"
   ```
   (Se nunca instalado: `npx playwright install chromium`)

**CHECKPOINT:** mostrar slide 1. Se aprovado, renderizar os demais.

3. Renderizar demais slides e salvar PNGs na mesma pasta

---

### Fase 3 — Versão TikTok/Stories (opcional)

Após finalizar Instagram, perguntar:
> "Quer a versão vertical também? (1080x1920 pra Stories e TikTok)"

Se sim:
- Adaptar HTMLs: `height: 1920px`, ajustar padding e tamanho de fonte
- Renderizar:
  ```bash
  npx playwright screenshot --viewport-size=1080,1920 --full-page "file:///caminho/absoluto/slide-XX.html" "slide-XX.png"
  ```
- Salvar em `growth-machine/conteudo/carrosseis/[tema]/tiktok/`

---

## Output final

```
growth-machine/conteudo/carrosseis/[tema]/
  carousel-text.md          ← texto aprovado + legenda sugerida
  instagram/
    slide-01.html → slide-01.png
    slide-02.html → slide-02.png
    ...
  tiktok/ (se solicitado)
    slide-01.html → slide-01.png
    ...
```

## Regras

- Texto aprovado na Fase 1 não muda na Fase 2
- Sempre mostrar slide 1 antes de renderizar os demais
- Se pedir ajuste no visual, editar o HTML e re-renderizar só o slide alterado
- Nunca fundo branco, nunca tipografia serifada, nunca múltiplas cores de destaque
