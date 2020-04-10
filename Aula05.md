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

### Adicionando e removendo elementos das listas

Como dito acima, podemos adicionar e remover elementos de uma lista. 

Adicionar é mais tranquilo porque é algo que acrescenta, porém, precisamos ter cuidado ao remover elementos de uma lista porque precisamos ter certeza que aquele elemento existe.

Por exemplo: Tenho uma lista com 5 elementos, ou seja, os elementos ocupam as posições 0, 1, 2, 3 e 4. Suponha que, por falta de atenção minha, eu tente remover o elemento da posição 5. Isso ocasionará um erro porque não há um elemento nessa posição.

Vamos conhecer os métodos para adicionar e remover elementos das listas!

**append()**

Adiciona um elemento ao final da lista.

```python
todo_list = ["Pagar contas", "Tirar o lixo"]

todo_list.append("Fazer imposto de renda")

print(todo_list)    # mostra ['Pagar contas', 'Tirar o lixo', 'Fazer imposto de renda']
```

**del**

Deleta o elemento conforme a posição informada ou parte da lista conforme a "fatia" informada.

```python
music = ["Rock", "Pop", "Gospel", "Anos 80", "Anos 90", "Axé", "Funk", "Sertanejo", "Clássica", "New Age"]

del music[2]    # remove o item na posição 2 -> Gospel

print(music)    # mostra ['Rock', 'Pop', 'Anos 80', 'Anos 90', 'Axé', 'Funk', 'Sertanejo', 'Clássica', 'New Age'] e temos outro item ocupando a posição 2 agora que é Anos 80

del music[4:7]  # remove a fatia que vai do item 4 ao item 6

print(music)    # mostra as minhas preferências musicais ['Rock', 'Pop', 'Anos 80', 'Anos 90', 'Clássica', 'New Age'] ;)
```

**somando uma lista à outra pré-existente**

Acrescenta os itens da lista somada à lista que já existia, resultando em uma lista maior.

```python
empty_list = []                         # lista vazia

empty_list += ["blablabla", "oioioi"]   # somo os itens ["blablabla", "oioioi"] 

print(empty_list)                       # mostra ['blablabla', 'oioioi'], que é a minha lista atual

empty_list += ["etcetcetc"]             # somo o item ["etcetcetc"] à lista

print(empty_list)                       # mostra ['blablabla', 'oioioi', 'etcetcetc']
```

**Atenção:** Isso é diferente de adicionar um novo elemento a uma lista pré-existente. Aqui estamos simplesmente somando um pedaço de lista e outro pedaço de lista, resultando numa lista maior.

**insert**

Acrescenta o elemento na posição especificada. Neste *método*, temos que informar *dois parâmetros*: o primeiro é a posição e o segundo é o elemento.

```python
junk_food = ["hamburguer", "batata frita", "pizza"]

junk_food.insert(1, "sorvete")      # insere o elemento "sorvete" na posição 1

print(junk_food)                    # mostra ['hamburguer', 'sorvete', 'batata frita', 'pizza']
```

**pop**

Remove o elemento da posição especificada. Neste *método*, passamos somente o *parâmetro* da posição.

Vamos aproveitar o exemplo anterior da lista junk_food que, neste ponto, contém os elementos ['hamburguer', 'sorvete', 'batata frita', 'pizza'].

```python
junk_food.pop(0)        # remove o elemento na posição 0

print(junk_food)        # mostra ['sorvete', 'batata frita', 'pizza']
```

**Alterando um elemento específicio**

Podemos alterar o conteúdo de um elemento específico utilizando a sintaxe *variavel[posição] = "novo valor do elemento naquela posição*.

Continuaremos com o mesmo exemplo e, neste ponto, junk_food contém os elementos ['sorvete', 'batata frita', 'pizza'].

```python
junk_food[0] = "sorvete de chocolate"   # modifica o elemento da posição 0

print(junk_food)                        # mostra ['sorvete de chocolate', 'batata frita', 'pizza']
```

**Obtendo o último elemento da lista**

Como o tamanho das listas pode variar, se quisermos ter certeza de que estamos nos refereindo ao último elemento, podemos utilizar a sintaxe *variavel[-1]*.

```python
last = junk_food[-1]    # pega o último elemento

print(last)             # mostra pizza
```

**Removendo um elemento específico com remove()**

Se soubermos da existência de um determinado elemento na lista, podemos removê-lo com o método remove() passando como parâmetro o elemento que desejamos remover.

Do exemplo anterior, temos a variável junk_food contendo ainda os elementos ['sorvete de chocolate', 'batata frita', 'pizza'].

```python
junk_food.remove("batata frita")    # remove o elemento especificado independentemente da posição

print(junk_food)                    # mostra ['sorvete de chocolate', 'pizza']
```