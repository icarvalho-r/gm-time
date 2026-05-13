---
name: meta-ads-criativos
description: Criação de criativos de Meta Ads para infoprodutos no mercado brasileiro. Use SEMPRE que o usuário mencionar qualquer um destes contextos ou atalhos — "começar", "fase 1", "próxima fase", "fase X", "hooks", "ângulos", "body", "CTA", "exportar", "formatos", criação de criativos, scripts de anúncio, ads para infoprodutos, Meta Ads, roteiros de vídeo pra tráfego pago. Também use quando o usuário colar inputs como VSL, pesquisa de público, ads validados, ou pedir análise de estilo de criativos. Este skill cobre TODO o pipeline: coleta de inputs → análise de estilo → ângulos → hooks → formatos → direção de vídeo → body → CTA → exportação.
---

# Meta Ads Criativos — Pipeline Completo

## VISÃO GERAL DO FLUXO

```
FASE 1 → 1.5 → 2 → 3 → 4/4.5 → 5 → 6 → 7
Inputs   Estilo  Ângulos  Hooks  Formatos  Body  CTA  Export
```

**Regra cardinal:** Execute UMA fase por vez. Apresente output. Aguarde aprovação. Só então avance.

---

## ROTEAMENTO DE COMANDOS

| Usuário diz | Ação |
|---|---|
| "começar" / "fase 1" / "bora" | Carregar `references/fase1-prereqs.md` → iniciar coleta de inputs |
| "próxima fase" | Avançar para a fase seguinte na sequência |
| "fase X" (número) | Ir direto para fase X (verificar se fases anteriores estão completas) |
| "exportar" | Ir para Fase 7 |
| "continuar" (nova conversa) | Pedir ao usuário o bloco de contexto acumulado, absorver, retomar |
| Usuário cola inputs brutos (VSL, pesquisa, ads, arquivos) | Carregar `references/fase1-prereqs.md` → tratar como Fase 1 |

---

## CARREGAMENTO DE REFERÊNCIAS

Antes de executar cada fase, leia o arquivo de referência correspondente:

| Fase | Arquivo | Dependências de fases anteriores |
|---|---|---|
| 1 | `references/fase1-prereqs.md` | — |
| 1.5 | `references/fase1.5-estilo.md` | Resumo da Fase 1 aprovado |
| 2 | `references/fase2-angulos.md` | Glossário + Calibrador de tom |
| 3 | `references/fase3-hooks.md` | Combos de ângulos aprovados + Glossário + Calibrador |
| 4 + 4.5 | `references/fase4-formatos.md` | 20 hooks fechados + Formatos disponíveis + Elementos de cena |
| 5 | `references/fase5-body.md` | Hooks formatados + Direção de vídeo + Tipo de funil + Calibrador + Glossário |
| 6 | `references/fase6-cta.md` | 5 bodys selecionados + Tipo de funil |
| 7 | `references/fase7-exportacao.md` | 5 scripts completos |

**Se uma dependência não estiver no contexto atual** (ex: nova conversa), peça ao usuário antes de prosseguir.

---

## REGRAS GLOBAIS (aplicam em TODAS as fases)

### Tom
O tom dos scripts ESPELHA os ads validados, não a VSL. Consultar o calibrador de tom (Fase 1.5) antes de escrever qualquer hook, body ou CTA.

### Recorte de dor
Após definido na Fase 1, TUDO é filtrado pela dor específica. Ignorar dores secundárias.

### Glossário do avatar
Referência obrigatória. Se um termo não aparece na pesquisa de público nem nos ads validados, substituir ou sinalizar.

### Scripts = texto falado
NÃO incluir direções de performance (pausas, tom de voz, expressão facial, ritmo). Apenas palavras.

### Funil
- **Indireto:** Nome do produto, preço, bônus e garantia NUNCA aparecem. CTA → "aula gratuita".
- **Direto:** Produto, preço, bônus, garantia podem aparecer. CTA → oferta.

---

## TRANSIÇÃO ENTRE CONVERSAS

Quando a conversa ficar longa (geralmente Fase 4-5), instruir o usuário a abrir nova conversa no mesmo projeto e colar o seguinte bloco:

```
=== CONTEXTO ACUMULADO ===

RESUMO FASE 1:
[resumo dos inputs, dor central, formatos disponíveis, elementos de cena]

TIPO DE FUNIL: [direto/indireto]

RESTRIÇÕES: [termos proibidos, limites de compliance]

GLOSSÁRIO DO AVATAR:
[lista de termos]

CALIBRADOR DE TOM:
[3 frases-exemplo + descrição do tom]

COMBOS DE ÂNGULOS (5):
[lista]

20 HOOKS FECHADOS (com formato e direção de vídeo):
[lista completa]

FASE ATUAL: [número]
```

Na nova conversa, ao receber esse bloco, absorver e retomar da fase indicada.
