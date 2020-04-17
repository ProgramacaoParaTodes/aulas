# Aula 07

Vamos relembrar o que foi visto na sétima aula online ;) No final do texto, você encontra alguns exercícios para praticar.

## Funções

Na última aula, aprendemos que podemos encapsular um bloco de código de modo que possamos reaproveitá-lo em outras partes do programa. Fazemos isso criando **funções**.

**Criando uma função**

Primeiro precisamos *declarar* a função. Colocamos as funções no início do nosso código porque, quando precisarmos utilizá-las, elas já estarão declaradas e **acessíveis**. 

```python
def nome_da_funcao():
    # tudo o que a 
    # função vai fazer
```

Toda função começa com a palavra reservada **def** seguida do **nome** que ela terá e **parênteses**.

Então, se quisermos declarar uma função que o único objetivo é mostrar "Bom dia!" na tela do interpretador, podemos fazer da seguinte maneira:

```python
def diga_bom_dia():
    print("Bom dia!")
```

Quando quisermos utilizar essa função, ou seja, quando quisermos **chamar a função**, basta escrever:

```python
diga_bom_dia()
```
**Atenção:** Parênteses vazios na declaração da função significa que ela não recebe argumentos.

**Funções com argumentos**

Vejamos o código a seguir:

```python
def validar(email):
  achou_arroba = False
  achou_ponto = False
  
  for letra in email:
    if letra == "@":
      achou_arroba = True
    if letra == ".":
      achou_ponto = True

  if achou_arroba == True and achou_ponto == True:
    print("E-mail válido")
  else:
    print("E-mail inválido")

validar("programacaoparatodes@gmail.com")

validar("emailerrado@blabla")
```

Temos uma função chamada *validar*. Repare que aqui o nome da função é seguido de parênteses e, dentro deles, temos a palavra *email*.

Isso significa que essa função possui um **argumento** que deverá ser **passado** quando ela for **chamada**.

Em outras palavras, quando quisermos utilizar essa função, não podemos simplesmente chamá-la escrevendo *validar()* porque ela **espera** que um argumento seja passado. Se chamarmos a função sem o argumento que ela espera, o código quebra! :(

Quando chamamos a função, colocamos entre parênteses o valor que deverá *ocupar* o lugar do argumento. 

Veja que utilizamos a função duas vezes nesse exemplo. 

Na 1a. utilização, chamamos a função *validar* passando a string *programacaoparatodes@gmail.com* como argumento. 

O resultado esperado é que apareça na tela a frase "E-mail válido".

Na 2a. utilização, chamado a função *validar* passando a string *emailerrado@blabla* como argumento. 

O resultado esperado é que apareça na tela a frase "E-mail inválido".

Mas como isso aconteceu?

Quando chamamos a função e passamos um valor dentro dos parênteses, esse valor assume o lugar do argumento. Na declaração da função, o "nome" do argumento é *email*. 

Quando chamamos a função pela 1a. vez nesse código, o argumento *email* lá da declaração da função é substituido por "programacaoparatodes@gmail.com". 

Em outras palavras, quando a linha *validar("programacaoparatodes@gmail.com")* é executada, **dentro da função**, em todos os pontos onde pudermos ler *email*, é como se estivessemos lendo "programacaoparatodes@gmail.com". 

Vamos utilizar um exemplo mais enfático para perceber como isso funciona:

```python
def teste(banana):
  print("Vou imprimir o argumento aqui ó: %s" % banana)

teste("Meu argumento :)")
```

O resultado desse código meio nonsense é mostrar na tela "Vou imprimir o argumento aqui ó: Meu argumento :)".

Se o meu argumento é *banana*, todas as vezes que *banana* aparecer dentro do código da função significa que estou fazendo referência ao argumento. 

**Atenção:** Em funções com dois ou mais argumentos, devemos passá-los na mesma ordem em que foram colocados na definição da função. 

**Retornando valores**

Uma função pode simplesmente executar alguns comandos ou pode, além de executar comandos, **retornar um valor**.

Os exemplos vistos até agora são de funções que **não** retornam valores.

Vejamos o exemplo a seguir:

```python
def gerar_senha(nome, nascimento):
  parte1 = nome[0:3]
  parte2 = nascimento[6:10]
  return parte1 + parte2

senha = gerar_senha("Erika", "04/05/1983")

print(senha)      # mostra Eri1983
```

Analisando o código, temos uma novidade na função: a palavra **return**.

O objetivo dessa palavra no código da função é enviar "para fora" o valor que está à sua direita.

No caso do exemplo, a função **gerar_senha** recebe 2 argumentos (nome e nascimento no formato dd/mm/aaaa). 

Dentro da função, a variável *parte1* recebe as três primeiras letras do nome e a variável *parte2* recebe o ano de nascimento. 

Na última linha da função, temos o *return* seguido da concatenação das strings *parte1* e *parte2*. Ou seja, a função **retorna** uma string unindo essas duas informações.

Esse **retorno da função** é automaticamente salvo na variável *senha*.

Então, quando utilizamos a linha *print(senha)* é executada, ela mostra *Eri1983*.

***Variável local x variável global***

Você deve ter reparado no código acima que dentro da função temos duas variáveis: *parte1* e *parte2*. Elas são **variáveis locais** porque existem somente **dentro** da função e **não podem** ser acessadas do lado de fora.

Depois que a última linha da função é executada, ou seja, quando ocorre o *return parte1 + parte2*, o valor dessa concatenação de strings é salvo na variável *senha* e as variáveis *parte1* e *parte2* "cumpriram seu papel".

Se tentarmos acessar essas variáveis, por exemplo, fazendo *print(parte1)* e/ou *print(parte2)* **fora** da função, o código quebra!

Já a variável *senha* pode ser acessada de qualquer ponto do código. Isso faz com que ela seja uma variável global.

Veja mais um exemplo para fixar o conceito:

```python
def adicao(x, y):
  soma = x + y
  print("Soma dentro da função: %d" % soma) # Soma dentro da função: 9
  return soma

resultado = adicao(4, 5)

print("Resultado: %d" % resultado)          # mostra Resultado: 9
print("Soma fora da função: %d" % soma)     # quebra
```

Aqui temos uma função **adicao** que recebe dois argumentos, que são os números que serão somados dentro dela. 

Ela também tem um retorno, ou seja, como atribuímos a função à variável *resultado*, ela retornará o valor da soma justamente para essa variável.

Note que dentro da função há uma variável chamada *soma*. Ela recebe *x + y* e depois é retornada na última linha de execução da função.

Dentro da função podemos utilizar essa variável tranquilamente para fazer o print que mostra na tela a informação *Soma dentro da função: 9*.

Do lado de fora da função, podemos utilizar o print para verificar o valor da variável *resultado*. Isso mostrará na tela *Resultado: 9*.

Porém, também do lado de fora da função, quando tentamos utilizar o print com a variável *soma*, **não** teremos sucesso. O código quebra! 

**Atenção:** Precisamos ter muito cuidado na utilização das variáveis. Não tente acessar variáveis locais fora da função! 

**Funções com atributos opcionais**

Até o momento, vimos duas possíveis situações para as funções: elas não terem argumentos e elas terem argumentos obrigatórios.

Existe a possibilidade de termos argumentos opcionais em uma função. Vejamos o exemplo a seguir:

```python
def cadastrar_contato(telefone, ddd="21"):
  completo = "(" + ddd + ") " + telefone
  return completo

tel_RJ = cadastrar_contato("99999-1234")
print(tel_RJ)

tel_SP = cadastrar_contato("99999-5678", "11")
print(tel_SP)
```

Temos uma função que recebe dois argumentos: *telefone* e *ddd*. Logo na definição da função, percebemos algo diferente: o argumento ddd já está com um valor.

Isso quer dizer que, ao chamarmos a função, se **não** passarmos um valor para *ddd*, ele vai assumir o valor que está pré-definido ali. Mas, se passarmos um valor para *ddd*, então será utilizado o valor que passarmos.

A variável *tel_RJ* recebe o retorno da função *cadastrar_contato("99999-1234")*. Não foi passado um valor para o *ddd*. Quando a linha *print(tel_RJ)* é executada, o valor *(21) 99999-1234* é mostrado.

Já a variável *tel_SP* recebe o retorno da função *tel_SP = cadastrar_contato("99999-5678", "11")*. Aqui está sendo passado o valor "11" para o *ddd*, então quando a linha *print(tel_SP)* é executada, o valor *(11) 99999-5678* é mostrado.

**Atenção:** Os argumentos obrigatórios devem vir primeiro na declaração da função.

## Tuplas

## Exercícios

1. 

2. 

---

**Desafio:** 