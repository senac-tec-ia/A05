# Estrutura da Aula — A05 / 12/03/2026 (Quinta-Feira)
**Arquivo:** `slides.md` | **Última revisão:** 2026-03-11
**Total estimado de slides Slidev:** ~21

> PRÉ-DOCUMENTO aprovado pelo orquestrador. Não modificar `slides.md` antes da aprovação deste plano.

---

## Composição do Dia — Decisão do Orquestrador

| Bloco | Horário | HA | Disciplina | Tópico Central |
|---|---|---|---|---|
| 1 | 7h10–9h30 | 3 | D05-UC03 Python | Loops (`for`/`while`) e Listas |
| — | 9h30–9h50 | — | Intervalo | — |
| 2 | 9h50–11h10 | 2 | D03-UC01 Matemática | **INÍCIO** — Aritmética comp. + Álgebra linear |
| 3 | 11h10–12h00 | 1 | D09-UC07 Estatística | **INÍCIO** — Função linear `y = ax + b` |

### Justificativa da composição

- **D05 no Bloco 1 (3 HA):** Python tem momentum — A04 encerrou com variáveis/condicionais. Loops/listas são a progressão natural e exigem tempo contínuo para prática em dupla. Disciplina pesada sempre no Bloco 1.
- **D03 no Bloco 2 (2 HA):** Urgência 🔴 — ainda não iniciada. Aritmética computacional e álgebra fazem ponte direta com operadores Python vistos em A04, reduzindo a curva de abstração.
- **D09 no Bloco 3 (1 HA):** Urgência 🔴 — ainda não iniciada. Função linear `y = ax + b` conecta com a álgebra recém-vista no Bloco 2 (ponte cognitiva imediata). 1 HA suficiente para introdução conceitual com exercício.
- **D08 (Banco de Dados) NÃO entra hoje:** Introduzir D03 + D09 juntos cria ponte matemática coesa. D08 entra em A06 (13/03) no Bloco 1 (3 HA), conforme regra: "D08 iniciar no Bloco 1 — disciplina nova + pesada requer foco total".

---

## Legenda de Tags

| Tag | Significado |
|---|---|
| `[TEORIA]` | Slide expositivo de conteúdo teórico |
| `[DEBATE]` | Pergunta aberta para debate coletivo ou brainstorming |
| `[EXERCICIO]` | Atividade individual ou em dupla com entrega ou resposta |
| `[DINAMICA]` | Atividade interativa, jogo, roleplay ou dinâmica de grupo |
| `[TAREFA DE CASA]` | Atividade para fazer fora da aula |

---

## BLOCO 1 — D05-UC03 Python: Loops e Listas
**Slides: 1–12** | Horário: 7h10–9h30 | 3 HA (~140 min)
**Contexto IA:** iterar sobre listas de tokens, acurácias e predições de modelos
**Dinâmica:** exercícios em dupla (padrão consolidado do campo)

| Slide(s) | Título | Tag | Resumo |
|---|---|---|---|
| 1 | Capa — A05: Python, Matemática e Estatística | `[TEORIA]` | Abertura geral da aula, roadmap do dia |
| 2 | Revisão-relâmpago A04 | `[TEORIA]` | 3 perguntas rápidas: tipo de dado, if/elif, def — não reensinar, só conectar |
| 3 | O que é um loop? Por que repetir? | `[TEORIA]` | Analogia: o modelo lê token por token — repetição é a base de todo processamento |
| 4 | `for` em Python: sintaxe e fluxo | `[TEORIA]` | `for item in lista:` — indentação, variável de iteração, `range()` |
| 5 | EX01 — `for`: iterar sobre lista de tokens | `[EXERCICIO]` | Starter code: `tokens = ["IA", "é", "legal"]; for t in tokens:` — imprimir cada token |
| 6 | `while`: loop com condição | `[TEORIA]` | Conceito de limiar — `while confianca < 0.9:` — cuidado com loop infinito |
| 7 | `break` e `continue`: controle de fluxo | `[TEORIA]` | `break` para quando encontrar o label certo; `continue` pula tokens irrelevantes |
| 8 | EX02 — `while` + `break`: limiar de confiança | `[EXERCICIO]` | Starter: `tentativa = 0; while tentativa < 10:` — parar quando acurácia supera 0.85 |
| 9 | Listas em Python: criar, indexar, `append` | `[TEORIA]` | `[]`, índices 0-based, `.append()`, `len()` — lista como "dataset mínimo" |
| 10 | EX03 — Lista de acurácias por época | `[EXERCICIO]` | Starter: `acuracias = []; for e in range(5):` — `append` de valores e `print` final |
| 11 | DINÂMICA — Dupla: "Purificador de dataset" | `[DINAMICA]` | Lista com tokens inválidos (None, "", 123) — escrever loop que filtra só strings válidas |
| 12 | Síntese Bloco 1 + gancho para Matemática | `[TEORIA]` | O loop `for` em Python faz o que as somatórias fazem em matemática — ponte para Bloco 2 |

---

## BLOCO 2 — D03-UC01 Fundamentos Matemáticos: Aritmética + Álgebra
**Slides: 13–18** | Horário: 9h50–11h10 | 2 HA (~100 min)
**Status:** INÍCIO DA DISCIPLINA
**Contexto IA:** operadores Python já vistos em A04 — agora formalizando a notação matemática por trás

| Slide(s) | Título | Tag | Resumo |
|---|---|---|---|
| 13 | Abertura D03 — Matemática entra em cena | `[TEORIA]` | Por que matemática é a linguagem da IA? Contexto motivador (todo modelo = operações matemáticas) |
| 14 | Aritmética computacional: int, float, precisão | `[TEORIA]` | `7 // 2 = 3` vs `7 / 2 = 3.5` — precedência `**`, `%`, `//` — regra PEMDAS em Python |
| 15 | EX04 — Ordem de operações em Python | `[EXERCICIO]` | Starter: expressões com resultado surpresa — alunos calculam à mão e verificam no Colab |
| 16 | Álgebra: variável matemática vs variável Python | `[TEORIA]` | `x = 10` — igual em Python, diferente em matemática (`=` atribuição vs `=` igualdade). Equação linear `y = 2x + 5` |
| 17 | EX05 — Resolver equação linear com Python | `[EXERCICIO]` | Starter: `def calcular_y(x):` — calcular y para x = 0, 1, 2, 5, 10 e imprimir tabela |
| 18 | DEBATE — Onde usamos álgebra em IA? | `[DEBATE]` | "Quantos parâmetros tem um modelo linear? O que é treinar esse modelo?" — coleta de intuições |

---

## BLOCO 3 — D09-UC07 Estatística: Função Linear
**Slides: 19–21** | Horário: 11h10–12h00 | 1 HA (~50 min)
**Status:** INÍCIO DA DISCIPLINA
**Contexto IA:** regressão linear como "prever preço de GPU pelo ano" — intuição sem fórmulas pesadas

| Slide(s) | Título | Tag | Resumo |
|---|---|---|---|
| 19 | Abertura D09 — Funções matemáticas em IA | `[TEORIA]` | Por que funções descrevem comportamento de modelos? `y = f(x)` — a curva de aprendizado |
| 20 | Função linear: `y = ax + b` — coeficientes e gráfico | `[TEORIA]` | `a` = inclinação (taxa de mudança), `b` = intercepto. Gráfico visual: reta que sobe/desce. Conexão direta com EX05 do Bloco 2 |
| 21 | EX06 — Tabela de valores da função linear | `[EXERCICIO]` | Starter: `def f_linear(x, a, b): return a*x + b` — preencher tabela para `a=3, b=-1` com x de 0 a 5 |

---

## Tarefa de Casa (final do Bloco 3)

> Incluir no último slide ou em slide separado após slide 21.

| Slide | Título | Tag | Resumo |
|---|---|---|---|
| 22 | Tarefa A05 — Loop, Álgebra e Função | `[TAREFA DE CASA]` | 3 itens: (1) criar loop que calcula y para uma lista de x usando f_linear; (2) identificar a e b de um gráfico dado; (3) ler captulo do glossário Python (for/while/list) |

---

## Resumo de Contagem

| Bloco | Disciplina | Slides | Exercícios | Dinâmicas | Debates |
|---|---|---|---|---|---|
| 1 | D05-UC03 Python | 12 | EX01, EX02, EX03 | 1 | 0 |
| 2 | D03-UC01 Matemática | 6 | EX04, EX05 | 0 | 1 |
| 3 | D09-UC07 Estatística | 3 | EX06 | 0 | 0 |
| TC | Tarefa de Casa | 1 | — | — | — |
| **Total** | | **22** | **6** | **1** | **1** |

---

## Checklist de Validação (preencher antes de gerar slides)

- [ ] Nenhum conteúdo de A04 reintroduzido no mesmo nível (variáveis, tipos, condicionais, def/return)
- [ ] Todo exercício tem starter code
- [ ] Máx. 2 slides [TEORIA] seguidos sem interação (verificar Blocos 1 e 2)
- [ ] Sem em-dash (`—`) em título de slide
- [ ] Ordem dentro de cada bloco: T → E → D → TC
- [ ] D03 e D09 marcadas como "iniciadas" nos contextos após a aula
- [ ] `meta.yaml` atualizado com `aulaNum: A05`
