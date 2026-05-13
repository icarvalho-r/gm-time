# Task: Market Scout — Execute Phase
**Task ID:** market-scout-execute
**Execution Type:** Agent
**Squad:** derick-vsl
**Agent:** market-scout

---

## Inputs Necessarios

- **nicho_alvo** (obrigatorio): Nicho ou mercado a ser analisado
- **avatar_preliminar** (obrigatorio): Descricao do publico-alvo
- **tipo_analise** (opcional): completa | parcial (conteudo/compra/marketing) | comparacao | swipe
- **mercado_comparacao** (opcional): Segundo mercado para comparacao

---

## Processo de Execucao

### Fase 1: Definicao de Mercado e Avatar

1. Definir o mercado como um **grupo de pessoas com desejo especifico**
2. Definir o avatar com detalhes demograficos e psicograficos
3. Mapear os desejos latentes do avatar

> **Principio**: Voce NAO cria desejo. O desejo ja existe na pessoa. Seu trabalho e encontrar esse desejo e posicionar a oferta como melhor resposta.

### Fase 2: Mapear Tendencia de Conteudo

**Pergunta-chave:** "Que conteudo as pessoas do mercado estao consumindo?"

O conteudo que as pessoas consomem indica no que elas ACREDITAM.

#### Fontes de Pesquisa

**YouTube (Principal):**
- Pesquisar palavras-chave do nicho
- Filtrar por visualizacoes (mais de 100K)
- Filtrar por data (ultimos 12 meses para ativas, ultimos 3 meses para quentes)
- Analisar titulos dos videos mais vistos
- Identificar temas recorrentes nos top 20 resultados
- Verificar canais que publicam esse conteudo (autoridade?)

Sinais positivos:
- Multiplos videos com 500K+ views no mesmo tema
- Canais diferentes abordando o mesmo assunto
- Comentarios engajados pedindo mais informacao
- Videos recentes performando melhor que antigos (tendencia crescente)

Sinais negativos:
- Poucos videos sobre o tema
- Views concentrados em um unico canal (pode ser anomalia)
- Conteudo antigo sem videos novos (tendencia morta)
- Comentarios negativos ou descrentes em massa

**TikTok (Complementar):**
- Pesquisar hashtags do nicho
- Analisar videos virais recentes
- Verificar criadores que estao crescendo nesse tema
- Observar formatos de conteudo que estao funcionando

**Google Trends (Validacao):**
- Comparar termos do nicho nos ultimos 5 anos
- Identificar sazonalidade (picos recorrentes)
- Verificar se a tendencia e crescente, estavel ou declinante
- Comparar termos relacionados para encontrar sub-tendencias

#### Output Esperado — Tendencia de Conteudo

Lista de temas virais com:
- Termo/tema principal
- Volume estimado (views totais nos top videos)
- Recencia (quando os videos mais recentes foram publicados)
- Sentimento geral (positivo, neutro, negativo)
- Crenca implicita (o que esse conteudo revela sobre o que o mercado acredita)

#### Exemplo Real: Truque da Banana

Antes da oferta do Truque da Banana ser criada, ja existia uma tendencia de conteudo massiva no YouTube sobre "banana emagrece", "dieta da banana", "banana verde para perder peso". Milhoes de visualizacoes em dezenas de canais. Isso indicava que o mercado JA ACREDITAVA que banana tinha propriedades de emagrecimento. A VSL nao precisou criar essa crenca — ela surfou nela.

### Fase 3: Mapear Tendencia de Compra

**Pergunta-chave:** "O que as pessoas do mercado estao comprando?"

O que as pessoas COMPRAM indica o que elas VALORIZAM.

#### Fontes de Pesquisa

**Amazon EUA (Benchmark global):**
- Pesquisar produtos do nicho
- Filtrar por bestseller
- Analisar reviews (quantidade e qualidade)
- Verificar produtos 'Amazon's Choice'
- Olhar secao 'Frequently bought together'
- Analisar historico de ranking do produto

Sinais positivos:
- Produto no top 100 da categoria
- Mais de 10.000 reviews
- Rating acima de 4.0 estrelas
- Multiplas marcas vendendo o mesmo tipo de produto
- Produto aparece em 'Trending' ou 'Movers & Shakers'

Sinais negativos:
- Poucas opcoes de produto disponivel
- Reviews majoritariamente negativos
- Apenas uma marca vendendo (mercado nao validado)

**Mercado Livre BR (Validacao Brasil):**
- Pesquisar produtos do nicho
- Filtrar por 'Mais vendidos'
- Analisar quantidade de vendas declaradas
- Verificar quantidade de vendedores do mesmo produto
- Olhar perguntas dos compradores (revelam desejos)

Sinais positivos:
- Multiplos vendedores com +1000 vendas
- Perguntas frequentes sobre beneficios especificos
- Produto com selo 'MercadoLider'
- Variacoes do produto disponivel (mercado maduro)

**Google Trends (Volume de busca):**
- Pesquisar nome do ingrediente/produto
- Comparar com ingredientes concorrentes
- Analisar pico de interesse ao longo dos anos
- Verificar buscas relacionadas ('comprar X', 'onde encontrar X')

Sinais positivos:
- Tendencia crescente nos ultimos 12 meses
- Buscas relacionadas incluem 'comprar', 'preco', 'onde encontrar'
- Volume de busca estavel (nao e moda passageira)

#### Output Esperado — Tendencia de Compra

Lista de produtos/ingredientes em alta com:
- Nome do produto/ingrediente
- Ranking em marketplaces (Amazon, ML)
- Volume de vendas estimado
- Tendencia no Google Trends (crescente/estavel/declinante)
- O que isso revela sobre o que o mercado VALORIZA

#### Exemplo Real: Psyllium / Fibras

O psyllium apareceu em alta no Google Trends com volume crescente. Na Amazon EUA, suplementos de psyllium estavam no top da categoria. No Mercado Livre, vendedores tinham +5000 vendas. Isso confirmou que as pessoas estao COMPRANDO — nao so lendo sobre — produtos relacionados a fibras para emagrecimento/digestao.

### Fase 4: Mapear Tendencia de Marketing

**Pergunta-chave:** "Como a galera que faz marketing nesse nicho esta operando?"

A tendencia de marketing mostra O QUE FUNCIONA para vender nesse mercado.

#### Fontes de Pesquisa

**Meta Ad Library (Principal):**
- Pesquisar por palavras-chave do nicho na biblioteca de anuncios
- Filtrar por anuncios ativos (rodando agora)
- Identificar anuncios com maior tempo ativo (indicador de lucratividade)
- Analisar formatos de video (VSL, entrevista, UGC, etc.)
- Mapear elementos visuais recorrentes (jaleco, cozinha, antes/depois)
- Identificar hooks mais usados nos primeiros 5 segundos
- Verificar paginas de destino (VSL page, sales page, quiz funnel)
- Contar quantos anunciantes diferentes estao no nicho

Sinais positivos:
- Mais de 20 anunciantes ativos no mesmo nicho
- Anuncios rodando ha mais de 30 dias (lucrativos)
- Multiplos formatos sendo testados (mercado aquecido)
- Novos anunciantes entrando (mercado em expansao)
- VSLs longas rodando ha meses (modelo validado)

Sinais negativos:
- Poucos anunciantes (menos de 5)
- Anuncios com pouco tempo de vida (ninguem achou o modelo)
- Apenas um formato sendo usado (mercado limitado)
- Anunciantes saindo do mercado (mercado em declinio)

**Elementos de Marketing Recorrentes:**

| Formato | O que indica |
|---------|-------------|
| Entrevista com especialista | Mercado responde a autoridade medica/cientifica |
| Jaleco branco | Mercado valoriza credencial de saude |
| Depoimento de usuario real | Mercado precisa de prova social para converter |
| Antes e depois | Mercado e visual e orientado a resultado |
| Ingrediente sendo mostrado | Mercado se conecta com o mecanismo tangivel |
| Pessoa falando direto pra camera | Mercado responde a conexao pessoal |
| Quiz/pesquisa antes da VSL | Mercado precisa de segmentacao e qualificacao |
| Noticia/reportagem falsa | Mercado confia em validacao da midia (cuidado com compliance) |

#### Swipe File — Metodo de Analise Estruturada

Metodo Derick para extrair inteligencia do swipe file. Nao basta coletar VSLs — voce precisa ANALISAR com metodo.

**Passo 1:** Separar VSLs por periodo (ano passado vs ano atual). Comecar pelas ofertas do ano passado. Elas mostram o caminho do que fazer E do que nao fazer.

**Passo 2:** Listar o que as VSLs tem EM COMUM:
- Nome chiclete (voltado para mecanismo solucao? problema?)
- Tipo de spokesperson (especialista? pessoa comum?)
- Angulo da lead (promessa? curiosidade? medo?)
- Formato (entrevista? talking head? animacao?)
- Tipo de produto (capsula? gotas? po? ebook?)
- Elemento do dia a dia citado (banana, agua, semente)

Exemplo: Truque da Banana, Semente Bariatrica, Truque da Agua — COMUM: nome chiclete voltado para solucao, spokesperson especialista, lead com angulo de promessa, algo do dia a dia.

**Passo 3:** Listar o que e DIFERENTE entre elas (ideias unicas). Identificar ideias de marketing que so UMA oferta tem. Se essa oferta deu certo, provavelmente a ideia unica influenciou o resultado.

Exemplo: So a Semente Bariatrica tinha pergunta paradoxal forte. As outras nao tinham. Isso e uma ideia unica para combinar.

**Passo 4:** Combinar elementos comuns + ideias unicas em algo novo. Elementos comuns = validados pelo mercado (manter). Ideias unicas = diferenciais que comprovaram resultado (adicionar). Combo = VSL com mais elementos validados que qualquer concorrente.

**O que coletar de cada VSL:**
- URL da VSL (ou screenshot se nao estiver mais no ar)
- Hook dos primeiros 30 segundos
- Mecanismo unico usado
- Formato (talking head, animacao, entrevista, etc.)
- Tempo de duracao estimado
- Promessa principal
- Estimativa de tempo no ar (quanto tempo o anuncio rodou)
- Plataforma onde foi encontrada

#### Output Esperado — Tendencia de Marketing

Mapa de tendencias de marketing com:
- Quantidade de anunciantes ativos
- Formatos de VSL mais usados (com porcentagem estimada)
- Elementos visuais/narrativos recorrentes
- Tempo medio de vida dos anuncios
- Hooks mais usados nos primeiros 5 segundos
- Swipe file com pelo menos 5-10 VSLs catalogadas
- Avaliacao: mercado quente, morno ou frio

### Fase 5: Empilhamento de Tendencias (Scoring)

Cruzar as 3 tendencias para gerar score final de oportunidade.

#### Scoring Matrix

**Tendencia de Conteudo (Peso: 0.25):**
- Forte (10 pts): 5+ temas virais com 500K+ views, tendencia crescente
- Moderado (7 pts): 3-4 temas com 100K+ views, tendencia estavel
- Fraco (4 pts): 1-2 temas com views moderados, tendencia incerta
- Ausente (1 pt): Sem conteudo relevante encontrado

**Tendencia de Compra (Peso: 0.30):**
- Forte (10 pts): Produtos bestseller, Google Trends crescente, multiplos marketplaces
- Moderado (7 pts): Produtos vendendo bem em 1 marketplace, GT estavel
- Fraco (4 pts): Poucos produtos, baixo volume de vendas
- Ausente (1 pt): Sem produtos relevantes encontrados

**Tendencia de Marketing (Peso: 0.45):**
- Forte (10 pts): 20+ anunciantes ativos, multiplos formatos, VSLs rodando 30+ dias
- Moderado (7 pts): 10-20 anunciantes, 2-3 formatos, anuncios com vida media
- Fraco (4 pts): 5-10 anunciantes, pouca diversidade, anuncios curta duracao
- Ausente (1 pt): Menos de 5 anunciantes, sem VSLs identificadas

#### Interpretacao do Score

| Range | Classificacao | Recomendacao |
|-------|--------------|-------------|
| 8.5-10.0 | MERCADO QUENTE | Entrada imediata recomendada. Priorizar VSL com angulo diferenciado. |
| 6.5-8.4 | MERCADO MORNO | Investigar tendencia mais fraca. Considerar teste de baixo orcamento. |
| 4.0-6.4 | MERCADO FRIO | Risco elevado. Nao recomendado para primeira VSL. |
| 1.0-3.9 | MERCADO MORTO | Sem tendencias relevantes. Evitar. Buscar outro mercado. |

### Fase 6: Identificar Fase do Desejo (Niveis de Consciencia)

As 5 fases do desejo (inspiradas nos niveis de consciencia de Eugene Schwartz, adaptadas pelo Derick):

#### Fase 1: Inconsciente
A pessoa sofre os sintomas mas NAO identificou o problema. Sabe que algo esta errado mas nao sabe o que e.
- **Implicacao VSL:** Comecar nomeando sintomas. Hook baseado em sintomas e identificacao. Educacao mais longa.
- **Exemplo hook:** "Voce sente um cansaco inexplicavel, mesmo dormindo 8 horas?"

#### Fase 2: Consciente do Problema
Momento eureka. A pessoa percebeu que tem o problema. Comeca a buscar informacao.
- **Implicacao VSL:** Ir direto ao problema. Hook que valida o problema e promete solucao.
- **Exemplo hook:** "Se voce descobriu que seus hormonios estao desregulados..."

#### Fase 3: Consciente da Solucao
A pessoa procura por solucoes ativamente. Consome conteudo, pesquisa.
- **Implicacao VSL:** Diferenciar das outras solucoes. Mecanismo unico e CRITICO.
- **Exemplo hook:** "Voce ja tentou reposicao hormonal, cha de amora, e nada funcionou?"

#### Fase 4: Consciente do Mecanismo
A pessoa se identificou com uma solucao/mecanismo especifico.
- **Implicacao VSL:** Mais direta na oferta. Reforcar mecanismo e posicionar produto como melhor execucao.
- **Exemplo hook:** "O composto fitoterapeico que endocrinologistas estao chamando de 'a revolucao hormonal feminina'..."

#### Fase 5: Totalmente Consciente
A pessoa sabe exatamente o que precisa. Busca melhor oferta.
- **Implicacao VSL:** Focar em oferta irresistivel. Hook baseado em preco, exclusividade, urgencia.
- **Exemplo hook:** "A formula fitoterapeica mais completa do mercado, com 30% de desconto so ate sexta."

**Como identificar a fase predominante:**
- Tendencia de conteudo mostra MUITOS videos basicos/educativos? → Fase 2-3
- Tendencia de compra mostra MUITOS produtos do mesmo tipo vendendo? → Fase 4-5
- Tendencia de marketing mostra VSLs educativas longas? → Fase 2-3
- Tendencia de marketing mostra VSLs de oferta direta curtas? → Fase 4-5

### Fase 7: Combo Competitivo

A TECNICA MAIS IMPORTANTE da analise de mercado. A vantagem competitiva NAO vem de inventar algo novo. Vem de COMBINAR elementos separados que diferentes concorrentes estao fazendo individualmente.

**Principio:** Quando voce olha o mercado de fora, voce ve que cada concorrente tem um elemento diferente que funciona. Um usa formato entrevista. Outro vende gotas. Outro tem celebridade. Outro usa pergunta paradoxal. Nenhum deles tem TUDO junto. Voce pega cada um desses elementos validados e COMBINA em uma unica VSL.

**Exemplo Derick:**
> "Tem 10 players rodando VSL no mesmo nicho? Otimo! Significa que tem 10 pessoas fazendo marketing, cada uma fazendo uma coisa diferente. Voce pega cada uma dessas coisas diferentes que cada um ta fazendo e mistura em um so."

**Exemplo pratico:**
- Concorrente A: VSL formato entrevista (funciona)
- Concorrente B: Suplemento em gotas (funciona)
- Concorrente C: Celebridade como spokesperson (funciona)
- SUA VSL: Entrevista com celebridade vendendo gotas = 3 elementos validados combinados = vantagem competitiva.

**Como aplicar:**
1. Listar todos os elementos que cada concorrente usa separadamente
2. Identificar quais elementos NAO estao sendo combinados por ninguem
3. Combinar o maximo de elementos validados em uma unica VSL
4. Isso vale para: formato, ingredientes, tipo de spokesperson, angulo de lead, mecanismo

---

## Exemplos Completos de Output

### Exemplo 1: Analise Completa — Emagrecimento com Ingrediente Natural

**Input:** `*analyze emagrecimento feminino com ingredientes naturais`

```
# RELATORIO DE MERCADO: Emagrecimento Feminino com Ingredientes Naturais

**Data da analise:** 2026-03-06
**Mercado:** Mulheres 30-60 que buscam emagrecer com solucoes naturais
**Score geral:** 9.2/10 — MERCADO QUENTE

---

## 1. TENDENCIA DE CONTEUDO (Score: 9/10 — FORTE)

**Fontes analisadas:** YouTube, TikTok, Google Trends

| Tema | Views estimados | Recencia | Sentimento |
|------|----------------|----------|------------|
| "cha que emagrece" | 15M+ (top 20 videos) | Ultimos 3 meses | Muito positivo |
| "dieta do metabolismo" | 8M+ (top 15 videos) | Ultimos 6 meses | Positivo |
| "alimento que queima gordura" | 22M+ (top 30 videos) | Continuo | Muito positivo |
| "fibra para emagrecer" | 6M+ (top 10 videos) | Ultimos 2 meses | Positivo |
| "receita para perder barriga" | 30M+ (top 50 videos) | Continuo | Muito positivo |

**Crenca implicita:** As pessoas ACREDITAM que existem ingredientes naturais
capazes de acelerar o emagrecimento.

---

## 2. TENDENCIA DE COMPRA (Score: 9/10 — FORTE)

**Fontes analisadas:** Amazon EUA, Mercado Livre BR, Google Trends

| Produto/Ingrediente | Ranking | Vendas estimadas | GT Trend |
|---------------------|---------|-----------------|----------|
| Psyllium husk | Top 20 Saude (Amazon) | 50K+/mes (ML) | Crescente |
| Cha verde capsulas | Top 10 Emagrecimento | 80K+/mes (ML) | Estavel alto |
| Fibra de maracuja | Top 50 Saude (ML) | 20K+/mes | Crescente |
| Oleo de coco capsulas | Top 30 Saude | 35K+/mes (ML) | Estavel |

**O que o mercado valoriza:** Produtos naturais em formato capsula/po.

---

## 3. TENDENCIA DE MARKETING (Score: 10/10 — FORTE)

**Fontes analisadas:** Meta Ad Library, swipe file

**Anunciantes ativos:** 60+ (estimativa conservadora)
**Formatos predominantes:**
- VSL formato entrevista (35%)
- VSL talking head com jaleco (25%)
- UGC com depoimento (20%)
- Animacao com ingrediente (10%)
- Quiz funnel + VSL (10%)

**Tempo medio de vida dos anuncios top:** 45+ dias

**Hooks mais usados:**
1. "Medica revela o ingrediente que esta chocando a industria"
2. "Coloque ISSO no seu cafe da manha e veja o que acontece"
3. "Por que nenhuma dieta funciona depois dos 40"

---

## 4. EMPILHAMENTO E SCORE FINAL

| Tendencia | Score | Peso | Contribuicao |
|-----------|-------|------|-------------- |
| Conteudo | 9/10 | 0.25 | 2.25 |
| Compra | 9/10 | 0.30 | 2.70 |
| Marketing | 10/10 | 0.45 | 4.50 |
| **TOTAL** | | | **9.45/10** |

**Classificacao:** MERCADO QUENTE
**Fase do desejo predominante:** Fase 3-4

---

## 5. RECOMENDACAO

**Entrar nesse mercado? SIM — com diferenciacao.**

**Oportunidades identificadas:**
1. Sub-nicho de mulheres 50+ com foco em metabolismo lento
2. Angulo de "cozinha" ao inves de "consultorio"
3. Mecanismo unico baseado em fibra + microbiota
4. Formato quiz + VSL curta (15 min)
```

### Exemplo 2: Comparacao de Mercados

**Input:** `*compare diabetes tipo 2 vs dor nas costas`

```
# COMPARATIVO DE MERCADOS

| Criterio | Diabetes Tipo 2 | Dor nas Costas |
|----------|----------------|----------------|
| **T. Conteudo** | 9/10 | 7/10 |
| **T. Compra** | 8/10 | 6/10 |
| **T. Marketing** | 10/10 | 5/10 |
| **Score Final** | **9.2/10** | **5.8/10** |
| **Classificacao** | QUENTE | FRIO-MORNO |
| **Fase do Desejo** | 3-4 | 2-3 |
| **Anunciantes ativos** | 40+ | 8-12 |

**Veredicto:** Diabetes tipo 2 e significativamente mais forte.
**Recomendacao:** Para primeira VSL, ir com Diabetes Tipo 2.
```

### Exemplo 3: Swipe File

**Input:** `*swipe insonia e qualidade do sono`

```
# SWIPE FILE: Mercado de Insonia / Qualidade do Sono

**Total de VSLs catalogadas:** 8
**Periodo coberto:** 2024-2026

### VSL #1 — "O Ritual do Sono Profundo"
- **Formato:** Entrevista com neurologista
- **Duracao estimada:** 22 minutos
- **Hook:** "Neurologista revela por que voce NAO consegue dormir
  mesmo estando exausta — e nao tem nada a ver com estresse"
- **Mecanismo:** Composto de magnesio + triptofano
- **Promessa:** Dormir em 15 minutos sem remedios
- **Tempo no ar:** 60+ dias (ativo)
- **Elementos visuais:** Jaleco, laboratorio, close no suplemento

### VSL #2 — "Desliga o Cerebro"
- **Formato:** Talking head feminino, cenario de quarto
- **Duracao estimada:** 18 minutos
- **Hook:** "Eu passava noites em claro ate descobrir esse
  truque de 30 segundos antes de dormir"
- **Mecanismo:** Tecnica de respiracao + suplemento natural
- **Promessa:** Acabar com a insonia em 7 dias
- **Tempo no ar:** 45+ dias (ativo)

### VSL #3 — "A Vitamina que Faltava"
- **Formato:** Animacao + voz off
- **Duracao estimada:** 12 minutos
- **Hook:** "97% dos brasileiros tem deficiencia DESSA vitamina
  e isso esta destruindo seu sono"
- **Mecanismo:** Vitamina D + magnesio glicina
- **Tempo no ar:** 30+ dias (ativo)

---

**Padroes identificados:**
1. 75% das VSLs usam autoridade medica
2. Magnesio aparece como ingrediente hero em 5 de 8 VSLs
3. Hook de "deficiencia" e o padrao mais usado
4. Formato entrevista domina mas "rotina noturna" esta crescendo
5. Duracao media de 18 minutos

**Oportunidade:** Nenhuma VSL usando angulo "microbiota intestinal e sono".
```

---

## Anti-Patterns

### AP1: Recomendar mercado baseado em apenas 1 tendencia
Uma tendencia isolada pode ser enganosa. Conteudo viral nao significa que as pessoas estao comprando. SEMPRE cruzar as 3 tendencias.

### AP2: Assumir que desejo pode ser criado
O desejo JA EXISTE na pessoa. Se nao encontra tendencias em nenhuma das 3 dimensoes, o desejo NAO existe ou e muito fraco.

### AP3: Ignorar tendencia de marketing por achar mercado "saturado"
Mercado com muitos anunciantes NAO e saturado — e VALIDADO. Se 50 pessoas estao lucrando, tem espaco para mais um com diferenciacao.

### AP4: Apresentar dados sem fontes verificaveis
Toda informacao deve ser rastreavel. Informar termos pesquisados, periodos, filtros usados. O usuario precisa poder replicar.

### AP5: Confundir tendencia de conteudo com tendencia de compra
As pessoas assistem videos sobre muitas coisas que nunca vao comprar. Sempre validar conteudo com dados de compra reais.

### AP6: Ignorar o ciclo de mercado
Um mercado que parece morto pode estar no vale do ciclo. VSLs de 2 anos atras podem ser adaptadas. Sempre verificar historico.

### AP7: Analisar mercado sem definir o avatar
"Emagrecimento" nao e um mercado — e uma categoria. "Mulheres 40+ que querem emagrecer sem dieta restritiva" e um mercado. Sem avatar, a analise fica generica.

### AP8: Entregar relatorio sem recomendacao clara
O usuario quer RECOMENDACAO. Entrar ou nao? Com qual angulo? Qual formato? Relatorio sem recomendacao acionavel e inutil.

### AP9: Copiar exatamente uma VSL do swipe file
Swipe file serve para inspiracao e padroes, NAO para copia. Use padroes para criar algo NOVO.

### AP10: Misturar dados de mercados geograficos diferentes sem contextualizar
O que funciona nos EUA nao necessariamente funciona no Brasil. Amazon EUA e indicador de tendencia global, mas validacao final deve ser com dados brasileiros.

---

## Quality Gates

### Analise Completa
- [ ] Mercado e avatar claramente definidos
- [ ] Tendencia de conteudo mapeada com pelo menos 5 temas analisados
- [ ] Tendencia de compra mapeada com pelo menos 3 produtos/ingredientes
- [ ] Tendencia de marketing mapeada com contagem de anunciantes e formatos
- [ ] Score de empilhamento calculado com peso correto
- [ ] Fase do desejo predominante identificada
- [ ] Recomendacao clara e acionavel fornecida
- [ ] Pelo menos 3 oportunidades especificas listadas
- [ ] Todas as fontes de dados estao identificadas
- [ ] O score reflete fielmente os dados encontrados
- [ ] A recomendacao e coerente com o score
- [ ] Exemplos reais foram citados quando disponivel

### Analise Parcial
- [ ] Tendencia solicitada mapeada completamente
- [ ] Dados com fontes verificaveis
- [ ] Conclusao parcial fornecida
- [ ] Indicacao de como as outras tendencias poderiam complementar

### Comparacao
- [ ] Ambos mercados analisados com mesma profundidade
- [ ] Tabela comparativa gerada com todas as dimensoes
- [ ] Vencedor claro identificado com justificativa
- [ ] Nuances e ressalvas explicitadas

### Swipe File
- [ ] Minimo 5 VSLs catalogadas
- [ ] Cada VSL com formato, hook, mecanismo e tempo no ar
- [ ] Padroes identificados e listados
- [ ] Oportunidades de angulo inexplorado apontadas
