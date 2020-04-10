# Aula 05

Vamos relembrar o que foi visto na quinta aula online e vamos dar alguns passinhos a mais até a próxima aula ;) No final do texto, você encontra alguns exercícios para praticar.

### Listas

Na aula, aprendemos que uma **lista** no Python é uma estrutura de dados que recebe uma sequência de elementos.

Quando definimos uma lista, utilizamos *colchetes*:

```python
new_list = []      # esta é uma lista vazia por enquanto
```

Separamos os elementos de uma lista com *vírgulas*:

```python
new_list = ["Um elemento", "Outro elemento", "E mais outro elemento"]
```

Podemos ter uma lista composta somente por elementos pertencentes ao mesmo tipo de variável:

```python
colors = ["azul", "amarelo", "vermelho", "branco", "preto"]    # lista formada somente por string

grades = [8.85, 9.0, 6.5, 7.0]                          # lista formada somente por float     
```

Podemos ter uma lista com tipos de variáveis diferentes:

```python
subject_data = ["Fulano", "Matemática", 9.5, True]      # lista formada por diferentes tipos de variáveis
```

E também podemos ter uma lista com listas!

```python
shopping_list = [["banana", "maçã", "tomate"], ["cerveja", "coca-cola", "suco de laranja", "água"], ["miojo", "bolacha"]]
```

Cada elemento da lista ocupa uma posição cuja numeração começa a partir do zero. Veja o exemplo: 

```python
fruits = ["maçã", "banana", "laranja", "limão"]
```

Temos uma lista com 4 elementos e cada um deles ocupa uma posição distinta. O primeiro elemento ocupa a posição 0 e, neste exemplo, o último elemento ocupa a posição 3.

| [ | "maçã" | , | "banana" | , | "laranja" | , | "limão" | ] |
|:-:|:------:|:-:|:--------:|:-:|:---------:|:-:|:-------:|:-:|
|   |    0   |   |     1    |   |     2     |   |    3    |   |

Isso nos lembra de algo que vimos nas aulas passadas: as posições dos caracteres dentro da string! Refrescando a memória...

```python
name = "Erika"
print(name[0])  # mostra E
print(name[1])  # mostra r
print(name[2])  # mostra i
print(name[3])  # mostra k
print(name[4])  # mostra a
```

Com as strings, isso também funciona! Veja:

```python
series = ["La Casa de Papel", "Lucifer", "Grey's Anatomy", "Perdidos no Espaço"]
print(series[0])   # mostra La Casa de Papel
print(series[1])   # mostra Lucifer
print(series[2])   # mostra Grey's Anatomy
print(series[3])   # mostra Perdidos no Espaço
```

Temos outras semelhanças entre o que vimos na aula 03 e o que vimos na aula 05. Podemos verificar o **tamanho de uma lista** e podemos **fatiá-la**, assim como fizemos com as strings. 

Vejam a comparação:

**string**

```python
name = "Erika"
print(len(name))    # mostra 5
print(name[1:4])    # mostra rik
```

**lista**

```python
series = ["La Casa de Papel", "Lucifer", "Grey's Anatomy", "Perdidos no Espaço"]
print(len(series))   # mostra 4
print(series[2:4])   # mostra ['Grey's Anatomy', 'Perdidos no Espaço']
```

