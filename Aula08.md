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

Como podemos acessar esses valores? Através das chaves! Veja:

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

## Exercícios

1. 

2. 

---

**Desafio:** 