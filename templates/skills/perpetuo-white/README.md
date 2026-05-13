# Perpetuo White Squad v1.0.0

> Sistema de Perpetuo White — Escalar infoprodutos com VSL + Trafego Direto + Ascensoes
> 100% baseado no framework Lucas Ramos (R$2M+/mes lucro)

## Origem

Framework extraido do podcast **Segredos da Escala #140** — Lucas Ramos (coprodutor, 21 anos, R$2M+/mes lucro com experts via trafego direto).

Extracao completa: `outputs/extracted/lucas-ramos-perpetuo-white-vsl-frameworks.md`

## O Modelo

```
[TRAFEGO] → [CRIATIVOS] → [VSL] → [FRONT R$200] → [UPSELL PRONTO R$600]
                                         ↓
                              ┌──────────┼──────────┐
                              ↓          ↓          ↓
                        [WEBINARIO] [WORKSHOP]  [FORMULARIO]
                         [DIARIO]   [SEMANAL]  [MATRICULA]
                              │          │          │
                              └──────┬───┘    [COMERCIAL]
                                     ↓              │
                              [LANCAMENTO]     [HIGH-END]
```

**Metricas reais:** CAC R$90 | Conversao VSL 4.8% | ROI front 1.7 | ROI final 3.3 | 15K alunos/mes | Margem 60-70%

## Agents (6)

| Agent | Pilar | Funcao |
|-------|-------|--------|
| `perpetuo-white-chief` | Orquestrador | Diagnostica, roteia, orquestra pipeline |
| `vsl-architect` | VSL | Escreve VSL (4 blocos + 5 leads) |
| `creative-engineer` | Criativos | Produz e testa criativos (hooks, formatos, Frankenstein) |
| `traffic-scaler` | Trafego | Estrutura e escala Meta Ads (ABO→CBO→Meta de Custo) |
| `ascension-builder` | Ascensoes | 5 sistemas de ascensao |
| `offer-architect` | Oferta | Escada de produtos + upsell PRONTO |

## Comandos

```bash
/PERPETUO:perpetuo-white-chief    # Ativar orquestrador
```

### Dentro do squad:
```
*diagnostico          # Diagnosticar funil e identificar gargalo
*pipeline             # Pipeline completo (produto→VSL→criativos→trafego→ascensoes)
*metricas             # Comparar metricas com benchmarks Lucas Ramos
*help                 # Listar todos os comandos
```

## Use Cases

1. **"Quero sair do lancamento e criar um perpetuo"** → chief → pipeline completo
2. **"Preciso escrever uma VSL para meu expert"** → chief → vsl-architect
3. **"Meus criativos estao morrendo rapido"** → chief → creative-engineer
4. **"Quero escalar de R$5K/dia para R$50K/dia"** → chief → traffic-scaler + creative-engineer
5. **"Como criar ascensoes front→back"** → chief → ascension-builder
6. **"Minha oferta nao converte"** → chief → offer-architect
7. **"Meu funil tem problema"** → chief → diagnostico rapido

## Estrutura

```
squads/perpetuo-white/
├── perpetuo-white-chief.md          # Orquestrador (Tier 0)
├── config.yaml                       # Configuracao do squad
├── README.md                         # Este arquivo
├── agents/
│   ├── vsl-architect.md              # Especialista VSL
│   ├── creative-engineer.md          # Especialista Criativos
│   ├── traffic-scaler.md             # Especialista Trafego
│   ├── ascension-builder.md          # Especialista Ascensoes
│   └── offer-architect.md            # Especialista Ofertas
├── tasks/
│   ├── pipeline-completo.md          # Pipeline 6 fases
│   └── diagnosticar-funil.md         # Diagnostico rapido
├── workflows/
│   └── wf-perpetuo-pipeline.yaml     # Workflow do pipeline
├── checklists/
│   ├── validacao-funil.yaml          # Checklist pre-escala
│   └── diagnostico-rapido.yaml       # Arvore de decisao
├── data/
│   ├── metricas-benchmark.yaml       # Benchmarks Lucas Ramos
│   ├── heuristicas.yaml              # 30+ heuristicas SE/ENTAO
│   └── routing-table.yaml            # Roteamento de problemas
├── templates/
└── docs/
```

## Sinergias com Outros Squads

| Squad | Uso |
|-------|-----|
| hormozi | Equacao de Valor para ofertas |
| todd | E5 Method para mecanismo unico |
| derick | Metodo Derick para VSLs longas |
| brunson | Funnel architecture |
| klt | Conteudo pago KLT |

## 5 Pilares do Framework

1. **Trafego** → ABO Gaveta → CBO Pre-Escala → CBO Meta de Custo (escalar 20-30%/dia)
2. **Criativos** → 10/dia em teste, 10-15 gravacoes/semana, Frankenstein, 16 formatos
3. **VSL** → 4 blocos (Lead + Mec. Problema + Mec. Solucao + Oferta), 5 leads, botao desconto
4. **Funil** → Checkout → Upsell PRONTO → Downsell → Formulario → Boas-vindas
5. **Ascensoes** → Upsell imediato + Webinario diario + Workshop semanal + Formulario + Lancamento
