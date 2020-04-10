# Aula 04

Vamos relembrar o que foi visto na quarta aula online e vamos dar alguns passinhos a mais até a próxima aula ;) No final do texto, você encontra alguns exercícios para praticar.

### while

Aprendemos a utilizar o while para fazer repetições. 

Vimos que podemos escrever uma repetição de comandos de uma maneira mais automatizada. Então, o problema de imprimir os números de 0 até 5 sem usar o *print()* cinco vezes pode ser resolvido da seguinte maneira:

```python
x = 0
while x <= 5: 
    print(x) 
    x = x + 1 
```

Onde *x = 0* é nosso **contador** que será incrementado dentro do *while*.

Enquanto a condição *x <= 5* for verdadeira, o programa continuará executando as linhas dentro do *while* (atenção para a indentação!).

Em um dado momento, o valor de x será 6. Sendo assim, a condição *x <= 5* deixa de ser verdadeira e o programa se encerra.

Se quisermos ampliar a resolução deste problema para "imprimir os números de 0 até ___", podemos pedir que o usuário digite um valor que será o nosso limite máximo:

```python
max_number = int(input("Imprimir os números de 0 até: \n"))
print("\n")
x = 0

while x <= max_number: 
    print(x) 
    x = x + 1

print("Fim")
```
A variável *max_number* entra no lugar do 5 deixando a resolução genérica. 

Aqui, temos a linha *print("Fim")* para nos lembrar que ela só será impressa na tela quando todas as iterações dentro do *while* acabarem. 

E quando isso ocorre?

Da mesma maneira que no primeiro exemplo, a variável **x** é o **contador**. 

Isso significa que ela nos ajudará a controlar o fluxo do programa. A cada iteração, ela será incrementada e, em um dado momento, a condição *x <= max_number* deixará de ser verdadeira. 

Neste momento, as iterações dentro do *while* terminam e a linha *print("Fim")* é executada.

**Aninhando outros blocos de código dentro do while**

Também vimos que podemos colocar outros blocos de código dentro do *while* como, por exemplo, o *if*.

No exemplo a seguinte, queremos mostrar na tela somente os números pares de 0 até um determinado número.

```python
max_number = int(input("Mostrar na tela os números pares de 0 até: \n"))
print("\n")
counter = 0

while counter <= max_number:
    if counter % 2 == 0:
        print(counter)
    counter += 1

print("\nPronto!")
```
Vamos entender o código passo-a-passo:

1. Primeiro eu peço para o usuário digitar o valor que limitará a execução do programa. Se ele digitar *9*, por exemplo, o programa deverá exibir na tela os números 0, 2, 4, 6 e 8.
2. A variável **counter** (nosso contador) inicia com o valor 0, afinal, queremos imprimir o zero! Dentro do *while* ela será incrementada até que a condição *counter <= max_number* seja falsa.
3. Dentro do *while* temos um *if* que verifica se a divisão de  *counter* por 2 tem resto zero. (Lembram da operação com **%**?) Se o resto é zero, significa que o número é par; caso contrário, é ímpar.
4. Note que a variável **counter** sempre será incrementada dentro do *while*, independentemente do que ocorre no *if*. 
5. Quando a condição *counter <= max_number* se tornar falsa, a linha *print("\nPronto!")* será executada.

Colocando a execução do código em uma tabela, temos o seguinte:

| Iteração | counter | counter <= max_number |  counter % 2 == 0 | print(counter) | counter += 1 |
|:--------:|:-------:|:---------------------:|:-----------------:|:--------------:|:------------:|
|    1a.   |    0    | 0 <= 6: True          | 0 % 2 == 0: True  |        0       |       1      |
|    2a.   |    1    | 1 <= 6: True          | 1 % 2 == 0: False |        -       |       2      |
|    3a.   |    2    | 2 <= 6: True          | 2 % 2 == 0: True  |        2       |       3      |
|    4a.   |    3    | 3 <= 6: True          | 3 % 2 == 0: False |        -       |       4      |
|    5a.   |    4    | 4 <= 6: True          | 4 % 2 == 0: True  |        4       |       5      |
|    6a.   |    5    | 5 <= 6: True          | 5 % 2 == 0: False |        -       |       6      |
|    7a.   |    6    | 6 <= 6: True          | 6 % 2 == 0: True  |        6       |       7      |
|    8a.   |    7    | 7 <= 6: False         |                   |                |              |

A 1a. iteração é a primeira vez que a execução do programa "bate" na linha do *while* e como *0 <= 6* é True, passará para a linha que tem o *if*.

A 8a. iteração é a última vez que a execução do programa "bate" na linha do *while* pois *7 <= 6* é False, portanto, a próxima linha a ser executada é *print("\nPronto!")*.

**Utilizando uma variável como acumulador**

Vimos também a situação de queremos somar 10 números distintos e exibir o valor da soma na tela.

```python
counter = 1        
total_sum = 0     

while counter <= 10:
    number = int(input("Digite o %do. número: " % counter)) 
    total_sum = total_sum + number
    counter += 1

print("Soma: %d" % total_sum)
```

A variável *total_sum* é o nosso acumulador porque ela irá guardar o total da soma. A cada iteração no *while* ela receberá o valor dela mesma acrescido do número digitado.

Quando estamos acumulando valores somados, inicializamos nosso acumulador com 0. Caso o acúmulo seja feito através de uma multiplicação, inicializamos a variável com o valor 1.

O valor total da soma é exibido **fora** do *while*, **depois** que as iterações terminaram. 

**Repetição indefinida e o comando *break***

Até agora, vimos exemplos nos quais nós determinados a condição do *while*. 

Existe a possibilidade de termos o *while* combinado com True, isso fará com que a repetição ocorra indefinidamente até que **algo ocorra**. 

Vejamos o exemplo a seguir:

```python
total_sum = 0

while True:
    number = int(input("Digite um número inteiro para somar ou digite 0 para encerrar a soma: ")) 
    if number == 0:
        break 
    total_sum += number

print(total_sum)
```

Não há uma condição a ser verificada no *while*, apenas o True. 

Neste programa, o usuário deverá digitar um número inteiro para ser somado ou digitar 0 para encerrar a soma. Se ele digitar números inteiros diferentes de zero indefinidamente, a soma continuará ocorrendo.

Temos um *if* dentro do *while* que verifica se o número digitado é 0 e, caso seja isso mesmo, temos o comando **break** ali. 

Esse comando faz com que a execução do programa prossiga para fora do *while*. Ou seja: se o usuário digitar o número 0, a próxima linha a ser executada é a linha *print(total_sum)*.

Outro ponto imporante: assim como vimos que *counter = counter + 1* também pode ser escrito como *counter += 1*, temos aqui a linha *total_sum += number* que significa exatamente *total_sum = total_sum + number*.

**Decréscimo de valores no contador**

Até o momento, vimos os contadores recebendo acréscimos. Podemos ter contadores que fazem decréscimos!

Vejamos o exemplo:

```python
start = int(input("Digite o início da contagem regressiva: \n"))

print("\n")

while 0 <= start:
    print(start)
    start -= 1

print("\n")
print("Fogo! 🚀")
```

Este código faz uma contagem regressiva a partir do início estipulado pelo usuário. Veja que o valor inicial da contagem regressiva - a variável **start** - é o próprio contador.

Dentro do *while*, a variável **start** sofre um decréscimo de 1. Temos ali *start -= 1* que é análogo a *start = start - 1*.

### Extras

Para aumentar um pouquinho o repertório de métodos de strings, vou deixar alguns novos aqui para que vocês utilizem nos exercícios ;)

**upper()**

Transforma todas as letras em maiúsculas.

```python
message = "Fica em casa!"
message_uppercase = message.upper()
print(message_uppercase)    # mostra na tela: FICA EM CASA!
```

**lower()**

Transforma todas as letras em minúsculas.

```python
message = "HAHAHAHAHAHAHAHA"
message_lowercase = message.lower()
print(message_lowercase)    # mostra na tela: hahahahahahahaha
```

**count()**

Conta o número de vezes que um determinado texto aparece na string.

```python
email = "usuario@provedor.com.br"
at_sign = email.count("@")
print(at_sign)
```

Esses métodos podem ser úteis de diversas formas, por exemplo, em um programa que o usuário precise escolher a opção A ou B. Ao pegar o input do usuário, você pode converter com o método *upper()* e só depois verificar se foi A ou B que ele digitou. 

O método *count()* pode ser útil para descobrir, como no exemplo mostrado, se o usuário digitou o e-mail mais próximo do valor válido, ou seja, com apenas uma @. 

## Exercícios

1. Escreva um programa que mostre na tela números inteiros de 0 até um valor escolhido pelo usuário. Porém, quando o número for múltiplo de 5, deverá mostrar um X no lugar.

2. Escreva um programa que mostre todas as tabuadas de 1 até 10. O programa não receberá dados do usuário. Quando for executado, deverá mostrar na tela:

Tabuada do 1:

1 x 0 = 0

1 x 1 = 1

...

Tabuada do 10:

10 x 0 = 0

10 x 1 = 10

...

10 x 10 = 100

---

**Desafio:** Escreva um programa que fornecerá a nota de um usuário com base nas respostas que ele dará para 5 questões. Cada questão terá somente duas alternativas: A ou B. O gabarito das questões é o seguinte: 1-A, 2-B, 3-B, 4-A e 5-B. O usuário deverá digitar o nome e depois a resposta para cada questão. No final, você deverá exibir o nome do usuário, o total de questões que ele acertou e a nota final sabendo que cada questão vale 2 pontos.