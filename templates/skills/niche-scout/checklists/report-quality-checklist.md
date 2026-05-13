# Checklist de Qualidade — Relatório Niche Scout

> **Checklist:** NS-DP-CL-001 | **Versão:** 1.0.0
> **Uso:** Executar antes de entregar relatório ao scout-chief
> **Executor:** report-compiler | **Política:** Todos os itens ✅ OBRIGATÓRIOS devem passar

---

## INSTRUÇÃO DE USO

Revise cada item abaixo. Marque:
- ✅ PASS: Item atendido corretamente
- ❌ FAIL: Item não atendido → BLOQUEADOR, corrija antes de entregar
- ⚠️ WARN: Item parcialmente atendido → documente a exceção

Itens marcados com 🔴 são VETO CONDITIONS — uma falha bloqueia toda a entrega.

---

## BLOCO 1: INTEGRIDADE DOS DADOS

| # | Item | Status | Observação |
|---|------|--------|------------|
| 1.1 | 🔴 Scores de autoridade presentes para TODOS os perfis do ranking | | |
| 1.2 | 🔴 Scores de engajamento presentes para TODOS os perfis | | |
| 1.3 | 🔴 Scores de conteúdo presentes para TODOS os perfis | | |
| 1.4 | 🔴 Score Final calculado com a fórmula correta: (Auth×0.30)+(Eng×0.25)+(Cont×0.25)+(Multi×0.10)+(Parceria×0.10) | | |
| 1.5 | Nenhum score inventado — todos rastreáveis aos agentes fonte | | |
| 1.6 | Dados dentro do período de validade (máx. 90 dias) OU aviso de validade presente | | |
| 1.7 | Nenhum perfil internacional incluído no ranking | | |
| 1.8 | Todos os perfis passaram pelo pipeline completo (Validator + Analyst + Auditor) | | |

**Resultado Bloco 1:** ___/8 itens | FAILs: ___ | VETOs acionados: ___

---

## BLOCO 2: ESTRUTURA DO RELATÓRIO

| # | Item | Status | Observação |
|---|------|--------|------------|
| 2.1 | 🔴 Seção 1 (Resumo Executivo) presente e com ≤ 150 palavras | | |
| 2.2 | 🔴 Seção 2 (Metodologia) com pesos, critérios e período documentados | | |
| 2.3 | 🔴 Seção 3 (Ranking) presente, ordenada por Score Final decrescente | | |
| 2.4 | 🔴 Seção 4 (Scorecards) com scorecard para CADA perfil do Top 10 | | |
| 2.5 | Seção 5 (Análise Comparativa) com mínimo 3 padrões identificados | | |
| 2.6 | Seção 6 (Recomendações) com ações concretas e prazos | | |
| 2.7 | Tabelas Markdown formatadas corretamente (sem linhas quebradas) | | |
| 2.8 | Metadados do relatório presentes (nicho, data, plataformas) | | |

**Resultado Bloco 2:** ___/8 itens | FAILs: ___ | VETOs acionados: ___

---

## BLOCO 3: RANKING E TIERS

| # | Item | Status | Observação |
|---|------|--------|------------|
| 3.1 | 🔴 Ranking ordenado por Score Final decrescente (sem erros de posição) | | |
| 3.2 | 🔴 Tiers atribuídos corretamente: A=80-100, B=60-79, C=40-59, D=0-39 | | |
| 3.3 | Distribuição de Tiers documentada (N Tier A, N Tier B, etc.) | | |
| 3.4 | Score médio do Top N calculado e documentado | | |
| 3.5 | Nenhum perfil Tier D no Top 5 sem justificativa explícita | | |

**Resultado Bloco 3:** ___/5 itens | FAILs: ___ | VETOs acionados: ___

---

## BLOCO 4: SCORECARDS INDIVIDUAIS

| # | Item | Status | Observação |
|---|------|--------|------------|
| 4.1 | 🔴 Todos os 5 scores de dimensão preenchidos em cada scorecard | | |
| 4.2 | Score Final no scorecard confere com o Score Final no ranking | | |
| 4.3 | 3 Pontos Fortes por scorecard (com dado quantitativo quando disponível) | | |
| 4.4 | 3 Pontos de Atenção por scorecard (objetivos, sem julgamento) | | |
| 4.5 | Tier no scorecard confere com o Tier no ranking | | |
| 4.6 | Ação sugerida clara e específica em cada scorecard | | |
| 4.7 | Nenhum placeholder {variavel} não substituído | | |

**Resultado Bloco 4:** ___/7 itens | FAILs: ___ | VETOs acionados: ___

---

## BLOCO 5: QUALIDADE DO CONTEÚDO

| # | Item | Status | Observação |
|---|------|--------|------------|
| 5.1 | Resumo Executivo cobre: nicho, N_total, N_aprovados, top 3, insight, recomendação | | |
| 5.2 | Insight principal da Análise Comparativa é não-óbvio e baseado em dado | | |
| 5.3 | Recomendações têm: perfil específico + ação + prazo | | |
| 5.4 | Linguagem executiva: dado → implicação → recomendação (sem achismo) | | |
| 5.5 | Sem uso de linguagem vaga: "bom", "razoável", "parece", "talvez" | | |
| 5.6 | Destaques no ranking são únicos por perfil (não repetir o mesmo destaque) | | |

**Resultado Bloco 5:** ___/6 itens | FAILs: ___ | VETOs acionados: ___

---

## BLOCO 6: TESTE FINAL DE USABILIDADE

*Simule ser o tomador de decisão que receberá este relatório:*

| # | Pergunta | Tempo | Status |
|---|----------|-------|--------|
| 6.1 | Consigo entender os achados principais lendo apenas o Resumo? | ≤ 30s | |
| 6.2 | Consigo identificar os 3 melhores perfis consultando apenas o Ranking? | ≤ 10s | |
| 6.3 | Consigo ter visão completa de qualquer perfil em 1 scorecard? | ≤ 60s | |
| 6.4 | Consigo seguir as Recomendações sem precisar de contexto adicional? | — | |

**Resultado Bloco 6:** ___/4 itens

---

## RESULTADO FINAL

| Bloco | Itens | Pass | Fail | Veto |
|-------|-------|------|------|------|
| 1 — Integridade | 8 | | | |
| 2 — Estrutura | 8 | | | |
| 3 — Ranking | 5 | | | |
| 4 — Scorecards | 7 | | | |
| 5 — Qualidade | 6 | | | |
| 6 — Usabilidade | 4 | | | |
| **TOTAL** | **38** | | | |

### Veredito

- **APROVADO** ✅: Zero VETOs + máximo 3 FAILs em itens não-críticos
- **APROVADO COM RESSALVAS** ⚠️: Zero VETOs + 4-6 FAILs documentados
- **REPROVADO** ❌: 1+ VETO acionado → corrija e reexecute o checklist

**Status do relatório:** _______________
**Ação:** _______________

---

> **NS-DP-CL-001 v1.0.0** | Squad: niche-scout | Executor: report-compiler
> Aplicar antes de qualquer entrega ao scout-chief ou ao usuário
