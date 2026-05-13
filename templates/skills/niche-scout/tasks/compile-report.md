# compile-report

> **Task:** Compilar o Relatório Final Ranqueado do Niche Scout
> **Agente Responsável:** report-compiler
> **Comando:** `*compile`
> **Squad:** niche-scout | **Prefixo:** NS | **Versão:** 1.0.0

---

```yaml
# ═══════════════════════════════════════════════════════════════════════════════
# TASK ANATOMY — NS-DP-TASK-001
# ═══════════════════════════════════════════════════════════════════════════════

task_name: "compile-report"
status: active
responsible_executor: report-compiler
execution_type: agent
estimated_time: "15-25 minutos"

input:
  obrigatorio:
    - name: dados_autoridade
      source: authority-validator
      format: "Lista de perfis com scores de autoridade (0-100) e justificativas"
      exemplo: |
        perfis:
          - handle: "@draanasardinha"
            score_autoridade: 93
            tier_autoridade: "Elite (9+/15)"
            justificativa: "CRM ativo, doutorado em sexologia, livros publicados"

    - name: dados_engajamento
      source: engagement-analyst
      format: "Lista de perfis com métricas de engajamento normalizadas (0-100)"
      exemplo: |
        perfis:
          - handle: "@draanasardinha"
            score_engajamento: 71
            seguidores_total: 285000
            taxa_engajamento: "4.2%"
            plataformas: ["instagram", "tiktok"]

    - name: dados_conteudo
      source: content-auditor
      format: "Lista de perfis com scores de conteúdo (0-100) e análise qualitativa"
      exemplo: |
        perfis:
          - handle: "@draanasardinha"
            score_conteudo: 80
            pilares: ["educação sexual", "saúde feminina", "relacionamentos"]
            formato_principal: "Reels"

  opcional:
    - name: presenca_multiplataforma
      source: engagement-analyst
      format: "Score 0-100 por perfil (calculado pelo analyst)"

    - name: potencial_parceria
      source: dados_publicos_perfil
      format: "Score 0-100 baseado em indicadores públicos"

output:
  primary: "Relatório executivo completo em Markdown com ranking e scorecards individuais"
  secondary: "Dados estruturados prontos para export"
  destino: "scout-chief (para revisão final)"
  formato_nome: "NS-{nicho}-{data-YYYY-MM}-relatorio.md"

# ═══════════════════════════════════════════════════════════════════════════════
# WORKFLOW DE EXECUÇÃO
# ═══════════════════════════════════════════════════════════════════════════════

action_items:

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 0: VALIDAÇÃO DE INPUTS
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 0
    nome: "Validação de Inputs"
    executor: report-compiler

    steps:
      - step: "0.1 — Verificar completude dos dados"
        instrucao: |
          Antes de iniciar, confirme que recebeu dados das TRÊS dimensões obrigatórias:
          ✅ Scores de autoridade (authority-validator)
          ✅ Scores de engajamento (engagement-analyst)
          ✅ Scores de conteúdo (content-auditor)

          Se QUALQUER dimensão estiver ausente → PARE e notifique o scout-chief:
          "Não posso compilar sem dados de: {dimensoes_faltantes}. Execute os agentes necessários antes de prosseguir."

      - step: "0.2 — Verificar quantidade mínima"
        instrucao: |
          Confirme que há pelo menos 3 perfis com dados completos.
          Se menos de 3 perfis → notifique: "Mínimo de 3 perfis necessário para gerar ranking confiável."

      - step: "0.3 — Verificar atualidade dos dados"
        instrucao: |
          Verifique a data de coleta dos dados.
          Se dados com mais de 90 dias → adicione AVISO de validade no relatório:
          "⚠️ AVISO: Dados coletados em {data}. Métricas podem estar desatualizadas. Recomenda-se nova coleta."

    checkpoint_0: |
      ✅ PASS: 3+ perfis com dados completos das 3 dimensões
      ❌ VETO: Qualquer dimensão principal ausente → PARE e notifique

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 1: CÁLCULO DO SCORE FINAL COMPOSTO
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 1
    nome: "Cálculo do Score Final Composto"
    executor: report-compiler

    formula: |
      Score Final = (Autoridade × 0.30) + (Engajamento × 0.25) + (Conteúdo × 0.25)
                    + (Presença Multiplataforma × 0.10) + (Potencial Parceria × 0.10)

      Escala final: 0 a 100

    steps:
      - step: "1.1 — Calcular score de Presença Multiplataforma"
        instrucao: |
          Para cada perfil, calcule o score de Presença Multiplataforma (0-100):
          - Ativo em Instagram E TikTok: 100
          - Presente em ambos, inativo em um: 60
          - Apenas Instagram com forte presença (100k+): 40
          - Apenas TikTok com forte presença: 30
          - Presença fraca em ambos: 20

      - step: "1.2 — Calcular score de Potencial de Parceria"
        instrucao: |
          Para cada perfil, calcule o score de Potencial de Parceria (0-100)
          verificando indicadores públicos:
          + Email de contato comercial na bio: +20 pontos
          + Histórico de collabs com marcas visíveis: +25 pontos
          + Menciona assessoria/consultoria na bio: +20 pontos
          + Evidência de que responde DMs (comentários públicos): +15 pontos
          + Link de contato profissional (Linktree, etc.): +10 pontos
          + Media kit ou "parcerias" mencionado: +10 pontos
          Máximo: 100 pontos

      - step: "1.3 — Aplicar fórmula do Score Final"
        instrucao: |
          Para CADA perfil, calcule:
          Score Final = (Auth_score × 0.30) + (Eng_score × 0.25) + (Cont_score × 0.25)
                        + (Multi_score × 0.10) + (Parceria_score × 0.10)

          Arredonde para 1 casa decimal.
          Documente cada componente para rastreabilidade.

      - step: "1.4 — Classificar Tiers"
        instrucao: |
          Atribua o Tier baseado no Score Final:
          - Tier A (80-100): Referência Absoluta
          - Tier B (60-79): Forte Relevância
          - Tier C (40-59): Potencial
          - Tier D (0-39): Não Recomendado

      - step: "1.5 — Ordenar ranking"
        instrucao: |
          Ordene todos os perfis por Score Final decrescente.
          Em caso de empate, desempate por score de Autoridade.

    checkpoint_1: |
      ✅ PASS: Todos os perfis com Score Final calculado e Tier atribuído
      ❌ VETO: Score Final calculado sem todas as 5 dimensões → recalcular

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 2: GERAÇÃO DO RELATÓRIO EXECUTIVO
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 2
    nome: "Geração do Relatório Executivo"
    executor: report-compiler

    instrucao_geral: |
      Gere o relatório seguindo EXATAMENTE a estrutura de 6 seções abaixo.
      Use o template em templates/report-template.md como referência visual.
      Princípio guia: "pirâmide invertida" — informação mais importante primeiro.

    steps:
      - step: "2.1 — Seção 1: Resumo Executivo"
        instrucao: |
          Redigir um parágrafo único de NO MÁXIMO 150 palavras cobrindo:
          - Nicho pesquisado
          - Total de perfis analisados e aprovados
          - Top 3 perfis com scores
          - Insight principal do nicho (padrão ou paradoxo identificado)
          - Recomendação em uma frase

          Template:
          "Esta pesquisa analisou {N_total} perfis de especialistas brasileiros no nicho
          de {nicho} nas plataformas Instagram e TikTok. Após o pipeline completo de
          validação, {N_aprovados} perfis atingiram os critérios mínimos de qualidade.
          Os três perfis com maior Score Final Composto são: {top1_nome} ({top1_score}/100),
          {top2_nome} ({top2_score}/100) e {top3_nome} ({top3_score}/100). O nicho
          apresenta {insight_principal}. Recomendamos {recomendacao_principal}."

      - step: "2.2 — Seção 2: Metodologia"
        instrucao: |
          Documente de forma transparente:
          - Pipeline de agentes utilizado (Hunter → Validator → Analyst → Auditor → Compiler)
          - Critérios de inclusão e exclusão de perfis
          - Pesos do Score Final Composto (tabela)
          - Período de coleta dos dados
          - Plataformas analisadas
          - Limitações conhecidas (dados públicos, stories não incluídos, etc.)

          Use tabela para os pesos:
          | Dimensão | Peso | Fonte |
          |----------|------|-------|
          | Autoridade | 30% | authority-validator |
          | Engajamento | 25% | engagement-analyst |
          | Conteúdo | 25% | content-auditor |
          | Presença Multiplataforma | 10% | avaliação combinada |
          | Potencial de Parceria | 10% | indicadores públicos |

      - step: "2.3 — Seção 3: Top 10 Ranking"
        instrucao: |
          Gere tabela Markdown com os TOP 10 perfis (ou todos se < 10):
          | # | Perfil | @Handle (IG) | Score Final | Tier | Destaque |
          Ordenação: decrescente por Score Final
          "Destaque" = 1 frase que captura o diferencial principal do perfil

      - step: "2.4 — Seção 4: Scorecards Individuais"
        instrucao: |
          Para cada perfil no Top 10, gere o scorecard completo usando o
          template de templates/scorecard-template.md.
          Ordem: mesma do ranking.
          Separe cada scorecard com linha divisória (---).

      - step: "2.5 — Seção 5: Análise Comparativa"
        instrucao: |
          Analise padrões transversais entre os perfis ranqueados:
          - Distribuição de scores por dimensão (quem tem alta autoridade mas baixo engajamento?)
          - Padrões recorrentes (ex: "90% dos Tier A são profissionais de saúde com CRM")
          - Gaps identificados no nicho (o que está sendo pouco explorado?)
          - Perfis com crescimento mais acelerado
          - Correlações entre métricas

      - step: "2.6 — Seção 6: Recomendações"
        instrucao: |
          Liste recomendações concretas e acionáveis:
          - Perfis prioritários para abordagem (Tier A) + ação sugerida
          - Perfis para monitoramento (Tier B) + prazo de reavaliação
          - Oportunidades de mercado identificadas no nicho
          - Próximos passos sugeridos
          - Prazo sugerido para nova pesquisa (90 dias padrão)

    checkpoint_2: |
      ✅ PASS: Relatório com todas as 6 seções completas
      ❌ VETO: Ausência de qualquer seção obrigatória → completar antes de entregar

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 3: VALIDAÇÃO E ENTREGA
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 3
    nome: "Validação e Entrega"
    executor: report-compiler

    steps:
      - step: "3.1 — Aplicar checklist de qualidade"
        instrucao: |
          Execute o checklist em checklists/report-quality-checklist.md.
          Todos os itens obrigatórios devem passar antes de entregar.

      - step: "3.2 — Teste final de legibilidade"
        instrucao: |
          Confirme que um tomador de decisão consegue:
          ✅ Ler o resumo executivo e entender os achados em 30 segundos
          ✅ Consultar o ranking e identificar os melhores em 10 segundos
          ✅ Abrir qualquer scorecard e ter visão completa em 1 minuto
          ✅ Seguir as recomendações sem contexto adicional

      - step: "3.3 — Entregar ao scout-chief"
        instrucao: |
          Notifique o scout-chief:
          "Relatório do nicho {nicho} compilado e pronto para revisão final.
          {N_perfis} perfis ranqueados | Score médio: {score_medio}/100 |
          Distribuição: {N_A} Tier A | {N_B} Tier B | {N_C} Tier C"

    checkpoint_3: |
      ✅ PASS: Checklist aprovado + relatório entregue ao scout-chief
      ❌ VETO: Itens bloqueantes no checklist → corrigir antes de entregar

# ═══════════════════════════════════════════════════════════════════════════════
# ACCEPTANCE CRITERIA
# ═══════════════════════════════════════════════════════════════════════════════

acceptance_criteria:
  obrigatorio:
    - "Score Final Composto calculado com exatamente os 5 pesos documentados"
    - "Todos os perfis do ranking com Tier atribuído corretamente"
    - "Resumo Executivo com no máximo 150 palavras"
    - "Seção de Metodologia com pesos e critérios transparentes"
    - "Top 10 Ranking em tabela ordenada por Score Final decrescente"
    - "Scorecard individual para cada perfil do Top 10"
    - "Análise Comparativa com pelo menos 3 padrões identificados"
    - "Recomendações com ações concretas e prazos"
    - "Nenhum perfil internacional incluído"
    - "Dados dentro do período de validade (90 dias) ou com aviso"

  qualidade:
    - "Scores rastreáveis até dados dos agentes anteriores"
    - "Linguagem executiva: dado → implicação → recomendação"
    - "Tabelas Markdown formatadas corretamente"
    - "Nenhuma opinião sem suporte em dados"

# ═══════════════════════════════════════════════════════════════════════════════
# ANTI-PATTERNS
# ═══════════════════════════════════════════════════════════════════════════════

anti_patterns:
  - "Nunca inventar scores — apenas dados recebidos dos agentes"
  - "Nunca omitir pontos de atenção para favorecer um perfil"
  - "Nunca alterar pesos do Score Final sem aprovação explícita"
  - "Nunca publicar ranking sem seção de Metodologia"
  - "Nunca incluir perfis sem os 3 scores principais (autoridade + engajamento + conteúdo)"
  - "Nunca usar linguagem vaga: 'bom engajamento' → sempre dado numérico"
  - "Nunca misturar perfis brasileiros com internacionais sem sinalização"
```

---

> **NS-TASK-COMPILE-REPORT v1.0.0** | Squad: niche-scout | Executor: report-compiler
> Comando: `*compile` | Fases: 3 | Output: Relatório executivo ranqueado em Markdown
