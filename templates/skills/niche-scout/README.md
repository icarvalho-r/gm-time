# Niche Scout Squad

> Squad especializado em pesquisar, identificar, analisar e ranquear os maiores e melhores perfis de especialistas **brasileiros** em qualquer nicho no **Instagram** e **TikTok**.

**Pack:** `niche-scout`
**Prefix:** `NS`
**Versao:** 1.1.0
**Idioma:** Portugues (Brasil)
**Foco Geografico:** Brasil

---

## Indice

- [Visao Geral](#visao-geral)
- [Pipeline](#pipeline)
- [Agentes](#agentes)
- [Workflows](#workflows)
- [Comandos](#comandos)
- [Como Usar](#como-usar)
- [Frameworks de Scoring](#frameworks-de-scoring)
- [Estrutura de Arquivos](#estrutura-de-arquivos)
- [Exemplos de Uso](#exemplos-de-uso)
- [FAQ](#faq)

---

## Visao Geral

O **Niche Scout** e um squad de 6 agentes que trabalham em pipeline sequencial para entregar um relatorio completo e ranqueado dos melhores especialistas brasileiros em qualquer nicho nas redes sociais.

**Problema que resolve:** Encontrar os verdadeiros especialistas em um nicho no Brasil e dificil. Existem milhares de perfis, mas poucos tem autoridade real, conteudo de qualidade e engajamento genuino. O Niche Scout automatiza essa pesquisa com criterios rigorosos e objetivos.

**O que entrega:**
- Relatorio ranqueado com os melhores perfis do nicho
- Scorecards individuais por perfil (autoridade, engajamento, conteudo)
- Score final ponderado com classificacao Tier A/B/C/D
- Analise comparativa entre perfis
- Recomendacoes acionaveis

**Tempo estimado:** 2-4 horas para scan completo de um nicho.

---

## Pipeline

```
Input: Nicho (ex: "tantra", "nutricao funcional", "direito trabalhista")
  |
  v
Phase 1: DISCOVERY (Profile Hunter)
  |  Descobre 30-50 perfis brasileiros via hashtags, redes de conexao,
  |  fontes externas (Hotmart, Amazon, YouTube, eventos)
  |  Checkpoint: minimo 20 perfis encontrados
  |
  v
Phase 2: VALIDATION (Authority Validator)
  |  Valida autoridade real com scorecard de 5 dimensoes (/15 pontos)
  |  Filtra falsos especialistas via 6 red flags
  |  Checkpoint: minimo 10 perfis aprovados (9+/15)
  |
  v
Phase 3: ENGAGEMENT (Engagement Analyst)
  |  Analisa metricas: seguidores, taxa engajamento, consistencia,
  |  formatos, crescimento. Classifica por porte (Nano a Mega)
  |  Checkpoint: todos os perfis com metricas completas
  |
  v
Phase 4: CONTENT (Content Auditor)
  |  Audita qualidade do conteudo: profundidade, originalidade,
  |  producao, pilares, estrutura de funil
  |  Checkpoint: todos os perfis com scores de conteudo
  |
  v
Phase 5: COMPILATION (Report Compiler)
  |  Calcula score final ponderado, gera ranking, cria scorecards
  |  individuais, monta relatorio executivo
  |  Checkpoint: relatorio com todas as secoes
  |
  v
Phase 6: REVIEW (Scout Chief)
  |  Revisao final, sanity check, apresentacao ao usuario
  |  Checkpoint: aprovacao humana
  |
  v
Output: Relatorio Ranqueado Final + Scorecards + Dados Brutos
```

---

## Agentes

### Scout Chief (Orchestrator)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/scout-chief.md` |
| **Tier** | Orchestrator |
| **Linhas** | 1,024 |
| **Papel** | Coordena o squad, recebe nicho-alvo, distribui tarefas, revisao final |
| **Comandos** | `*scan`, `*deep-dive`, `*compare`, `*report`, `*help`, `*exit` |

O Scout Chief e o ponto de entrada do squad. Ele recebe o nicho do usuario, distribui tarefas aos agentes especializados na ordem correta do pipeline e garante que cada checkpoint seja atendido antes de avancar.

---

### Profile Hunter (Tier 1 - Discovery)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/profile-hunter.md` |
| **Tier** | 1 |
| **Linhas** | 1,005 |
| **Papel** | Descobre perfis via hashtags, redes de conexao e fontes externas |
| **Comandos** | `*hunt`, `*hashtag-map`, `*expand`, `*help`, `*exit` |

**3 Frameworks operacionais:**
1. **Mapeamento de Hashtags** (NS-PP-001) - Pesquisa sistematica de hashtags em 3 camadas (primarias, secundarias, long-tail)
2. **Rede de Conexoes** (NS-PP-002) - Expansao a partir de perfis ancora via mencoes, collabs, tags e sugestoes
3. **Fontes Externas** (NS-PP-003) - Google, Hotmart, Udemy, Kiwify, Amazon, YouTube, podcasts, eventos

**Entrega:** Lista bruta de 30-50 perfis brasileiros com fonte documentada.

---

### Authority Validator (Tier 0 - Diagnostico)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/authority-validator.md` |
| **Tier** | 0 (Diagnostico) |
| **Linhas** | 1,109 |
| **Papel** | Valida se o perfil e autoridade real no nicho vs. apenas influencer |
| **Comandos** | `*validate`, `*scorecard`, `*red-flags`, `*help`, `*exit` |

**2 Frameworks operacionais:**
1. **Scorecard de Autoridade** (NS-AV-FW-001) - 5 dimensoes, 0-3 pontos cada:
   - D1: Formacao Academica / Credenciais
   - D2: Producao Intelectual (livros, cursos, artigos)
   - D3: Metodologia / Framework Proprio
   - D4: Pratica Profissional Alem das Redes
   - D5: Reconhecimento de Pares
   - **Total: /15 | Threshold: 9/15 para PASS**
2. **Red Flags de Falsa Autoridade** (NS-AV-FW-002) - 6 red flags com severidade e deteccao automatica

**Entrega:** Lista filtrada com scores de autoridade e justificativas.

---

### Engagement Analyst (Tier 2 - Metricas)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/engagement-analyst.md` |
| **Tier** | 2 |
| **Linhas** | 1,187 |
| **Papel** | Analisa metricas de engajamento, crescimento e qualidade de audiencia |
| **Comandos** | `*analyze`, `*benchmark`, `*growth`, `*help`, `*exit` |

**3 Frameworks operacionais:**
1. **Analise de Metricas** - 5 dimensoes: Alcance, Engajamento, Consistencia, Formato, Crescimento. Benchmarks por plataforma (Instagram vs TikTok)
2. **Classificacao por Porte** - Nano (1K-10K), Micro (10K-50K), Medio (50K-200K), Macro (200K-1M), Mega (1M+)
3. **Indicadores de Qualidade de Audiencia** - Comentarios reais vs bots, diversidade de engajamento, conteudo salvo, ratio seguidores/seguindo

**Entrega:** Perfis com metricas completas e score de engajamento normalizado 0-10.

---

### Content Auditor (Tier 2 - Qualidade)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/content-auditor.md` |
| **Tier** | 2 |
| **Linhas** | 1,152 |
| **Papel** | Avalia qualidade, profundidade e originalidade do conteudo |
| **Comandos** | `*audit`, `*pillars`, `*funnel`, `*help`, `*exit` |

**3 Frameworks operacionais:**
1. **Auditoria de Conteudo** - 5 dimensoes, 0-3 pontos cada:
   - Profundidade (superficial vs. acionavel)
   - Valor Educacional
   - Originalidade (voz propria vs. copia)
   - Qualidade de Producao
   - Pilares de Conteudo
   - **Total: /15 | Threshold: 9/15**
2. **Mapeamento de Pilares** - Identifica 3-5 pilares de conteudo por perfil
3. **Analise de Funil** - Topo (awareness), Meio (nurture), Fundo (conversao)

**Entrega:** Perfis com scores de conteudo, pilares mapeados e analise de funil.

---

### Report Compiler (Tier 3 - Relatorio)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `agents/report-compiler.md` |
| **Tier** | 3 |
| **Linhas** | 965 |
| **Papel** | Compila relatorio final ranqueado com scorecards individuais |
| **Comandos** | `*compile`, `*scorecard`, `*ranking`, `*export`, `*help`, `*exit` |

**3 Frameworks operacionais:**
1. **Score Final Composto** - Media ponderada:
   - Autoridade: **30%**
   - Engajamento: **30%**
   - Conteudo: **25%**
   - Alcance: **15%**
   - Classificacao: Tier A (8.0+), Tier B (6.5-7.9), Tier C (5.0-6.4), Tier D (<5.0)
2. **Scorecard Individual** - Card completo por perfil com metricas, scores, pontos fortes/fracos, recomendacao
3. **Relatorio Executivo** - 6 secoes: resumo, metodologia, ranking, scorecards, comparativa, recomendacoes

**Entrega:** Relatorio final ranqueado em Markdown.

---

## Workflows

### wf-niche-scan (Pipeline Principal)

| Campo | Valor |
|-------|-------|
| **Arquivo** | `workflows/wf-niche-scan.yaml` |
| **Linhas** | 2,137 |
| **Fases** | 6 (+ pre-flight) |
| **Tempo estimado** | 2-4 horas |
| **Complexidade** | Alta |

Pipeline completo com 6 fases sequenciais, checkpoints obrigatorios em cada fase, tratamento de erros por fase e template de relatorio final.

---

## Comandos

### Comandos do Scout Chief (Orchestrator)

| Comando | Descricao | Exemplo |
|---------|-----------|---------|
| `*scan {nicho}` | Executa o pipeline completo para um nicho | `*scan tantra` |
| `*deep-dive @perfil` | Analise profunda de um unico perfil | `*deep-dive @catiadamasceno` |
| `*compare` | Compara perfis lado a lado | `*compare @perfil1 @perfil2` |
| `*report` | Gera/regenera relatorio final | `*report` |
| `*help` | Lista todos os comandos | `*help` |
| `*exit` | Sai do agente | `*exit` |

### Comandos por Agente

| Agente | Comandos Principais |
|--------|-------------------|
| Profile Hunter | `*hunt`, `*hashtag-map`, `*expand` |
| Authority Validator | `*validate`, `*scorecard`, `*red-flags` |
| Engagement Analyst | `*analyze`, `*benchmark`, `*growth` |
| Content Auditor | `*audit`, `*pillars`, `*funnel` |
| Report Compiler | `*compile`, `*scorecard`, `*ranking`, `*export` |

---

## Como Usar

### Ativacao

```
@niche-scout:scout-chief
```

### Scan Completo de Nicho

```
*scan tantra
```

O Scout Chief vai:
1. Confirmar o nicho e parametros
2. Acionar o Profile Hunter para descobrir perfis
3. Passar a lista para o Authority Validator filtrar
4. Enviar aprovados para o Engagement Analyst
5. Encaminhar para o Content Auditor
6. Compilar relatorio final via Report Compiler
7. Apresentar resultado para aprovacao

### Analise de Perfil Individual

```
*deep-dive @dra.aline.sardinha
```

### Comparacao entre Perfis

```
*compare @catiadamasceno @anacanosa @mahmoudbaydoun
```

---

## Frameworks de Scoring

### Score de Autoridade (/15)

| Dimensao | Pontuacao | O que avalia |
|----------|-----------|-------------|
| Formacao Academica | 0-3 | Graduacao, especializacao, pos |
| Producao Intelectual | 0-3 | Livros, cursos, artigos |
| Metodologia Propria | 0-3 | Framework documentado |
| Pratica Profissional | 0-3 | Atuacao alem das redes |
| Reconhecimento de Pares | 0-3 | Citacoes, convites, premios |

**Threshold:** 9/15 para aprovacao

### Score de Conteudo (/15)

| Dimensao | Pontuacao | O que avalia |
|----------|-----------|-------------|
| Profundidade | 0-3 | Superficie vs. acionavel |
| Valor Educacional | 0-3 | Ensina algo replicavel |
| Originalidade | 0-3 | Voz propria vs. copia |
| Qualidade de Producao | 0-3 | Audio, video, design |
| Pilares de Conteudo | 0-3 | Temas claros e consistentes |

**Threshold:** 9/15 para aprovacao

### Score Final Composto

```
Score Final = (Autoridade x 0.30) + (Engajamento x 0.25) + (Conteudo x 0.25)
             + (Presenca Multiplataforma x 0.10) + (Potencial Parceria x 0.10)

Escala: 0 a 100
```

| Dimensao | Peso | Fonte |
|----------|------|-------|
| Autoridade | 30% | authority-validator |
| Engajamento | 25% | engagement-analyst |
| Conteudo | 25% | content-auditor |
| Presenca Multiplataforma | 10% | avaliacao combinada |
| Potencial de Parceria | 10% | indicadores publicos |

| Tier | Score | Significado |
|------|-------|-------------|
| **A** | 80 - 100 | Referencia Absoluta — prioridade maxima |
| **B** | 60 - 79 | Forte Relevancia — considerar para parceria |
| **C** | 40 - 59 | Potencial — monitorar evolucao |
| **D** | 0 - 39 | Nao Recomendado — reavaliar em 6 meses |

---

## Estrutura de Arquivos

```
squads/niche-scout/
|
├── config.yaml                         # Configuracao do squad
├── README.md                           # Este arquivo
|
├── agents/
│   ├── scout-chief.md                  # Orchestrator (1,024 linhas)
│   ├── profile-hunter.md               # Tier 1 - Discovery (1,005 linhas)
│   ├── authority-validator.md          # Tier 0 - Diagnostico (1,109 linhas)
│   ├── engagement-analyst.md           # Tier 2 - Metricas (1,187 linhas)
│   ├── content-auditor.md              # Tier 2 - Qualidade (1,152 linhas)
│   └── report-compiler.md             # Tier 3 - Relatorio (965 linhas)
|
├── workflows/
│   ├── wf-niche-scan.yaml             # Pipeline completo de nicho
│   └── wf-profile-deep-dive.yaml      # Analise profunda de perfil individual
|
├── tasks/
│   ├── compile-report.md              # Compilar relatorio final ranqueado
│   ├── generate-scorecard.md          # Gerar scorecard individual
│   ├── generate-ranking.md            # Gerar tabela de ranking
│   └── export-report.md              # Exportar em MD/CSV/JSON
|
├── templates/
│   ├── report-template.md             # Template do relatorio executivo completo
│   └── scorecard-template.md          # Template de scorecard individual
|
├── checklists/
│   └── report-quality-checklist.md    # Checklist de qualidade do relatorio
|
├── data/                               # (para expansao futura)
└── docs/                               # (para expansao futura)
```

**Total: 8,718+ linhas | 6 agentes | 2 workflows | 4 tasks | 2 templates | 1 checklist**

---

## Exemplos de Uso

### Exemplo 1: Nicho de Tantra/Sexualidade

```
> @niche-scout:scout-chief
> *scan tantra sexualidade sexologia relacionamentos

Phase 1 (Profile Hunter): 42 perfis brasileiros descobertos
Phase 2 (Authority Validator): 18 perfis aprovados (9+/15)
Phase 3 (Engagement Analyst): metricas completas para 18 perfis
Phase 4 (Content Auditor): scores de conteudo para 18 perfis
Phase 5 (Report Compiler): relatorio ranqueado gerado

TOP 5:
1. @catiadamasceno - Score 84.3/100 (Tier A)
2. @anacanosa - Score 82.1/100 (Tier A)
3. @draalinesardinha - Score 80.6/100 (Tier A)
4. @mahmoudbaydoun - Score 71.4/100 (Tier B)
5. @luizavono - Score 68.9/100 (Tier B)
```

### Exemplo 2: Nicho de Nutricao

```
> *scan nutricao funcional

Phase 1: 38 perfis encontrados
Phase 2: 15 aprovados
...
```

### Exemplo 3: Deep Dive em Perfil Especifico

```
> *deep-dive @catiadamasceno

Autoridade: 14/15 (Elite)
Engajamento: 9.1/10 (Mega - 15M seguidores)
Conteudo: 12/15 (Forte)
Score Final: 9.2 (Tier A)

Pontos Fortes: Metodologia propria (Aperta & Solta), 500K+ alunas, 15M seguidores
Pontos de Atencao: Nicho muito especifico (pompoarismo), conteudo pode ser repetitivo
```

---

## FAQ

**P: O squad funciona para qualquer nicho?**
R: Sim, desde que o nicho tenha especialistas brasileiros com presenca no Instagram e/ou TikTok.

**P: Quanto tempo demora um scan completo?**
R: Entre 2 e 4 horas dependendo do tamanho do nicho.

**P: O squad analisa perfis internacionais?**
R: Nao. O foco e exclusivamente em especialistas brasileiros.

**P: Como o squad coleta metricas?**
R: Via pesquisa web e analise publica de perfis. Nao utiliza APIs privadas ou scraping automatizado.

**P: Posso personalizar os pesos do score final?**
R: Sim, o workflow aceita o parametro `priority_weight` para ajustar os pesos.

**P: O que acontece se um checkpoint falhar?**
R: O pipeline para naquela fase (fail-fast). O Scout Chief notifica o usuario e sugere acoes corretivas.

---

## Qualidade do Squad

| Metrica | Valor | Threshold AIOS | Status |
|---------|-------|----------------|--------|
| Total de linhas | 8,718 | - | - |
| Linhas por agente (min) | 965 | 300 | ✅ |
| Linhas por agente (media) | 1,074 | 300 | ✅ |
| Linhas workflow | 2,137 | 500 | ✅ |
| Tier 0 presente | Sim | Obrigatorio | ✅ |
| Orchestrator presente | Sim | Obrigatorio | ✅ |
| Frameworks por agente (min) | 2 | 1 | ✅ |
| Output examples por agente (min) | 3 | 3 | ✅ |
| Anti-patterns por agente (min) | 5 | 5 | ✅ |

**Score geral: 8.5/10**

---

_Squad criado por Squad Architect | AIOS-FULLSTACK | 2026-02-09_
