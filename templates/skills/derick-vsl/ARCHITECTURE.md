# ARCHITECTURE — Squad derick-vsl

## Pipeline Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    BLOCO 1: PSICOLOGIA                          │
│                   (Planejamento Estrategico)                    │
│                                                                 │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐                  │
│  │  Phase 1  │───▶│  Phase 2  │───▶│  Phase 3  │                │
│  │  Mercado  │    │Mecanismo │    │ Big Idea │                  │
│  │market-scout│   │mechanism-│    │  idea-   │                  │
│  │           │    │engineer  │    │architect │                  │
│  └──────────┘    └──────────┘    └─────┬────┘                  │
│       │                                │                        │
│       │          ┌──────────┐          │                        │
│       └─────────▶│  Phase 4  │◀────────┘                        │
│                  │ Big Offer │                                   │
│                  │  offer-   │                                   │
│                  │ designer  │                                   │
│                  └─────┬────┘                                   │
│                        │                                        │
│                  ┌──────────┐                                   │
│                  │  Phase 5  │                                   │
│                  │Storytelling│                                  │
│                  │  story-   │                                   │
│                  │ builder   │                                   │
│                  └─────┬────┘                                   │
│                        │                                        │
│                  ┌──────────┐                                   │
│                  │  Phase 6  │                                   │
│                  │  BRIEF    │  ◀── brief-completeness-checklist │
│                  │derick-chief│                                  │
│                  └─────┬────┘                                   │
└────────────────────────┼────────────────────────────────────────┘
                         │
            ┌────────────▼─────────────┐
            │    QUALITY GATE: BRIEF   │
            │  Todos os checks passam? │
            └────────────┬─────────────┘
                         │
┌────────────────────────┼────────────────────────────────────────┐
│                    BLOCO 2: COMUNICACAO                          │
│                        (Escrita)                                │
│                                                                 │
│                  ┌──────────┐                                   │
│                  │  Phase 7  │                                   │
│                  │   TESE    │  ◀── Centro de tudo               │
│                  │thesis-    │                                   │
│                  │writer     │                                   │
│                  └─────┬────┘                                   │
│                        │                                        │
│         ┌──────────────┼──────────────┐                         │
│         ▼              ▼              ▼                          │
│    ┌─────────┐   ┌─────────┐   ┌─────────┐                     │
│    │  PBU    │──▶│  Oferta  │──▶│  Close  │                     │
│    │         │   │          │   │         │                     │
│    └─────────┘   └─────────┘   └─────────┘                     │
│         │              │              │                          │
│         └──────────────┼──────────────┘                         │
│                        ▼                                        │
│                  ┌─────────┐                                    │
│                  │Historias │                                    │
│                  └────┬────┘                                    │
│                       ▼                                         │
│                  ┌─────────┐                                    │
│                  │  LEAD   │  ◀── Escrito por ULTIMO             │
│                  └────┬────┘                                    │
│                       │         Todos: vsl-assembler             │
│                       ▼                                         │
│              ┌─────────────────┐                                │
│              │  VSL COMPLETA   │  ◀── vsl-quality-checklist      │
│              └─────────────────┘                                │
└─────────────────────────────────────────────────────────────────┘
```

## Data Flow

```
market-scout ──▶ mechanism-engineer ──▶ idea-architect
     │                    │                    │
     │                    ▼                    │
     │              offer-designer ◀───────────┘
     │                    │
     ▼                    ▼
     └──────────▶ story-builder
                       │
                       ▼
              ┌─────────────┐
              │    BRIEF    │  ◀── derick-chief compila
              │ (Documento  │
              │  Central)   │
              └──────┬──────┘
                     │
              ┌──────▼──────┐
              │thesis-writer │
              └──────┬──────┘
                     │
              ┌──────▼──────┐
              │vsl-assembler │──▶ VSL Final
              └─────────────┘
```

## Estrutura de Diretorios

```
Squads/derick-vsl/
├── config.yaml                  # Configuracao do squad
├── ARCHITECTURE.md              # Este arquivo
├── README.md                    # Documentacao do squad
│
├── agents/                      # Identidade dos agentes (~300 linhas cada)
│   ├── derick-chief.md          # Orchestrator
│   ├── market-scout.md          # Tier 0 — Analise de mercado
│   ├── mechanism-engineer.md    # Tier 1 — Selecao de mecanismo
│   ├── idea-architect.md        # Tier 1 — Big Idea
│   ├── offer-designer.md        # Tier 1 — Big Offer
│   ├── story-builder.md         # Tier 1 — Storytelling
│   ├── thesis-writer.md         # Tier 1 — Tese de Marketing (CRITICAL)
│   └── vsl-assembler.md         # Tier 1 — Montagem VSL
│
├── tasks/                       # Logica de execucao
│   ├── market-scout-execute.md
│   ├── mechanism-engineer-execute.md
│   ├── idea-architect-execute.md
│   ├── offer-designer-execute.md
│   ├── story-builder-execute.md
│   ├── thesis-writer-execute.md
│   ├── vsl-assembler-execute.md
│   ├── compile-brief.md         # Phase 6: Compilacao do Brief
│   └── validate-phase-output.md # Validacao reutilizavel
│
├── data/                        # Frameworks compartilhados
│   ├── derick-method-core.yaml  # Filosofia, 3 vendas, pipeline, writing order
│   ├── mechanism-framework.yaml # Triade POR QUE/O QUE/COMO, regras de combo
│   ├── big-idea-framework.yaml  # Pergunta paradoxal, nome chiclete
│   ├── vsl-structure-reference.yaml  # Blocos da VSL, ordem canonica
│   └── thesis-argument-templates.yaml  # Templates dos 3 argumentos da tese
│
├── checklists/                  # Validacao
│   ├── vsl-quality-checklist.md      # Quality gate final da VSL
│   └── brief-completeness-checklist.md  # Quality gate pre-escrita
│
├── workflows/
│   └── wf-pipeline-vsl.yaml    # Workflow principal (8 fases)
│
├── templates/
│   └── brief-template.yaml     # Template do Brief
│
├── briefs/                     # Briefs de projetos (memorias)
│   └── ...
│
└── .backup/                    # Backups pre-upgrade
    ├── agents-v1/
    ├── config-v1.yaml
    └── wf-pipeline-vsl-v1.yaml
```

## Principio de Separacao

```
AGENT (identidade)     →  "Quem eu sou, como penso, como falo"
TASK  (execucao)       →  "O que fazer, passo a passo, com exemplos"
DATA  (conhecimento)   →  "Frameworks compartilhados entre agents"
CHECKLIST (validacao)  →  "Criterios de qualidade com severidade"
```

## Responsabilidades por Fase

| Fase | Agent | Task | Output |
|------|-------|------|--------|
| 1. Mercado | market-scout | market-scout-execute.md | Relatorio 3 tendencias |
| 2. Mecanismo | mechanism-engineer | mechanism-engineer-execute.md | Combo (POR QUE + O QUE + COMO) |
| 3. Big Idea | idea-architect | idea-architect-execute.md | Pergunta paradoxal + nome chiclete |
| 4. Big Offer | offer-designer | offer-designer-execute.md | Oferta com 9 elementos |
| 5. Storytelling | story-builder | story-builder-execute.md | 3 historias estruturadas |
| 6. Brief | derick-chief | compile-brief.md | Brief completo |
| 7. Tese | thesis-writer | thesis-writer-execute.md | 3 argumentos da tese |
| 8. VSL | vsl-assembler | vsl-assembler-execute.md | VSL completa |

## As 3 Vendas (Mapeamento)

| Venda | Blocos | Pergunta que Responde |
|-------|--------|----------------------|
| Venda do Conteudo | Lead | "Por que assistir?" |
| Venda da Esperanca | Historias + Tese | "Por que funciona pra mim?" |
| Venda do Valor | PBU + Oferta + Close | "Por que comprar?" |

## Quality Gates

| Gate ID | Nome | Quando | Checklist |
|---------|------|--------|-----------|
| QG-BRIEF | Brief Completo | Apos Fase 6, antes da escrita | brief-completeness-checklist.md |
| QG-TESE | Tese Forte | Apos Fase 7, antes do assembly | Inline no workflow |
| QG-FINAL | VSL Completa | Apos Fase 8, entrega final | vsl-quality-checklist.md |
