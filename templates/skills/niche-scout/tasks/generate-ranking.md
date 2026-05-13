# generate-ranking

> **Task:** Gerar Tabela de Ranking Ranqueado por Score Final
> **Agente Responsável:** report-compiler
> **Comando:** `*ranking`
> **Squad:** niche-scout | **Prefixo:** NS | **Versão:** 1.0.0

---

```yaml
# ═══════════════════════════════════════════════════════════════════════════════
# TASK ANATOMY — NS-DP-TASK-003
# ═══════════════════════════════════════════════════════════════════════════════

task_name: "generate-ranking"
status: active
responsible_executor: report-compiler
execution_type: agent
estimated_time: "3-5 minutos"

input:
  obrigatorio:
    - name: scores_finais
      format: "Lista de perfis com Score Final Composto calculado (0-100)"
      fonte: "Dados dos agentes anteriores ou de *compile já executado"
      exemplo: |
        perfis:
          - handle: "@draanasardinha"
            nome: "Dra. Ana Sardinha"
            score_final: 84.3
            tier: "A"
            score_autoridade: 93
            score_engajamento: 71
            score_conteudo: 80
            nicho: "sexologia"
          - handle: "@catiadamasceno"
            nome: "Catia Damasceno"
            score_final: 73.6
            tier: "B"
            ...

  opcional:
    - name: limite_ranking
      format: "Número inteiro (padrão: 10)"
      descricao: "Quantos perfis exibir no ranking"
    - name: filtro_tier
      format: "A, B, C ou D"
      descricao: "Filtrar apenas perfis de um Tier específico"

output:
  primary: "Tabela de ranking em Markdown, ordenada por Score Final decrescente"
  secondary: "Estatísticas de distribuição de Tiers"
  formato: "Resposta concisa e visual — tabela como elemento central"

# ═══════════════════════════════════════════════════════════════════════════════
# WORKFLOW DE EXECUÇÃO
# ═══════════════════════════════════════════════════════════════════════════════

action_items:

  - fase: 0
    nome: "Preparação dos Dados"
    steps:
      - step: "0.1 — Verificar disponibilidade dos Score Finais"
        instrucao: |
          Confirme que possui Score Final calculado para todos os perfis.
          Se scores não foram calculados ainda:
          → Execute a fórmula: Score Final = (Auth×0.30) + (Eng×0.25) + (Cont×0.25)
                                             + (Multi×0.10) + (Parceria×0.10)
          Se dados de alguma dimensão estiverem ausentes:
          → Notifique: "Impossível gerar ranking sem scores completos. Execute *compile primeiro."

      - step: "0.2 — Aplicar filtros se solicitados"
        instrucao: |
          Se limite_ranking fornecido: exibir apenas os top N perfis
          Se filtro_tier fornecido: exibir apenas perfis daquele Tier
          Padrão sem filtros: exibir top 10 por Score Final

      - step: "0.3 — Ordenar por Score Final"
        instrucao: |
          Ordenar todos os perfis de forma DECRESCENTE pelo Score Final.
          Em caso de empate exato: desempatar por score de Autoridade (maior = melhor).
          Em empate de Autoridade: desempatar por score de Engajamento.

  - fase: 1
    nome: "Geração da Tabela de Ranking"
    steps:
      - step: "1.1 — Montar tabela principal"
        instrucao: |
          Gere a tabela Markdown no seguinte formato:

          ## 🏆 Ranking — {nicho} (Brasil | {plataformas})
          *Período de análise: {periodo} | {N_total} perfis analisados → {N_ranking} no ranking*

          | # | Especialista | @Handle (IG) | Score Final | Tier | Destaque |
          |---|-------------|-------------|-------------|------|----------|
          | 1 | {nome_1} | @{handle_1} | {score_1}/100 | {tier_1} | {destaque_1} |
          | 2 | {nome_2} | @{handle_2} | {score_2}/100 | {tier_2} | {destaque_2} |
          ...

          "Destaque" = 1 frase curta (máximo 8 palavras) que captura o principal diferencial.
          Exemplos:
          - "Maior taxa de engajamento do nicho (8.2%)"
          - "Único urologista com 1M+ no TikTok"
          - "Metodologia própria documentada em 3 livros"

      - step: "1.2 — Adicionar emoji de Tier"
        instrucao: |
          Use indicadores visuais nos Tiers:
          - Tier A: 🟢 A
          - Tier B: 🟡 B
          - Tier C: 🟠 C
          - Tier D: 🔴 D

      - step: "1.3 — Adicionar distribuição de Tiers"
        instrucao: |
          Após a tabela, adicione linha de distribuição:

          **Distribuição:** {N_A} Tier A 🟢 | {N_B} Tier B 🟡 | {N_C} Tier C 🟠 | {N_D} Tier D 🔴
          **Score médio do Top {N}:** {score_medio}/100

      - step: "1.4 — Adicionar nota de validade"
        instrucao: |
          Sempre adicionar ao final:
          > ⏱️ *Dados coletados em {data_coleta}. Validade recomendada: 90 dias.*
          > *Para análise detalhada de cada perfil, use `*scorecard [@handle]`.*

# ═══════════════════════════════════════════════════════════════════════════════
# ACCEPTANCE CRITERIA
# ═══════════════════════════════════════════════════════════════════════════════

acceptance_criteria:
  obrigatorio:
    - "Tabela com posição (#), nome, handle, score e tier para cada perfil"
    - "Ordenação decrescente por Score Final"
    - "Tier atribuído corretamente para cada perfil"
    - "Destaque de 1 frase por perfil"
    - "Distribuição de Tiers no rodapé da tabela"
    - "Score médio calculado"
    - "Nota de validade dos dados"

  qualidade:
    - "Leitura completa em menos de 30 segundos"
    - "Nenhum dado inventado — apenas scores calculados pelos agentes"
    - "Destaques únicos por perfil (não repetir o mesmo destaque)"

# ═══════════════════════════════════════════════════════════════════════════════
# ANTI-PATTERNS
# ═══════════════════════════════════════════════════════════════════════════════

anti_patterns:
  - "Nunca gerar ranking sem Score Final calculado"
  - "Nunca incluir perfis com dados parciais sem sinalização"
  - "Nunca repetir o mesmo destaque para perfis diferentes"
  - "Nunca omitir a data de coleta dos dados"
  - "Nunca exibir ranking sem distribuição de Tiers"
  - "Nunca usar Tier sem correspondência correta com o Score Final"
```

---

> **NS-TASK-GENERATE-RANKING v1.0.0** | Squad: niche-scout | Executor: report-compiler
> Comando: `*ranking` | Output: Tabela de ranking visual em Markdown
