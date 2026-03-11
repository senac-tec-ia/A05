---
# ─────────────────────────────────────────────────────────────────
#  A05 — 12/03/2026 — Python: Loops e Listas · Matemática · Estatística
# ─────────────────────────────────────────────────────────────────
theme: ./
colorSchema: dark

title: "Técnico em IA — Aula 05"
author: Leonardo Zanini
courseTitle: Técnico em Inteligência Artificial
aulaNum: "Aula 05"

bgPreset: palette
# ─────────────────────────────────────────────────────────────────
---

---
layout: cover
bgPreset: palette
---

<!-- SLIDE 1 - Capa -->

# Aula 05
## Python: Loops e Listas · Matemática · Estatística

*12 de março de 2026*

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- SLIDE 2 - Revisão relâmpago -->
<!-- objetivo: ativar memória de curto prazo sobre variáveis, condicionais e funções antes de avançar para loops -->

# Revisão Relâmpago

**3 perguntas, 2 minutos — sem pesquisar**

- Qual a diferença entre `int` e `float`?
- Complete: `if nota >= 7: ____`
- O que faz `def somar(a, b): return a + b`?

> Já sabemos isso. Hoje vamos além: repetição e coleções.

---
layout: center
card: true
bgPreset: palette
---

<!-- SLIDE 3 - Divisor Bloco 1 -->

# Bloco 1
## Python: Loops e Listas

*7h10 - 9h30 · 3 HA · D05-UC03*

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 4 - Por que repetir? -->
<!-- objetivo: criar intuição sobre repetição sequencial como base do processamento em IA -->

# Por que repetir?

<v-click>

- Todo modelo de linguagem lê **token por token**
- Reconhecimento facial analisa **pixel por pixel**
- Treino de rede neural percorre o dataset **época por época**

</v-click>

<v-click>

> **Conclusão:** repetição controlada é o coração de todo sistema de IA.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 5 - O loop for -->
<!-- objetivo: aprender a sintaxe do for com range() e iteração sobre coleção -->

# O loop `for`

```python {1-3|4-6|all}
# iterar sobre uma lista de tokens
tokens = ["IA", "é", "incrível"]
for token in tokens:
    print(token)   # processa cada item da lista

# iterar com range
for epoca in range(5):
    print(f"Época {epoca} rodando...")
```

<v-click>

- **`for variavel in colecao:`** — sempre com `:` e indentação de 4 espaços
- `range(n)` gera 0, 1, 2, ..., n-1

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 6 - EX01 -->

# EX01 - Iterando Tokens

**Em dupla · 8 minutos · Nível 1**

Complete o código para imprimir cada token e contar quantos existem:

```python
# EX01 - Iterando Tokens
tokens = ["machine", "learning", "é", "incrível", "mesmo"]

# TAREFA 1: imprimir cada token
for ___ in ___:
    print(___)

# TAREFA 2: contar tokens
contador = 0
for t in tokens:
    ___ += 1

print(f"Total de tokens: {contador}")
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 7 - O loop while -->
<!-- objetivo: entender loop com condição de parada dinâmica, relevante para critérios de convergência em IA -->

# O loop `while`

```python {1-2|3-6|7|all}
# continua enquanto a condição for verdadeira
confianca = 0.5

while confianca < 0.9:
    confianca += 0.1   # simula melhora a cada iteração
    print(f"Confiança atual: {confianca:.1f}")

print("Modelo convergiu!")
```

<v-click>

- **Cuidado:** se a condição nunca for falsa, o loop não termina
- Use `while` quando **não sabe quantas repetições** serão necessárias

</v-click>

---
layout: two-cols-text
card: true
bgPreset: default
---

<!-- SLIDE 8 - break e continue -->
<!-- objetivo: controlar o fluxo de um loop para pular ou interromper iterações -->

# Controlando o Loop

## `break` - encerra tudo

```python
for token in tokens:
    if token == "STOP":
        break       # sai do loop
    print(token)
```

Usado quando encontrou o que precisava.

::right::

## `continue` - pula este item

```python
for token in tokens:
    if token == "":
        continue    # pula vazios
    print(token)
```

Usado para filtrar itens indesejados.

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 9 - EX02 -->

# EX02 - Limiar de Confiança

**Em dupla · 10 minutos · Nível 2**

O modelo treina até atingir 85% de acurácia. Complete:

```python
# EX02 - Limiar de Confiança
acuracia = 0.50
tentativa = 0

while ___:            # continue enquanto acurácia < 0.85
    acuracia += 0.05
    tentativa += 1
    print(f"Tentativa {tentativa}: acurácia = {acuracia:.2f}")

    if acuracia >= 1.0:
        break         # limite de segurança

print(f"Modelo pronto após {tentativa} tentativas!")
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 10 - Listas em Python -->
<!-- objetivo: entender listas como estrutura sequencial para armazenar resultados de modelos de IA -->

# Listas em Python

```python {1|2-4|5-7|all}
# criar lista vazia
acuracias = []

# adicionar itens com append
acuracias.append(0.62)
acuracias.append(0.75)
acuracias.append(0.83)

# acessar por índice (começa em 0)
print(acuracias[0])    # 0.62 - primeira época
print(acuracias[-1])   # 0.83 - última época
print(len(acuracias))  # 3 - total de épocas
```

<v-click>

> Pense na lista como o **histórico de treino** de um modelo: cada índice é uma época.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 11 - EX03 -->

# EX03 - Histórico de Acurácias

**Individual · 8 minutos · Nível 2**

Construa o histórico de treino ao longo de 5 épocas:

```python
# EX03 - Histórico de Acurácias
acuracias = []
acuracia_inicial = 0.50

for epoca in range(5):
    acuracia = acuracia_inicial + ___ * 0.08   # cresce 8% por época
    acuracias.___(___)                          # adiciona à lista

print("Histórico completo:", acuracias)
print("Melhor acurácia:", max(acuracias))
print("Pior acurácia:", min(acuracias))
```

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- SLIDE 12 - DINAMICA: Purificador de Dataset -->

# Dinâmica em Dupla: Purificador de Dataset

**15 minutos · Desafio colaborativo**

O dataset chegou com sujeira. Seu loop deve filtrar só os tokens válidos:

```python
# dataset com problemas
dataset = ["gato", None, "cachorro", "", 42, "pássaro", None, "peixe"]

tokens_validos = []

for item in dataset:
    # ESCREVA A CONDIÇÃO: apenas strings não vazias
    if ___:
        tokens_validos.append(item)

print(f"Válidos: {tokens_validos}")
print(f"Removidos: {len(dataset) - len(tokens_validos)}")
```

> Dica: `type(item) == str` e `item != ""`

---
layout: center
card: true
bgPreset: animate
---

<!-- SLIDE 13 - Sintese Bloco 1 e gancho -->

# Loops e Listas: o que fizemos

<v-click>

`for` percorre coleções · `while` repete com condição · listas guardam o histórico

</v-click>

<v-click>

> Em matemática, o loop `for` sobre uma lista é o equivalente visual de uma **somatória**.
> No próximo bloco, vamos colocar nome nos números que estamos calculando.

</v-click>

---
layout: cover
bgPreset: palette
---

<!-- SLIDE 14 - Abertura Bloco 2 -->

# Bloco 2
## Matemática: Aritmética e Álgebra

*9h50 - 11h10 · 2 HA · D03-UC01 · Primeiro contato*

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 15 - Abertura motivadora D03 -->
<!-- objetivo: mostrar que toda operação de IA é uma operação matemática, motivando o estudo formal -->

# Matemática é a Linguagem da IA

<v-click>

- Um modelo de linguagem executa **bilhões de multiplicações por segundo**
- Uma rede neural é **álgebra linear aplicada em matrizes gigantes**
- Uma classificação é **uma equação que separa grupos de dados**

</v-click>

<v-click>

> Você já faz matemática toda vez que escreve Python.
> Hoje vamos dar nome aos conceitos que usamos sem saber.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 16 - Aritmética computacional -->
<!-- objetivo: dominar precisão numérica e precedência de operadores em contextos computacionais -->

# Aritmética Computacional

```python {1-3|4-6|7-9|all}
# divisão: inteira vs real
7 / 2    # 3.5  (float - resultado exato)
7 // 2   # 3    (int - descarta a vírgula)
7 % 2    # 1    (resto da divisão)

# potência e precedência (PEMDAS)
2 ** 10       # 1024 (2 elevado a 10)
2 + 3 * 4     # 14   (multiplicação antes!)
(2 + 3) * 4   # 20   (parênteses mudam tudo)

# float: cuidado com precisão
0.1 + 0.2     # 0.30000000000000004
```

<v-click>

<MLToast title="ATENÇÃO">
  Em IA, imprecisão de float acumula ao longo de <strong>milhões de operações</strong>. Por isso modelos usam <code>float32</code> e <code>float16</code>.
</MLToast>

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 17 - EX04 -->

# EX04 - Ordem das Operações

**Individual · 5 minutos · Nível 1**

Calcule cada linha **na mão** antes de rodar no Colab:

```python
# EX04 - Ordem das Operações
# Calcule mentalmente, depois verifique no Colab

a = 2 + 3 * 4       # qual o resultado?
b = (2 + 3) * 4     # e agora?
c = 10 // 3         # divisão inteira de 10 por 3?
d = 10 % 3          # sobra quanto?
e = 2 ** 3 + 1      # potência antes da soma?

print(a, b, c, d, e)

# BONUS: por que isso retorna False?
print(0.1 + 0.2 == 0.3)
```

---
layout: two-cols-text
card: true
bgPreset: default
---

<!-- SLIDE 18 - Variável matemática vs Python -->
<!-- objetivo: diferenciar o conceito de variável em álgebra do conceito em programação -->

# Variável: Matemática vs Python

## Em Matemática

- `x` é uma **incógnita** - valor desconhecido
- `x + 3 = 10` - resolve-se para encontrar x
- `=` significa **igualdade** (verdade ou falsidade)

Equação linear: **`y = 2x + 5`**
- Cada valor de `x` gera um valor de `y`
- Descreve uma reta num gráfico

::right::

## Em Python

- `x` é um **rótulo** - aponta para um valor na memória
- `x = 10` - **atribui** o valor 10 à variável
- `=` significa **atribuição** (comando, não pergunta)

```python
x = 3
y = 2 * x + 5   # y = 11
print(y)         # 11
```

> Em IA: `y = wx + b` é a equação de um neurônio linear.

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 19 - EX05 -->

# EX05 - Tabela da Equação Linear

**Em dupla · 10 minutos · Nível 2**

Gere a tabela de valores para `y = 2x + 5`:

```python
# EX05 - Tabela da Equação Linear
def calcular_y(x):
    """Retorna y para a equação y = 2x + 5"""
    return ___   # complete a equação aqui

# gerar tabela para x de 0 a 5
print("x  |  y = 2x + 5")
print("---|-------------")
for x in range(___):       # de 0 até 5 inclusive
    y = calcular_y(x)
    print(f"{x}  |  {y}")
```

> Resultado: quando x=0, y=5. Quando x=3, y=11.

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- SLIDE 20 - DEBATE: Álgebra em IA -->

# Debate: Álgebra em IA

**Discussão coletiva - 5 minutos**

<v-click>

- O EX05 criou uma tabela de `y = 2x + 5`. Isso te lembra alguma coisa do mundo real?
- Se `x` for "ano" e `y` for "preço de uma GPU", o que a equação faz?
- Um modelo de regressão **aprende** os valores de `a` e `b`. O que isso significa?

</v-click>

<v-click>

> **Treinar um modelo linear** é encontrar os melhores valores de `a` e `b`
> para descrever os dados reais. Isso é o que veremos agora em Estatística.

</v-click>

---
layout: cover
bgPreset: palette
---

<!-- SLIDE 21 - Abertura Bloco 3 -->

# Bloco 3
## Estatística: Função Linear

*11h10 - 12h00 · 1 HA · D09-UC07 · Primeiro contato*

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 22 - Funções descrevem comportamento -->
<!-- objetivo: introduzir o conceito de função matemática como descrição de comportamento de modelos -->

# Funções Descrevem Comportamento

<v-click>

- A curva de perda de um modelo durante o treino é uma **função**
- A relação entre dados de entrada e predição é uma **função**
- A sigmoid que transforma um número em probabilidade é uma **função**

</v-click>

<v-click>

**Definição:** `y = f(x)` — para cada entrada `x`, há exatamente uma saída `y`

> A forma mais simples é a **função linear**: `y = ax + b`

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 23 - Função linear coeficientes -->
<!-- objetivo: compreender os coeficientes a e b de uma função linear e sua representação gráfica -->

# Função Linear: `y = ax + b`

<SlideTable>

| Componente | Nome | Papel |
|---|---|---|
| `a` | coeficiente angular | inclinação da reta: positivo sobe, negativo desce |
| `b` | coeficiente linear | onde a reta cruza o eixo y (valor quando x = 0) |

</SlideTable>

<v-click>

```python
# a=2, b=5: y cresce 2 unidades para cada 1 de x
# x=0  ->  y = 2(0) + 5 =  5
# x=1  ->  y = 2(1) + 5 =  7
# x=3  ->  y = 2(3) + 5 = 11
```

</v-click>

<v-click>

> Conexão direta com o EX05: você já calculou isso! Agora temos o nome matemático.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 24 - EX06 -->

# EX06 - Tabela da Função Linear

**Individual · 8 minutos · Nível 1**

Calcule os valores para `f(x) = 3x - 1`:

```python
# EX06 - Tabela da Função Linear
def f_linear(x, a, b):
    """Calcula y = ax + b para os coeficientes dados"""
    return ___   # complete a função

# coeficientes: a=3, b=-1
a = 3
b = -1

print("x  |  f(x) = 3x - 1")
print("---|------------------")
for x in range(6):    # x de 0 a 5
    y = f_linear(x, a, b)
    print(f"{x}  |  {y}")
```

> Quando x=0: f(0) = -1. Quando x=2: f(2) = 5.

---
layout: default
card: true
bgPreset: animate
---

<!-- SLIDE 25 - Tarefa de Casa -->

# Tarefa A05

**Entrega: próxima aula (13/03) · Arquivo:** `tarefa_05_loops_algebra.py`

<v-click>

**Parte 1 - Python:** Dado o dataset `[0.91, None, 0.73, "", 0.85, 0.44, None]`, escreva um loop que filtre apenas os `float` e calcule a média das acurácias válidas.

</v-click>

<v-click>

**Parte 2 - Matemática:** Usando `f_linear()`, gere a tabela de `y = 3x + 2` para `x` de 0 a 9 e imprima cada par `(x, y)`.

</v-click>

<v-click>

**Parte 3 - Reflexão:** Na equação `y = 3x + 2`, quando `x` dobra de 3 para 6, `y` dobra também? Por que não? (responder em comentário no código)

</v-click>

---
layout: end
bgPreset: palette
---

<!-- SLIDE 26 - Encerramento -->

# Até amanhã!

**Hoje cobrimos:**

`for` · `while` · `break/continue` · listas · aritmética computacional · equação linear · função `y = ax + b`

*Amanhã (A06 - 13/03): Banco de Dados entra em cena - primeiro contato com SQL.*
