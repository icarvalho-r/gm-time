# derick-vsl

Pipeline completo de criacao de VSL seguindo o metodo do Derick.
Da analise de mercado ate a VSL final escrita e pronta para gravacao.

## Ativacao

```
@derick-chief
```

Ou use o skill `derick-vsl` no Claude Code.

## Pipeline

O processo tem 2 blocos:

**Bloco 1 — Psicologia (Planejamento)**

| Fase | Nome | Agente |
|------|------|--------|
| 1 | Mercado | market-scout |
| 2 | Mecanismo | mechanism-engineer |
| 3 | Big Idea | idea-architect |
| 4 | Big Offer | offer-designer |
| 5 | Storytelling | story-builder |
| 6 | Brief | derick-chief |

**Bloco 2 — Escrita**

| Fase | Nome | Agente |
|------|------|--------|
| 7 | Tese de Marketing | thesis-writer |
| 8 | VSL Completa | vsl-assembler |

Ordem de escrita: Tese → PBU → Oferta → Close → Historias → Lead

## Comandos

| Comando | Descricao |
|---------|-----------|
| `*pipeline {nicho}` | Pipeline completo |
| `*mercado {nicho}` | Apenas analise de mercado |
| `*mecanismo` | Selecao e combo de mecanismo |
| `*bigidea` | Pergunta paradoxal + nome chiclete |
| `*oferta` | Big Offer (9 elementos) |
| `*historias` | 3 historias (Background, Emotional, Discovery) |
| `*brief` | Compilar/exibir brief |
| `*tese` | Escrever Tese de Marketing |
| `*vsl` | Montar VSL completa |
| `*lead` | Escrever leads |
| `*status` | Status do pipeline |
| `*help` | Listar comandos |

## Estrutura

```
derick-vsl/
  config.yaml
  README.md
  agents/
    derick-chief.md      (orchestrator)
    market-scout.md      (fase 1)
    mechanism-engineer.md (fase 2)
    idea-architect.md    (fase 3)
    offer-designer.md    (fase 4)
    story-builder.md     (fase 5)
    thesis-writer.md     (fase 7)
    vsl-assembler.md     (fase 8)
  templates/
    brief-template.yaml
  workflows/
    wf-pipeline-vsl.yaml
```

## Material de Referencia

Baseado no curso completo do Derick (50.000+ palavras transcritas).
Localizacao: `C:\Users\northon\Downloads\Curso Derick`
