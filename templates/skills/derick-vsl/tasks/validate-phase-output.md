# Task: Validate Phase Output

**Task ID:** validate-phase-output
**Execution Type:** Reusable
**Squad:** derick-vsl
**Agent:** derick-chief

---

## Descricao

Task reutilizavel de validacao para cada fase do pipeline. O Chief executa esta validacao ao receber o output de qualquer agente antes de avancar para a proxima fase.

---

## Validacao por Fase — Planejamento

### Fase 1 — Mercado (market-scout)

```yaml
checks:
  - "Tendencias de conteudo identificadas"
  - "Padroes de consumo mapeados"
  - "Estrategias de marketing dos concorrentes analisadas"
action_if_fail: "Devolver pro market-scout com instrucoes do que falta"
```

### Fase 2 — Mecanismo (mechanism-engineer)

```yaml
checks:
  - "Pelo menos 5 mecanismos do nicho foram listados"
  - "O combo e genuinamente unico (nao existe igual no mercado)"
  - "A justificativa explica por que o combo funciona"
  - "O mecanismo e explicavel em linguagem simples"
action_if_fail: "Devolver se mecanismo parecer generico demais"
```

### Fase 3 — Big Idea (idea-architect)

```yaml
checks:
  - "A pergunta gera paradoxo real (nao e obvia)"
  - "O nome chiclete e memoravel e facil de falar"
  - "A Big Idea conecta com o mecanismo combado"
  - "Passa o 'teste do bar' — alguem falaria isso numa conversa?"
action_if_fail: "Devolver se a pergunta nao gerar curiosidade"
```

### Fase 4 — Big Offer (offer-designer)

```yaml
checks:
  - "1. Produto que o mercado ja compra (validado)"
  - "2. Feito pra aquela pessoa (personalizado)"
  - "3. Beneficios multiplos listados"
  - "4. Prazo pra cada beneficio definido"
  - "5. Esforco reduzido ao maximo"
  - "6. Reason why (justificativa do preco)"
  - "7. Preco menor que concorrencia"
  - "8. Bonus que o mercado compraria (nao lixo)"
  - "9. Seguranca/garantia maximizada"
note: "Elementos 1-6 = oferta justa. 7-9 = transforma em Big Offer."
action_if_fail: "Devolver pro offer-designer com elemento faltante"
```

### Fase 5 — Storytelling (story-builder)

```yaml
checks:
  - "As 3 historias estao presentes:"
  - "  Background Story (por que confiar?)"
  - "  Emotional Story (por que pode ajudar?)"
  - "  Discovery Story (como descobriu?)"
  - "Emotional Story segue os 8 passos (Personagem → Vida Comum → Problema → Sintomas → Solucoes que Falharam → Frustracoes → Fundo do Poco → Motivacao)"
  - "Discovery Story conecta com a Pergunta Paradoxal da Big Idea"
  - "Tipo de porta-voz definido (Guru ou Avatar Transformado)"
  - "Tem detalhes especificos (nao sao genericas)"
action_if_fail: "Devolver se alguma historia estiver rasa"
```

### Fase 6 — Brief (chief)

```yaml
checks:
  - "Resumo do mercado presente"
  - "Mecanismo combado presente"
  - "Big Idea (pergunta + nome) presente"
  - "Big Offer (9 elementos) presente"
  - "3 Historias presentes"
  - "Avatar definido"
  - "Tom de voz definido"
  - "Direcionamento de escrita presente"
action_if_fail: "So libera pro Bloco 2 se tudo estiver completo"
```

---

## Validacao por Fase — Escrita

### Escrita 1 — Tese de Marketing (thesis-writer)

```yaml
checks:
  - "Argumento 1 (Causa) tem: Ponto de Partida + Peca Faltante + Crenca Comum + Grande Pesquisa"
  - "Argumento 2 (Funcao) tem: Conclusao do Estudo + pelo menos 2 tipos de Grande Prova"
  - "Argumento 3 (Solucao) tem: Pergunta Paradoxal + Explicacao + Evidencias + Teste + Grande Resultado"
  - "A logica progride: causa → prova → solucao (cada passo leva ao proximo)"
  - "A linguagem e acessivel (nao academica)"
  - "Nao menciona produto (apenas mecanismo)"
note: "A Tese e o centro. Se estiver fraca, tudo desaba."
action_if_fail: "Devolver pro thesis-writer com feedback especifico"
```

### Escrita 2 — Product Build Up (vsl-assembler)

```yaml
checks:
  - "O PBU apresenta o produto como consequencia natural da Tese"
  - "Nao parece 'venda' ainda — parece descoberta"
  - "Conecta mecanismo → produto de forma logica"
  - "O avatar pensa 'faz sentido, quero isso'"
action_if_fail: "Devolver se PBU parecer ficha tecnica em vez de narrativa"
```

### Escrita 3 — Oferta (vsl-assembler)

```yaml
checks:
  - "Todos os 9 elementos da Big Offer viraram copy"
  - "A ancoragem de preco esta clara"
  - "A garantia remove risco"
  - "O valor percebido e muito maior que o preco"
action_if_fail: "Devolver se algum elemento estiver faltando"
```

### Escrita 4 — Close (vsl-assembler)

```yaml
checks:
  - "Urgencia e escassez estao no close"
  - "CTA e claro e direto"
  - "Tem recap de valor"
  - "Elimina ultimas objecoes"
action_if_fail: "Devolver se close nao tiver as Duas Opcoes"
```

### Escrita 5 — Historias (vsl-assembler)

```yaml
checks:
  - "As 3 historias fluem naturalmente"
  - "Cada uma reforca a Tese de Marketing"
  - "Tem emocao mas nao sao melodramaticas"
  - "Os detalhes sao especificos e criveis"
action_if_fail: "Devolver se historias estiverem desconectadas dos mecanismos"
```

### Escrita 6 — Lead (vsl-assembler)

```yaml
checks:
  - "O Lead vende o CONTEUDO (nao o produto)"
  - "Gera curiosidade imediata nos primeiros 10 segundos"
  - "Usa a Big Idea ou elemento dela"
  - "A pessoa pensa 'preciso ver o resto'"
  - "Nao revela demais — so abre o loop"
  - "Existem 4 versoes com hooks diferentes"
action_if_fail: "Devolver se Lead mencionar produto ou nao tiver 4 versoes"
```

---

## Quality Gates Transversais

### Pre-Brief (antes de compilar o Brief)
- Todas as 5 fases do planejamento estao completas?
- Cada fase foi validada pelo Chief?
- O usuario aprovou cada output?
- Existe coerencia entre as fases?

### Pre-Writing (antes de iniciar a escrita)
- O Brief esta 100% completo?
- O avatar esta claramente definido?
- O tom de voz esta definido?
- O mecanismo combado e claro e explicavel?
- A Big Idea e forte o suficiente?

### Pre-Assembly (antes de montar a VSL final)
- A Tese de Marketing esta completa (3 argumentos)?
- Os 3 argumentos progridem logicamente?
- A Tese conecta com o mecanismo e a Big Idea?

### Final Review (revisao final da VSL completa)
- A VSL faz as 3 vendas (conteudo, esperanca, valor)?
- O Lead vende o conteudo?
- As historias vendem a esperanca?
- A oferta vende o valor?
- O flow e natural — nao parece "blocos colados"?
- A Tese e o fio condutor de tudo?
- A Big Idea aparece no Lead?
- O Close tem CTA claro?

---

## Protocolo de Acao

```yaml
quando_output_incompleto:
  - "Identifica o que esta faltando"
  - "Explica pro usuario"
  - "Devolve pro agente com instrucoes claras"
  - "Nao avanca sem output completo"

quando_usuario_quer_pular:
  - "Explica o risco"
  - "Se insistir, respeita mas registra como risco no Brief"

quando_fases_incoerentes:
  - "Para o pipeline"
  - "Identifica onde quebrou a coerencia"
  - "Refaz a partir do ponto de quebra"

quando_info_insuficiente:
  - "Lista exatamente o que precisa"
  - "Sugere onde encontrar"
  - "Oferece usar o market-scout pra levantar dados"

quando_outputs_conflitam:
  - "Chama atencao pro conflito"
  - "Mostra os dois outputs lado a lado"
  - "Pede pro usuario decidir direcao"
  - "Ajusta fases impactadas"
```
