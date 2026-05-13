---
name: squad-creator-pro
description: >
  Squad Creator Pro — workflow de criação de conteúdo em squad multi-agente.
  Pro upgrade pack que adiciona clonagem de mente, extração de DNA, delegação
  por especialista, roteamento de modelo, otimização avançada e quality gates.
  Use quando quiser produzir conteúdo em escala simulando o pensamento de um
  especialista real.
---

# /squad-creator-pro — Workflow multi-agente

Esse é um pacote complexo. Toda a configuração e instruções estão em:

- `config.yaml` — manifesto de features, agentes, tasks
- `workflows/` — workflows orquestrados
- `agents/` — definições de agentes
- `tasks/` — tasks atômicas
- `minds/` — clones de mente
- `scripts/` — utilitários

## Como usar

1. Leia `config.yaml` pra entender quais features e workflows estão disponíveis nessa versão
2. Pergunte ao usuário: que tipo de conteúdo ele quer criar e se já tem um especialista de referência (mind)
3. Carregue o workflow apropriado em `workflows/`
4. Execute as tasks listadas no workflow

Se faltar contexto (ex: o usuário não tem mind, não sabe qual especialista usar), conduza ele pelo onboarding extraindo DNA de fontes reais.
