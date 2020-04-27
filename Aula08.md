# Aula 08

Vamos relembrar o que foi visto na oitava aula online ;) No final do texto, você encontra alguns exercícios para praticar.

## Dicionários

Até aqui, vimos listas e tuplas, que são conjuntos ordenados de valores que nós podemos acessar através de seus índices. 

```python
series = ["Grey's Anatomy", "The Good Place", "The Walking Dead", "Breaking Bad"]

print(series[0])    # mostra Grey's Anatomy pois acessamos o índice 0

print(series[2])    # mostra The Walking Dead pois acessamos o índice 2
```
Tanto para listas quanto para tuplas, temos o índice como maneira de acessar os valores. 

Vamos comparar as três estruturas:

```python
lista = ["Valor 1", "Valor 2", "Valor 3"]

print(lista)      # mostra ['Valor 1', 'Valor 2', 'Valor 3']

tupla = ("Valor 1", "Valor 2", "Valor 3")

print(tupla)      # mostra ('Valor 1', 'Valor 2', 'Valor 3')

dicionario = { 
  "chave1": "Valor 1",
  "chave2": "Valor 2",
  "chave3": "Valor 3"
}

print(dicionario) # mostra {'chave1': 'Valor 1', 'chave2': 'Valor 2', 'chave3': 'Valor 3'}
```

Veja que listas são definidas com colchetes [ ], tuplas com parenteses ( ) e dicionários com chaves { }.

Agora podemos prosseguir falando dos dicionários :)

Um dicionário é uma coleção de dados com **chave e valor**. O que isso significa?

Significa que cada valor dentro do dicionário está atrelado a uma chave e não a um índice.

Veja o exemplo:

```python
estudante = { 
    "nome": "Fulana de Tal",
    "email": "fulana@gmail.com",
    "curso": "Ciência da Computação",
    "periodo": 4,
    "cr": 9.5
}
```

Aqui temos um dicionário com 5 chaves e 5 valores correspondentes.

Para a chave "nome" temos o valor "Fulana de Tal", para a chave "email" temos o valor "fulana@gmail.com" e assim sucessivamente.

Então, como podemos acessar esses valores? Através das chaves! 

Veja:

```python
estudante = { 
    "nome": "Fulana de Tal",
    "email": "fulana@gmail.com",
    "curso": "Ciência da Computação",
    "periodo": 4,
    "cr": 9.5
}

print(estudante["nome"])       # mostra Fulana de Tal pois acessamos o valor da chave nome

print(estudante["periodo"])    # mostra 4 pois acessamos o valor da chave periodo
```

**Quais valores podem ser salvos no dicionário?**

Veja o dicionário do exemplo a seguir:

```python
produto = { 
  "nome": "Maionese",
  "marca": "Heinz",
  "estoque": 4200,
  "geladeira": False,
  "repositor": { 
    "nome": "Fulano de Tal",
    "telefone": "99999-0000"
  },
  "instrucoes": [
    "Colocar na prateleira ao lado do ketchup.",
    "Potes maiores em cima no alto."
  ],
  "embalagens": ("Pote 300g", "Pote 500g"),
  "preco": [{ 
    "embalagem": "Pote 300g",
    "valor": 3.50
  },
  { 
    "embalagem": "Pote 500g",
    "valor": 6.50
  }]
}
```
Nas chaves "nome" e "marca" temos strings. Na chave "estoque" temos um número inteiro. Na chave "geladeira" temos um booleano. 

Agora, repare na chave "repositor", o valor dela é um dicionário.

Já a chave "instrucoes" contém uma lista como valor. A chave "embalagens" contém uma tupla.

E, veja com atenção a chave "preco": o valor dela é uma lista de dicionários!

**Modificando valores de uma chave já existente e adicionando novas chaves**

Veja o dicionário a seguir:

```python
usuario = { 
  "nome": "Fulano"
}

print(usuario)    # mostra {'nome': 'Fulano'}

usuario["nome"] = "Ninguém"

print(usuario)    # mostra {'nome': 'Ninguém'}

usuario["email"] = "ninguem@internet.com"

print(usuario)    # mostra {'nome': 'Ninguém', 'email': 'ninguem@internet.com'}
```

Inicialmente, ele possui apenas a chave "nome". 

Quando executamos a linha com *usuario["nome"] = "Ninguém"*, o valor existente da chave "nome" será alterado de "Fulano" para "Ninguém".

Já quando executamos a linha com *usuario["email"] = "ninguem@internet.com"*, como essa chave ainda não existe dentro do dicionário, ela será criada.

Podemos confirmar a criação quando executamos a linha *print(usuario)* e ela nos mostra *{'nome': 'Ninguém', 'email': 'ninguem@internet.com'}*.

**Removendo uma chave**

Quando removemos uma chave de um dicionário, o valor atribuído a ela também é removido.

Existem duas maneiras de remover uma chave.

A primeira é com o **del**:

```python
produtos = { 
  "lapis": 1.50,
  "borracha": 0.80,
  "caderno": 6.50,
  "caneta": 2.50,
  "regua": 1.60
}

print(produtos)   # mostra {'lapis': 1.5, 'borracha': 0.8, 'caderno': 6.5, 'caneta': 2.5, 'regua': 1.6}

del produtos["caneta"]

print(produtos)   # mostra {'lapis': 1.5, 'borracha': 0.8, 'caderno': 6.5, 'regua': 1.6}
```

Precisamos passar o nome da variável e o nome da chave: *del produtos["caneta"]*. Executando essa linha, a chave "caneta" é removida, bem como seu valor.

A segunda é com o **pop**:

```python
produtos.pop("caneta")
```

Esse método tem exatamente o mesmo efeito do **del**.

**Limpar x Deletar**

Existe uma diferença entre limpar e deletar um dicionário. 

O método **clear()** simplesmente removerá as chaves e valores do dicionário. Ele continuará existindo, porém, vazio.

Já o comando **del** apaga o dicionário. Ele deixa de existir.

Veja as diferenças abaixo:

```python
dicionario1 = { 
  "chave1": "bla bla bla",
  "chave2": False
}

dicionario1.clear()

print(dicionario1)    # mostra {}

dicionario2 = { 
  "chave0": "bla bla bla bla bla",
  "chave1": True
}

del dicionario2

print(dicionario2)    # quebra o programa!
```
Se acessarmos o dicionario1, ele continua existindo, porém, vazio. 

Se acessarmos o dicionario2, o programa quebra porque depois do **del**, ele deixa de existir.

**Iterando em dicionários**

Assim como fazemos em listas, podemos iterar em dicionários utilizando o **for**.

Podemos fazer uma iteração que nos permita acessar chaves e valores do dicionário.

Veja:

```python
estudante = { 
  "nome": "Fulana de Tal",
  "email": "fulana@provedor.com.br",
  "curso": "Ciência da Computação",
  "semestre": 4,
  "CR": 9.5
}

for chave, valor in estudante.items():
  print(chave, valor)
```

Aqui, precisamos utilizar o método **items()** para que possamos ter acesso aos valores do dicionário.

Note que temos duas variáveis temporárias: *chave* e *valor*. 

Poderíamos ter usado qualquer outro nome para essas variáveis, basta ter em mente que, dentro do **for**, precisamos utilizar os mesmos nomes. 

No exemplo, quando é feito o *print* dentro do **for**, utilizamos as variáveis temporárias "chave" e "valor".

Como retorno desta iteração, teremos na tela as seguintes informações:

```
nome Fulana de Tal
email fulana@provedor.com.br
curso Ciência da Computação
semestre 4
CR 9.5
```

Podemos perceber que o primeiro elemento de cada linha impressa é o nome da chave seguido de seu valor, sem maiores formatações porque utilizamos apenas *print(chave, valor)*. 

Seguindo o mesmo exemplo, podemos fazer uma iteração acessando somente os nomes das chaves do dicionário:

```python
estudante = { 
  "nome": "Fulana de Tal",
  "email": "fulana@provedor.com.br",
  "curso": "Ciência da Computação",
  "semestre": 4,
  "CR": 9.5
}

for chave in estudante:
  print(chave)
```

O retorno que teremos em tela é:

```
nome
email
curso
semestre
CR
```

Ou seja, somente as chaves são exibidas.

Também podemos fazer uma iteração acessando somente os valores de cada chave do dicionário:

```python
estudante = { 
  "nome": "Fulana de Tal",
  "email": "fulana@provedor.com.br",
  "curso": "Ciência da Computação",
  "semestre": 4,
  "CR": 9.5
}

for valor in estudante.values():
  print(valor)
```

O retorno que teremos em tela é:

```
Fulana de Tal
fulana@provedor.com.br
Ciência da Computação
4
9.5
```

Ou seja, somente os valores são exibidos.

**Verificando a existência de uma chave no dicionário**

Verificar a existência de uma chave no dicionário pode nos poupar de um problema que quebra nosso código: tentar deletar uma chave que não existe!

Em português, essa verificação poderia ser escrita da seguinte maneira:

```
SE chave (existe) NO dicionario:
    # faça isso
SENÃO
    # faça aquilo
```

Em Python, essa instrução fica da seguinte maneira:

```python
if chave in dicionario:
    # faça isso
else:
    # faça aquilo
```

Sendo o **else** opcional.

Veja o exemplo:

```python
carro = {
  "marca": "Ford",
  "modelo": "Mustang",
  "ano": 1964
}

if "modelo" in carro:
  print("Existe a chave modelo.")
else: 
  print("Não existe a chave modelo.")

# mostra Existe a chave modelo.

if "cor" in carro:
  print("Existe a chave cor.")
else: 
  print("Não existe a chave cor.")

# mostra Não existe a chave cor.
```

## Exercícios

1. Escreva um programa simples somente para cadastrar dados de um usuário e salvá-los em um dicionário. Os dados que você deverá armazenar são: nome (string), email (string), curso (string), período (int), disciplinas (lista de strings) e CR (float). Ao final do cadastro, o programa deverá mostrar o dicionário na tela com um print simples.

2. Escreva um programa em que primeiro você cadastrará 10 produtos e seus respectivos preços em um único dicionário. A chave é o nome do produto (string e sem acentuação) e o valor é o preço (float). Em seguida, o programa deverá exibir cada produto (nome e preço) e você deverá informar a quantidade que está comprando. Ao terminar, deverá aparecer na tela o valor total da compra.

---

**Desafio:** Escreva um programa para cadastrar os dados de usuários. O programa deverá perguntar quantos usuários você deseja cadastrar. Os dados que serão cadastrados são nome e email. Os dados de cada usuário deverão ser salvos em um dicionário e, este dicionário, deverá ser salvo em uma lista. Ao final do cadastro, você terá uma lista de dicionários. Exiba essa lista na tela mostrando **Posição - Nome (Email)**. Se você tiver 2 usuários cadastrados, um com nome de João e outro com o nome de Maria, deverá aparecer na tela:
```
0 - João (joao@provedor.com)
1 - Maria (maria@internet.com)
```