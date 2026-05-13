# Task: Thesis Writer — Execute Phase

**Task ID:** thesis-writer-execute
**Execution Type:** Agent
**Squad:** derick-vsl
**Agent:** thesis-writer
**Priority:** CRITICAL — Este e o agente MAIS IMPORTANTE de todo o squad.

---

## Input

```yaml
inputs_obrigatorios:
  - nicho: "Nicho de mercado (emagrecimento, pele, energia, diabetes, etc.)"
  - mecanismo:
      causa_oculta: "O que realmente causa o problema"
      solucao: "O que resolve a causa oculta"
  - publico_alvo: "Perfil da pessoa que vai assistir a VSL"

inputs_opcionais:
  - pesquisas: "Estudos cientificos ja coletados para usar como base"
  - persona_cobaia: "Quem vai ser o cobaia do teste (esposa, mae, paciente)"
  - resultados_referencia: "Resultados reais que podem ser usados como base"
  - crencas_do_nicho: "Crencas comuns do publico que podem ser usadas como ancora"
```

---

## Processo de Execucao

### Workflow Sequencial

```yaml
passos:
  - passo: 1
    nome: "Receber Briefing"
    descricao: >
      Receber o nicho, o mecanismo (causa + solucao), o publico-alvo,
      e quaisquer pesquisas/dados ja coletados.
    inputs:
      - "Nicho de atuacao"
      - "Mecanismo unico (causa oculta + solucao)"
      - "Perfil do publico-alvo"
      - "Pesquisas e dados cientificos (se disponiveis)"
      - "Produto (para referencia interna — nao sera mencionado na Tese)"

  - passo: 2
    nome: "Construir Argumento 1"
    descricao: >
      Escrever o Argumento da Causa do Problema seguindo as 4 etapas:
      Ponto de Partida, Peca Faltante, Crenca Comum, Grande Pesquisa.
    output: "Argumento 1 completo e revisado"

  - passo: 3
    nome: "Construir Argumento 2"
    descricao: >
      Escrever o Argumento da Funcao com a Conclusao do Estudo e
      pelo menos 2 tipos de Grande Prova.
    output: "Argumento 2 completo e revisado"

  - passo: 4
    nome: "Construir Argumento 3"
    descricao: >
      Escrever o Argumento da Solucao seguindo as 5 etapas: Pergunta
      Paradoxal, Explicacao Rapida, Evidencias Cientificas, Teste,
      Grande Resultado.
    output: "Argumento 3 completo e revisado"

  - passo: 5
    nome: "Integrar e Polir"
    descricao: >
      Unir os 3 argumentos numa narrativa fluida. Revisar transicoes.
      Garantir que o Voice DNA esta consistente. Verificar todos os
      criterios de conclusao.
    output: "Tese completa, pronta para revisao final"

  - passo: 6
    nome: "Validacao Final"
    descricao: >
      Passar a Tese por todos os criterios do completion_criteria.
      Se algum criterio falhar, voltar ao passo correspondente
      e corrigir.
    output: "Tese validada e aprovada"
```

---

## Estrutura Detalhada dos 3 Argumentos

> Os templates completos de cada argumento estao em `@ref: data/thesis-argument-templates.yaml`

### ARGUMENTO 1 — Argumento da Causa do Problema

**Objetivo:** Fazer a pessoa entender que existe uma CAUSA REAL e OCULTA para o problema dela.

**Importancia:** Planta a semente da duvida: "Sera que tudo que eu tentei ate agora falhou porque eu estava atacando o problema errado?" Quando a pessoa aceita isso, ela fica faminta pela solucao certa.

#### Etapa 1.1 — PONTO DE PARTIDA

Comece mencionando algo que as pessoas JA SABEM sobre o problema. Isso cria rapport e faz a pessoa concordar desde o inicio.

**Funcao persuasiva:** Ao validar o conhecimento existente, voce ganha credibilidade instantanea. Ela pensa: "Essa pessoa entende do assunto."

**Tecnica:** Use frases que comecem com "Como voce deve saber..." ou "Voce provavelmente ja ouviu falar que..."

**Exemplos:**
- Emagrecimento: "Como voce deve saber, o que causa o acumulo de gordura e o metabolismo lento. Quando o metabolismo desacelera, o corpo nao consegue queimar calorias de forma eficiente, e tudo que voce come acaba sendo armazenado como gordura."
- Pele/Anti-aging: "Como voce ja deve saber, o que causa o envelhecimento da pele e a perda de colageno. Com o passar dos anos, o corpo vai produzindo cada vez menos colageno, e e por isso que surgem as rugas, as linhas de expressao e a flacidez."
- Diabetes/Glicemia: "Como voce provavelmente ja sabe, o que causa o descontrole da glicemia e a resistencia a insulina. O seu corpo ate produz insulina, mas as celulas simplesmente param de responder a ela."
- Dor nas articulacoes: "Como voce ja deve ter ouvido, o que causa as dores nas articulacoes e o desgaste da cartilagem. Com o tempo, essa camada protetora vai se deteriorando, e osso comeca a raspar em osso."

**Regras:**
- Sempre use algo que seja CONSENSO no nicho
- Nao invente — use o que as pessoas realmente acreditam
- Seja breve — 2 a 3 frases no maximo
- O tom deve ser de confirmacao, nao de ensino
- Evite jargoes tecnicos neste momento

#### Etapa 1.2 — PECA FALTANTE

Logo apos validar o que a pessoa ja sabe, aponte que falta uma PECA no quebra-cabeca. Cria um GAP de curiosidade.

**Funcao persuasiva:** DESESTABILIZAR a crenca atual. A pessoa pensava que sabia tudo, mas descobre que ha algo a mais. Gera tensao cognitiva.

**Tecnica:** Use transicao "Porem..." ou "No entanto..." + constatacao de que o problema persiste + introducao de que algo novo foi descoberto.

**Exemplos:**
- Emagrecimento: "Porem, mesmo sabendo disso, ninguem ate entao conseguiu encontrar uma solucao definitiva para o metabolismo lento. Dietas, exercicios, suplementos... nada parecia funcionar de forma permanente. Ate que em dezembro de 2023, um grupo de pesquisadores de uma universidade americana encontrou uma resposta completamente inusitada."
- Pele/Anti-aging: "No entanto, mesmo com toda essa informacao disponivel, os cremes anti-idade continuam falhando. O colageno em capsulas nao funciona como prometido. Ate que um estudo publicado no Journal of Dermatological Science revelou algo que ninguem esperava."
- Calvicie: "Porem, apesar de todos saberem disso, os tratamentos para queda de cabelo continuam sendo ineficazes para a maioria das pessoas. Minoxidil, finasterida, transplante... nada ataca a causa raiz. Ate que uma pesquisa conduzida em 2024 encontrou uma pista surpreendente."

**Regras:**
- A transicao deve ser SUAVE — nao pode parecer forcada
- Mencione tentativas frustradas para validar a experiencia da pessoa
- Introduza a pesquisa/descoberta com MISTERIO
- Use datas especificas para dar credibilidade (mes + ano)
- Nunca revele a causa real aqui — apenas insinue que foi encontrada

#### Etapa 1.3 — CRENCA COMUM

Ancore a explicacao em algo que a pessoa JA ACREDITA. Funciona como ponte mental.

**Funcao persuasiva:** ANCORAGEM COGNITIVA. Usa crenca existente como trampolim para nova informacao.

**Tecnica:** Use "Voce ja deve ter ouvido falar que [crenca comum], certo?" + conexao com o tema da pesquisa.

**Exemplos:**
- Emagrecimento: "Voce ja deve ter ouvido falar que o intestino e o nosso segundo cerebro, certo? Que ele influencia tudo — desde o humor ate a imunidade. Pois bem, foi exatamente no intestino que os pesquisadores focaram a atencao."
- Pele/Anti-aging: "Voce ja deve ter ouvido falar que a pele e o maior orgao do corpo humano, certo? E que tudo que acontece por dentro se reflete por fora. Foi exatamente essa conexao que levou os cientistas a olhar para um lugar inesperado."
- Energia/Disposicao: "Voce ja deve ter ouvido falar que as mitocondrias sao as 'usinas de energia' das nossas celulas, certo? Que sao elas as responsaveis por gerar toda a energia que o corpo precisa. Pois foi justamente nelas que os pesquisadores encontraram a resposta."

**Regras:**
- A crenca deve ser AMPLAMENTE conhecida e aceita
- Use a estrutura de pergunta retorica ("certo?")
- A crenca deve ter conexao logica com a causa que sera revelada
- Nao force conexoes — se nao houver crenca comum relevante, adapte
- Este passo e uma PONTE — deve ser curto e fluido

#### Etapa 1.4 — GRANDE PESQUISA

O CLIMAX do Argumento 1. Revela o estudo cientifico que descobriu a CAUSA REAL do problema.

**Funcao persuasiva:** A pesquisa serve como AUTORIDADE EXTERNA. Nao e voce quem esta dizendo — sao CIENTISTAS. Remove a objecao "quem e voce para dizer isso?"

**Tecnica:** Narre como historia. Use numeros especificos (8 mil pessoas, 14 anos). Crie suspense antes de revelar a causa. Use frase de impacto na revelacao.

**Exemplos:**
- Emagrecimento: "Veja bem, cientistas da Universidade de Washington estavam analisando o organismo de mais de 8 mil pessoas — metade obesas, metade magras — tentando entender por que algumas pessoas simplesmente nao conseguem emagrecer, nao importa o que facam. Eles analisaram sangue, hormones, DNA, microbioma... tudo. E depois de 3 anos de pesquisa, encontraram algo que os deixou de queixo caido. Ao que parece, o intestino de pessoas gordas esta recheado por uma bacteria chamada Prevotella. Essa bacteria nao e encontrada em quantidades significativas no intestino de pessoas magras. Apenas em quem tem dificuldade para emagrecer. E o mais impressionante: essa bacteria age como um 'parasita metabolico'. Ela se alimenta dos nutrientes que voce ingere, produz toxinas inflamatorias, e literalmente BLOQUEIA o metabolismo. E como se alguem tivesse colocado uma trava no seu corpo."
- Pele/Anti-aging: "Veja bem, pesquisadores do MIT estavam conduzindo um estudo com mais de 5 mil mulheres entre 35 e 65 anos, tentando entender por que algumas mulheres envelhecem muito mais rapido do que outras — mesmo tendo habitos de vida parecidos. Eles compararam pele, sangue, niveis hormonais, ate exposicao solar. E apos 4 anos de analise, a resposta estava num lugar que ninguem esperava: no nivel celular. Ao que parece, existe uma enzima chamada MMP-1 que, quando em excesso, DEVORA o colageno da pele por dentro. E como um exercito de micro-tesouras cortando as fibras de colageno uma por uma. E essa enzima e ativada por um fator que ninguem imaginava: a inflamacao cronica silenciosa."

**Regras:**
- Narre como HISTORIA, nao como artigo cientifico
- Use numeros especificos para dar peso (quantidade de pessoas, anos)
- Crie suspense antes da revelacao
- A causa revelada deve ser ESPECIFICA — nao generica
- Use analogias para tornar a causa compreensivel
- A causa deve parecer "obvia em retrospecto"
- Mencione universidade ou instituicao para credibilidade
- Use "Ao que parece..." para a revelacao — cria tom de descoberta

---

### ARGUMENTO 2 — Argumento da Funcao

**Objetivo:** Provar COMO a causa identificada no Argumento 1 realmente funciona.

**Importancia:** O Argumento 1 planta a semente. O Argumento 2 rega com PROVAS. Sem provas: "sera que e verdade?" Com provas: "faz total sentido."

#### Etapa 2.1 — CONCLUSAO DO ESTUDO

Reforce a conclusao da pesquisa de forma clara e direta. Transforme a descoberta numa SENTENCA definitiva.

**Funcao persuasiva:** REITERACAO. Grava a informacao na memoria. Zero duvida sobre a causa.

**Tecnica:** Use "Foi nesse momento que os cientistas perceberam que..." + reafirme a causa de forma ainda mais simples.

**Exemplos:**
- Emagrecimento: "Foi nesse momento que os cientistas perceberam que essa bacteria — a Prevotella — e a verdadeira causa do ganho de peso. Nao e o metabolismo lento em si. Nao e a genetica. Nao e falta de forca de vontade. E uma bacteria que esta, neste exato momento, sabotando o seu corpo por dentro."
- Insonia: "Foi nesse momento que os pesquisadores compreenderam: a causa real da insonia nao e o estresse, nao e a ansiedade, nao e a tela do celular antes de dormir. A causa real e um desequilibrio quimico especifico no nucleo supraquiasmatico — o relogio biologico do seu cerebro — causado pelo excesso de cortisol noturno."

**Regras:**
- Seja DIRETO e INCISIVO
- Negue as causas populares para reforcar a causa real
- Use a estrutura "Nao e X. Nao e Y. E Z."
- Traga de volta ao momento presente: "neste exato momento"
- A frase deve ter peso — deve soar como um VEREDITO

#### Etapa 2.2 — GRANDE PROVA

Apresente prova IRREFUTAVEL que comprove a causa. Existem 4 tipos de Grande Prova.

**Funcao persuasiva:** Elimina a ultima barreira de ceticismo. Se a pessoa estava 80% convencida, a Grande Prova leva para 95%+.

##### Tipo A — ILUSTRACAO
Imagem, raio-X, exame ou comparacao visual que MOSTRA a causa em acao. Prova mais poderosa (apela ao visual).

**Quando usar:** Quando e possivel VISUALIZAR a causa. Melhor em nichos de saude.

**Exemplo (Emagrecimento):**
> "E para voce entender o quao serio isso e, olhe esta imagem. A esquerda, voce ve o intestino de uma pessoa magra — limpo, com uma microbiota equilibrada. A direita, o intestino de uma pessoa com sobrepeso — completamente tomado pela Prevotella. Veja como as colonias dessa bacteria se espalham por todo o trato digestivo, bloqueando a absorcao de nutrientes e inflamando a parede intestinal."

**Regras:**
- Descreva a imagem em detalhes para quem esta OUVINDO
- Use contraste: antes vs depois, saudavel vs doente
- A imagem deve causar IMPACTO EMOCIONAL

##### Tipo B — DEMONSTRACAO
Experimento ou caso pratico que DEMONSTRA a causa em acao.

**Quando usar:** Quando existe um experimento famoso ou replicavel.

**Exemplo (Emagrecimento):**
> "E veja o que aconteceu quando os cientistas fizeram um teste com ratos de laboratorio. Eles pegaram ratos magros e saudaveis e injetaram a bacteria Prevotella no intestino deles. Em apenas 4 semanas, esses ratos engordaram 40% — comendo a mesma quantidade de racao de sempre. Depois, eles removeram a bacteria com um tratamento especifico. E o que aconteceu? Os ratos voltaram ao peso normal em 3 semanas. Sem dieta. Sem exercicio. Apenas removendo a bacteria."

**Regras:**
- Narre como historia com comeco, meio e fim
- Use numeros especificos (40%, 4 semanas, 3 semanas)
- O resultado deve ser DRAMATICO e claro
- Se possivel, mostre a reversao (causa removida = problema resolvido)

##### Tipo C — ESTUDO / GRAFICO
Dado estatistico ou grafico que correlaciona causa com problema em larga escala.

**Quando usar:** Quando tem dados populacionais ou estatisticas com correlacao clara.

**Exemplo (Emagrecimento):**
> "E os numeros confirmam isso. De acordo com o estudo, 94% da populacao com sobrepeso possui niveis elevados dessa bacteria no intestino. E quando voce olha o grafico de crescimento da obesidade nas ultimas 3 decadas, ele acompanha EXATAMENTE o grafico de exposicao a alimentos ultraprocessados — que sao o principal 'combustivel' da Prevotella. Nao e coincidencia. E causa e efeito."

**Regras:**
- Use porcentagens altas e numeros impressionantes
- Mostre correlacao temporal se possivel
- Termine com frase de peso: "Nao e coincidencia"
- Simplifique os dados — nao use linguagem academica

##### Tipo D — PROVA TESTAVEL
Teste simples que a propria pessoa pode fazer AGORA para verificar se a causa se aplica a ela.

**Quando usar:** Quando e possivel criar um "auto-diagnostico" simples. Prova mais ENGAJANTE.

**Exemplo (Emagrecimento):**
> "E voce pode verificar isso agora mesmo. Coloque a mao na sua barriga. Sinta a temperatura. Se estiver FRIA, e um sinal de que nao ha fluxo sanguineo adequado na regiao abdominal — o que indica inflamacao causada justamente por essa bacteria. Pessoas magras e saudaveis tem a barriga QUENTE, porque o sangue circula livremente. Pessoas com a Prevotella em excesso tem a barriga fria, porque a inflamacao restringe o fluxo sanguineo."

**Regras:**
- O teste deve ser SIMPLES — realizavel em segundos
- Deve ter resultado binario: sim/nao, frio/quente
- Explique POR QUE o resultado indica a causa
- Nao pode ser algo que a pessoa possa "errar"
- Crie urgencia: "voce pode verificar isso AGORA MESMO"

##### Escolha e Combinacao de Provas:
O ideal e combinar 2 ou mais tipos. A combinacao mais poderosa e: Demonstracao + Prova Testavel.

**Ordem recomendada:**
1. Estudo/Grafico (dados frios, racionais)
2. Demonstracao (experimento, emocional)
3. Ilustracao (visual, impactante)
4. Prova Testavel (participativa, pessoal)

---

### ARGUMENTO 3 — Argumento da Solucao

**Objetivo:** Apresentar a SOLUCAO para a causa identificada e comprovada nos Argumentos 1 e 2.

**Importancia:** Transforma PROBLEMA em ESPERANCA. Ate agora, preocupacao. Agora, alivio.

#### Etapa 3.1 — PERGUNTA PARADOXAL

Faca uma pergunta que leve a pessoa a pensar em alguem que JA TEM o resultado desejado.

**Funcao persuasiva:** Planta a ideia de que alguem ja encontrou a solucao. Reacende a esperanca.

**Conexao com Big Idea:** A Pergunta Paradoxal usada aqui NAO e inventada neste momento. Vem do trabalho do idea-architect na Fase 3. Formula: "Como [ENTIDADE] consegue [RESULTADO] mesmo [COMPORTAMENTO CONTROVERSO]?" O thesis-writer ADAPTA para o contexto narrativo da Tese.

**Tecnica:** Use figuras aspiracionais ou grupo demografico que representa o resultado desejado.

**Exemplos:**
- Emagrecimento: "Mas me diga uma coisa: voce ja se perguntou como e que as celebridades de Hollywood conseguem manter um corpo magro e definido ano apos ano? Mesmo depois dos 40, 50 anos? Sera que e tudo genetica? Sera que e so personal trainer e dieta rigorosa?"
- Pele/Anti-aging: "Mas voce ja parou para pensar como e que algumas mulheres japonesas aparentam ter 30 anos quando na verdade tem 55? O que elas sabem que nos nao sabemos?"
- Energia/Disposicao: "Mas me responda uma coisa: como e que existem pessoas de 60, 70 anos que tem mais energia e disposicao do que gente de 30? O que essas pessoas fazem de diferente?"

**Regras:**
- A pergunta deve ser GENUINAMENTE intrigante
- Use exemplos que a pessoa CONHECE e ADMIRA
- Nao responda imediatamente — deixe a pergunta no ar por 1-2 frases
- A resposta para a pergunta DEVE SER a sua solucao
- Evite perguntas cliches — seja criativo

#### Etapa 3.2 — EXPLICACAO RAPIDA DA SOLUCAO

Revele COMO voce encontrou a solucao e O QUE ela e.

**Funcao persuasiva:** Historia pessoal de descoberta cria conexao emocional. Nao e empresa vendendo produto — e PESSOA que encontrou algo.

**Tecnica:** Micro-historia de como encontrou + explicacao em termos simples.

**Exemplos:**
- Emagrecimento: "A boa noticia e que a resposta para essa pergunta me levou a uma descoberta que mudou tudo. Numa madrugada, enquanto pesquisava sobre o assunto, encontrei um artigo do Dr. Robert Benson, um gastroenterologista de Harvard. No artigo, ele descrevia uma combinacao de 6 ervas naturais que, quando ingeridas juntas, criam um ambiente intestinal HOSTIL para a Prevotella — sem afetar as bacterias boas. Trata-se de um composto que age de 3 formas simultaneas: primeiro, ele elimina a Prevotella. Segundo, ele restaura a flora intestinal saudavel. E terceiro, ele desinflama a parede do intestino, permitindo que o metabolismo volte a funcionar normalmente."
- Pele/Anti-aging: "A boa noticia e que existe sim uma forma de bloquear essa enzima. E a resposta veio de um lugar inesperado. Eu estava lendo uma publicacao da Dra. Yuki Tanaka, uma dermatologista japonesa, e ela descrevia um peptideo bioativo extraido de uma alga encontrada no Mar do Japao. Esse peptideo tem a capacidade de inibir a MMP-1 em ate 87%, segundo testes in vitro. Mas o mais impressionante e que, quando combinado com 3 outros ingredientes — vitamina C estabilizada, acido hialuronico de baixo peso molecular e resveratrol — ele nao so bloqueia a destruicao do colageno como ESTIMULA a producao de novo colageno."

**Regras:**
- A historia de descoberta deve ser VEROSSIMIL
- Mencione um especialista/pesquisador para credibilidade
- Explique a solucao em linguagem SIMPLES
- Use a estrutura "primeiro, segundo, terceiro" para clareza
- A solucao deve endercar DIRETAMENTE a causa do Argumento 1
- Nao mencione nome de produto ainda — apenas o mecanismo

#### Etapa 3.3 — EVIDENCIAS CIENTIFICAS

Apresente estudos e dados que comprovam a eficacia da solucao.

**Funcao persuasiva:** Se ja acreditava na causa, agora precisa acreditar que a solucao FUNCIONA.

**Exemplo (Emagrecimento):**
> "E nao sou so eu quem esta dizendo isso. Um estudo da Universidade de Chicago, publicado no Nature Medicine, mostrou que 8 a cada 10 pessoas que utilizaram essa combinacao de ervas tiveram uma reducao significativa da Prevotella em apenas 30 dias. Outro estudo, este da Universidade de Sao Paulo, mostrou que os participantes perderam em media 7,4 kg em 60 dias — sem alterar dieta ou rotina de exercicios."

**Regras:**
- Cite pelo menos 2 estudos/fontes diferentes
- Use numeros especificos e impressionantes
- Mencione universidades/journals conhecidos
- Mostre resultados em PRAZO definido (30 dias, 60 dias)
- Use "E nao sou so eu quem esta dizendo" para distanciar

#### Etapa 3.4 — TESTE

Relate o teste que voce (ou alguem proximo) fez com a solucao.

**Funcao persuasiva:** Estudos sao frios e distantes. Historia pessoal e quente e proxima. Humaniza a solucao.

**Conexao com porta-voz:** A escolha do COBAIA depende do tipo de porta-voz:
- AVATAR TRANSFORMADO: O cobaia e VOCE MESMO. "Eu decidi testar em mim mesmo."
- GURU que ajudou familiar: O cobaia e esposa, mae, alguem proximo. "Decidi testar na minha esposa."
- GURU que ajudou paciente: O cobaia e um paciente. "Decidi testar no meu paciente."
Essa escolha DEVE ser consistente com o tipo de porta-voz da VSL.

**Exemplo (Emagrecimento):**
> "Eu fiquei tao empolgado com esses estudos que decidi testar na minha propria esposa. Ela lutava contra a balanca ha mais de 15 anos. Ja tinha tentado de tudo: dieta cetogenica, jejum intermitente, crossfit... nada funcionava de forma duradoura. Ela concordou em testar por 90 dias. Sem mudar mais nada na rotina — mesma alimentacao, mesma atividade fisica. A unica mudanca foi tomar esse composto de ervas todas as manhas, em jejum."

**Regras:**
- O cobaia deve ser alguem com quem a audiencia se IDENTIFICA
- Mencione as frustracoes anteriores (ja tentou tudo)
- Deixe claro que NAO houve outras mudancas (isola a variavel)
- Crie expectativa para o resultado (nao revele ainda)
- Use esposa, mae, paciente — figuras proximas e criveis

#### Etapa 3.5 — GRANDE RESULTADO

Revele o resultado do teste de forma progressiva e dramatica.

**Funcao persuasiva:** Resultado progressivo e mais credivel que instantaneo. Mostra consistencia crescente.

**Exemplo (Emagrecimento):**
> "Na primeira semana, ela ja notou uma diferenca. A barriga estava menos inchada, e ela acordava com mais disposicao. Perdeu 1,2 kg. Na segunda semana, as roupas comecaram a ficar mais folgadas. A balanca marcou menos 3,1 kg. Ela me disse: 'Pela primeira vez na vida, sinto que algo esta funcionando de verdade.' Na terceira semana, as pessoas comecaram a comentar. 'Voce emagreceu?' 'O que voce esta fazendo?' Ela estava 5,4 kg mais leve. No final dos 90 dias, minha esposa havia perdido 14,7 kg. Sem dieta. Sem exercicio extra. Sem passar fome. Apenas eliminando a bacteria que estava sabotando o corpo dela por dentro."

**Regras:**
- Mostre progressao: semana 1, semana 2, semana 3, resultado final
- Use numeros ESPECIFICOS (1.2 kg, nao "cerca de 1 kg")
- Inclua REACOES de terceiros para validacao social
- Inclua uma FALA da pessoa (citacao direta)
- Reconecte o resultado com a causa (eliminando a bacteria)
- O resultado deve ser IMPRESSIONANTE mas CREDIVEL
- Finalize com resumo que reforce: "sem dieta, sem exercicio"

---

## Regras Gerais de Escrita

```yaml
fluxo:
  - "Cada argumento deve fluir NATURALMENTE para o proximo"
  - "Nao deve haver saltos logicos — cada passo deve ser consequencia do anterior"
  - "A pessoa que le deve sentir que 'nao tem como nao acreditar'"
  - "A logica e: '1, 2, 3, 4 — e somar'. Cada passo se soma ao anterior"

linguagem:
  - "Usar linguagem acessivel, NUNCA tecnica demais"
  - "Analogias simples para conceitos complexos"
  - "Falar como se estivesse explicando para um amigo inteligente"
  - "Evitar jargoes medicos/cientificos — traduzir sempre"

credibilidade:
  - "Usar numeros especificos (nunca arredondados)"
  - "Citar universidades e pesquisadores (com nomes)"
  - "Mencionar journals/publicacoes conhecidas"
  - "Incluir datas especificas para pesquisas"

emocao:
  - "Alternar entre PREOCUPACAO (causa) e ALIVIO (solucao)"
  - "Criar momentos de suspense antes de revelacoes"
  - "Incluir reacoes emocionais dos personagens"
  - "A Tese deve criar uma montanha-russa emocional controlada"
```

---

## Exemplos Completos de Output

### Exemplo 1 — Emagrecimento

**Nicho:** Emagrecimento | **Mecanismo:** Bacteria intestinal Prevotella | **Publico:** Mulheres 35-60 anos

```
--- ARGUMENTO 1: A CAUSA DO PROBLEMA ---

Como voce provavelmente ja sabe, o que causa o acumulo de gordura
no corpo e o metabolismo lento. Quando o seu metabolismo
desacelera, cada caloria que voce consome acaba sendo armazenada
como gordura, ao inves de ser convertida em energia.
E por isso que voce pode comer pouco e mesmo assim nao emagrecer.

Porem, mesmo sabendo disso... ninguem ate entao conseguiu encontrar
uma solucao definitiva. Dietas restritivas funcionam por algumas
semanas e depois o peso volta. Exercicios ajudam, mas nao resolvem
a raiz do problema. Suplementos termogenicos dao uma forcinha, mas
o efeito e temporario.

Ate que em outubro de 2023, um grupo de pesquisadores da
Universidade de Washington publicou um estudo que virou o jogo
completamente.

Voce ja deve ter ouvido falar que o intestino e o nosso segundo
cerebro, certo? Que ele influencia tudo — desde o humor ate o
sistema imunologico, desde a qualidade do sono ate os niveis de
energia. Pois foi exatamente no intestino que esses pesquisadores
focaram a atencao.

Veja bem, eles estavam analisando o organismo de mais de 8 mil
pessoas — metade com sobrepeso, metade com peso saudavel —
tentando entender por que algumas pessoas simplesmente nao
conseguem emagrecer, nao importa o que facam.

Analisaram sangue. Hormonios. DNA. Niveis de cortisol. Funcao
tireoidiana. Tudo que voce possa imaginar. E apos 3 anos de
pesquisa, encontraram algo que deixou a comunidade cientifica
de queixo caido.

Ao que parece, o intestino de pessoas com sobrepeso esta
recheado por uma bacteria chamada Prevotella. Essa bacteria nao
e encontrada em quantidades significativas no intestino de pessoas
magras. Apenas no intestino de quem tem dificuldade para perder peso.

E o mais impressionante: essa bacteria age como um parasita
metabolico. Ela se alimenta dos nutrientes que voce ingere,
produz toxinas inflamatorias, e literalmente BLOQUEIA o
metabolismo. E como se alguem tivesse instalado uma trava
no motor do seu corpo.


--- ARGUMENTO 2: A FUNCAO ---

Foi nesse momento que os cientistas perceberam que essa bacteria
— a Prevotella — e a verdadeira causa do ganho de peso.

Nao e o metabolismo lento em si. O metabolismo lento e apenas
o SINTOMA. Nao e a genetica. Nao e a falta de forca de vontade.
Nao e porque voce come muito. E uma bacteria que esta, neste
exato momento, sabotando o seu organismo por dentro.

E veja o que aconteceu quando os cientistas fizeram um
experimento com ratos de laboratorio. Eles pegaram ratos magros
e saudaveis — ratos que nunca tiveram problemas de peso — e
introduziram a bacteria Prevotella no intestino deles.

Em apenas 4 semanas, esses ratos engordaram 40%. Quarenta por
cento. Comendo a mesma racao de sempre. Na mesma quantidade.
Com o mesmo nivel de atividade.

Depois, eles fizeram o caminho inverso: removeram a bacteria
com um tratamento especifico. E o que aconteceu? Os ratos
voltaram ao peso normal em apenas 3 semanas. Sem dieta. Sem
exercicio. Sem nenhuma outra intervencao. Apenas removendo
a bacteria.

E os numeros populacionais confirmam isso. De acordo com o
estudo, 94% das pessoas com sobrepeso possuem niveis elevados
dessa bacteria. E quando voce olha o grafico de crescimento
da obesidade nas ultimas 3 decadas, ele acompanha EXATAMENTE
o aumento do consumo de alimentos ultraprocessados — que sao
o principal combustivel da Prevotella.

Nao e coincidencia. E causa e efeito.

E voce pode verificar isso agora mesmo. Coloque a mao na sua
barriga. Sinta a temperatura. Se estiver fria, e sinal de que
nao ha fluxo sanguineo adequado na regiao — o que indica
inflamacao causada pela Prevotella. Pessoas magras tem a
barriga quente. Pessoas com essa bacteria em excesso tem a
barriga fria.


--- ARGUMENTO 3: A SOLUCAO ---

Mas me diga uma coisa: voce ja se perguntou como e que certas
celebridades conseguem manter um corpo magro e definido ano apos
ano? Mesmo depois dos 40, 50 anos? Sera que e tudo genetica?
Sera que e so personal trainer 5 vezes por semana?

A boa noticia e que a resposta para essa pergunta me levou a
uma descoberta que mudou absolutamente tudo.

Numa madrugada, enquanto pesquisava sobre microbioma intestinal,
encontrei um artigo do Dr. Robert Benson, um gastroenterologista
formado em Harvard. No artigo, ele descrevia uma combinacao de
6 ervas naturais que, quando ingeridas juntas, criam um
ambiente intestinal completamente hostil para a Prevotella —
sem afetar as bacterias beneficas.

Trata-se de um composto que age de 3 formas simultaneas:
primeiro, ele elimina as colonias de Prevotella. Segundo, ele
restaura a flora intestinal saudavel, repovoando o intestino
com bacterias beneficas. E terceiro, ele desinflama a parede
intestinal, permitindo que o metabolismo volte a funcionar
na velocidade normal.

E nao sou so eu quem esta dizendo isso. Um estudo da
Universidade de Chicago, publicado no Nature Medicine, mostrou
que 8 a cada 10 pessoas que utilizaram essa combinacao de
ervas tiveram uma reducao de 89% nos niveis de Prevotella
em apenas 30 dias. Outro estudo, este da Universidade de
Sao Paulo, mostrou que os participantes perderam em media
7,4 kg em 60 dias — sem alterar dieta ou exercicios.

Eu fiquei tao empolgado que decidi testar na minha propria
esposa. Ela lutava contra a balanca ha 15 anos. Ja tinha
tentado cetogenica, jejum intermitente, low carb, crossfit,
pilates... nada funcionava de forma duradoura. Ela concordou
em testar por 90 dias, sem mudar mais nada na rotina.

Na primeira semana, a barriga dela ja estava visivelmente
menos inchada. Ela perdeu 1,2 kg e me disse que estava
acordando com mais energia.

Na segunda semana, as roupas comecaram a ficar folgadas. A
balanca marcou menos 3,1 kg. Ela me disse, com lagrimas nos
olhos: "Pela primeira vez na vida, eu sinto que algo esta
funcionando de verdade."

Na terceira semana, as amigas comecaram a perguntar: "O que
voce esta fazendo? Voce esta diferente." Ela estava 5,4 kg
mais leve e com a autoestima nas alturas.

No final dos 90 dias, minha esposa havia eliminado 14,7 kg.
Sem dieta restritiva. Sem exercicio extra. Sem passar fome.
Sem efeito sanfona. Apenas eliminando a bacteria que estava
sabotando o corpo dela por dentro.

E por essa razao que eu decidi compartilhar essa descoberta
com voce hoje.
```

### Exemplo 2 — Pele e Anti-Aging

**Nicho:** Rejuvenescimento | **Mecanismo:** Enzima MMP-1 ativada por inflamacao cronica | **Publico:** Mulheres 40-65 anos

```
--- ARGUMENTO 1: A CAUSA DO PROBLEMA ---

Como voce ja deve saber, o que causa o envelhecimento visivel
da pele — as rugas, as linhas de expressao, a flacidez — e
a perda de colageno. Com o passar dos anos, o corpo vai
produzindo cada vez menos colageno, e a pele vai perdendo
firmeza e elasticidade. E um processo natural.

No entanto, mesmo com toneladas de informacao disponivel sobre
colageno, os cremes anti-idade continuam decepcionando. O
colageno em capsulas nao funciona como prometido. Os
procedimentos esteticos dao resultado temporario e custam
uma fortuna. Algo nao esta fazendo sentido.

Ate que um estudo publicado no Journal of Dermatological
Science, em marco de 2024, revelou algo que ninguem
na industria cosmetica queria que voce soubesse.

Voce ja deve ter ouvido falar que a pele e o maior orgao do
corpo humano, certo? E que tudo que acontece no interior do
organismo se reflete na superfice da pele. Pois foi exatamente
essa conexao entre o interior e o exterior que levou os
cientistas a investigar um lugar completamente inesperado.

Veja bem, pesquisadores do MIT analisaram amostras de pele
de mais de 5 mil mulheres entre 35 e 65 anos. Mulheres com
habitos de vida parecidos, mesma faixa etaria, mesma regiao
geografica. A unica diferenca? Algumas aparentavam ter 10 a
15 anos a menos do que tinham.

Apos 4 anos de estudo, a resposta apareceu: existe uma enzima
chamada MMP-1 que, quando em excesso, DEVORA o colageno da
pele por dentro. E como um exercito de micro-tesouras cortando
as fibras de colageno uma a uma, dia apos dia. E essa enzima
e ativada por um gatilho que ninguem imaginava: a inflamacao
cronica silenciosa.

Ao que parece, nao e que o corpo para de produzir colageno.
Ele continua produzindo. Mas a MMP-1 esta destruindo o
colageno mais rapido do que o corpo consegue repor.
E como tentar encher um balde com um furo no fundo.


--- ARGUMENTO 2: A FUNCAO ---

Foi nesse momento que os pesquisadores compreenderam a
mecanica real do envelhecimento: a MMP-1 e a verdadeira
responsavel. Nao e a idade em si. Nao e a exposicao solar
(embora ela piore). Nao e a genetica. E essa enzima
devoradora de colageno, alimentada pela inflamacao silenciosa.

E a prova mais impressionante veio de uma comparacao visual.
Os pesquisadores fizeram biopsia da pele de duas mulheres de
52 anos. Uma com niveis normais de MMP-1, outra com niveis
elevados. A diferenca era gritante: a pele da primeira tinha
fibras de colageno densas e organizadas. A pele da segunda
parecia uma rede de pesca rasgada — fibras fragmentadas,
desorganizadas, com espacos vazios.

E os dados populacionais sao igualmente chocantes: 91% das
mulheres que apresentam envelhecimento acelerado tem niveis
de MMP-1 acima do normal. E o mais interessante: esse indice
disparou nos ultimos 20 anos, coincidindo exatamente com o
aumento da exposicao a poluentes ambientais e alimentos
ultraprocessados — dois dos maiores gatilhos de inflamacao
cronica.

Nao e coincidencia. E biologia.


--- ARGUMENTO 3: A SOLUCAO ---

Mas voce ja parou para pensar como e que mulheres japonesas
aparentam ter 30 anos quando na verdade tem 55? O que elas
sabem — ou fazem — que nos nao sabemos?

A boa noticia e que foi justamente essa pergunta que me levou
a uma descoberta fascinante.

Eu estava lendo uma publicacao da Dra. Yuki Tanaka, uma
dermatologista de Toquio com 28 anos de experiencia. Ela
descrevia um peptideo bioativo extraido de uma alga vermelha
encontrada no litoral do Japao — a mesma alga que faz parte
da dieta tradicional japonesa ha seculos.

Esse peptideo tem a capacidade de inibir a MMP-1 em ate 87%,
segundo testes realizados em laboratorio. Mas o mais
impressionante e que, quando combinado com 3 outros
ingredientes — vitamina C estabilizada, acido hialuronico de
baixo peso molecular e resveratrol — ele nao apenas bloqueia
a destruicao do colageno existente, mas ESTIMULA a producao
de novo colageno em ate 340%.

Um estudo clinico conduzido na Universidade de Toquio com
320 mulheres mostrou que, apos 8 semanas de uso, 87% das
participantes apresentaram reducao visivel de rugas e linhas
de expressao. Outro estudo, este da Universidade de Seul,
confirmou que a firmeza da pele aumentou em media 62% em
apenas 60 dias.

Eu decidi testar na minha mae. Ela tem 63 anos e sempre se
queixou do envelhecimento da pele — rugas profundas na
testa, papada, flacidez no pescoco. Ja tinha gasto mais de
R$ 20 mil em cremes, seruns e procedimentos.

Na primeira semana, a pele dela ficou mais luminosa. Como
se tivesse ganho um brilho natural.

Na segunda semana, a textura comecou a mudar. O toque
estava mais macio, mais liso.

Na quarta semana, minha irma veio visitar e disse:
"Mae, o que voce fez? Sua pele esta incrivel."

Ao final de 90 dias, as rugas da testa tinham suavizado
visivelmente. A papada estava mais firme. Ela me disse:
"Eu pareco 10 anos mais nova. Ja fazia tempo que nao me
sentia tao bonita."
```

### Exemplo 3 — Energia e Disposicao

**Nicho:** Energia | **Mecanismo:** Disfuncao mitocondrial por radicais livres | **Publico:** Homens e mulheres 40-65 anos

```
--- ARGUMENTO 1: A CAUSA DO PROBLEMA ---

Como voce provavelmente ja sabe, a sensacao de cansaco constante
esta diretamente ligada a queda hormonal que acontece com a
idade. Apos os 40 anos, os niveis de testosterona nos homens
e de estrogeno nas mulheres comecam a cair, e com eles vai
embora a energia e a disposicao.

Porem, existe algo estranho: por que algumas pessoas de 60, 70
anos tem mais energia do que gente de 30? Se fosse apenas
questao hormonal, isso seria impossivel. Mas nao e. E isso
intrigou profundamente um grupo de pesquisadores da Clinica
Mayo.

Ate que em agosto de 2024, eles publicaram um estudo que
reescreveu tudo que a medicina sabia sobre cansaco cronico.

Voce ja ouviu falar que as mitocondrias sao as usinas de
energia das nossas celulas, certo? Que sao elas as
responsaveis por converter os nutrientes que ingerimos em
ATP — a molecula de energia que faz tudo funcionar no corpo.
Pois foi justamente nas mitocondrias que os pesquisadores
encontraram a resposta.

Veja bem, eles analisaram celulas de mais de 12 mil pessoas
de diversas idades. E descobriram que pessoas com cansaco
cronico tinham algo em comum: suas mitocondrias estavam
DANIFICADAS. Nao por causa da idade, como todos pensavam.
Mas por causa de um acumulo excessivo de radicais livres
que, ao longo dos anos, vao corroendo a membrana
mitocondrial como ferrugem corroe metal.

Ao que parece, quando a membrana mitocondrial esta
comprometida, a mitocondria perde a capacidade de produzir
ATP de forma eficiente. E como se o motor de um carro
estivesse falhando — ele ate funciona, mas gasta o triplo
de combustivel e gera um terco da potencia.


--- ARGUMENTO 2: A FUNCAO ---

Foi nesse momento que os pesquisadores perceberam: o
cansaco cronico nao e um problema hormonal. Nao e falta
de vitamina. Nao e estresse. Nao e "coisa da idade".
E um problema CELULAR — suas mitocondrias estao
literalmente enferrujando.

E a demonstracao mais convincente veio de um experimento
simples. Os pesquisadores mediram a producao de ATP em
celulas saudaveis e celulas com mitocondrias danificadas.
As celulas danificadas produziam apenas 31% da energia
que as celulas saudaveis produziam. Menos de um terco.

Isso significa que o seu corpo esta operando com apenas
um terco da energia que deveria ter. Nao e que voce
esta cansado. E que as suas celulas estao FAMINTAS
por energia.

E um teste simples comprova isso: preste atencao no
seu nivel de energia as 3 da tarde. Se voce sente
aquela sonolencia pesada, aquele desejo incontrolavel
de deitar, aquela sensacao de que precisa de cafe
para sobreviver o resto do dia — e um sinal classico
de que suas mitocondrias estao comprometidas. Pessoas
com mitocondrias saudaveis passam o dia inteiro com
energia estavel, sem picos e quedas.


--- ARGUMENTO 3: A SOLUCAO ---

Mas voce ja parou para pensar como e que existem pessoas
de 70, 80 anos que correm maratonas, viajam o mundo, e
tem mais disposicao do que gente de 35? O que essas
pessoas tem de diferente?

A boa noticia e que a resposta e mais simples do que
voce imagina. E ela veio de uma pesquisa que mudou
completamente a minha perspectiva.

Eu estava assistindo a uma palestra do Dr. David
Sinclair, professor de Genetica em Harvard e uma das
maiores autoridades mundiais em longevidade. Ele
explicava que existe uma molecula chamada CoQ10 que,
quando combinada com PQQ e NAD+, tem a capacidade de
REPARAR a membrana mitocondrial danificada — e
restaurar a producao de ATP para niveis saudaveis.

Trata-se de um trio de moleculas que age em sinergia:
a CoQ10 repara a membrana. O PQQ estimula a criacao de
NOVAS mitocondrias. E o NAD+ potencializa o processo
de producao de energia. Juntos, eles transformam celulas
exaustas em celulas que funcionam como novas.

Um estudo publicado na Cell Metabolism mostrou que
participantes que utilizaram essa combinacao tiveram
um aumento de 144% na producao de ATP em 45 dias.
Outro estudo, da Universidade de Stanford, mostrou
que 9 em cada 10 participantes relataram aumento
significativo de energia e disposicao.

Eu mesmo fui o primeiro cobaia. Aos 47 anos, eu vivia
arrastando o dia. Cafe da manha, cafe no meio da manha,
cafe apos o almoco, cafe as 4 da tarde. E mesmo assim,
as 8 da noite eu ja estava destruido.

Na primeira semana usando essa combinacao, percebi que
acordava antes do despertador. Sem esforco. Sem aquela
sensacao de que o travesseiro e um ima.

Na segunda semana, consegui passar a tarde inteira
trabalhando sem sentir aquela sonolencia das 3 horas.
Pela primeira vez em anos, nao precisei de cafe a tarde.

Na quarta semana, minha esposa disse: "Voce esta
diferente. Voce parece ter voltado aos 30 anos."
E eu me sentia assim. Energia constante do amanhecer
ao anoitecer.

Hoje, 6 meses depois, eu tenho mais energia aos 47
do que tinha aos 35. Durmo melhor, acordo melhor,
produzo mais, e ainda sobra disposicao para brincar
com meus filhos no final do dia.
```

---

## Anti-Patterns — Erros Fatais que Destroem uma Tese

| ID | Erro | Por que falha | Como corrigir |
|------|------|------|------|
| AP-01 | Tese Generica (causas vagas) | Nao ha mecanismo unico. Nao gera curiosidade nem diferencia | Identifique causa ESPECIFICA e OCULTA com nome e pesquisa |
| AP-02 | Salto Logico (pular etapas) | Sem provas a pessoa nao acredita. Cada etapa constroi credibilidade | Siga os 3 argumentos RELIGIOSAMENTE |
| AP-03 | Linguagem de Vendedor na Tese | Pessoa levanta barreiras de defesa. Tese deve parecer AULA | Fale sobre MECANISMO, nunca sobre produto |
| AP-04 | Prova Ausente ou Fraca | Provas vagas geram desconfianca. Falta de especificidade = mentira | Inclua universidade, participantes, duracao, resultado com numeros |
| AP-05 | Resultado Inverossimil | Destroi toda credibilidade dos Argumentos 1 e 2 | Resultados impressionantes mas CRIVEIS (14kg em 90 dias, nao 30kg em 7 dias) |
| AP-06 | Crenca Comum Desconectada | Ponte mental nao faz sentido, perde confianca | A crenca deve ser PONTE NATURAL para a causa |
| AP-07 | Teste sem Contexto Emocional | Sem emocao, sem identificacao | Humanize o cobaia. Conte frustracoes. Use citacoes diretas |
| AP-08 | Transicao Brusca entre Argumentos | Tese deve fluir como UMA UNICA narrativa | Use transicoes: "Foi nesse momento que...", "A boa noticia e que..." |

---

## Quality Gates — Checklist de Qualidade da Tese

### Criterios Estruturais (obrigatorios)
- [ ] Possui os 3 argumentos completos (Causa, Funcao, Solucao)
- [ ] Argumento 1 possui todas as 4 etapas (Ponto de Partida, Peca Faltante, Crenca Comum, Grande Pesquisa)
- [ ] Argumento 2 possui Conclusao do Estudo + pelo menos 2 tipos de Grande Prova
- [ ] Argumento 3 possui todas as 5 etapas (Pergunta, Explicacao, Evidencias, Teste, Resultado)
- [ ] As transicoes entre argumentos sao SUAVES e naturais
- [ ] Nao ha mencao direta ao produto (apenas ao mecanismo)

### Criterios de Persuasao (obrigatorios)
- [ ] A causa e ESPECIFICA (tem nome, nao e generica)
- [ ] Ha pelo menos 1 pesquisa citada com universidade e numeros
- [ ] Ha pelo menos 1 tipo de Grande Prova
- [ ] O resultado do teste e progressivo (semana a semana) e verossimil
- [ ] Ha pelo menos 1 analogia simples para explicar conceitos complexos
- [ ] Ha pelo menos 1 citacao direta de uma pessoa
- [ ] A narrativa cria ESPERANCA genuina na solucao

### Criterios de Voz (obrigatorios)
- [ ] Escrito em Portugues Brasileiro natural e fluido
- [ ] Usa pelo menos 3 transicoes-assinatura do Voice DNA
- [ ] Nao usa emojis, ingles desnecessario, ou linguagem academica
- [ ] Tom didatico e persuasivo, nunca agressivo ou desesperado
- [ ] Paragrafos curtos (maximo 3-4 linhas cada)

### Criterios de Credibilidade (obrigatorios)
- [ ] Numeros sao especificos, nao arredondados (7.4 kg, nao "uns 7 kg")
- [ ] Universidades/instituicoes sao nomeadas
- [ ] Pesquisadores sao nomeados quando possivel
- [ ] Datas sao especificas (mes + ano)
- [ ] Resultados sao impressionantes mas criveis

### Teste Final
Leia a Tese completa em voz alta. Se em algum momento voce pensar "isso nao faz sentido" ou "isso parece forcado", a Tese precisa ser reescrita nesse ponto. A Tese deve fluir como uma conversa com um amigo que esta te contando algo incrivel que descobriu.

---

## Output

```yaml
output:
  principal:
    nome: "Tese de Marketing Completa"
    formato: "Texto corrido em Portugues Brasileiro"
    estrutura:
      - "Argumento 1 — Causa do Problema (com 4 etapas)"
      - "Argumento 2 — Funcao (com Conclusao + Provas)"
      - "Argumento 3 — Solucao (com 5 etapas)"
    tamanho_esperado: "1500 a 3000 palavras"

  secundarios:
    - nome: "Mapa de Mecanismo"
      descricao: "Resumo visual da logica: Causa -> Funcao -> Solucao"
    - nome: "Lista de Provas Utilizadas"
      descricao: "Catalogo das provas e evidencias usadas na Tese"
    - nome: "Pontos de Transicao"
      descricao: "As frases exatas usadas para conectar os argumentos"
```
