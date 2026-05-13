# TEMPLATE: Relatório Niche Scout

> **Template:** NS-DP-TMPL-001 | **Versão:** 1.0.0
> **Uso:** Preencher via task compile-report.md | Executor: report-compiler
> **Instrução:** Substitua TODOS os placeholders {variavel} por dados reais.

---

<!-- ═══════════════════════════════════════════════════════════════════════════
     METADADOS DO RELATÓRIO (manter no topo do arquivo final)
     ═══════════════════════════════════════════════════════════════════════════ -->

---
**Relatório Niche Scout** | Nicho: {nicho} | Data: {data_relatorio}
Pipeline: Niche Scout Squad v1.0 | Plataformas: {plataformas}
Período de coleta: {data_inicio} a {data_fim}
---

# RELATÓRIO NICHE SCOUT — {NICHO_EM_MAIUSCULO}

**Especialistas brasileiros no Instagram e TikTok**

---

## 1. Resumo Executivo

Esta pesquisa analisou **{N_total} perfis** de especialistas brasileiros no nicho
de **{nicho}** nas plataformas {plataformas}. Após o pipeline completo de validação
(autoridade, engajamento e conteúdo), **{N_aprovados} perfis** atingiram os critérios
mínimos de qualidade para inclusão no ranking final.

Os três perfis com maior Score Final Composto são: **{top1_nome}** ({top1_score}/100),
**{top2_nome}** ({top2_score}/100) e **{top3_nome}** ({top3_score}/100).
O nicho apresenta {insight_principal}. Recomendamos {recomendacao_principal}.

> ⚠️ {aviso_validade_se_aplicavel}

---

## 2. Metodologia

### Pipeline de Análise

```
Profile Hunter (T1) → Authority Validator (T0) → Engagement Analyst (T2)
→ Content Auditor (T2) → Report Compiler (T3) → Scout Chief (revisão)
```

### Critérios de Inclusão

- Perfil brasileiro ativo (post nos últimos 30 dias)
- Conteúdo predominantemente sobre o nicho pesquisado (>70% dos posts)
- Autoridade validada com score ≥ 9/15 no Scorecard de Autoridade
- Mínimo de {min_seguidores} seguidores em pelo menos uma plataforma

### Critérios de Exclusão

- Perfis internacionais (fora do Brasil)
- Contas de marcas/empresas (apenas pessoas físicas)
- Perfis inativos (sem post nos últimos 30 dias)
- Crescimento inorgânico detectado (flags de bot/compra de seguidores)

### Pesos do Score Final Composto

| Dimensão | Peso | Fonte | Escala |
|----------|------|-------|--------|
| Autoridade | 30% | authority-validator | 0-100 |
| Engajamento | 25% | engagement-analyst | 0-100 |
| Conteúdo | 25% | content-auditor | 0-100 |
| Presença Multiplataforma | 10% | avaliação combinada | 0-100 |
| Potencial de Parceria | 10% | indicadores públicos | 0-100 |

**Fórmula:** Score Final = (Auth×0.30) + (Eng×0.25) + (Cont×0.25) + (Multi×0.10) + (Parceria×0.10)

### Classificação de Tiers

| Tier | Range | Significado |
|------|-------|-------------|
| 🟢 A | 80-100 | Referência Absoluta — prioridade máxima |
| 🟡 B | 60-79 | Forte Relevância — considerar para parceria |
| 🟠 C | 40-59 | Potencial — monitorar evolução |
| 🔴 D | 0-39 | Não Recomendado — reavaliar em 6 meses |

### Limitações

- Dados públicos apenas (Stories não incluídos)
- Métricas de TikTok limitadas ao que é visível publicamente
- Taxa de engajamento baseada em posts recentes (últimos 30 dias)
- Potencial de Parceria estimado por indicadores públicos

---

## 3. Ranking Top {N_ranking}

*{N_total} perfis analisados → {N_aprovados} aprovados → Top {N_ranking} no ranking*

| # | Especialista | @Handle (IG) | Score Final | Tier | Destaque |
|---|-------------|-------------|-------------|------|----------|
| 1 | {nome_1} | @{handle_1} | {score_1}/100 | 🟢 A | {destaque_1} |
| 2 | {nome_2} | @{handle_2} | {score_2}/100 | 🟢 A | {destaque_2} |
| 3 | {nome_3} | @{handle_3} | {score_3}/100 | 🟡 B | {destaque_3} |
| 4 | {nome_4} | @{handle_4} | {score_4}/100 | 🟡 B | {destaque_4} |
| 5 | {nome_5} | @{handle_5} | {score_5}/100 | 🟡 B | {destaque_5} |
| {N} | {nome_N} | @{handle_N} | {score_N}/100 | {tier_N} | {destaque_N} |

**Distribuição:** {N_A} Tier A 🟢 | {N_B} Tier B 🟡 | {N_C} Tier C 🟠 | {N_D} Tier D 🔴
**Score médio Top {N_ranking}:** {score_medio}/100

---

## 4. Scorecards Individuais

> *Scorecards gerados para os Top {N_ranking} perfis do ranking.*

---
### SCORECARD #1: {nome_1}
**@{handle_ig_1}** (IG) | **@{handle_tt_1}** (TT) | Plataformas: {plataformas_1}
**Nicho:** {nicho} | **Tier: 🟢 A**

#### Métricas-Chave
| Métrica | Valor |
|---------|-------|
| Seguidores (total) | {seguidores_1} |
| Taxa de Engajamento | {taxa_eng_1}% |
| Posts/semana | {posts_semana_1} |
| Formato principal | {formato_1} |

#### Scores Detalhados
| Dimensão | Score | Observação |
|----------|-------|-----------|
| Autoridade | {auth_1}/100 | {obs_auth_1} |
| Engajamento | {eng_1}/100 | {obs_eng_1} |
| Conteúdo | {cont_1}/100 | {obs_cont_1} |
| Presença Multiplataforma | {multi_1}/100 | {obs_multi_1} |
| Potencial de Parceria | {parceria_1}/100 | {obs_parceria_1} |
| **SCORE FINAL** | **{score_final_1}/100** | |

#### Pontos Fortes
1. {pf1_1}
2. {pf2_1}
3. {pf3_1}

#### Pontos de Atenção
1. {pa1_1}
2. {pa2_1}
3. {pa3_1}

#### Recomendação
**Tier A** — {justificativa_1}
**Ação:** {acao_1}

---

<!-- Repetir bloco de scorecard para cada perfil no ranking -->
<!-- ### SCORECARD #2: {nome_2} ... -->
<!-- ### SCORECARD #N: {nome_N} ... -->

---

## 5. Análise Comparativa

### Distribuição de Scores por Dimensão

| Dimensão | Média Top {N} | Máximo | Mínimo | Observação |
|----------|--------------|--------|--------|------------|
| Autoridade | {media_auth}/100 | {max_auth}/100 | {min_auth}/100 | {obs_auth} |
| Engajamento | {media_eng}/100 | {max_eng}/100 | {min_eng}/100 | {obs_eng} |
| Conteúdo | {media_cont}/100 | {max_cont}/100 | {min_cont}/100 | {obs_cont} |

### Padrões Identificados

{padrao_1}

{padrao_2}

{padrao_3}

### Gaps do Nicho

{gap_1}

{gap_2}

### Perfis com Crescimento Acelerado

{perfil_crescimento_1}

{perfil_crescimento_2}

---

## 6. Recomendações

### Abordagem Prioritária (Tier A 🟢)

{rec_tier_a}

### Monitoramento (Tier B 🟡)

{rec_tier_b}

### Oportunidades de Mercado Identificadas

1. {oportunidade_1}
2. {oportunidade_2}
3. {oportunidade_3}

### Próximos Passos

1. {proximo_passo_1}
2. {proximo_passo_2}
3. {proximo_passo_3}

**Prazo sugerido para nova pesquisa:** {prazo_reavaliacao} (recomendado: 90 dias)

---

> 📊 **Relatório gerado pelo Niche Scout Squad v1.0**
> Pipeline: Hunter → Validator → Analyst → Auditor → Compiler → Scout Chief
> Foco exclusivo: especialistas brasileiros | Instagram e TikTok
> ⏱️ *Dados de {data_coleta}. Validade: 90 dias.*
