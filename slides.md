---
# ─────────────────────────────────────────────────────────────────
#  A05 — 12/03/2026 — Python: Operadores, Strings e Condicionais · Matemática · Estatística
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


# Aula 05
## Python: Operadores, Strings e Condicionais · Matemática · Estatística

*12 de março de 2026*

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 2 - Tipos de dados: por que isso importa -->
<!-- objetivo: mostrar por que tipos existem e a diferença entre x=5 e x='5' -->

# Tipos de Dados: Por Que Isso Importa?

## `x = 5` vs `x = '5'`

```python
x = 5      # número inteiro — int
y = '5'    # texto — str

print(x + x)   # 10  → somou
print(y + y)   # '55' → colou junto
```

O Python trata os dois de jeitos completamente diferentes.
**Tipo errado = resultado errado, ou erro na execução.**

<v-click>

> Para o Python, `5` e `'5'` são tão diferentes quanto uma maçã e uma laranja.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 3 - Aspas em Python -->
<!-- objetivo: mostrar diferença entre aspas simples e duplas e quando usar cada uma -->

# Aspas em Python: `'` ou `"` ?

```python
nome = 'Ana'        # aspas simples — funciona
cidade = "Maceió"   # aspas duplas  — também funciona

# use duplas quando tiver apóstrofo dentro:
frase = "it's Python"   # ✅
frase = 'it\'s Python'  # funciona, mas feio
```

<v-click>

> Regra prática: use `"duplas"` por padrão. Reserve `'simples'` para quando precisar de aspas dentro da string.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 4 - Interpolação com f-string -->
<!-- objetivo: apresentar f-string como a forma profissional de montar texto com variáveis -->

# Interpolação com f-string

```python
nome = "Bruno"
nota = 8.5

# cole variável dentro do texto com { }
print(f"Aluno: {nome}, nota: {nota}")
# → Aluno: Bruno, nota: 8.5

print(f"Aprovado: {nota >= 7}")
# → Aprovado: True
```

<v-click>

**Como funciona:** o `f` antes das aspas ativa as chaves `{}`. Tudo dentro de `{}` é executado como Python e colado no texto.

> Sem o `f`, as chaves aparecem literalmente na tela. Com o `f`, viram valores reais.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 5 - Consolidação: print() e f-string -->
<!-- objetivo: fixar print() e f-string como ferramenta de saída antes de entrar em loops -->

# `print()` — Fixando a Ferramenta

```python
# print() mostra qualquer coisa na tela
print("Olá, turma!")              # texto (str)
print(14)                          # número inteiro (int)
print(9.5)                         # decimal (float)
print(True)                        # verdadeiro/falso (bool)

# variável junto com texto
nome = "Ana"
print("Aluno:", nome)              # Aluno: Ana

# f-string: a forma profissional de montar texto
print(f"Oi, {nome}!")             # Oi, Ana!
nota = 8.5
print(f"Nota final: {nota}")      # Nota final: 8.5
print(f"Aprovado: {nota >= 7}")   # Aprovado: True
```

<v-click>

**F-string:** coloque `f` antes das aspas e use `{variavel}` para colar o valor dentro do texto.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 6 - Os 4 tipos de dados básicos -->
<!-- objetivo: consolidar os 4 tipos com metáfora visual das caixinhas antes de loops -->

# Os 4 Tipos de Dados Básicos

## As Caixinhas do Python

| Tipo | Guarda | Exemplos |
|---|---|---|
| `str` | texto | `"Ana"`, `"Python 3"` |
| `int` | número inteiro | `14`, `2026`, `100` |
| `float` | número decimal | `9.5`, `3.14` |
| `bool` | sim ou não | `True`, `False` |

<v-click>

> Cada variável tem exatamente um tipo. O Python decide pelo que você escreveu: tem aspas = `str`. Sem aspas com ponto = `float`. Sem aspas sem ponto = `int`. `True`/`False` = `bool`.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 7 - Armadilhas de tipo -->
<!-- objetivo: mostrar as armadilhas clássicas de tipo com código executável -->

# Cuidado com as Armadilhas de Tipo

```python
# "3" é str — não é o número 3!
x = "3"
y = 3

print(x + x)    # "33" (juntou textos)
print(y + y)    # 6   (somou números)

# armadilha clássica de iniciante:
print("3" + 3)  # ERRO: TypeError!

# para ver o tipo de qualquer variável:
print(type(x))  # <class 'str'>
print(type(y))  # <class 'int'>
```

> O Python não mistura caixas. Tente misturar e ele reclama.

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 8 - Aquecimento: identifique o tipo -->
<!-- objetivo: consolidar tipos com exercício de leitura — prática antes de loops -->

# Aquecimento — Qual o Tipo?

**Individual · 5 minutos · Nível 0 — sem digitar ainda**

Leia cada linha e escreva o tipo no caderno (`str`, `int`, `float`, `bool`):

```python
a = "machine learning"     # tipo: ___
b = 14                     # tipo: ___
c = 98.6                   # tipo: ___
d = False                  # tipo: ___
e = "3.14"                 # tipo: ___  ← ATENÇÃO: armadilha!
f = 3.14                   # tipo: ___  ← igual ao de cima?
```

<v-click>

Agora rode no VS Code e use `type()` para conferir:

```python
print(type(a))   # <class 'str'>
```

> `"3.14"` e `3.14` parecem iguais na tela, mas o Python os trata completamente diferente.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 9 - Roteiro do bloco -->
<!-- objetivo: orientar os alunos sobre o que vão aprender, reduzindo ansiedade antes de conteúdo novo -->

# O Que Vamos Fazer Hoje

Você já sabe criar variáveis e usar tipos básicos. Hoje vamos subir um degrau:

<v-click>

1. **Operadores de comparação**: `==`, `!=`, `<`, `>`, `<=`, `>=`
2. **Operadores lógicos**: `and`, `or`, `not`
3. **Condicionais**: revisão profunda de `if`, `elif`, `else`
4. **Funções de string**: `len()`, `.upper()`, `.lower()`, `.strip()`, `.replace()`
5. **Funções de número**: `abs()`, `round()`, `int()`, `float()`, `str()`

</v-click>

<v-click>

> Hoje sem listas. Só operadores, decisões e ferramentas de texto e número.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 10 - Operadores de comparação -->
<!-- objetivo: apresentar os 6 operadores de comparação com resultado bool -->

# Operadores de Comparação

Toda comparação retorna `True` ou `False`:

```python
10 == 10    # True  — igual a
10 != 9     # True  — diferente de
10 > 5      # True  — maior que
5 < 10      # True  — menor que
10 >= 10    # True  — maior ou igual
5 <= 10     # True  — menor ou igual
```

<v-click>

```python
nota = 7.5
print(nota >= 7)    # True  — aprovado!
print(nota == 10)   # False — não é nota máxima
print(nota < 5)     # False — não está reprovado
```

> O resultado é sempre `bool`: `True` ou `False`. Esse valor pode ser guardado em variável ou usado direto num `if`.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 11 - EX00: Verdadeiro ou Falso? -->
<!-- objetivo: calcular expressões de comparação na mão antes de rodar código -->

# EX00 - Verdadeiro ou Falso?

**Individual · 5 minutos · Nível 0: calcule na mão**

Antes de rodar, escreva `True` ou `False` para cada linha:

```python
# EX00 - Verdadeiro ou Falso?
a = 8
b = 5

print(a > b)        # ___
print(a == b)       # ___
print(a != b)       # ___
print(b >= 5)       # ___
print(a + b > 15)   # ___
print(a * 2 == 16)  # ___
```

<v-click>

Agora rode no VS Code e confira.

> Cuidado com `==` vs `=`: `==` pergunta, `=` atribui.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 12 - Operadores lógicos -->
<!-- objetivo: apresentar and, or, not com exemplos de aprovação como contexto -->

# Operadores Lógicos

Combine comparações com `and`, `or`, `not`:

```python
nota = 7.5
frequencia = 0.80

# and: as DUAS precisam ser True
nota >= 7 and frequencia >= 0.75    # True — aprovado

# or: PELO MENOS UMA precisa ser True
nota >= 7 or frequencia >= 0.75     # True — alguma condição

# not: inverte o resultado
not (nota >= 7)                     # False — não é True
```

<v-click>

| Operador | Resultado True quando... |
|---|---|
| `a and b` | `a` E `b` são True |
| `a or b` | `a` OU `b` são True |
| `not a` | `a` é False |

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 13 - Condicionais if/elif/else -->
<!-- objetivo: aprofundar if/elif/else com múltiplas condições e operadores lógicos -->

# Condicionais: `if`, `elif`, `else`

Você já viu isso em A04. Agora com mais condições:

```python {1-4|5-11|all}
nota = 7.5
frequencia = 0.80

if nota >= 7 and frequencia >= 0.75:
    print("Aprovado!")
elif nota >= 5 and frequencia >= 0.75:
    print("Recuperação")
elif frequencia < 0.75:
    print("Reprovado por falta")
else:
    print("Reprovado por nota")
```

<v-click>

> O Python verifica cada `if`/`elif` de cima para baixo. Para na primeira condição `True`. O `else` é o "nenhuma das anteriores".

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 14 - EX01: Classificador de notas -->
<!-- objetivo: praticar if/elif/else com múltiplos critérios de nota -->

# EX01 - Classificador de Notas

**Em dupla · 8 minutos · Nível 1**

```python
# EX01 - Classificador de Notas
def classificar(nota):
    """Classifica a nota em conceito A, B, C, D ou F"""
    if nota >= 9.0:
        return ___    # "A"
    elif nota >= 7.0:
        return ___    # "B"
    elif nota >= 5.0:
        return ___    # "C"
    elif nota >= 3.0:
        return ___    # "D"
    else:
        return ___    # "F"

# teste com esses valores:
print(classificar(9.5))   # A
print(classificar(7.0))   # B
print(classificar(4.9))   # D
print(classificar(1.0))   # F
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 15 - Funções de string -->
<!-- objetivo: apresentar as funções de string mais usadas em tratamento de dados de texto -->

# Funções de String

Strings têm ferramentas prontas. Use o `.` para chamar:

```python
modelo = "  GPT-4 Turbo  "

len(modelo)               # 16  — tamanho (conta espaços!)
modelo.strip()            # "GPT-4 Turbo"  — remove espaços das pontas
modelo.upper()            # "  GPT-4 TURBO  "  — tudo maiúsculo
modelo.lower()            # "  gpt-4 turbo  "  — tudo minúsculo
modelo.replace("4", "5")  # "  GPT-5 Turbo  "  — troca trecho
```

<v-click>

**Encadeamento: aplicar várias de uma vez**

```python
nome_limpo = "  gpt-4 turbo  ".strip().upper()
print(nome_limpo)   # "GPT-4 TURBO"
```

> Em dados reais, nomes de modelos e labels chegam sujos: espaços extras, caixa errada, caracteres estranhos. Essas funções são o primeiro passo de limpeza.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 16 - EX02: Processe o nome do modelo -->
<!-- objetivo: praticar strip, upper, lower, replace e len com contexto de nome de modelos de IA -->

# EX02 - Processe o Nome do Modelo

**Individual · 8 minutos · Nível 1**

```python
# EX02 - Processe o Nome do Modelo
entrada = "  gemini 1.5 pro  "   # dado "sujo" de entrada

# 1. qual o tamanho do texto (com espaços)?
print(len(entrada))               # ___

# 2. remova os espaços das pontas
limpo = ___                       # use .strip()
print(limpo)                      # "gemini 1.5 pro"

# 3. coloque em maiúsculo
maiusculo = ___                   # use .upper()
print(maiusculo)                  # "GEMINI 1.5 PRO"

# 4. troque "pro" por "flash" (na versão limpa)
novo = limpo.replace(___, ___)
print(novo)                       # "gemini 1.5 flash"
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 17 - Funções de número -->
<!-- objetivo: apresentar abs, round e os conversores int/float/str como caixa de ferramentas numérica -->

# Funções de Número

```python
# abs() — valor absoluto (sem sinal negativo)
abs(-7.5)           # 7.5
abs(3)              # 3

# round() — arredonda para N casas decimais
round(3.14159, 2)   # 3.14
round(7.5)          # 8    — arredonda para inteiro

# conversores: traduzem entre tipos
int("14")           # 14   — str para int
int(9.9)            # 9    — float para int (corta, não arredonda!)
float("9.5")        # 9.5  — str para float
str(42)             # "42" — int para str
```

<v-click>

> `int(9.9)` dá `9`, não `10`. Ele corta o decimal, não arredonda. Use `round()` para arredondar antes se precisar.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 18 - EX03: Formate o relatório -->
<!-- objetivo: combinar abs, round, str e f-string para montar saída formatada de dados de modelo -->

# EX03 - Formate o Relatório

**Individual · 8 minutos · Nível 2**

```python
# EX03 - Formate o Relatório
acuracia_bruta = 0.91666666
variacao = -0.045
nome_modelo = "  claude-3  "

# 1. arredonde a acurácia para 2 casas decimais
acuracia = ___             # use round()

# 2. valor absoluto da variação (sem sinal)
variacao_abs = ___         # use abs()

# 3. limpe o nome: sem espaços, em maiúsculo
nome = ___                 # use .strip() e .upper()

# 4. monte o relatório com f-string:
print(f"Modelo: {nome}")
print(f"Acurácia: {acuracia}")
print(f"Variação: {variacao_abs}")
```

Saída esperada:
```
Modelo: CLAUDE-3
Acurácia: 0.92
Variação: 0.045
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 19 - Integração: condicional + funções juntos -->
<!-- objetivo: mostrar como operadores, condicionais e funções trabalham juntos numa validação real -->

# Tudo Junto: Validação de Entrada

Na prática, você vai combinar operadores, condicionais e funções:

```python {1-4|5-13|all}
def validar_modelo(nome, acuracia):
    """Valida e classifica um resultado de modelo"""
    nome_limpo = nome.strip().upper()
    acuracia_ok = round(acuracia, 3)

    if not nome_limpo:
        return "ERRO: nome vazio"
    elif acuracia_ok >= 0.90:
        return f"{nome_limpo}: EXCELENTE ({acuracia_ok})"
    elif acuracia_ok >= 0.70:
        return f"{nome_limpo}: BOM ({acuracia_ok})"
    else:
        return f"{nome_limpo}: BAIXO ({acuracia_ok})"
```

<v-click>

> Isso é o que acontece em pipelines de ML reais: limpa o dado, valida, classifica, formata a saída.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 20 - EX04: Validador de entrada -->
<!-- objetivo: praticar integração completa de funções de string, round e condicionais -->

# EX04 - Validador de Entrada

**Em dupla · 10 minutos · Nível 2**

```python
# EX04 - Validador de Entrada
def validar_nota(nome_aluno, nota_bruta):
    """Limpa o nome, arredonda a nota e retorna situação"""
    # 1. limpe o nome: sem espaços extras, em maiúsculo
    nome = ___

    # 2. arredonde nota para 1 casa decimal
    nota = ___

    # 3. classifique: >= 7.0 Aprovado | >= 5.0 Recuperação | senão Reprovado
    if ___:
        situacao = ___
    elif ___:
        situacao = ___
    else:
        situacao = ___

    return f"{nome}: {nota} - {situacao}"

print(validar_nota("  ana  ", 7.666))   # ANA: 7.7 - Aprovado
print(validar_nota(" bruno ", 4.999))   # BRUNO: 5.0 - Recuperação
print(validar_nota("carla  ", 3.1))     # CARLA: 3.1 - Reprovado
```

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- SLIDE 21 - DINAMICA: Triagem de Dados -->
<!-- objetivo: fixar operadores e funções de string em situação lúdica de dupla -->

# Dinâmica em Dupla: Triagem de Dados

**10 minutos · Nível 2**

**Colega A:** cria um dado de modelo com nome e acurácia:

```python
nome = "  gpt-4 turbo  "
acuracia = 0.8733
```

**Colega B:** escreve uma função que:
- Limpa o nome (`.strip().upper()`)
- Arredonda a acurácia (`round()`)
- Classifica com `if/elif/else`
- Retorna uma string formatada com f-string

<v-click>

Depois: troquem de papel. Colega A vira programador.

> Sem listas. Sem loops. Só operadores, funções e condicionais.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 22 - Síntese e gancho para A06 -->
<!-- objetivo: consolidar o que foi aprendido e preparar o aluno para loops e listas na próxima aula -->

# O Que Você Aprendeu Hoje

<v-click>

- **Operadores de comparação**: `==`, `!=`, `<`, `>`, `<=`, `>=` retornam `bool`
- **Operadores lógicos**: `and`, `or`, `not` combinam condições
- **Condicionais**: `if/elif/else` decide com base em comparações
- **Funções de string**: `.strip()`, `.upper()`, `.lower()`, `.replace()`, `len()`
- **Funções de número**: `abs()`, `round()`, `int()`, `float()`, `str()`

</v-click>

<v-click>

**A06:** com essas ferramentas na mão, vamos aprender `for`, `while` e, depois, listas.
Os loops vão repetir tudo isso que você já sabe, muitas vezes, de forma automática.

> Hoje você aprendeu a tomar decisões. Amanhã você aprende a repetir.

</v-click>

---
layout: cover
bgPreset: palette
---

<!-- SLIDE 23 - Abertura Bloco 2 -->

# Bloco 2
## Matemática: Aritmética e Álgebra

*9h50 - 11h10 · 2 HA · UC03 · Primeiro contato*

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

Calcule cada linha **na mão** antes de rodar no VS Code:

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

*11h10 - 12h00 · 1 HA · UC09 · Primeiro contato*

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

operadores · condicionais · `if`/`elif`/`else` · funções de string · funções de número · aritmética computacional · equação linear

*Amanhã (A06 - 13/03): Banco de Dados entra em cena - primeiro contato com SQL.*
