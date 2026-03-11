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

<!-- SLIDE 2 - Revisão relâmpago (sem funções) -->
<!-- objetivo: ativar memória com perguntas sobre o que foi definitivamente consolidado — sem mencionar def/funções -->

# Revisão Relâmpago

**3 perguntas, 2 minutos — sem pesquisar**

- O que aparece na tela quando rodamos `print("Python")`?
- Qual a diferença entre `x = 5` e `x = "cinco"`?
- Complete: `if nota >= 7: ____`

> Já sabemos isso. Hoje vamos além: repetição e coleções.

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 3 - Consolidação: print() e f-string -->
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
layout: two-cols-text
card: true
bgPreset: default
---

<!-- SLIDE 4 - Tipos de dados: as caixinhas -->
<!-- objetivo: consolidar os 4 tipos com metáfora visual e armadilhas comuns antes de loops -->

# Os 4 Tipos de Dados Básicos

## As Caixinhas do Python

| Tipo | Guarda | Exemplos |
|---|---|---|
| `str` | texto | `"Ana"`, `"Python 3"` |
| `int` | número inteiro | `14`, `2026`, `100` |
| `float` | número decimal | `9.5`, `3.14` |
| `bool` | sim ou não | `True`, `False` |

::right::

## Cuidado com as Armadilhas

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

<!-- SLIDE 5 - Aquecimento: identifique o tipo -->
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

Agora rode no Colab e use `type()` para conferir:

```python
print(type(a))   # <class 'str'>
```

> `"3.14"` e `3.14` parecem iguais na tela, mas o Python os trata completamente diferente.

</v-click>

---
layout: center
card: true
bgPreset: palette
---

<!-- SLIDE 6 - Divisor Bloco 1 -->

# Bloco 1
## Python: Loops e Listas

*7h10 - 9h30 · 3 HA · UC05*

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 7 - Você já faz loops todo dia -->
<!-- objetivo: criar intuição sobre repetição com analogias do cotidiano adolescente ANTES de qualquer código -->

# Você Já Faz Loops Todo Dia

<v-click>

Pense na sua rotina:

- **Spotify:** toca faixa 1, faixa 2, faixa 3... até acabar a playlist
- **WhatsApp:** você abre cada mensagem não lida, uma por uma
- **Chamada:** professor fala nome 1, nome 2... até chamar todos
- **Jogo:** personagem anda, pula, ataca — repete centenas de vezes por segundo

</v-click>

<v-click>

> **Loop = repetir uma ação para cada item de uma lista** — ou enquanto uma condição for verdadeira.

Sem loop: você escreveria `print("Ana")`, `print("Bruno")`, `print("Carla")`... para cada nome.
**Com loop: Python faz isso por você, quantas vezes precisar.**

</v-click>

---
layout: two-cols-text
card: true
bgPreset: default
---

<!-- SLIDE 8 - Da vida real para o Python -->
<!-- objetivo: criar ponte explícita entre a intuição cotidiana e a sintaxe do for antes de ver qualquer código de IA -->

# Da Vida Real para o Python

## Chamada da turma (passo a passo)

1. Pegar a lista de nomes
2. **Para cada nome** na lista: falar em voz alta
3. Repetir até o fim da lista

::right::

## Em Python

```python
turma = ["Ana", "Bruno", "Carla", "Daniel"]

for nome in turma:
    print(nome, "- Presente!")

# saída:
# Ana - Presente!
# Bruno - Presente!
# Carla - Presente!
# Daniel - Presente!
```

**Como ler em voz alta:**
*"Para cada `nome` dentro de `turma`, execute o bloco abaixo"*

- `for` → começa o loop
- `nome` → variável temporária (você escolhe o nome!)
- `in turma` → de onde vêm os itens
- `:` → **obrigatório**, não esqueça!
- 4 espaços → tudo dentro do loop fica recuado

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 9 - O loop for: sintaxe completa com range() -->
<!-- objetivo: ver for com range() e iterar sobre coleões diferentes — ainda sem contexto IA -->

# O loop `for` — Sintaxe Completa

```python {1-4|5-8|9-12|all}
# Exemplo 1: percorrer lista de valores
notas = [7.5, 8.0, 6.5, 9.0]
for nota in notas:
    print(f"Nota: {nota}")

# Exemplo 2: range() gera sequência de números
for numero in range(5):         # 0, 1, 2, 3, 4
    print(f"Número {numero}")

# Exemplo 3: range com início e fim
for numero in range(1, 6):      # 1, 2, 3, 4, 5
    print(f"Questão {numero}")
```

<v-click>

- `range(5)` → gera 0, 1, 2, 3, 4  *(termina **antes** do 5)*
- `range(1, 6)` → gera 1, 2, 3, 4, 5  *(termina **antes** do 6)*
- Indentação de 4 espaços define o que está **dentro** do loop

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 10 - EX00: leia e preveja — nível 0 -->
<!-- objetivo: ensinar a ler código antes de escrever — habilidade essencial para quem nunca programou -->

# EX00 - Leia e Preveja

**Individual · 5 minutos · Nível 0 — sem digitar nada ainda**

O que este código vai imprimir? Escreva no **caderno** antes de rodar:

```python
frutas = ["maçã", "banana", "uva", "morango"]

for fruta in frutas:
    print("Fruta:", fruta)

print(f"Total: {len(frutas)} frutas")
```

No caderno:
1. Quantas linhas esse código imprime no total?
2. Qual é a terceira linha impressa?
3. O que `len(frutas)` retorna?

<v-click>

> Depois: rode no Colab e compare com o que escreveu no caderno.
> **Ler código antes de rodar é uma habilidade profissional essencial.**

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 11 - EX01: complete a chamada (contexto cotidiano) -->
<!-- objetivo: primeiro exercício de escrita — preencher lacunas em contexto completamente familiar -->

# EX01 - Complete a Chamada

**Em dupla · 8 minutos · Nível 1**

Complete os `___`. A lógica já está escrita pra vocês:

```python
# EX01 - Chamada digital da turma
turma = ["Alice", "Bruno", "Carla", "Daniel", "Eduarda"]

# TAREFA 1: imprima cada nome com "Presente!" na frente
for ___ in turma:
    print(___, "- Presente!")

# TAREFA 2: conte quantos alunos há na turma
total = ___(turma)         # dica: use len()
print(f"Total de alunos: {total}")

# TAREFA 3: imprima os números de 1 a 5 usando range
for numero in range(___):  # dica: range(1, 6) vai de 1 até 5
    print(numero)
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 12 - Bridge: cotidiano para IA (tokens) -->
<!-- objetivo: mostrar que a lógica que usaram para nomes é exatamente o que a IA usa com tokens -->

# Da Turma para a IA: É o Mesmo `for`

O loop que você usou na chamada é **exatamente igual** ao que uma IA usa para processar texto:

```python
# Contexto cotidiano — você já fez isso:
turma = ["Alice", "Bruno", "Carla"]
for aluno in turma:
    print(aluno)

# Contexto IA — mesma sintaxe, outro contexto:
tokens = ["machine", "learning", "é", "incrível"]
for token in tokens:
    print(token)   # IA processa palavra por palavra
```

<v-click>

**Token** = menor unidade de texto que um modelo de linguagem processa.
Quando você digita no ChatGPT, ele quebra seu texto em tokens e percorre cada um com um loop assim.

> A sintaxe é idêntica. O que muda é o **significado** da lista.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 13 - O loop while: analogia do alarme primeiro -->
<!-- objetivo: criar intuição para while com condição de parada usando analogia do cotidiano antes do código -->

# O loop `while` — Enquanto...

<v-click>

**Analogia do alarme:**
O despertador toca, você aperta soneca. E repete... **enquanto** não for hora de levantar.

```
enquanto (hora_atual < hora_de_acordar):
    tocar alarme
    apertar soneca
```

</v-click>

<v-click>

**Em Python:**

```python
hora_atual = 6
hora_de_acordar = 7

while hora_atual < hora_de_acordar:
    print(f"⏰ São {hora_atual}h — mais 5 minutinhos...")
    hora_atual += 1    # avança 1 hora

print("Hora de levantar!")
```

- `while condição:` → **enquanto** a condição for `True`, repete
- A cada repetição, algo deve **mudar** — senão o loop nunca para!

</v-click>

---
layout: two-cols-text
card: true
bgPreset: default
---

<!-- SLIDE 14 - break e continue: analogia da playlist -->
<!-- objetivo: tornar break/continue concretos com analogia de playlist do Spotify antes de ver código -->

# Controlando o Loop: `break` e `continue`

## `break` — para tudo

Como **fechar o Spotify** quando aparece anúncio:

```python
playlist = ["Música 1", "Música 2",
            "ANUNCIO", "Música 3"]

for musica in playlist:
    if musica == "ANUNCIO":
        break        # sai do loop
    print(f"Tocando: {musica}")
```

Sai do loop assim que encontra o anúncio.

::right::

## `continue` — pula este item

Como **apertar próxima** na faixa que você odeia:

```python
playlist = ["Música 1", "Música 2",
            "Aquela que odeio", "Música 3"]

for musica in playlist:
    if musica == "Aquela que odeio":
        continue     # pula esta, vai à próxima
    print(f"Tocando: {musica}")
```

Não ouve aquela faixa, mas a playlist continua.

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 15 - EX02: while em contexto cotidiano -->
<!-- objetivo: praticar while com contexto acessível (contagem regressiva) antes de ir para contexto IA -->

# EX02 - Contagem Regressiva

**Em dupla · 8 minutos · Nível 1**

Complete a contagem regressiva do foguete:

```python
# EX02 - Contagem Regressiva
contagem = 10

while ___:                   # enquanto contagem > 0
    print(f"{contagem}...")
    ___ -= 1                 # diminui 1 na contagem

print("🚀 Lançamento!")

# BÔNUS: pule o número 7 na contagem
# dica: if + continue dentro do while
```

Resultado esperado:
```
10...
9...
8...
...
1...
🚀 Lançamento!
```

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 16 - Listas em Python: analogia do carrinho -->
<!-- objetivo: introduzir listas com metáfora cotidiana (carrinho de mercado) antes de índices e append -->

# Listas em Python

<v-click>

**Analogia:** Lista = carrinho de mercado.
Você pode adicionar itens, ver o que tem, pegar pelo número da posição.

</v-click>

<v-click>

```python {1-2|3-6|7-10|all}
# criar lista vazia (carrinho vazio)
notas = []

# adicionar itens com append (colocar no carrinho)
notas.append(7.5)
notas.append(8.0)
notas.append(6.5)

# acessar por índice — começa em 0!
print(notas[0])    # 7.5  (primeiro item)
print(notas[-1])   # 6.5  (último item — de trás)
print(len(notas))  # 3    (quantos itens tem)
```

</v-click>

<v-click>

> `max(notas)` → maior · `min(notas)` → menor · `sum(notas)` → soma total
> **Atenção:** índice começa em 0. Primeiro item = `lista[0]`, não `lista[1]`.

</v-click>

---
layout: default
card: true
bgPreset: default
---

<!-- SLIDE 17 - EX03: boletim da turma (contexto cotidiano) -->
<!-- objetivo: praticar append + for em contexto cotidiano de notas antes de ir para contexto IA -->

# EX03 - Boletim da Turma

**Individual · 8 minutos · Nível 2**

Construa o boletim ao longo de 5 provas:

```python
# EX03 - Boletim da Turma
notas_turma = []
nota_base = 5.0

for prova in range(5):
    nota = nota_base + ___ * 0.8    # melhora 0.8 a cada prova
    notas_turma.___(___)             # adiciona à lista

print("Notas:", notas_turma)
print("Melhor nota:", max(notas_turma))
print("Pior nota:", min(notas_turma))
print("Quantidade:", len(notas_turma))
```

> `prova` vale 0, 1, 2, 3, 4 a cada rodada. Como usar isso na conta?

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- SLIDE 18 - DINAMICA: Purificador de Lista -->
<!-- objetivo: dinâmica em dupla combinando for + if + listas para resolver problema concreto de filtragem -->

# Dinâmica em Dupla: Purificador de Lista

**15 minutos · Desafio colaborativo**

A lista de notas chegou com problemas — tem `None`, strings vazias e valores absurdos. Filtre só as notas válidas:

```python
# Lista com sujeira
registros = [8.5, None, 7.0, "", 42, 6.5, None, 9.0]

notas_validas = []

for item in registros:
    # ESCREVA A CONDIÇÃO: apenas float entre 0 e 10
    if ___:
        notas_validas.append(item)

print(f"Válidas: {notas_validas}")
print(f"Removidos: {len(registros) - len(notas_validas)}")
print(f"Média: {sum(notas_validas) / len(notas_validas):.1f}")
```

> Dica: `type(item) == float` verifica o tipo. E o limite 0 a 10?

---
layout: center
card: true
bgPreset: animate
---

<!-- SLIDE 19 - Síntese Bloco 1 e gancho -->

# Loops e Listas: o que fizemos

<v-click>

`for` percorre coleções · `while` repete com condição · `break/continue` controlam o fluxo · listas guardam sequências

</v-click>

<v-click>

> O mesmo loop que percorreu nomes de alunos é o que percorre **tokens numa IA**.
> O mesmo `append` que montou o boletim é o que guarda o **histórico de treino** de um modelo.

</v-click>

<v-click>

> Em matemática, o loop `for` sobre uma lista é o equivalente visual de uma **somatória**.
> No próximo bloco, vamos dar nome matemático às operações que já fizemos em Python.

</v-click>

---
layout: cover
bgPreset: palette
---

<!-- SLIDE 14 - Abertura Bloco 2 -->

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

`for` · `while` · `break/continue` · listas · aritmética computacional · equação linear · função `y = ax + b`

*Amanhã (A06 - 13/03): Banco de Dados entra em cena - primeiro contato com SQL.*
