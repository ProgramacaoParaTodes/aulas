# Aula 01

Vamos relembrar o que foi visto na primeira aula online e dar alguns passinhos a mais até a próxima aula ;) No final do texto, você encontra alguns exercícios para praticar. 

## Repl.it

Para que não tenhamos que instalar nada num primeiro momento, utilizamos a interface do [Repl.it](https://repl.it/).

Basta acessar o site, clicar em **+ new repl** e escolher Python.

Essa é a maneira mais rápida de utilizar, porém, é legal criar uma conta para que você possa guardar os arquivos que fizer e também para que você possa compartilhar comigo os exercícios feitos.

## Comandos aprendidos

### print()

A função print() escreve um texto na tela.

```python
print("Hello World")
```

O resultado será:

```python
Hello World
```

### input()

Aprendemos que a função input() capta o que o usuário digita.

```python
print("Digite seu nome: ")
name = input()
print("Olá, " + name)
```
O resultado será:

```
Digite seu nome:
|
```

Quando o usuário digita o nome (ex.: Fulano) e depois pressiona a tecla Enter, teremos:

```
Olá, Fulano
```

Vamos avançar um pouco mais? :) Temos uma outra maneira mais enxuta de utilizar o mesmo comando:

```python
name = input("Digite seu nome: ")
```

E também podemos fazer a leitura de um número inteiro (int) através do comando:

```python
age = int(input("Digite sua idade: "))
```

Também funciona escrever assim:
```python
print("Digite sua idade: ")
age = int(input())
```

Podemos fazer a leitura de um número decimal (float):

```python
grade = float(input("Digite a nota do aluno: "))
```

Também funciona escrever assim:
```python
print("Digite a nota do aluno: ")
grade = float(input())
```

**Atenção:** No Repl.it o decimal deve ser digitado com ponto e não vírgula! Por exemplo: 4.5 e não 4,5.

### Combinando print() e input()

Vamos avançar um pouquinho mais? ;)

Quero perguntar ao usuário quanto ele pagou de conta de luz e, em seguida, quero escrever: "O usuário pagou R$ .... de conta de luz". Como posso fazer isso?

```python
print("Quando você pagou de conta de luz? ")
value = float(input())
print("O usuário pagou R$", value, "de conta de luz")
```
Talvez você esteja se perguntando porque a maneira de fazer o **print** aqui mudou em relação ao exemplo lá de cima:

```python
print("Digite seu nome: ")
name = input()
print("Olá, " + name)
```

É que neste exemplo do nome, estamos unindo texto com texto, ou seja, estamos concatenando strings: "Digite seu nome: " com o conteúdo digitado pelo usuário "Fulano".

Quando fazemos o exemplo da conta de luz, estamos escrevendo na tela textos e um número, que é o valor da conta de luz. Por esse motivo, não podemos simplesmente unir tudo, então fazemos o print dessa maneira: um texto *vírgula* uma variável *vírgula* outro texto.


### Comandos matemáticos

Vimos rapidamente que o Python faz contas. Então deixarei aqui uma listinha de comandos matemáticos para você utilizar:

```python
a = 5
b = 6

# soma
print(a + b) 

# subtração
print(a - b)
print(b - a) 

# multiplicação
print(a * b) 

# divisão
print(a / b)

# potenciação
# a elevado a b
print(a ** b)
# b elevado a a
print(b ** a)

# resto da divisão inteira
# 6 dividido por 5 dá resto 1
print(b % a)
```

**O que acontece se você dividir algum número por zero? Experimente fazer isso no interpretador! ;)**

Você também pode utilizar parênteses para mudar a precedência das operações, por exemplo:

```python
(5 + 6) * 4
```

É diferente de:
```python
5 + 6 * 4
```


## Exercícios

1. Escreva um programa que exiba o resultado de 7a x 5b, onde a vale -2 e b vale 4.

2. Escreva um programa que pergunte ao usuário o nome e a idade, em seguida, escreva **" _ _ _ _ tem _ _ anos"** onde o primeiro espaço deverá trazer o nome e o segundo espaço a idade.

---

**Desafio:** Escreva um programa que calcule o valor de uma compra numa papelaria que possui somente três itens: lápis a R$ 2.75 cada, borrachas a R$ 1.82 cada e resmas de papel a R$ 19.95 cada. O usuário deverá ser perguntado sobre a quantidade de cada item e, no final, deverá receber uma mensagem na tela informando quantos itens comprou (X lápis, Y borrachas, Z resmas) e o valor final da compra.
