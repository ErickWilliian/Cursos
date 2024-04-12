# Python

## Tuplas 

Tuplas são estruturas de dados muito pareceidas com as listas, a principal diferença é que tuplas são imutáveis enquanto listas são mutaveis. Podemos criar tuplas através da classe **tuple**, ou colocando valores separados por vírgula de parenteses 

```py

    frutas = ("laranja","pera","uva")


    # OBS:  Se você não colocar uma virgula no fim o python vai entender que é para separar 
    # o elemento  
    letras = tuple("python")

    numeros = tuple([1,2,3,4,5,6])

    pais = ("Brasil")


    # Para acessar é igual as listas 
    # Praticamente a maioria das funções das lista funcionam nas tuplas
    letras[0]
```

## Conjuntos

> Criando **sets**

Um set é uma coleção que não possui objetos repetidos, usamos sets para representar conjuntos matemáticos ou eliminar itens duplicados de um interável

```py

set([1,2,3,1,2,3,4]) # {1,2,3,4}


```
- Conjuntos em Python não suportam indexação e nem fatiamento, caso queira acessar os seus valores é necessário converter o conjunto para lista

```py
numeros = set([1,2,3,1,2,3,4])


numeros = list(numeros)
```

### Métodos da classe set

- De certa forma os conjutos no Python é igual aos conjuntos matemáticos


> Union

Serve para unir dois conjuntos

```py
conjunto_a = {1,2}
conjunto_b = {3,4}

conjunto_a.union(conjunto_b) #  {1, 2, 3, 4}


```

> Intersection

Serve para saber o meio desses dois conjuntos, falando de forma mais simples ele serve para ver o que os dois tem de iguais
```py
conjunto_a = {1,2}
conjunto_b = {2,3,4}

conjunto_a.intersection(conjunto_b)


```
> Difference

Serve para que você ache a diferença entre os conjuntos
```py
conjunto_a = {1,2,3}
conjunto_b = {2,3,4}


# no caso ele vai retornar o que tem no A mas não tem no B
conjunto_a.difference(conjunto_b)

# e invertendo você pode pegar o que tem no A mas não tem no B
conjunto_b.difference(conjunto_a)
```

> Symmetric Difference

Funciona quase da mesma forma que o diference, so que nesse caso ele serve para encontrar TODAS as diferenças ou seja valores que não estão na Intersection
```py
conjunto_a = {1,2,3}
conjunto_b = {2,3,4}


# no caso ele vai retornar o que tem no A mas não tem no B
conjunto_a.difference(conjunto_b)

# e invertendo você pode pegar o que tem no A mas não tem no B
conjunto_b.difference(conjunto_a)
```

> Issubset

Esse no caso é uma pergunta, ele meio que pergunta se o conjunto A pertence ao B ( Se todos os elementos que tem no A tem no B )

```py

conjunto_a = {1,2,3}
conjunto_b = {1,2,3,4}


# Aqui pergunta o conjunto A pertence ao B
conjunto_a.issubset(conjunto_b)


conjunto_b.issubset(conjunto_a)

```

> Issuperset

Aqui ele é um pouco parecido com o anterior, so que a pergunta é diferente, anteriormente vocÊ perguntou se o primeiro elemento pertence ao elemento no parenteses, ja essa ele pergunta se o que está nos parenteses pertence ao primeiro 

```py

conjunto_a = {1,2,3}
conjunto_b = {1,2,3,4}


# Aqui pergunta o conjunto b pertence ao a
conjunto_a.issuperset(conjunto_b)


conjunto_b.issuperset(conjunto_a)

```

> isdisjoint

Esse ele vai perguntar se os conjuntos se "tocam", como assim ? Simples ele vai perguntar se algo tem no outro se não tiver ele vai retornar `true` se eles tiverem algo em comum "false"

```py

conjunto_a = {1,2,3}
conjunto_b = {4,5,6,7,8}
conjunto_c = {1,2}



conjunto_a.isdisjoint(conjunto_c)


conjunto_b.issuperset(conjunto_a)

```

> add

Vai adicionar mais um elemento no conjunto
```py

a = {1,2,3}

a.add(25)

```
> clear

Vai limpar o conjunto
```py
a = {1,2,3}

a.clear()

```
> copy

Vai copiar o conjunto
```py
a = {1,2,3}

a.copy()

```
> discard

Vai discartar algum elemento
```py
a = {1,2,3}

a.discard(1)

```

> pop

Vai discartar algum elemento, so que diferente do discard o pop tira sem receber param, ele tira o primeiro elemento
```py
a = {1,2,3}

a.pop()

```

> remove

ele remove o item atravez de um index passado por um param
```py

a = {1,2,3}

a.remove(0)
```

> len

ele mostra a quantidade de elementos no conjunto
```py

a = {1,2,3}

len(a)
```

> in

ele verifica se algum elemento está presente no conjunto
```py
numeros = {1,2,3}

# Aqui ele pergunta 1 esta em numeros

1 in numeros
```

## Dicionários

- Um dicionário é um conjunto não-ordenado de pares chave:valor, onde as chaves são únicas em uma dada instância do dicionário. Dicipnários são delimitados por chaves: {}, e contém uma lista de pares chaves:valor separada por vírgulas

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

pessoa = dict( nome = "Erick", idade = 20)

# Para acesar basta usar:
pessoa["Nome"]

# Mudar o valor
pessoa["Nome"] = "Pedro"
```

- Dicionários podem armazenar qualquer tipo de objeto Python como valor, desde que a chave para esse valor seja um objeto imutável como ( string e números )

```py

contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}

# Para acessar funciona da mesma forma de uma matriz

contatos["erickwillian@gmail.com"]["telefone"]
```

### Usando o For

```py

for chave in contatos:
    print(chave, contatos[chave])



for chave, valor in contatos.items():
    print(chave, valor)
```

### Métodos de um dicionário 

> {}.clear
- Serve para limpar um dicionário

```py
contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}

contatos.clear()


```
> {}.copy
- Cria uma cópia do dicionário

```py
contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}

copia = contatos.copy()


```

> {}.fromkeys
- Ele cria chaves para um dicionário

```py
dict.fromkeys(["nome","telefone"])


dict.fromkeys(["nome","telefone"], "vazio")
```

> {}.get
- É uma outra forma de acessar valores dentro de um dicionário 


```py
contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}

contatos["chave"] # KeyError


# Aqui caso ele não encontre ele retorna null
contatos.get("chave") # None

# Aqui caso ele não encontre ele retorna o que foi passado no segundo param
contatos.get("chave",{})

contatos.get("erickwillian@gmail.com",{})

```

> {}.items


- Usado para transformar o dicionário em uma tupla

```py

contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}
contatos.items()


```
> {}.keys


- Retorna só as chaves do dicionário

```py

contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}
contatos.keys()


```

> {}.pop


- Retira algo do dicionário

```py

contatos = {
    "erickwillian@gmail.com":{ "nome" : "Erick", "idade" : 20 }

}
contatos.pop("erickwillian@gmail.com")


# Da mesma forma de antes se colocar outro param ele vai retornar aquele valor ao inves de um erro
contatos.pop("erickwillian@gmail.com",{})


```

> {}.setdefault

- Ele funciona da seguinte forma, ele vai adicionar um elemento no dicionario e caso ele ja exista nele essa função não altera e so retorna o valor que ja tinha

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

pessoa.setdefault("nome","Gabriella")


```

> {}.update

- Ele vai atualizar o valor do dicionário

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

pessoa.update({"nome","Gabriella"})


```
> {}.values

- Ele vai retornar uma tupla com os values de cada key

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

pessoa.values()


```
> in

- Assim você pode meio que perguntar se existe ou não uma key em um dicionário

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

"nome" in pessoa


```

> del

- Assim você deleta algo de um dicionário

```py

pessoa = {
    "nome" : "Erick",
    "idade" : 20
}

del pessoa["idade"]


```


## Funções
- Função é um bloco de código identificado por um nome e pode receber uma lista de parâmetros, esses parâmetros pode ou não ter valores padroes. Usar funções torna o código mais legível e possibilita o reaproveitamento de código. Programar baseado em funções, é o mesmo que dizer que estamos programando de forma estruturada 

```py
# def inicia uma função
# logo apos vem o nome da função
# depois os parenteses que ficam os param
def exibir_mensagem():
    print("Olá mundo")


```
> Retorno
```py

def soma():
    return 1 + 2


```

> Args e Kwargs

- Podemos combinar parâmetros obrigatórios com args e kwargs. Quando esses são definidos (*args e **kwargs), o métodrecebe os valores como tupla e dicionário respectivamente


> Parâmetros especiais 

- Por padrão, argumentos podem ser passados para uma função Python tanto por posição quanto explicitamente pelo nome. Para uma melhor legibilidade e desempenho, faz sentido restringir a maneira pelo qual argumentos possam ser passados, assim um desenvolvedor precisa apenas olhar para a definição da função para determinar se os itens são passados **por posição, por posição e nome, ou por nome** 

```py

def criar_carro(modelo, ano,placa, /, marca):
    print(modelo, ano, placa, marca)


# Aqui ele exige que tudo que tiver antes da "/" seja apenas param por posi~ção
# 
criar_carro("Palio",1999,"ABC-1234",marca="Fiat")
```

> Objetos de primeira classe

- Em Python tudo é objeto, dessa forma funções também são objetos o que as tornam objetos de primeira classe. Com isso podemos atribuir funções a variáveis, passá-las como parâmetro para funções, usá-las como valores em estruturas de dados( listas, tuplas, dicionários, etc) e usar como valor de retorno para uma função (closures)


```py

def somar(a, b):
    return a + b


def exibir_resultado(a, b, funcao):
    resultado = funcao(a, b)
    print(f"O resultado da operação {a} + {b} = {resultado}")


exibir_resultado(10, 10, somar)
```

> Escopo local e escopo global

- Python trabalha com escopo local e global, dentro do bloco da função o escopo é local. Portanto alterações ali feitas em objetos imutáveis serão perdidas quando o método terminar de ser executado. Para usar objetos globais utilizamos a palavra chave **global**, que informa ao interpretador que a variável que está sendo manipulada no escopo local é global. Essa **NÃO é uma boa prática e deve ser evitada**

```py

salario = 2000

def salario_bonus(bonus):
    global salario
    salario += bonus
    return salario

salario_bonus(500)

```

## Classes 

- Init : usada quando a classe é instanciada, esse init é usado para iniciar as variaveis
- E o self dentro dos parenteses indica que ele está referenciando a classe controle ou seja tudo que for inicializado vai pertencer a classe controle ele funciona como se fosse o this em outras linguagens 
- E depois da virgula são os params de inicialização
```py

class Controle:
    def __init__(self, cor):
        self.cor = cor            

    pass


```

## Decorators

- Exemplo com flask
- O que um decorator faz é dar uma nova funcionalidade para uma função que vem abaixo ele
```py

from flask import Flask

app = Flask(__name__)


# Então que acontece aqui, normalmente a função abaixo vai so retornar um texto
# Mas com esse decorator ele vai fazer com que o resultado dessa função seja exibido numa rota
# entendeu? Ele deu numa nova funcionalidade pra essa função
# inves de exibir so um texto ele vai criar uma pagina
@app.route("/")
def homepage():
    return " Olá mundo !"


app.run()
```
