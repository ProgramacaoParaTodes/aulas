# Aula 02

Vamos relembrar o que foi visto na segunda aula online e vamos dar alguns passinhos a mais até a próxima aula ;) No final do texto, você encontra alguns exercícios para praticar.

### Variáveis

Aprendemos que uma variável é um espaço alocado na memória do computador contendo uma informação que será utilizada e/ou alterada durante a execução do programa.

### Regras de nomenclatura de variáveis no Python

Não podemos dar qualquer nome às variáveis, precisamos seguir algumas regrinhas:

- O nome pode ser formado por letras, números e underscore (_).
- O nome NÃO pode começar com números.
- O nome pode começar com underscore.
- Não são aceitos caracteres especiais, somente o underscore.
- Não pode ter espaços em branco.

**Importante:** você pode acentuar o nome da variável, mas não é algo recomendável por causa do encoding de cada computador. Prefira nomes sem acentuação :)

Veja alguns exemplos:

```python
# Pode:
name = "Ada Lovelace"
year = 2020
_name = "Ada Lovelace"
_year = 2020
n_a_m_e = "Turing"
y_e_a_r = 2020

# Poder, pode... Mas é bom evitar:
aniversário = "04-05"
datadenascimento = "04-05-1983"
v1d4l0k4 = True

# É melhor escrever sem acentos:
aniversario = "04-05"

# Nomes grandes? Vamos de snake_case:
data_de_nascimento = "04-05-1983"

# Pode ser v1d4 l0k4, mas seja legível ;)
vida_loka = True

# NÃO pode:
%aniversario = "04-05"
4ge = 36
```

### Tipos de Variáveis do Python

Vamos relembrar os tipos de variáveis do Python:

```python
# variável numérica do tipo inteiro (int)
age = 36
temperature = -5

# variável numérica do tipo ponto flutuante (float)
price = 125.50
balance = -1.50

# variável do tipo lógico (bool)
at_home = True
sleeping = False 

# variável do tipo texto (string)
email = "user@provider.com"
message = "Fica em casa, tá?"

# variável complexa (complex)
a = 4 + 3j
```

### Entrada de dados

Revisamos rapidinho as entradas de dados que vimos na aula 01:

```python
# entrada de texto, maneira 1
print("Digite seu nome: ")
name = input()

# entrada de texto, maneira 2
name = input("Digite seu nome: ")

# entrada de número inteiro, maneira 1
print("Digite sua idade: ")
age = int(input())

# entrada de número inteiro, maneira 2
age = int(input("Digite sua idade: "))

# entrada de ponto flutuante, maneira 1
print("Digite a nota do aluno: ")
grade = float(input())

# entrada de ponto flutuante, maneira 2
grade = float(input("Digite a nota do aluno: "))
```

### Operadores relacionais e operadores lógicos

Para podermos estudar estruturas condicionais para **tomada de decisão**, precisamos aprender os operadores relacionais e os operadores lógicos.

### Operadores relacionais

São aqueles famosos operadores que nós já conhecemos da matemática e que vamos utilizar para **comparar** valores.

**Atenção:** O resultado de uma comparação de valores é sempre **True** ou **False**.

| Operador |    Operação    | Símbolo matemático |
|:--------:|:--------------:|:------------------:|
|    ==    |    igualdade   |          =         |
|     >    |    maior que   |          >         |
|     <    |    menor que   |          <         |
|    !=    |    diferente   |          ≠         |
|    >=    | maior ou igual |          ≥         |
|    <=    | menor ou igual |          ≤         |

**Atenção:** Não confundir o operador **==** com o símbolo de atribuição **=**! 

Por exemplo, **3 == 4** significa que estamos **comparando** os números 3 e 4 (o resultado, neste caso, é False). 

E se fizermos **a = 3** e **b = 4** significa que estamos *atribuindo os valores* 3 e 4 às variáveis a e b respectivamente.

### Operadores lógicos

Quando fazemos comparações, podemos querer colocar mais condições. Para isso, utilizamos operadores lógicos.

| Operador Python | Operação |
|:---------------:|:--------:|
|       not       |    não   |
|       and       |     e    |
|        or       |    ou    |

Basicamente, o operador **not** é a **negação** de algo, o operador **and** é a **conjunção** e o operador **or** é a **disjunção**. Vamos ver isso em exemplos:

**not:** inverte o valor.

| Valor | not Valor |
|:-----:|:---------:|
|  True |   False   |
| False |    True   |

Você pode testar isso no interpretador:

```python
print(not True)     # imprime False
print(not False)    # imprime True
```

**and:** basta que um valor seja False para que as combinações de valores sejam False.

| Valor 1 | Valor 2 | Valor 1 and Valor 2 |
|:-------:|:-------:|:-------------------:|
|   True  |   True  |         True        |
|   True  |  False  |        False        |
|  False  |   True  |        False        |
|  False  |  False  |        False        |

Você pode testar isso no interpretador:

```python
print(True and True)    # imprime True
print(True and False)   # imprime False
print(False and True)   # imprime False
print(False and False)  # imprime False
```

**or:** basta que um dos valores seja True para que as combinações de valores sejam True.

| Valor 1 | Valor 2 | Valor 1 or Valor 2 |
|:-------:|:-------:|:------------------:|
|   True  |   True  |        True        |
|   True  |  False  |        True        |
|  False  |   True  |        True        |
|  False  |  False  |        False       |

```python
print(True or True)    # imprime True
print(True or False)   # imprime True
print(False or True)   # imprime True
print(False or False)  # imprime False
```

### Condições

Na aula, vimos a estrutura condicional *if* acompanhada do *else*. Basicamente, quando precisamos avaliar uma condição para tomar uma decisão, utilizaremos essa estrutura.

Em português, temos algo do tipo:

    SE A CONDIÇÃO TESTADA FOR VERDADEIRA:
        FAÇA X
    CASO CONTRÁRIO:
        FAÇA Y

Em Python, teremos algo assim:

```python
age = int(input("Digite sua idade: \n"))

if age >= 18:
  print("Maior de idade")
else: 
  print("Menor de idade") 
```

**Obs.:** O \n pula linha ;)

Fazemos a leitura da idade que será salva na variável *age* e em seguida fazemos a verificação da condição.

Aqui temos duas possibilidades ao avaliar a idade: ou a pessoa é maior de idade ou a pessoa é menor de idade, não existe uma terceira possibilidade.

Por isso, aqui a condição *if* acompanhada de *else* se encaixa perfeitamente.

Se a condição *age >= 18* é verdadeira, o bloco de código executado é o imediatamente abaixo do *if* (atenção para a indentação). 

Se a condição *age >= 18* é falsa, o bloco de código executado é o imediatamente abaixo do *else*.

**Atenção:** A indentação no Python é obrigatória e ajuda a limitar os blocos de código!

**Observação:** Existem situações que vamos utilizar somente o *if*. Por exemplo, quando um perfil é do tipo "Verificado" em alguma rede social como Instagram ou Twitter. Possivelmente, em algum lugar do código, existe uma verificação de algum atributo que indica se aquele perfil é verificado e isso não requer nenhum tipo de ação que se encaixaria no "caso contrário". O perfil verificado ganha um ícone específico enquanto o perfil não verificado permanece o mesmo. Então é como se houvesse uma variável lá dentro do código *verified_profile* que, tendo o valor True dentro dela faz com que seja exibido um ícone diferente para aquele usuário.

Existem casos em que temos mais de duas possibilidades na tomada de decisão. Vamos ver o exemplo a seguir.

Em português, podemos ter uma situação assim:

    SE A CONDIÇÃO 1 TESTADA FOR VERDADEIRA:
        FAÇA X
    CASO CONTRÁRIO, SE A CONDIÇÃO 2 FOR VERDADEIRA:
        FAÇA Y
    CASO CONTRÁRIO:
        FAÇA Z

Vamos traduzir isso para o Python com o exemplo a seguir:

```python
promo_code = int(input("Digite o código para saber o desconto: "))

if promo_code == 1:
    print("Desconto de 20%")
elif promo_code == 2: 
    print("Desconto de 35%")
else: 
    print("Desconto de 10%")
```

A primeira condição é promo_code ser igual a 1. Se o usuário digitar o número 2, esse teste falhará e a próxima condição a ser testada é promo_code ser igual a 2. 

A cada nova condição que desejamos testar, acrescentamos *elif* seguido da condição e, por fim, o *else*. Veja como o mesmo exemplo fica com mais condições:

```python
promo_code = int(input("Digite o código para saber o desconto: \n"))

if promo_code == 1:
    print("Desconto de 20%")
elif promo_code == 2: 
    print("Desconto de 35%")
elif promo_code == 3: 
    print("Desconto de 40%")
elif promo_code == 4:
    print("Desconto de 50%")
else: 
    print("Não há desconto para esse código.")
```

Em tomadas de decisão dentro do código, é importante pensarmos bem nas opções e também colocarmos alguma ação no *else* para contemplar casos que fujam das opções possíveis.

**Uma observação importante sobre *elif* e os operadores lógicos:** Podemos ter avaliações combinadas no *elif* com o *and* e com o *or*, sendo assim, precisamos escrever da seguinte maneira (veja o último *elif*):

```python
promo_code = int(input("Digite o código para saber o desconto: \n"))

if promo_code == 1:
    print("Desconto de 20%")
elif promo_code == 2: 
    print("Desconto de 35%")
elif promo_code == 3: 
    print("Desconto de 40%")
elif promo_code == 4 or promo_code == 19:
    print("Desconto de 50%")
else: 
    print("Não há desconto para esse código.")
```

### Melhorando nossa saída de dados

Vamos avançar um pouquinho mais? Nos exercícios e no desafio da primeira aula, não precisamos nos preocupar com a melhor maneira de mostrar uma informação na tela. Mas agora vamos aprender a fazer isso de uma forma mais correta e mais assertiva.

Antes de refazermos um dos exercícios da aula anterior, vamos conhecer os marcadores que podemos utilizar para compor uma string, ou seja, para compor um texto que será exibido na tela.

| Marcador |       Tipo       |
|:--------:|:----------------:|
|    %d    | Números inteiros |
|    %s    |      Strings     |
|    %f    | Números decimais |

Na aula anterior, tínhamos o seguinte exercício: 

*Escreva um programa que pergunte ao usuário o nome e a idade, em seguida, escreva " _ _ _ _ tem _ _ anos" onde o primeiro espaço deverá trazer o nome e o segundo espaço a idade.*

Com a utilização de marcadores, a resolução fica assim:

```python
name = input("Digite seu nome: ")
age = int(input("Digite sua idade: "))
print("%s tem %d anos" % (name, age))
```

Estamos mostrando uma string na tela composta por uma variável (string) + texto + outra variável (inteiro) + texto. Essas variáveis estão representadas no comando *print* pelos marcadores *%s* e *%d* e que correspondem **respectivamente** às variáveis *name* e *age*. Precisamos colocar o *%* depois da string completa e, em seguida, precisamos colocar as variáveis depois dele. No exemplo, temos dois marcadores e duas variáveis, então foi necessário colocá-las entre parênteses: *(name, age)*. Se for apenas um marcador e uma variável, não é necessário colocar entre parênteses. 

Também podemos utilizar o marcador *%f* para formatar a exibição das casas decimais de um float. Veja no exemplo a seguir:

```python
grade1 = 7.75
grade2 = 8.0
grade3 = 6.35

average = (grade1 + grade2 + grade3)/3

print("Média SEM formatação de casas decimais: %f" % average)   # mostra 7.366667
print("Média COM formatação de casas decimais: %.2f" % average) # mostra 7.37
```

Veja que ao mostrar a média com a formatação de casas decimais, mudamos o marcador *%f* para *%.2f*. Isso quer dizer que estamos pedindo que o Python exiba somente duas casas decimais.

## Exercícios

1. Escreva um programa que peça o valor de uma compra e informe em quantas parcelas ela pode ser paga seguindo os critérios:
- Até R$ 150,00 em 2x;
- Entre R$ 151,00 e 500,00 em 3x;
- Entre R$ 501,00 e 950,00 em 4x;
- Acima de R$ 950,00 em 5x.

O programa deve imprimir a quantidade das parcelas e o valor: "Você pode pagar sua compra de R$ ______ em ___ parcelas de R$ _____" e o valor das parcelas deverá ter duas casas decimais.

2. Escreva um programa que o usuário digitará a quantidade de minutos decorridos desde o início de uma partida de futebol e informe se o jogo está no primeiro tempo (até 45 minutos), no segundo tempo (até 90 minutos) ou se o juiz já deveria ter apitado o final (além de 90 minutos).

3. Escreva um programa que pergunte a quantidade de km percorridos por um carro alugado pelo usuário, assim como a quantidade de dias pelos quais o carro foi alugado. Calcule o preço a pagar, sabendo que o carro custa R$ 65,00 por dia e R$ 0,35 por km rodado. Imprima na tela: "O valor a pagar pelo aluguel do carro é de R$ ______" com duas casas decimais.

4. Escreva um programa que leia três números inteiros e imprima qual deles é o maior e qual deles é o menor.

5. Escreva um programa que pergunte o salário do funcionário e quantos anos ele trabalha na empresa. Se o funcionário estiver na empresa há mais de 3 anos e se ganhar menos de R$ 2.500,00, aplicar um aumento de 15%, caso contrário, aplicar um aumento de 8%. Em seguida, mostrar o novo valor do salário na tela escrevendo "O novo salário é de R$ _____" com duas casas decimais.

6. Escreva um programa que leia dois números decimais e que pergunte qual operação você deseja realizar. Você deve poder calcular a soma (+), subtração (-), multiplicação (*) e divisão (/). Atenção: Não permitir divisão por zero! Exiba o resultado da operação solicitada sem formatação de casas decimais.

---

**Desafio:** Escreva um programa para aprovar o empréstimo bancário para compra de uma casa. O programa deve perguntar o valor da casa a comprar, o salário e a quantidade de anos a pagar. O valor da prestação mensal não pode ser superior a 30% do salário. Calcule o valor da prestação como sendo o valor da casa a comprar dividido pelo número de meses a pagar.
