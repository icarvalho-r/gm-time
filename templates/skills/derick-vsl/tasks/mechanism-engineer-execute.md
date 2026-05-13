# Task: Mechanism Engineer — Execute Phase
**Task ID:** mechanism-engineer-execute
**Execution Type:** Agent
**Squad:** derick-vsl
**Agent:** mechanism-engineer

---

## Inputs Necessarios

- **nicho** (obrigatorio): Nicho de mercado alvo (ex: emagrecimento, energia, cognitivo)
- **publico_alvo** (obrigatorio): Descricao do publico alvo (ex: mulheres 40+, homens 35-55)
- **swipe_file** (obrigatorio): Lista de VSLs campeoes com seus mecanismos. Cada item deve conter: nome da VSL, mecanismo usado, tempo no ar, estimativa de performance.
- **restricoes** (opcional): Restricoes do produto ou oferta (ex: ingredientes disponiveis, claims permitidos, mecanismos a evitar por saturacao)
- **historico_proprio** (opcional): Historico de mecanismos que a equipe ja usou e seus resultados.

---

## Framework Central — Mecanismo Unico

> Referencia completa: `@ref: data/mechanism-framework.yaml`

### Definicao

Mecanismo = a explicacao do PORQUE que a pessoa nao conseguiu resolver o problema + COMO ela vai resolver agora. E a espinha dorsal de toda VSL de alta conversao. Sem mecanismo forte, nao ha VSL que converta.

O mecanismo unico e o que diferencia uma VSL generica de uma VSL milionaria. Ele da ao espectador uma NOVA explicacao para o problema dele e uma NOVA solucao que ele ainda nao tentou. A chave e que o mecanismo precisa parecer novo, mesmo sendo construido a partir de elementos ja validados.

### Tres Componentes

#### 1. Mecanismo do Problema (POR QUE)

**Pergunta:** "POR QUE a pessoa nao conseguiu resolver o problema ate agora?"

Explica a causa REAL do problema. Apresenta uma razao que a pessoa nunca ouviu ou nunca considerou. Cria o efeito de "revelacao".

Caracteristicas:
- Deve soar como uma descoberta — algo que a pessoa nao sabia
- Precisa ser especifico — nomes, termos tecnicos, dados
- Deve invalidar as tentativas anteriores da pessoa
- Cria o efeito "entao era isso o tempo todo!"
- Quanto mais tangivel e nomeavel, mais poderoso

**Exemplos:**

| Mecanismo | Descricao | Nicho | Por que funciona |
|-----------|-----------|-------|-----------------|
| Bacterias Firmicutes | "Seu intestino esta cheio de bacterias acumuladoras de gordura chamadas Firmicutes" | Emagrecimento | Nomeia vilao especifico, invalida dietas anteriores |
| Temperatura Corporal Baixa | "Sua temperatura corporal esta abaixo do ideal, metabolismo em camera lenta" | Emagrecimento | Conceito simples, facil de verificar |
| Figado Sobrecarregado | "Seu figado esta tao sobrecarregado de toxinas que nao processa gordura" | Emagrecimento | Personifica o orgao, razao logica e emocional |
| Cortisol Noturno | "Corpo libera cortisol durante a noite, sabotando esforco diurno" | Emagrecimento/Sono | Sabotador invisivel, cria urgencia |
| Inflamacao Silenciosa | "Inflamacao silenciosa bloqueia absorcao de nutrientes" | Saude Geral | "Silenciosa" cria misterio e urgencia |

#### 2. Mecanismo da Funcao (O QUE)

**Pergunta:** "O QUE precisa ser feito para resolver o problema?"

Define a FUNCAO que precisa acontecer para que o problema seja resolvido. E a ponte logica entre problema e solucao.

Caracteristicas:
- Deve ser a consequencia logica do problema apresentado
- Precisa soar como a unica coisa que faz sentido fazer
- Deve ser simples de entender — uma acao clara
- Cria o efeito "faz total sentido!"
- Conecta problema e solucao de forma inevitavel

**Exemplos:**

| Funcao | Descricao | Problema vinculado |
|--------|-----------|-------------------|
| Eliminar bacterias Firmicutes | "Enquanto elas estiverem la, nenhuma dieta vai funcionar" | Bacterias Firmicutes |
| Elevar temperatura corporal | "Metabolismo volta a funcionar na velocidade correta" | Temperatura Corporal Baixa |
| Desintoxicar o figado | "Eliminar toxinas para figado voltar a processar gordura" | Figado Sobrecarregado |
| Regular cortisol noturno | "Corpo pare de sabotar seus esforcos" | Cortisol Noturno |
| Eliminar inflamacao silenciosa | "Corpo volte a absorver nutrientes e queimar gordura" | Inflamacao Silenciosa |

#### 3. Mecanismo da Solucao (COMO)

**Pergunta:** "COMO exatamente a pessoa vai resolver isso?"

Apresenta a SOLUCAO ESPECIFICA. E o produto, ingrediente, metodo ou ritual. Deve ser concreto, nomeavel e parecer unico.

Caracteristicas:
- Deve ter um nome ou identidade propria
- Quanto mais especifico e inusitado, mais poderoso
- Precisa parecer acessivel
- Deve soar como algo que a pessoa nunca tentou
- Cria o efeito "preciso experimentar isso!"

**Exemplos:**

| Solucao | Descricao | Funcao vinculada |
|---------|-----------|-----------------|
| Epigalocatequina | "Substancia de cha verde raro que elimina Firmicutes em semanas" | Eliminar bacterias |
| Psilio | "Fibra natural que com agua morna eleva temperatura interna" | Elevar temperatura |
| Vitamina Detox de 5 Ingredientes | "Vitamina caseira com 5 ingredientes de qualquer feira" | Desintoxicar figado |
| Ritual de 2 Minutos | "Ritual antes de dormir com ingrediente de menos de 3 reais" | Regular cortisol |
| Especiaria Dourada | "Especiaria milenar ayurvedica que elimina inflamacao em 72h" | Eliminar inflamacao |

---

## Processo de Selecao e Combo de Mecanismos (6 Etapas)

### Etapa 1 — Levantamento de Mecanismos Campeoes

Listar todos os mecanismos campeoes do mercado no nicho alvo.

**Acoes:**
1. Pesquisar VSLs campeoes no nicho nos ultimos 12-24 meses
2. Identificar quais mecanismos estao sendo usados atualmente
3. Identificar quais mecanismos ja foram usados no passado e deram certo
4. Catalogar mecanismos de nichos adjacentes que podem ser adaptados
5. Priorizar mecanismos com prova de performance (vendas, tempo no ar)

**Output:** Lista de 10-20 mecanismos campeoes com contexto de performance

### Etapa 2 — Decomposicao Triadica

Decompor cada mecanismo campeao nos seus 3 componentes: POR QUE (Problema), O QUE (Funcao), COMO (Solucao).

**Acoes:**
1. Para cada mecanismo, extrair o componente de Problema
2. Para cada mecanismo, extrair o componente de Funcao
3. Para cada mecanismo, extrair o componente de Solucao
4. Registrar em formato tabular para facilitar combinacao
5. Identificar quais componentes individuais sao mais fortes

**Output:** Tabela de decomposicao com todos os mecanismos em 3 colunas

### Etapa 3 — Analise de Performance Historica

Analisar quais mecanismos e componentes individuais tiveram melhor performance historica e por que.

**Acoes:**
1. Classificar cada mecanismo por tempo que ficou no ar
2. Classificar por volume estimado de vendas
3. Identificar quais COMPONENTES especificos foram mais impactantes
4. Mapear tendencias — o que esta subindo, o que esta saturando
5. Identificar componentes que apareceram em multiplos mecanismos campeoes

**Output:** Ranking de componentes por performance com analise de tendencia

### Etapa 4 — Criacao de Combos

Misturar componentes de mecanismos diferentes para criar combos ineditos. Essa e a etapa mais criativa e mais importante.

**Acoes:**
1. Pegar o Problema de um mecanismo + Funcao de outro + Solucao de outro
2. Testar combinacoes que fazem sentido logico e narrativo
3. Verificar se o combo cria uma historia coerente
4. Verificar se o combo soa NOVO para o mercado
5. Gerar pelo menos 5 combos diferentes para avaliacao

**Regras de Combinacao:**
- O combo PRECISA fazer sentido logico — Problema leva a Funcao que leva a Solucao
- Componentes de diferentes nichos podem ser combinados se a logica se mantiver
- Quanto mais inesperada a combinacao (mantendo a logica), mais poderoso o combo
- Priorizar componentes que vieram de mecanismos de alta performance
- O combo deve soar como algo que o mercado nunca viu, mesmo sendo feito de partes conhecidas

**Regra Temporal Obrigatoria:** O combo SEMPRE junta uma tendencia que esta funcionando AGORA com um elemento campeao do PASSADO (1-2 anos atras). Derick: "reviver coisas do passado usando coisas que estao funcionando agora." O elemento atual garante relevancia. O elemento do passado garante que ja foi testado.

**Output:** 5+ combos de mecanismo com descricao completa

### Etapa 5 — Validacao de Combos

Avaliar cada combo contra criterios de qualidade.

**Criterios de Validacao:**

| Criterio | Pergunta | Peso |
|----------|----------|------|
| Coerencia Narrativa | O combo conta uma historia logica do inicio ao fim? | 25% |
| Novidade Percebida | O combo soa novo para quem ja viu os mecanismos individuais? | 25% |
| Credibilidade | O combo e crivel? A pessoa vai acreditar? | 20% |
| Simplicidade | O combo e facil de entender em 30 segundos? | 15% |
| Potencial Emocional | O combo gera emocao (raiva, esperanca, curiosidade)? | 15% |

**Scoring:** Cada criterio recebe nota de 1-10, multiplicada pelo peso. Total maximo: 1000.

**Output:** Ranking de combos com scoring detalhado

### Etapa 6 — Recomendacao Final

Apresentar o combo vencedor com justificativa completa e variantes para teste.

**Acoes:**
1. Selecionar o combo com maior pontuacao
2. Escrever a narrativa completa do mecanismo combo
3. Apresentar 2 variantes para teste A/B
4. Incluir justificativa baseada em performance historica
5. Sugerir angulos de abordagem para a VSL

**Output:** Recomendacao final com narrativa, variantes e justificativa

---

## Exemplo Classico de Combo

### Mecanismos Fonte:

1. **Mecanismo Firmicutes:** Problema: Bacterias acumulam gordura | Funcao: Eliminar bacterias | Solucao: Epigalocatequina do cha verde
2. **Mecanismo Circulatorio:** Problema: Fluxo sanguineo comprometido | Funcao: Restaurar fluxo para areas de gordura | Solucao: Exercicio de 7 minutos
3. **Mecanismo do Banho:** Problema: Pele nao absorve nutrientes | Funcao: Abrir poros para absorcao transdermica | Solucao: Ervas antes do banho

### Combo Resultado: "Bacteria-Fluxo-Ervas"
- **Problema:** Bacterias Firmicutes (do Mecanismo 1 — NOVO, impactante)
- **Funcao:** Restaurar fluxo sanguineo (do Mecanismo 2 — LOGICO, conhecido)
- **Solucao:** Ervas antes do banho (do Mecanismo 3 — INUSITADO, curioso)

**Narrativa:**
> "Cientistas descobriram que bacterias chamadas Firmicutes no seu intestino estao bloqueando o fluxo sanguineo para as areas onde a gordura se acumula. Sem fluxo de sangue adequado, seu corpo simplesmente nao consegue queimar essa gordura. A solucao? Um ritual simples com ervas naturais que voce aplica antes do banho, e que penetram pela pele, eliminando essas bacterias e restaurando o fluxo de sangue para as areas criticas."

**Por que funciona:**
- Problema (Firmicutes) e novo e impactante — gera curiosidade
- Funcao (fluxo sanguineo) e logica e familiar — gera confianca
- Solucao (ervas antes do banho) e inusitada — gera desejo de testar
- A narrativa conecta os 3 de forma coerente e crivel
- Ninguem no mercado usou essa combinacao exata antes

---

## Exemplos Completos de Output

### Output Exemplo 1 — Nicho Emagrecimento

**Titulo:** Mecanismo Combo para VSL de Emagrecimento Feminino 40+

**Mecanismos Analisados:**

| # | Nome | Fonte | Problema | Funcao | Solucao | Performance |
|---|------|-------|----------|--------|---------|-------------|
| 1 | Firmicutes | VSL GreenLean (18 meses) | Bacterias acumulam gordura | Eliminar bacterias | Capsula epigalocatequina | 50M+ |
| 2 | Temperatura | VSL ThermoBoost (12 meses) | Temperatura baixa desacelera metabolismo | Elevar temperatura interna | 6 ingredientes termogenicos | 30M+ |
| 3 | Figado Toxico | VSL LiverPure (14 meses) | Figado sobrecarregado nao queima gordura | Desintoxicar figado | Vitamina detox 5 ingredientes | 40M+ |

**Tabela de Decomposicao:**

| # | PROBLEMA | FUNCAO | SOLUCAO |
|---|----------|--------|---------|
| 1 | Bacterias Firmicutes | Eliminar bacterias | Capsula epigalocatequina |
| 2 | Temperatura baixa | Elevar temperatura | 6 ingredientes termogenicos |
| 3 | Figado toxico | Desintoxicar figado | Vitamina detox 5 ingredientes |

**Combo Recomendado: "Firmicutes-Detox-Termo"**
- Problema: Bacterias Firmicutes (do Mecanismo 1)
- Funcao: Desintoxicar o figado onde as bacterias se alojam (do Mecanismo 3)
- Solucao: Mistura termogenica que elimina bacterias e toxinas simultaneamente (do Mecanismo 2)

**Narrativa:** "Cientistas da Universidade de Harvard descobriram que bacterias chamadas Firmicutes nao ficam apenas no intestino — elas migram para o figado e se alojam la, criando uma camada de toxinas que impede a queima de gordura. A unica forma de elimina-las e atraves de uma mistura termogenica especifica de 6 ingredientes que eleva a temperatura do figado e literalmente 'derrete' a camada de toxinas onde as Firmicutes se escondem."

**Scoring:** Coerencia 9 | Novidade 8 | Credibilidade 8 | Simplicidade 7 | Emocao 9 | **Total: 830**

**Justificativa:** Firmicutes como problema e o componente mais forte (50M+ em vendas). Desintoxicacao do figado como funcao e logica e familiar. Mistura termogenica traz novidade. O combo conecta os 3 de forma inedita. A narrativa de "derreter a camada de toxinas" e visual e poderosa.

**Alternativas:**
1. Combo Temperatura-Bacterias-Detox (Score: 780)
2. Combo Figado-Termo-Capsula (Score: 750)

### Output Exemplo 2 — Nicho Energia/Disposicao Masculina

**Combo Recomendado: "Testosterona-Mitocondria-Curcumina"**
- Problema: SHBG sequestra testosterona (35M+ em vendas, 16 meses no ar)
- Funcao: Reativar mitocondrias que dependem de testosterona
- Solucao: Curcumina potencializada com piperina

**Narrativa:** "Existe uma proteina no seu sangue chamada SHBG que esta sequestrando sua testosterona livre. Sem testosterona disponivel, suas mitocondrias — as usinas de energia do seu corpo — entram em modo hibernacao. Voce nao esta cansado porque esta velho. Voce esta cansado porque suas mitocondrias estao dormindo. A solucao? Uma forma potencializada de curcumina com piperina que desbloqueia a testosterona do SHBG e acorda suas mitocondrias em questao de dias."

**Scoring:** Total: 870

### Output Exemplo 3 — Nicho Saude Cognitiva

**Combo Recomendado: "Placa-Oxigenio-Barreira"**
- Problema: Placas amiloides bloqueiam sinapses (25M+ vendas)
- Funcao: Aumentar fluxo sanguineo para "lavar" as placas
- Solucao: DHA que atravessa a barreira e carrega oxigenio

**Narrativa:** "Neurologistas de Stanford descobriram que a perda de memoria nao e causada pela idade — e causada por placas amiloides que se acumulam no cerebro e bloqueiam a comunicacao entre neuronios. O problema e que seu cerebro nao tem fluxo sanguineo suficiente para 'lavar' essas placas naturalmente. A solucao? Uma forma especifica de DHA que atravessa a barreira cerebral e carreia oxigenio diretamente ate as areas onde as placas se acumulam, dissolvendo-as de dentro para fora."

**Scoring:** Total: 890

---

## Anti-Patterns

### AP001: Mecanismo Inventado (CRITICO)
Criar um mecanismo completamente novo que nunca foi testado no mercado. Sem validacao historica, e puro achismo.
- **Sintoma:** O mecanismo nao aparece em nenhuma VSL existente
- **Fix:** Volte ao swipe file e encontre componentes validados

### AP002: Combo Sem Logica (CRITICO)
Combinar componentes que nao fazem sentido narrativo juntos. Ex: Problema de bacteria + Funcao de sono + Solucao de exercicio.
- **Sintoma:** Ao ler o combo em voz alta, ele nao faz sentido
- **Fix:** Teste a coerencia: Problema -> portanto -> Funcao -> portanto -> Solucao

### AP003: Combo Familiar Demais (ALTO)
Usar componentes do mesmo mecanismo original ou muito parecidos, resultando em algo que nao parece novo.
- **Sintoma:** O combo parece uma variacao de algo que ja existe
- **Fix:** Troque pelo menos 2 dos 3 componentes por elementos de mecanismos bem diferentes

### AP004: Mecanismo Complexo Demais (ALTO)
Criar um mecanismo com tantos elementos que a pessoa nao entende em 30 segundos.
- **Sintoma:** Precisa de mais de 3 frases para explicar
- **Fix:** POR QUE em 1 frase. O QUE em 1 frase. COMO em 1 frase.

### AP005: Mecanismo Generico (MEDIO)
Usar termos vagos e genericos. Ex: "Voce tem toxinas no corpo" sem nomear quais.
- **Sintoma:** O mecanismo poderia ser de qualquer produto
- **Fix:** Adicione nomes, numeros, dados especificos. "Firmicutes" e melhor que "bacterias"

### AP006: Solucao Desconectada (ALTO)
A solucao nao resolve a funcao de forma logica. Ex: Funcao e "elevar temperatura" mas solucao e "cha calmante".
- **Sintoma:** A solucao nao tem relacao clara com a funcao
- **Fix:** Garanta que a solucao DIRETAMENTE realiza a funcao descrita

### AP007: Repetir Mecanismo Completo Sem Combo (ALTO)
Usar um mecanismo INTEIRO exatamente como ja foi usado. Componentes individuais podem e devem ser reutilizados — o que nao pode e repetir o mecanismo completo sem combinar com algo novo. Derick: "Mecanismo nao satura. O combo o torna novo."
- **Sintoma:** O mecanismo e identico a uma VSL ativa
- **Fix:** Troque pelo menos 1 dos 3 componentes

### AP008: Combo de Um So (MEDIO)
Gerar apenas 1 combo e apresentar como recomendacao final.
- **Sintoma:** Apenas 1 combo foi analisado
- **Fix:** Gere no minimo 5 combos e avalie todos

---

## Output Esperado

O output final deve conter as seguintes secoes:

1. **Mecanismos Campeoes Analisados** — Tabela com todos os mecanismos pesquisados e suas decomposicoes
2. **Tabela de Decomposicao** — Matriz POR QUE / O QUE / COMO de cada mecanismo
3. **Combos Gerados** — Minimo 5 combos com descricao completa
4. **Scoring de Validacao** — Pontuacao de cada combo nos 5 criterios
5. **Recomendacao Final** — Combo vencedor com narrativa completa, justificativa baseada em dados, e 2 variantes para teste A/B
6. **Anti-Pattern Check** — Verificacao de que nenhum anti-pattern foi violado

---

## Quality Gates

- [ ] Minimo 5 mecanismos campeoes foram analisados e decompostos
- [ ] Cada mecanismo foi decomposto nos 3 componentes (POR QUE / O QUE / COMO)
- [ ] Minimo 5 combos foram gerados
- [ ] Cada combo tem narrativa completa e coerente
- [ ] Todos os combos foram avaliados pelos 5 criterios de validacao
- [ ] Recomendacao final inclui justificativa com dados de mercado
- [ ] Recomendacao final inclui 2 variantes para teste A/B
- [ ] Nenhum anti-pattern foi violado
- [ ] Combo vencedor tem scoring total >= 700/1000
- [ ] Coerencia narrativa do combo vencedor >= 7/10
- [ ] Todos os componentes do combo tem historico de performance documentado
- [ ] O combo nao replica nenhuma VSL existente no mercado

---

## Notas de Implementacao

- O processo de decomposicao deve ser rigoroso — cada mecanismo PRECISA ser separado em exatamente 3 componentes, sem excecao.
- O scoring de validacao deve ser apresentado de forma transparente, com justificativa para cada nota.
- Em caso de empate no scoring, priorizar o combo com maior novidade percebida.
- O agente deve ser capaz de iterar — se o derick-chief rejeitar, gerar novos combos com componentes diferentes.
- Manter registro de combos ja usados para evitar repeticao em VSLs futuras.
