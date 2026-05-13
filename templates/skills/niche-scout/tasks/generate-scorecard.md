# generate-scorecard

> **Task:** Gerar Scorecard Individual de um Perfil
> **Agente Responsável:** report-compiler
> **Comando:** `*scorecard [@handle]`
> **Squad:** niche-scout | **Prefixo:** NS | **Versão:** 1.0.0

---

```yaml
# ═══════════════════════════════════════════════════════════════════════════════
# TASK ANATOMY — NS-DP-TASK-002
# ═══════════════════════════════════════════════════════════════════════════════

task_name: "generate-scorecard"
status: active
responsible_executor: report-compiler
execution_type: agent
estimated_time: "5-8 minutos por perfil"

input:
  obrigatorio:
    - name: handle_perfil
      format: "@handle ou nome completo do especialista"
      exemplo: "@draanasardinha"

    - name: dados_completos_perfil
      source: "Todos os agentes anteriores do pipeline"
      campos_obrigatorios:
        - "nome_completo"
        - "handle_instagram"
        - "handle_tiktok (ou null se não presente)"
        - "plataformas_ativas"
        - "nicho"
        - "score_autoridade (0-100)"
        - "score_engajamento (0-100)"
        - "score_conteudo (0-100)"
        - "seguidores_total"
        - "taxa_engajamento_media"
        - "frequencia_postagem (posts/semana)"
        - "formato_principal"

  opcional:
    - name: score_presenca_multi
      format: "0-100 (se não fornecido, será calculado)"
    - name: score_potencial_parceria
      format: "0-100 (se não fornecido, será calculado a partir de dados públicos)"
    - name: contexto_comparativo
      format: "Score médio do nicho para benchmarking"

output:
  primary: "Scorecard individual completo em Markdown"
  formato: "Card padronizado com cabeçalho, métricas, scores, pontos fortes/fracos e recomendação"
  destino: "Usuário ou inclusão no relatório completo"

# ═══════════════════════════════════════════════════════════════════════════════
# WORKFLOW DE EXECUÇÃO
# ═══════════════════════════════════════════════════════════════════════════════

action_items:

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 0: PREPARAÇÃO E VALIDAÇÃO
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 0
    nome: "Preparação"
    steps:
      - step: "0.1 — Verificar dados disponíveis"
        instrucao: |
          Confirme que possui os dados obrigatórios do perfil.
          Se faltarem scores de alguma dimensão:
          → Notifique: "Dados incompletos para {handle}. Faltam: {campos_faltantes}.
            Execute os agentes correspondentes antes de gerar o scorecard."

      - step: "0.2 — Calcular scores auxiliares se ausentes"
        instrucao: |
          Se score_presenca_multi não fornecido, calcule:
          - Ativo em IG + TT: 100
          - Presente em ambos, inativo em um: 60
          - Apenas IG forte (100k+): 40
          - Apenas TT forte: 30
          - Fraco em ambos: 20

          Se score_potencial_parceria não fornecido, estime com base em dados públicos:
          + Email comercial na bio: +20
          + Histórico de collabs visível: +25
          + Assessoria/consultoria na bio: +20
          + Evidência de resposta a DMs: +15
          + Link profissional (Linktree etc.): +10
          + Menciona "parcerias" ou "media kit": +10

      - step: "0.3 — Calcular Score Final Composto"
        instrucao: |
          Score Final = (Auth×0.30) + (Eng×0.25) + (Cont×0.25) + (Multi×0.10) + (Parceria×0.10)
          Arredonde para 1 casa decimal.

          Atribuir Tier:
          - 80-100: Tier A — Referência Absoluta
          - 60-79:  Tier B — Forte Relevância
          - 40-59:  Tier C — Potencial
          - 0-39:   Tier D — Não Recomendado

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 1: ANÁLISE QUALITATIVA
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 1
    nome: "Análise Qualitativa"
    steps:
      - step: "1.1 — Identificar Top 3 Pontos Fortes"
        instrucao: |
          Identifique os 3 aspectos mais positivos do perfil, priorizando:
          - Scores acima de 80 em qualquer dimensão
          - Métricas que superam a média do nicho
          - Características únicas (metodologia própria, credenciais raras, etc.)
          - Crescimento acelerado ou tendências positivas

          Formato: Frase objetiva com dado quantitativo quando disponível.
          Exemplo: "Taxa de engajamento 8.2% — top 3% do nicho (média: 3.1%)"

      - step: "1.2 — Identificar Top 3 Pontos de Atenção"
        instrucao: |
          Identifique os 3 aspectos mais fracos ou preocupantes:
          - Scores abaixo de 60 em qualquer dimensão
          - Inconsistências (alta autoridade + baixo engajamento)
          - Riscos (crescimento inorgânico suspeito, conteúdo irregular)
          - Gaps estratégicos (presença apenas em uma plataforma)

          Formato: Frase objetiva, sem julgamento, focada em dado.
          Exemplo: "Presença no TikTok incipiente (57k vs 285k no IG) — oportunidade não aproveitada"

      - step: "1.3 — Formular Recomendação Final"
        instrucao: |
          Com base no Tier e nos dados, formule:
          1. Justificativa em 1-2 frases: por que este Tier?
          2. Ação sugerida:
             - Tier A: "Abordagem prioritária para parceria — contato imediato recomendado"
             - Tier B: "Considerar para parceria — validar fit antes de abordar"
             - Tier C: "Monitorar por 90 dias — reavaliar evolução"
             - Tier D: "Não recomendado no momento — reavaliar em 6 meses"

  # ─────────────────────────────────────────────────────────────────────────────
  # FASE 2: GERAÇÃO DO SCORECARD
  # ─────────────────────────────────────────────────────────────────────────────
  - fase: 2
    nome: "Geração do Scorecard"
    steps:
      - step: "2.1 — Gerar scorecard usando template"
        instrucao: |
          Use o template em templates/scorecard-template.md e preencha todos os campos.
          Substitua TODOS os placeholders {variavel} por dados reais.
          Não deixe nenhum campo em branco — use "N/D" se dado não disponível.

          ESTRUTURA OBRIGATÓRIA:
          ---
          ### SCORECARD: {nome_especialista}
          **{@handle_ig}** (IG) | **{@handle_tt}** (TT, se aplicável) | Plataformas: {plataformas}
          **Nicho:** {nicho} | **Tier: {tier}**

          #### Métricas-Chave
          | Métrica | Valor |
          |---------|-------|
          | Seguidores (total) | {total_seguidores} |
          | Taxa de Engajamento | {taxa_engajamento}% |
          | Posts/semana | {freq_postagem} |
          | Formato principal | {formato_principal} |

          #### Scores Detalhados
          | Dimensão | Score | Observação |
          |----------|-------|-----------|
          | Autoridade | {score_autoridade}/100 | {justificativa_autoridade} |
          | Engajamento | {score_engajamento}/100 | {justificativa_engajamento} |
          | Conteúdo | {score_conteudo}/100 | {justificativa_conteudo} |
          | Presença Multiplataforma | {score_multi}/100 | {justificativa_multi} |
          | Potencial de Parceria | {score_parceria}/100 | {justificativa_parceria} |
          | **SCORE FINAL** | **{score_final}/100** | |

          #### Pontos Fortes
          1. {ponto_forte_1}
          2. {ponto_forte_2}
          3. {ponto_forte_3}

          #### Pontos de Atenção
          1. {ponto_atencao_1}
          2. {ponto_atencao_2}
          3. {ponto_atencao_3}

          #### Recomendação
          **{tier}** — {justificativa}
          **Ação:** {acao_sugerida}
          ---

      - step: "2.2 — Adicionar contexto comparativo (se disponível)"
        instrucao: |
          Se score médio do nicho foi fornecido, adicione linha de contexto após Métricas-Chave:
          > 📊 **Contexto:** Score médio do nicho é {score_medio}/100.
          > Este perfil está {acima_abaixo} da média por {diferenca} pontos.

# ═══════════════════════════════════════════════════════════════════════════════
# ACCEPTANCE CRITERIA
# ═══════════════════════════════════════════════════════════════════════════════

acceptance_criteria:
  obrigatorio:
    - "Cabeçalho completo: nome, handle(s) e plataformas"
    - "Tabela de Métricas-Chave com 4 campos preenchidos"
    - "Todos os 5 scores de dimensão com observação"
    - "Score Final calculado corretamente pela fórmula"
    - "Tier atribuído corretamente baseado no Score Final"
    - "3 Pontos Fortes com dado quantitativo quando disponível"
    - "3 Pontos de Atenção objetivos e sem julgamento"
    - "Tier justificado em 1-2 frases"
    - "Ação recomendada clara e específica"

  qualidade:
    - "Cada score rastreável ao dado bruto do agente fonte"
    - "Pontos Fortes e de Atenção baseados em dados, não em impressão"
    - "Linguagem executiva e direta"
    - "Nenhum placeholder {variavel} não substituído"

# ═══════════════════════════════════════════════════════════════════════════════
# ANTI-PATTERNS
# ═══════════════════════════════════════════════════════════════════════════════

anti_patterns:
  - "Nunca gerar scorecard com dados parciais sem avisar"
  - "Nunca usar linguagem subjetiva: 'parece bom', 'possivelmente'"
  - "Nunca deixar placeholder não substituído"
  - "Nunca omitir pontos negativos para inflar a avaliação"
  - "Nunca alterar Score Final manualmente — apenas recalcular com dados corrigidos"
  - "Nunca recomendar Tier A para perfil com Score Final < 80"
```

---

> **NS-TASK-GENERATE-SCORECARD v1.0.0** | Squad: niche-scout | Executor: report-compiler
> Comando: `*scorecard [@handle]` | Output: Scorecard individual em Markdown
