# export-report

> **Task:** Exportar Relatório em Formato Específico
> **Agente Responsável:** report-compiler
> **Comando:** `*export [formato]`
> **Squad:** niche-scout | **Prefixo:** NS | **Versão:** 1.0.0

---

```yaml
# ═══════════════════════════════════════════════════════════════════════════════
# TASK ANATOMY — NS-DP-TASK-004
# ═══════════════════════════════════════════════════════════════════════════════

task_name: "export-report"
status: active
responsible_executor: report-compiler
execution_type: agent
estimated_time: "2-5 minutos"

input:
  obrigatorio:
    - name: relatorio_compilado
      format: "Relatório já compilado via *compile"
      descricao: "O relatório completo precisa estar pronto antes do export"

    - name: formato_export
      format: "md | csv | json"
      opcoes:
        md:
          descricao: "Markdown formatado — padrão, legível em qualquer editor"
          uso: "Documentação, apresentações, compartilhamento"
        csv:
          descricao: "CSV tabulado — ranking e scores em planilha"
          uso: "Análise em Excel/Google Sheets, comparação numérica"
        json:
          descricao: "JSON estruturado — dados completos para integração"
          uso: "APIs, automações, dashboards programáticos"

  opcional:
    - name: campos_csv
      format: "Lista de campos a incluir no CSV (padrão: todos)"
    - name: destino_arquivo
      format: "Caminho/nome do arquivo (padrão: gerado automaticamente)"

output:
  primary: "Arquivo exportado no formato solicitado"
  nome_padrao: "NS-{nicho}-{YYYY-MM}-{formato}.{ext}"
  exemplos:
    - "NS-nutricao-esportiva-2026-03-relatorio.md"
    - "NS-nutricao-esportiva-2026-03-ranking.csv"
    - "NS-nutricao-esportiva-2026-03-dados.json"

# ═══════════════════════════════════════════════════════════════════════════════
# WORKFLOW DE EXECUÇÃO
# ═══════════════════════════════════════════════════════════════════════════════

action_items:

  - fase: 0
    nome: "Validação"
    steps:
      - step: "0.1 — Verificar relatório compilado"
        instrucao: |
          Confirme que *compile foi executado e que o relatório está disponível.
          Se relatório não compilado → notifique: "Execute *compile antes de exportar."

      - step: "0.2 — Confirmar formato solicitado"
        instrucao: |
          Verifique se o formato solicitado é: md, csv ou json
          Se formato inválido → notifique: "Formatos disponíveis: md, csv, json."

  - fase: 1
    nome: "Exportação por Formato"
    steps:

      - step: "1.A — Export Markdown (md)"
        condicao: "Apenas se formato = md"
        instrucao: |
          O relatório Markdown já está no formato correto.
          Apenas garanta:
          1. Cabeçalho do arquivo com metadados:
             ---
             Relatório Niche Scout — {nicho}
             Data: {data_coleta} | Pipeline: Niche Scout Squad v1.0
             Arquivo: NS-{nicho-slug}-{YYYY-MM}-relatorio.md
             ---
          2. Todas as seções presentes e formatadas
          3. Tabelas alinhadas corretamente

          Entregue o conteúdo pronto para cópia/salvar.

      - step: "1.B — Export CSV (csv)"
        condicao: "Apenas se formato = csv"
        instrucao: |
          Gere arquivo CSV com os dados do ranking, incluindo:

          Cabeçalho (linha 1):
          posicao,nome,handle_ig,handle_tt,nicho,tier,score_final,score_autoridade,score_engajamento,score_conteudo,score_presenca_multi,score_parceria,seguidores_total,taxa_engajamento,posts_semana,formato_principal,plataformas

          Dados (uma linha por perfil, ordenado por posição):
          1,"Dra. Ana Sardinha","@draanasardinha","@draanasardinha.tt","sexologia","A",84.3,93,71,80,100,60,285000,4.2,5,Reels,"Instagram,TikTok"

          Regras:
          - Valores com vírgula: encapsular em aspas duplas
          - Decimais: ponto como separador (não vírgula)
          - Datas: YYYY-MM-DD
          - Arrays: valores separados por | dentro das aspas

          Após o CSV, indique o nome sugerido do arquivo:
          💾 Nome sugerido: NS-{nicho-slug}-{YYYY-MM}-ranking.csv

      - step: "1.C — Export JSON (json)"
        condicao: "Apenas se formato = json"
        instrucao: |
          Gere JSON estruturado com toda a informação do relatório:

          {
            "metadata": {
              "squad": "niche-scout",
              "versao": "1.0.0",
              "nicho": "{nicho}",
              "data_coleta": "{data}",
              "data_relatorio": "{data_hoje}",
              "plataformas": ["instagram", "tiktok"],
              "total_analisados": {N},
              "total_aprovados": {N}
            },
            "formula": {
              "autoridade": 0.30,
              "engajamento": 0.25,
              "conteudo": 0.25,
              "presenca_multi": 0.10,
              "potencial_parceria": 0.10
            },
            "tiers": {
              "A": {"range": "80-100", "label": "Referência Absoluta"},
              "B": {"range": "60-79", "label": "Forte Relevância"},
              "C": {"range": "40-59", "label": "Potencial"},
              "D": {"range": "0-39", "label": "Não Recomendado"}
            },
            "ranking": [
              {
                "posicao": 1,
                "nome": "{nome}",
                "handle_ig": "{handle_ig}",
                "handle_tt": "{handle_tt ou null}",
                "nicho": "{nicho}",
                "tier": "{tier}",
                "scores": {
                  "final": {score_final},
                  "autoridade": {score_autoridade},
                  "engajamento": {score_engajamento},
                  "conteudo": {score_conteudo},
                  "presenca_multi": {score_multi},
                  "potencial_parceria": {score_parceria}
                },
                "metricas": {
                  "seguidores_total": {N},
                  "taxa_engajamento": "{pct}%",
                  "posts_semana": {N},
                  "formato_principal": "{formato}",
                  "plataformas": ["{plataforma1}", ...]
                },
                "analise": {
                  "pontos_fortes": ["{pf1}", "{pf2}", "{pf3}"],
                  "pontos_atencao": ["{pa1}", "{pa2}", "{pa3}"],
                  "recomendacao": "{recomendacao}",
                  "acao": "{acao}"
                }
              }
            ],
            "insights": ["{insight1}", "{insight2}"],
            "recomendacoes": ["{rec1}", "{rec2}"]
          }

          Após o JSON, indique o nome sugerido:
          💾 Nome sugerido: NS-{nicho-slug}-{YYYY-MM}-dados.json

# ═══════════════════════════════════════════════════════════════════════════════
# ACCEPTANCE CRITERIA
# ═══════════════════════════════════════════════════════════════════════════════

acceptance_criteria:
  obrigatorio:
    - "Formato solicitado respeitado (md, csv ou json)"
    - "Todos os dados do relatório compilado presentes no export"
    - "Nome do arquivo sugerido no padrão NS-{nicho}-{data}-{formato}"
    - "Sem perda de dados na conversão de formato"

  por_formato:
    md:
      - "Todas as 6 seções presentes"
      - "Formatação Markdown válida"
    csv:
      - "Cabeçalho com todos os campos"
      - "Uma linha por perfil"
      - "Valores com vírgula encapsulados em aspas"
    json:
      - "JSON válido (sem erros de sintaxe)"
      - "Estrutura com metadata, formula, tiers, ranking, insights e recomendações"

# ═══════════════════════════════════════════════════════════════════════════════
# ANTI-PATTERNS
# ═══════════════════════════════════════════════════════════════════════════════

anti_patterns:
  - "Nunca exportar sem relatório compilado disponível"
  - "Nunca perder dados na conversão de formato"
  - "Nunca usar formato diferente do solicitado sem avisar"
  - "Nunca gerar CSV sem cabeçalho"
  - "Nunca gerar JSON com sintaxe inválida"
  - "Nunca omitir metadados do relatório (nicho, data, período)"
```

---

> **NS-TASK-EXPORT-REPORT v1.0.0** | Squad: niche-scout | Executor: report-compiler
> Comando: `*export [md|csv|json]` | Formatos: Markdown, CSV, JSON
