# Contexto — Desenvolvimento de Linguagem Python (UC05)

**Código:** UC05  
**UC:** UC05 — Desenvolvimento de Linguagem Python  
**Disciplina:** Python para IA  
**Carga Total:** 67h (80 HA) | `T1: 26 HA (ajustado: 20) · T2: 27 HA · T3: 27 HA`  
**Peso no dia:** Pesado (3 HA/bloco, sempre no Bloco 1)

---

## Estado Geral

| Trim. | HA Alocado | HA Dado | HA Restante |
|---|---|---|---|
| T1 | 20 (ajustado) | 8,5 | 11,5 |
| T2 | 27 | 0 | 27 |
| T3 | 27 | 0 | 27 |

---

## Indicadores Curriculares

| Ind. | Descrição | Status T1 |
|---|---|---|
| 1 | Elabora código conforme funcionalidades e características do aplicativo, na linguagem Python | Em andamento |
| 2 | Utiliza comandos de integração dos códigos construídos em Python, conforme estrutura projetada | Pendente |
| 3 | Realiza a depuração, verificando e corrigindo erros na programação, de acordo com recomendação técnica (T2) | Pendente |
| 4 | Utiliza bibliotecas de manipulação de dados para aplicações de IA (T3) | Pendente |

---

## Aulas Realizadas

| Aula | Data | HA (D05) | Tópicos Principais | Status |
|---|---|---|---|---|
| A01 | 26/02/2026 | 0 | Não trabalhada | - |
| A02 | 27/02/2026 | ~0,5 | Reconhecimento do ambiente: VS Code, GitHub, Jupyter Notebook, onde rodar Python | Ministrada |
| A03 | 05/03/2026 | 0 | Não trabalhada | - |
| A04 | 06/03/2026 | ~2 | Variáveis, tipos (str/int/float/bool), `print()` | Ministrada |
| A05 | 12/03/2026 | ~3 | Operadores de comparação (`==`, `!=`, `<`, `>`, `<=`, `>=`); operadores lógicos (`and`, `or`, `not`); condicionais `if/elif/else` com múltiplas condições; funções de string (`.strip()`, `.upper()`, `.lower()`, `.replace()`, `len()`); funções de número (`abs()`, `round()`, `int()`, `float()`, `str()`); f-string avançada | Ministrada |

---

## Conceitos Consolidados (não reintroduzir no mesmo nível)

| Conceito | Aula | Nível de Profundidade |
|---|---|---|
| Ambientes Python (VS Code, Jupyter) | A02 | Reconhecimento |
| Variáveis e atribuição | A04 | Introdutório |
| Tipos de dados: str, int, float, bool | A04 | Introdutório |
| `print()` | A04 | Introdutório|
|`input()` | A05 | Introdutório |
| Operadores aritméticos (+, -, *, /, //, %, **) | A05 | Introdutório |
| Condicionais: `if/elif/else` | A05 | Introdutório |
| Operadores de comparação: `==`, `!=`, `<`, `>`, `<=`, `>=` | A05 | Introdutório |
| Operadores lógicos: `and`, `or`, `not` | A05 | Introdutório |
| Condicionais com múltiplas condições e lógica combinada | A05 | Intermediário |
| Funções de string: `.strip()`, `.upper()`, `.lower()`, `.replace()`, `len()` | A05 | Introdutório |
| Funções de número: `abs()`, `round()`, `int()`, `float()`, `str()` | A05 | Introdutório |
| f-string com expressões dentro de `{}` | A05 | Intermediário |

---

## Tópicos Pendentes no T1 (11,5 HA restantes)
| Seq. | Tópico | HA | Ind. |
|---|---|---|---|
| 1 | Loops: `for`, `while`, `break`, `continue` | 2 | 1 |
| 2 | Listas: criação, indexação, `append`, `len`, `max`, `min`, `for` sobre listas | 2 | 1 |
| 3 | Dicionários: criação, acesso por chave, `.keys()`, `.values()`, `.items()` | 2 | 1 |
| 4 | Funções avançadas: parâmetros default, `*args`, docstrings, escopo | 2 | 1 |
| 5 | Módulos e importações: `import`, `random`, `math`, `os` | 2 | 2 |
| 6 | Leitura e escrita de arquivos: `open()`, `read()`, `write()`, `.csv` | 2 | 2 |
| 7 | Tratamento de erros: `try/except` | 1 | 1 |
| 8 | Exercício integrador: mini-projeto com lista de dados de IA | 1,5 | 1, 2 |

---

## Recomendações para o Próximo Encontro

> A05 consolidou: operadores de comparação, operadores lógicos, if/elif/else com múltiplas condições, funções de string (.strip/.upper/.lower/.replace/len), funções de número (abs/round/int/float/str), f-string.
> A06 (próximo encontro com D05) deve iniciar loops: começar com `for` sobre `range()`, depois `while`, `break`, `continue`.
> Introduzir listas logo após loops, usando contexto de datasets de IA.
> Regra: todo exemplo de loop deve ter analogia do cotidiano (playlist, fila, lista de chamada) ANTES do contexto IA.

---

## Feedback de Campo

| Data | Observacao | Acao tomada |
|---|---|---|
| 2026-03-05 | Alunos sem nenhuma experiencia previa em programacao | Introducao ao Python iniciada em Fundamentos de Computacao com ritmo bem lento |
| 2026-03-05 | Dinamicas em dupla funcionam melhor do que exercicios individuais para programacao | Estrutura de pares adotada como padrao para exercicios de codigo |

---

## Conexoes com Outras Disciplinas

| Conceito | Disciplina Relacionada | Observacao |
|---|---|---|
| GPU para treino | Arquitetura de Computadores e GPU | Python usa PyTorch/TF que dependem de GPU |
| CSV como formato de dados | Fundamentos de Computacao | Base para Pandas e leitura de datasets |
| Estatistica descritiva | Estatistica Aplicada a IA | Pandas describe() vai precisar desse embasamento |
