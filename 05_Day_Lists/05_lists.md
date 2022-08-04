<div align="center">
  <h1> 30 Days Of Python: Day 5 - Lists</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Second Edition: July - 2021</small>
</sub>

</div>

[<< Day 4](../04_Day_Strings/04_strings.md) | [Day 6 >>](../06_Day_Tuples/06_tuples.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [Day 5](#day-5)
  - [Lists](#lists)
    - [How to Create a List](#how-to-create-a-list)
    - [Accessing List Items Using Positive Indexing](#accessing-list-items-using-positive-indexing)
    - [Accessing List Items Using Negative Indexing](#accessing-list-items-using-negative-indexing)
    - [Unpacking List Items](#unpacking-list-items)
    - [Slicing Items from a List](#slicing-items-from-a-list)
    - [Modifying Lists](#modifying-lists)
    - [Checking Items in a List](#checking-items-in-a-list)
    - [Adding Items to a List](#adding-items-to-a-list)
    - [Inserting Items into a List](#inserting-items-into-a-list)
    - [Removing Items from a List](#removing-items-from-a-list)
    - [Removing Items Using Pop](#removing-items-using-pop)
    - [Removing Items Using Del](#removing-items-using-del)
    - [Clearing List Items](#clearing-list-items)
    - [Copying a List](#copying-a-list)
    - [Joining Lists](#joining-lists)
    - [Counting Items in a List](#counting-items-in-a-list)
    - [Finding Index of an Item](#finding-index-of-an-item)
    - [Reversing a List](#reversing-a-list)
    - [Sorting List Items](#sorting-list-items)
  - [💻 Exercises: Day 5](#-exercises-day-5)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)

# Day 5

## Lists

Hay cuatro tipos de datos de coleccion en Python :

- List: es una colección ordenada y modificable. Permite duplicar miembros.
- Tuple: es una colección ordenada y no modificable (inmutable). Permite duplicar miembros.
- Set: es una colección no ordenada, no indexada y no modificable, pero podemos añadir nuevos elementos al conjunto. No se permiten los miembros duplicados.
- Dictionary: es una colección desordenada, modificable e indexada. No hay miembros duplicados.

Una lista es una colección de diferentes tipos de datos que está ordenada y es modificable (mutable). Una lista puede estar vacía o puede tener elementos de diferentes tipos de datos.

### How to Create a List

En Python podemos crear listas de dos maneras:

- Uso de la función incorporada a la lista

```py
# syntax
lst = list()
```

```py
empty_list = list() # esta es una lista vacía, no hay ningún elemento en la lista
print(len(empty_list)) # 0
```

- Uso de corchetes, []

```py
# syntax
lst = []
```

```py
empty_list = [] # esta es una lista vacía, no hay ningún elemento en la lista
print(len(empty_list)) # 0
```

Listas con valores iniciales. Utilizamos _len()_ para encontrar la longitud de una lista.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']                     # list of fruits
vegetables = ['Tomato', 'Potato', 'Cabbage','Onion', 'Carrot']      # list of vegetables
animal_products = ['milk', 'meat', 'butter', 'yoghurt']             # list of animal products
web_techs = ['HTML', 'CSS', 'JS', 'React','Redux', 'Node', 'MongDB'] # list of web technologies
countries = ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']

# Imprimir las listas y su longitud
print('Fruits:', fruits)
print('Number of fruits:', len(fruits))
print('Vegetables:', vegetables)
print('Number of vegetables:', len(vegetables))
print('Animal products:',animal_products)
print('Number of animal products:', len(animal_products))
print('Web technologies:', web_techs)
print('Number of web technologies:', len(web_techs))
print('Countries:', countries)
print('Number of countries:', len(countries))
```

```sh
output
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Las listas pueden tener elementos de diferentes tipos de datos

```py
 lst = ['Asabeneh', 250, True, {'country':'Finland', 'city':'Helsinki'}] # list containing different data types
```

### Accessing List Items Using Positive Indexing
(Acceso a los elementos de la lista mediante la indexación positiva)

Accedemos a cada elemento de una lista utilizando su índice. El índice de una lista empieza por 0. La imagen siguiente muestra claramente dónde empieza el índice

![List index](../images/list_index.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[0] # estamos accediendo al primer elemento utilizando su índice
print(first_fruit)      # banana
second_fruit = fruits[1]
print(second_fruit)     # orange
last_fruit = fruits[3]
print(last_fruit) # lemon
# Último índice
last_index = len(fruits) - 1
last_fruit = fruits[last_index]
```

### Accessing List Items Using Negative Indexing
(Acceso a los elementos de la lista mediante la indexación negativa)

La indexación negativa significa comenzar desde el final, -1 se refiere al último elemento, -2 se refiere al penúltimo elemento.

![List negative indexing](../images/list_negative_indexing.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[-4]
last_fruit = fruits[-1]
second_last = fruits[-2]
print(first_fruit)      # banana
print(last_fruit)       # lemon
print(second_last)      # mango
```

### Unpacking List Items

```py
lst = ['item','item2','item3', 'item4', 'item5']
first_item, second_item, third_item, *rest = lst
print(first_item)     # item1
print(second_item)    # item2
print(third_item)     # item3
print(rest)           # ['item4', 'item5']

```

```py
# 1er ejemplo
fruits = ['banana', 'orange', 'mango', 'lemon','lime','apple']
first_fruit, second_fruit, third_fruit, *rest = lst
print(first_fruit)     # banana
print(second_fruit)    # orange
print(third_fruit)     # mango
print(rest)           # ['lemon','lime','apple']
# 2do ejemplo sobre la lista unpacking 
first, second, third,*rest, tenth = [1,2,3,4,5,6,7,8,9,10]
print(first)          # 1
print(second)         # 2
print(third)          # 3
print(rest)           # [4,5,6,7,8,9]
print(tenth)          # 10
# 3er ejemplo sobre la lista unpacking 
countries = ['Germany', 'France','Belgium','Sweden','Denmark','Finland','Norway','Iceland','Estonia']
gr, fr, bg, sw, *scandic, es = countries
print(gr)
print(fr)
print(bg)
print(sw)
print(scandic)
print(es)
```

### Slicing Items from a List
(Rebanar elementos de una lista)
- Indexación positiva: Podemos especificar un rango de índices positivos especificando el inicio, el final y el paso, el valor de retorno será una nueva lista. (default values for start = 0, end = len(lst) - 1 (last item), step = 1)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[0:4] # devuelve todas las frutas
# esto también dará el mismo resultado que el anterior
all_fruits = fruits[0:] # si no fijamos dónde parar se lleva todo el resto
orange_and_mango = fruits[1:3] # no incluye el primer índice
orange_mango_lemon = fruits[1:]
orange_and_lemon = fruits[::2] # aquí utilizamos un 3er argumento, paso. Tomará 1 de cada 2 elementos - ['banana', 'mango']
```

- Indexación negativa: Podemos especificar un rango de índices negativos especificando el inicio, el final y el paso, el valor de retorno será una nueva lista.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[-4:] # devuelve todos los frutos
orange_and_mango = fruits[-3:-1] # no incluye el último índice,['orange', 'mango']
orange_mango_lemon = fruits[-3:] # esto dará a partir de -3 hasta el final,['orange', 'mango', 'lemon']
reverse_fruits = fruits[::-1] # un paso negativo tomará la lista en orden inverso,['lemon', 'mango', 'orange', 'banana']
```

### Modifying Lists

La lista es una colección ordenada de elementos mutable o modificable. Vamos a modificar la lista de frutas.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits[0] = 'avocado'
print(fruits)       #  ['avocado', 'orange', 'mango', 'lemon']
fruits[1] = 'apple'
print(fruits)       #  ['avocado', 'apple', 'mango', 'lemon']
last_index = len(fruits) - 1
fruits[last_index] = 'lime'
print(fruits)        #  ['avocado', 'apple', 'mango', 'lime']
```

### Checking Items in a List

Comprobación de un elemento si es miembro de una lista utilizando el operador *in*. Ejemplo:

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
does_exist = 'banana' in fruits
print(does_exist)  # True
does_exist = 'lime' in fruits
print(does_exist)  # False
```

### Adding Items to a List

Para añadir un elemento al final de una lista existente utilizamos el método *append()*.

```py
# syntax
lst = list()
lst.append(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.append('apple')
print(fruits)           # ['banana', 'orange', 'mango', 'lemon', 'apple']
fruits.append('lime')   # ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
print(fruits)
```

### Inserting Items into a List

Podemos utilizar el método *insert()* para insertar un solo elemento en un índice especificado en una lista. Tenga en cuenta que los demás elementos se desplazan a la derecha. El método *insert()* toma dos argumentos: el índice y el elemento a insertar.

```py
# syntax
lst = ['item1', 'item2']
lst.insert(index, item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.insert(2, 'apple') # insert apple between orange and mango
print(fruits)           # ['banana', 'orange', 'apple', 'mango', 'lemon']
fruits.insert(3, 'lime')   # ['banana', 'orange', 'apple', 'lime', 'mango', 'lemon']
print(fruits)
```

### Removing Items from a List

El método *remove* elimina un elemento especificado de una lista

```py
# syntax
lst = ['item1', 'item2']
lst.remove(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'banana']
fruits.remove('banana')
print(fruits)  # ['orange', 'mango', 'lemon', 'banana'] - this method removes the first occurrence of the item in the list
fruits.remove('lemon')
print(fruits)  # ['orange', 'mango', 'banana']
```

### Removing Items Using Pop

El método *pop()* elimina el índice especificado, (o el último elemento si no se especifica el índice):

```py
# syntax
lst = ['item1', 'item2']
lst.pop()       # ultimo item
lst.pop(index)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.pop()
print(fruits)       # ['banana', 'orange', 'mango']

fruits.pop(0)
print(fruits)       # ['orange', 'mango']
```

### Removing Items Using Del

La palabra clave *del* elimina el índice especificado y también puede utilizarse para eliminar elementos dentro del rango del índice. También puede eliminar la lista por completo

```py
# syntax
lst = ['item1', 'item2']
del lst[index] # only a single item
del lst        # to delete the list completely
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[0]
print(fruits)       # ['orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[1]
print(fruits)       # ['orange', 'lemon', 'kiwi', 'lime']
del fruits[1:3]     # ¡esto borra los elementos entre los índices dados, por lo que no borra el elemento con índice 3!
print(fruits)       # ['orange', 'lime']
del fruits
print(fruits)       # Esto debería dar: NameError: el nombre 'fruits' no está definido
```

### Clearing List Items

El método *clear()* vacía la lista:

```py
# syntax
lst = ['item1', 'item2']
lst.clear()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.clear()
print(fruits)       # []
```

### Copying a List

Es posible copiar una lista reasignándola a una nueva variable de la siguiente manera: lista2 = lista1. Ahora, la lista2 es una referencia de la lista1, cualquier cambio que hagamos en la lista2 también modificará la original, la lista2. Pero hay muchos casos en los que no queremos modificar el original, sino que queremos tener una copia diferente. Una de las formas de evitar el problema anterior es utilizar _copy()_.

```py
# syntax
lst = ['item1', 'item2']
lst_copy = lst.copy()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits_copy = fruits.copy()
print(fruits_copy)       # ['banana', 'orange', 'mango', 'lemon']
```

### Joining Lists

Hay varias formas de unir, o concatenar, dos o más listas en Python.

- Plus Operator (+)

```py
# syntax
list3 = list1 + list2
```

```py
positive_numbers = [1, 2, 3, 4, 5]
zero = [0]
negative_numbers = [-5,-4,-3,-2,-1]
integers = negative_numbers + zero + positive_numbers
print(integers) # [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits_and_vegetables = fruits + vegetables
print(fruits_and_vegetables ) # ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

- Unir usando el método extend()
  El método *extend()* permite añadir una lista en una lista. Véase el ejemplo siguiente.

```py
# syntax
list1 = ['item1', 'item2']
list2 = ['item3', 'item4', 'item5']
list1.extend(list2)
```

```py
num1 = [0, 1, 2, 3]
num2= [4, 5, 6]
num1.extend(num2)
print('Numbers:', num1) # Numbers: [0, 1, 2, 3, 4, 5, 6]
negative_numbers = [-5,-4,-3,-2,-1]
positive_numbers = [1, 2, 3,4,5]
zero = [0]

negative_numbers.extend(zero)
negative_numbers.extend(positive_numbers)
print('Integers:', negative_numbers) # Integers: [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits.extend(vegetables)
print('Fruits and vegetables:', fruits ) # Fruits and vegetables: ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

### Counting Items in a List

El método *count()* devuelve el número de veces que un elemento aparece en una lista:

```py
# syntax
lst = ['item1', 'item2']
lst.count(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.count('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.count(24))           # 3
```

### Finding Index of an Item

El método *index()* devuelve el índice de un elemento de la lista:

```py
# syntax
lst = ['item1', 'item2']
lst.index(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.index('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.index(24))           # 2, the first occurrence
```

### Reversing a List

El método *reverse()* invierte el orden de una lista.

```py
# syntax
lst = ['item1', 'item2']
lst.reverse()

```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.reverse()
print(fruits) # ['lemon', 'mango', 'orange', 'banana']
ages = [22, 19, 24, 25, 26, 24, 25, 24]
ages.reverse()
print(ages) # [24, 25, 24, 26, 25, 24, 19, 22]
```

### Sorting List Items

Para ordenar las listas podemos utilizar el método _sort()_ o las funciones incorporadas _sorted()_. El método _sort()_ reordena los elementos de la lista en orden ascendente y modifica la lista original. Si un argumento del método _sort()_ inverso es igual a true, ordenará la lista en orden descendente.

- sort(): este método modifica la lista original

  ```py
  # syntax
  lst = ['item1', 'item2']
  lst.sort()                # ascendente
  lst.sort(reverse=True)    # descendente
  ```

  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits.sort()
  print(fruits)             # ordenados por orden alfabético, ['banana', 'lemon', 'mango', 'orange']
  fruits.sort(reverse=True)
  print(fruits) # ['orange', 'mango', 'lemon', 'banana']
  ages = [22, 19, 24, 25, 26, 24, 25, 24]
  ages.sort()
  print(ages) #  [19, 22, 24, 24, 24, 25, 25, 26]
 
  ages.sort(reverse=True)
  print(ages) #  [26, 25, 25, 24, 24, 24, 22, 19]
  ```

  sorted(): devuelve la lista ordenada sin modificar la lista original
  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  print(sorted(fruits))   # ['banana', 'lemon', 'mango', 'orange']
  # Reverse order
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits = sorted(fruits,reverse=True)
  print(fruits)     # ['orange', 'mango', 'lemon', 'banana']
  ```

🌕 Eres diligente y ya has logrado bastante. Acabas de completar los desafíos del día 5 y estás a 5 pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Exercises: Day 5

### Exercises: Level 1

1. Declarar una lista vacía
2. Declarar una lista con más de 5 elementos
3. Encuentre la longitud de su lista
4. Obtener el primer elemento, el elemento del medio y el último elemento de la lista
5. Declara una lista llamada mixed_data_types, pon tu(name, age, height, marital status, address)
6. Declarar una variable de lista llamada it_companies y asignar valores iniciales Facebook, Google, Microsoft, Apple, IBM, Oracle and Amazon.
7. Imprime la lista utilizando _print()_
8. Imprimir el número de empresas de la lista
9. Imprime la primera, media y última empresa
10. Imprimir la lista después de modificar una de las empresas
11. Añadir una empresa de TI a it_companies
12. Inserta una empresa de informática en el centro de la lista de empresas
13. Cambie uno de los nombres it_companies a mayúsculas (IBM excluido!)
14. Unir las it_companies con una cadena '#;&nbsp; '
15. Comprobar si una determinada empresa existe en la lista it_companies.
16. Ordenar la lista mediante el método sort()
17. Invertir la lista en orden descendente utilizando el método reverse()
18. Cortar las 3 primeras empresas de la lista
19. Cortar las 3 últimas empresas de la lista
20. Corta la empresa o empresas de TI del medio de la lista
21. Elimine la primera empresa de TI de la lista
22. Eliminar la empresa o empresas de TI del medio de la lista
23. Elimine la última empresa de TI de la lista
24. Elimine todas las empresas de TI de la lista
25. Destruir la lista de empresas informáticas
26. Unir las siguientes listas:

    ```py
    front_end = ['HTML', 'CSS', 'JS', 'React', 'Redux']
    back_end = ['Node','Express', 'MongoDB']
    ```

27. Después de unir las listas de la pregunta 26. Copiar la lista unida y asignarla a una variable full_stack. Luego inserta Python y SQL después de Redux.

### Exercises: Level 2

1. A continuación se presenta una lista de 10 estudiantes de edades:

```sh
ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
```

- Ordena la lista y encuentra la edad mínima y máxima
- Añade la edad mínima y la edad máxima a la lista
- Encuentra la edad media (un elemento medio o dos elementos medios divididos por dos)
- Encuentra la edad media (suma de todos los elementos dividida por su número )
- Encuentra el rango de las edades (max minus min)
- Compara el valor de (min - average) y (max - average), utiliza el método _abs()_.

1. Encuentre el(los) país(es) del medio en el [countries list](https://github.com/Asabeneh/30-Days-Of-Python/tree/master/data/countries.py)
1. Divida la lista de países en dos listas iguales si es que no hay un país más para la primera mitad.
1. ['China', 'Russia', 'USA', 'Finland', 'Sweden', 'Norway', 'Denmark']. Unpack los tres primeros países y el resto como países escandinavos.

🎉 CONGRATULATIONS ! 🎉

[<< Day 4](../04_Day_Strings/04_strings.md) | [Day 6 >>](../06_Day_Tuples/06_tuples.md)
