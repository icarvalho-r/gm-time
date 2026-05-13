# Task: Diagnosticar Funil Perpétuo White

## Metadata
```yaml
task_id: PW_TASK_002
name: diagnosticar-funil
description: "Identificar gargalo no funil e rotear para o agent correto"
executor: perpetuo-white-chief
elicit: true
estimated_duration: "15-30 minutos"
```

## Objetivo
Diagnosticar rapidamente onde está o problema no funil perpétuo white e rotear para o agent especialista correto.

## Elicitação

Coletar do usuário:

```
1. Há quanto tempo o funil está rodando?
2. Qual o investimento diário atual em tráfego? (R$)
3. Qual o faturamento diário do front? (R$)
4. Qual o ticket do front-end? (R$)
5. Qual a conversão da VSL? (%)
6. Tem upsell imediato? (sim/não — se sim, qual conversão?)
7. ROI do front (sem ascensões)?
8. ROI final (com todas as ascensões)?
9. Quantos criativos estão rodando atualmente?
10. Quantos criativos novos testa por semana?
11. Quais ascensões tem ativas? (upsell/webinário/workshop/formulário/lançamento)
12. Qual o principal problema que sente? (vendas? ROI? escala? estabilidade?)
```

## Árvore de Diagnóstico

### Nível 1: ROI Geral
```
ROI < 1.0 (prejuízo):
  → Problema CRÍTICO. Pausar escala. Ir para Nível 2.

ROI 1.0-1.3 (empate/marginal):
  → Problema SÉRIO. Não escalar. Ir para Nível 2.

ROI 1.3-1.7 (operacional):
  → Front ok. Verificar ascensões (Nível 3).

ROI > 1.7 (saudável):
  → Front excelente. Focar em escala (Nível 4).
```

### Nível 2: Diagnóstico do Front
```
Conversão VSL < 1%:
  → VSL precisa reescrita completa
  → ROTEAR: @vsl-architect (*escrever-vsl)

Conversão VSL 1-2%:
  → Verificar métricas intermediárias:
  → Play rate < 40%? → Headline/thumbnail → @creative-engineer
  → Retenção 1min < 55%? → Lead ruim → @vsl-architect (*escrever-lead)
  → Retenção pitch < 30%? → Mecanismo fraco → @vsl-architect (*escrever-mecanismo)
  → Retenção ok mas não compra? → Oferta fraca → @offer-architect

Conversão VSL > 2% MAS ROI baixo:
  → CPC muito alto → Criativos fracos → @creative-engineer
  → Ticket médio baixo → Falta upsell → @offer-architect
  → Muitos reembolsos → Produto precisa melhorar + aula boas-vindas → @ascension-builder

Menos de 10 criativos testados:
  → NÃO CULPAR VSL. Produzir mais criativos primeiro.
  → ROTEAR: @creative-engineer (*produzir-criativos)
```

### Nível 3: Diagnóstico de Ascensões
```
Sem upsell imediato:
  → IMPLEMENTAR AGORA — é o mais fácil e impactante
  → ROTEAR: @offer-architect (*criar-upsell-pronto)

Upsell < 10% conversão:
  → Provavelmente é curso como upsell. Mudar para PRONTO.
  → ROTEAR: @offer-architect (*criar-upsell-pronto)

Sem webinário diário:
  → Segundo maior impacto após upsell
  → ROTEAR: @ascension-builder (*webinario-diario)

Sem workshop:
  → Terceiro maior impacto
  → ROTEAR: @ascension-builder (*workshop)

Sem formulário de matrícula:
  → Perda de leads qualificados para comercial
  → ROTEAR: @ascension-builder (*formulario-matricula)

ROI front+upsell ok (2.0+) mas ROI final < 2.5:
  → Ascensões não estão funcionando bem
  → Verificar: CTR das mensagens WhatsApp, comparecimento, conversão
  → ROTEAR: @ascension-builder (*diagnosticar-ascensao)
```

### Nível 4: Diagnóstico de Escala
```
Quer escalar mas criativos morrem:
  → Produzir mais volume (10/dia em teste)
  → ROTEAR: @creative-engineer (*produzir-criativos + *frankenstein)

Quer escalar mas ROI cai ao aumentar orçamento:
  → Estrutura de campanha inadequada
  → ROTEAR: @traffic-scaler (*escalar)

Público saturado:
  → Worldwide em português + novos formatos de criativo
  → ROTEAR: @traffic-scaler (*worldwide) + @creative-engineer (*formatos)

Tudo ok, quer mais lucro:
  → Apertar parafusos em cada etapa
  → Ordem de prioridade: upsell → leads VSL → criativos → ascensões
```

## Comparação com Benchmarks

Após diagnóstico, comparar métricas do usuário com benchmarks Lucas Ramos:

| Métrica | Usuário | Benchmark | Status |
|---------|---------|-----------|--------|
| CAC | ? | R$90 | ? |
| Conversão VSL | ? | 4.8% | ? |
| Retenção 1min | ? | 70-81% | ? |
| ROI front | ? | 1.6-1.7 | ? |
| ROI front+upsell | ? | 2.2-2.4 | ? |
| ROI final | ? | 3.2-3.3 | ? |
| Conversão upsell | ? | 15% | ? |
| Volume diário | ? | 500 alunos | ? |

## Output Esperado
- Diagnóstico claro do gargalo principal
- Roteamento para o agent correto com comando específico
- Comparação com benchmarks para mostrar onde tem gap
- Plano de ação priorizado (corrigir o que dá mais impacto primeiro)
