# Aula 03

A terceira aula online foi uma revisão das aulas [01](https://github.com/ProgramacaoParaTodes/aula01) e [02](https://github.com/ProgramacaoParaTodes/aula02).

## O que foi visto na aula

### Concatenação de strings

Podemos concatenar strings... Ou seja, podemos 'somar' e 'multiplicar' strings! 

```python
string1 = "ABC"
string2 = "DEF"

print(string1 + string) # exibe ABCDEF na tela

string = "Ai"
print(string*10) # exibe AiAiAiAiAiAiAiAiAiAi na tela
```

Combinando as duas coisas...

```python
hello = "Oi"
print((hello + "!\n")*3)

# exibe na tela
# Oi!
# Oi!
# Oi!
```

**Atenção:** Colocamos *hello + "!\n"* entre parênteses para que o "pacote" todo *Hello!* seja multiplicado 3x e pulando linha por causa do \n.

### len()

Como podemos descobrir o número de caracteres de uma string?

```python
big = "pneumoultramicroscopicossilicovulcanoconiótico"
size = len(big)
print(size) # mostra o número 46 na tela
```

O comando len() conta o número de caracteres incluindo os espaços, portanto...

```python
chokito1 = "Leite condensado, caramelizado com flocos crocantes e coberto com o delicioso chocolate Nestlé"
chokito1_size = len(chokito1)
print("Tamanho com espaços:", chokito1_size) # 94 caracteres

chokito2 = "Leitecondensado,caramelizadocomflocoscrocantesecobertocomodeliciosochocolateNestlé"
chokito2_size = len(chokito2)
print("Tamanho sem espaços:", chokito2_size) # 82 caracteres
```

### Pegando um caractere da string

Vamos entender como é numerada a posição de cada caractere na string.

```python
advice = "FICA EM CASA"
```

Cada caractere - incluindo os espaços - ocupa uma posição cuja numeração começa do ZERO e não do UM.

| F | I | C | A |   | E | M |   | C | A | S  | A  |
|:-:|---|---|:-:|---|---|---|---|---|---|----|----|
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |

Portanto, se eu quiser pegar o primeiro caractere dessa string - que é a letra "F" - basta utilizar o seguinte comando:

```python
first_char = advice[0]
```

Estamos dizendo para o Python pegar o caractere na posição zero! Se fizermos o print do que foi salvo na variável *first_char*, teremos a letra "F".

### Conversões entre tipos

Podemos efetuar a conversão de tipos no Python. Por exemplo, um sistema obtém o ano de nascimento de um usuário e salva isso como uma string. Por algum motivo, é necessário converter para inteiro para descobrir quantos anos o usuário tem. Como podemos fazer isso?

```python
year_input = "2020"
year = int(year_input)
```

Utilizamos o comando *int()* para converter a string "2020" em um inteiro 2020.

Podemos converter um decimal em um inteiro:

```python
grade = 8.4
print(int(grade)) # imprime 8 na tela
```

Precisamos tomar cuidado porque a conversão de um float em um int despreza a parte decimal do número, então não é uma conversão segura. O contrário é tranquilo:

```python
temperature = 19
print(float(temperature)) # imprime 19.0 na tela
```

Também podemos converter números em strings:

```python
number = 1234
string = str(number)
```

Como podemos saber se a conversão funcionou?

Podemos utilizar o comando type()!

```python
grade1 = 8
print(type(grade1)) # mostrará <class 'int'> na tela

grade2 = 8.0
print(type(grade2)) # mostrará <class 'float'> na tela

grade3 = "8.0"
print(type(grade3)) # mostrará <class 'str'> na tela
```

E, a título de curiosidade, mesmo a gente não usando a variável complexa...

```python
number = 1+3j
print(type(number)) # mostrará <class 'complex'> na tela
```

### Mais métodos relacionados a strings

**isnumeric()**

Vamos pensar no seguinte problema: quero que o usuário do sistema cadastre uma senha e quero que ela obrigatoriamente comece com uma letra.

Sendo assim, tenho a variável password que recebe uma string composta por letras e números e vou pegar o primeiro caractere dela: 

```python
password = "61b2x8W4"
last_character = password[0]
```

Utilizando o método isnumeric() é possível saber se o que está salvo na variável last_character é um número ou uma letra:

```python
print(last_character.isnumeric()) # mostra True na tela
```

O método *isnumeric()* retorna True caso o conteúdo da string seja composto pelos dígitos de 0 a 9 e retorna False caso haja algum outro tipo de caractere.

Desta maneira, podemos validar se o usuário pode cadastrar a senha ou não :)

**isalpha()**

De maneira similar ao *isnumeric()*, o método *isalpha()* verifica se a string é composta pelos caracteres do alfabeto.

Assim:

```python
alpha = "abcdefghijklmnopqrstuvwxyz"
print(alpha.isalpha()) # mostra True na tela
```

O método *isalpha()* retorna True caso o conteúdo da string seja composto pelas letras do alfabeto e retorna False caso haja algum outro tipo de caractere.

**Slicing / Fatiamento**

Suponha que no meu cadastro de usuários o campo "celular" foi preenchido por padrão da seguinte maneira: *+55(21)999999999**. Como eu faço se eu quiser exibir somente a parte *(21)999999999*?

Podemos fazer isso "fatiando" a string! Mas antes, vamos lembrar de como numerar cada caractere da string:

| + | 5 | 5 | ( | 2 | 1 | ) | 9 | 9 | 9 | 9  | 9  | 9  | 9  | 9  | 9  |
|:-:|---|---|:-:|---|---|---|---|---|---|----|----|----|----|----|----|
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |

Precisamos "fatiar" a string começando da posição 3 e terminando **depois** da posição 15, uma vez que queremos que o **primeiro (** e o **último 9** estejam contidos no resultado.

```python
mobile = "+55(21)999999999"
print(mobile[3:16])     # imprime (21)999999999 na tela
```

Quando fazemos isso, estamos dizendo "Python, pega a string mobile e corta o pedaço que vai do 3 até o 16, beleza?". 

No comando, escrevemos 16 porque o caractere que ocupa a posição 15 deve estar incluso.

## Exercícios

**Lembrete:** Pensem nas validações <3

1. Escreva um programa que peça para o usuário digitar o próprio nome e o nome de mais alguém. Exiba na tela o maior nome.

2. Escreva um programa que peça para o usuário digitar separadamente o dia, o mês e o ano em que ele nasceu. Exiba na tela a data inteira de nascimento dele no formato DD/MM/AAAA e também no formato *DD de NOME DO MÊS de AAAA*.

3. Em algumas empresas, o endereço de e-mail dos colaboradores é gerado automaticamente pegando as 2 primeiras letras do primeiro nome, as 4 primeiras letras do último nome e acrescentando algumas letras correspondentes ao departamento ou cargo. Por exemplo, na Microsoft, meu e-mail era t-erbuen@microsoft.com e o *t-* era o indicativo de que aquele e-mail pertence a um estagiário. Na nossa empresa fictícia, os e-mails são determinados segundo as regras a seguir:

- primeira letra do primeiro nome;
- último nome inteiro;
- um traço (-);
- sigla do cargo;
- arroba (@);
- domínio da empresa (crazysoftcompany.com.br).

A tabela de cargos e siglas é a seguinte:
|      Cargo     | Sigla |
|:--------------:|:-----:|
|  Estagiário(a) | ESTAG |
| Programador(a) |  DEV  |
|   Testador(a)  |   QA  |

Sendo assim, nesta empresa, meu e-mail seria **EBueno-DEV@crazysoftcompany.com.br** se eu ocupasse o cargo de programadora. **Não se preocupe com letras maiúsculas e minúsculas!**

A senha do e-mail será uma string composta pelas 3 primeiras letras do primeiro nome e o ano de nascimento do colaborador, portanto, no meu caso, a senha seria **eri1983**.

Escreva um programa que leia os seguintes dados do colaborador:
- primeiro nome;
- último nome;
- data de nascimento no formato DD/MM/AAAA;
- cargo.

Em seguida, mostre na tela o nome todo do colaborador, o cargo, o e-mail gerado e a senha.

---

**Desafio:** Escreva um programa que receba a data de nascimento do usuário já no formato DD/MM/AAAA e o dia de hoje, também no formato DD/MM/AAAA. Mostre na tela se o usuário já fez aniversário neste ano, se ainda vai fazer ou se hoje é o aniversário dele. Mostre também a idade atual considerando se ele fez aniversário ou não.

