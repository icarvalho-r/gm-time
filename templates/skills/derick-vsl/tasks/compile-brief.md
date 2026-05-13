# Task: Derick Chief — Compile Brief

**Task ID:** compile-brief
**Execution Type:** Agent
**Squad:** derick-vsl
**Agent:** derick-chief
**Phase:** 6 (ultima fase do planejamento)

---

## Descricao

Compilar o Brief central — documento que conecta todas as 6 fases do planejamento e habilita a escrita da VSL. O Brief so e compilado quando TODAS as 5 fases anteriores estao completas e validadas.

---

## Input

```yaml
inputs:
  - fase_1_mercado: "Relatorio de mercado (conteudo, consumo, marketing)"
  - fase_2_mecanismo: "Mecanismo combado unico com justificativa"
  - fase_3_big_idea: "Pergunta paradoxal + nome chiclete"
  - fase_4_big_offer: "Big Offer com 9 elementos"
  - fase_5_historias: "3 historias estruturadas (Background, Emotional, Discovery)"
  - dados_usuario: "Nicho, produto, ticket, avatar, formato"
```

---

## Processo de Compilacao

### 1. Verificacao Pre-Brief

Antes de compilar, verificar:
- Todas as 5 fases do planejamento estao completas?
- Cada fase foi validada pelo Chief?
- O usuario aprovou cada output?
- Existe coerencia entre as fases (mecanismo → big idea → oferta)?

### 2. Montagem do Brief

Preencher cada secao do template abaixo com os dados das fases.

### 3. Validacao de Coerencia

Apos montar, verificar:
- O mecanismo combado conecta com a Big Idea?
- A Big Idea reflete na Big Offer?
- As historias referenciam o mecanismo?
- O avatar esta consistente em todas as fases?

### 4. Apresentacao ao Usuario

Mostrar o Brief formatado e pedir aprovacao antes de iniciar a escrita.

---

## Brief Template — Estrutura do Documento Central

```yaml
sections:

  - section: "DADOS GERAIS"
    fields:
      - "Nicho"
      - "Produto"
      - "Avatar (quem e, o que sente, o que quer)"
      - "Ticket (preco do produto)"
      - "Formato da VSL (tempo estimado)"

  - section: "MERCADO (Fase 1)"
    fields:
      - "Tendencias de Conteudo"
      - "Tendencias de Consumo"
      - "Tendencias de Marketing"
      - "Oportunidades identificadas"
      - "Concorrentes principais e angulos usados"

  - section: "MECANISMO (Fase 2)"
    fields:
      - "Mecanismos listados"
      - "Mecanismo combado (final)"
      - "Por que o combo funciona"
      - "Diferenciacao vs. concorrencia"

  - section: "BIG IDEA (Fase 3)"
    fields:
      - "Pergunta paradoxal"
      - "Nome chiclete"
      - "Variacoes testadas"
      - "Teste do bar (passa ou nao?)"

  - section: "BIG OFFER (Fase 4)"
    fields:
      - "1. Produto que o mercado ja compra"
      - "2. Feito pra aquela pessoa (avatar)"
      - "3. Beneficios multiplos"
      - "4. Prazo pra cada beneficio"
      - "5. Reduzir esforco"
      - "6. Reason Why (justificar preco)"
      - "7. Preco menor que concorrencia"
      - "8. Bonus que o mercado compraria"
      - "9. Maximizar seguranca/garantia"

  - section: "STORYTELLING (Fase 5)"
    fields:
      - "Background Story (por que confiar em voce?)"
      - "Emotional Story (por que pode me ajudar?)"
      - "Discovery Story (como descobriu isso?)"
      - "Tipo de porta-voz (Guru/Autoridade ou Avatar Transformado)"

  - section: "DIRECIONAMENTO DE ESCRITA"
    fields:
      - "Tom de voz da VSL"
      - "Nivel de consciencia do avatar"
      - "Objecoes principais a quebrar"
      - "Emocoes dominantes a explorar"
      - "Referencias de VSLs similares"
```

---

## Exemplo de Brief Compilado

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
         BRIEF VSL — Metodo Termofit
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PRODUTO: Metodo Termofit — Programa digital de emagrecimento
TICKET: R$ 197
AVATAR: Mulher, 30-50, ja tentou dietas sem sucesso

MECANISMO COMBADO: Termogenese Intestinal
(combo de termogenese adaptativa + microbioma intestinal)

BIG IDEA:
Pergunta: 'Como e possivel emagrecer comendo mais do que come hoje?'
Nome Chiclete: Metodo Termofit

BIG OFFER:
✅ Produto principal: Programa Termofit (8 semanas)
✅ Bonus 1: Cardapio Termofit (receitas que ativam termogenese)
✅ Bonus 2: Checklist do Intestino Magro
✅ Garantia: 30 dias incondicional
✅ Ancoragem: R$ 1.200 → R$ 197
✅ Urgencia: Turma fecha em 48h
✅ Escassez: 200 vagas (suporte personalizado)
✅ Facilitador: 12x de R$ 19,17
✅ CTA: 'Quero Ativar Minha Termogenese'

HISTORIAS:
✅ Background Story: Nutricionista que descobriu o combo por acidente
✅ Emotional Story: Dona Maria, 47 anos, tentou de tudo, nada funcionava
✅ Discovery Story: Pesquisa sobre intestino + metabolismo revelou a causa

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Output

```yaml
output:
  - "Brief completo e consolidado em formato estruturado"
  - "Indicacao de aprovacao ou pendencias"
  - "Direcionamento para inicio da escrita (thesis-writer)"
```
