# Aula 04

Vamos relembrar o que foi visto na aula quarta online e vamos dar alguns passinhos a mais até a próxima aula ;) No final do texto, você encontra alguns exercícios para praticar.

### while

Aprendemos a utilizar o while para fazer repetições. 

Vimos que podemos escrever uma repetição de comandos de uma maneira mais automatizada. Então, o problema de imprimir os números de 0 até 5 sem usar o *print()* pode ser resolvido da seguinte maneira:

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
4. Note que a variável **counter** sempre será incrementada, independentemente do que ocorre no *if*. 
5. Quando a condição *counter <= max_number* se tornar falsa, a linha *print("\nPronto!")* será executada.

Colocando a execução do código em uma tabela, temos:

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

Através da tabela, podemos ver que somente na 8a. iteração é que o *counter* atinge um valor que torna a condição *counter <= max_number* falsa. Isso faz com que o programa "saia" do *while*.

## Exercícios

---

**Desafio:**