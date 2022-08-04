<div align="center">
  <h1> 30 Days Of Python: Day 6 - Tuples</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Second Edition: July, 2021</small>
</sub>

</div>

[<< Day 5](../05_Day_Lists/05_lists.md) | [Day 7 >>](../07_Day_Sets/07_sets.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [Day 6:](#day-6)
  - [Tuples](#tuples)
    - [Creating a Tuple](#creating-a-tuple)
    - [Tuple length](#tuple-length)
    - [Accessing Tuple Items](#accessing-tuple-items)
    - [Slicing tuples](#slicing-tuples)
    - [Changing Tuples to Lists](#changing-tuples-to-lists)
    - [Checking an Item in a Tuple](#checking-an-item-in-a-tuple)
    - [Joining Tuples](#joining-tuples)
    - [Deleting Tuples](#deleting-tuples)
  - [💻 Exercises: Day 6](#-exercises-day-6)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)

# Day 6:

## Tuples

Una tupla es una colección de diferentes tipos de datos que está ordenada y es inmutable. Las tuplas se escriben con corchetes, (). Una vez creada una tupla, no podemos cambiar sus valores. No podemos utilizar los métodos add, insert, remove en una tupla porque no es modificable (mutable). A diferencia de las listas, las tuplas tienen pocos métodos. Métodos relacionados con las tuplas:

- tuple(): para crear una tupla vacía
- count(): para contar el número de un elemento especificado en una tupla
- index(): para encontrar el índice de un elemento especificado en una tupla
- Operador +: para unir dos o más tuplas y crear una nueva tupla

### Creating a Tuple

- Empty tuple: Creación de una tupla vacía
  
  ```py
  # syntax
  empty_tuple = ()
  # o utilizando el constructor de tuplas
  empty_tuple = tuple()
  ```

- Tuple con valores iniciales
  
  ```py
  # syntax
  tpl = ('item1', 'item2','item3')
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  ```

### Tuple length

Utilizamos el método _len()_ para obtener la longitud de una tupla.

```py
# syntax
tpl = ('item1', 'item2', 'item3')
len(tpl)
```

### Accessing Tuple Items

- Indexación positiva Al igual que el tipo de datos lista, utilizamos la indexación positiva o negativa para acceder a los elementos de las tuplas.

  ![Accessing tuple items](../images/tuples_index.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3')
  first_item = tpl[0]
  second_item = tpl[1]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[0]
  second_fruit = fruits[1]
  last_index =len(fruits) - 1
  last_fruit = fruits[las_index]
  ```
  
 - La indexación negativa significa que empezando por el final, -1 se refiere al último elemento, -2 se refiere al penúltimo y el negativo de la longitud de la lista/tupla se refiere al primer elemento.

  ![Tuple Negative indexing](../images/tuple_negative_indexing.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  first_item = tpl[-4]
  second_item = tpl[-3]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[-4]
  second_fruit = fruits[-3]
  last_fruit = fruits[-1]
  ```

### Slicing tuples

Podemos cortar un sub-tuple especificando un rango de índices donde empezar y donde terminar en la tupla, el valor de retorno será una nueva tupla con los elementos especificados.

- Rango de índices positivos

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[0:4]         # todos los items
  all_items = tpl[0:]         # todos los items
  middle_two_items = tpl[1:3]  # no incluye el elemento del índice 3
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[0:4]    # todos los items
  all_fruits= fruits[0:]      # todos los items
  orange_mango = fruits[1:3]  # no incluye el item del índice 3
  orange_to_the_rest = fruits[1:]
  ```

- Rango de índices negativos

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[-4:]         # all items
  middle_two_items = tpl[-3:-1]  # does not include item at index 3 (-1)
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[-4:]    # all items
  orange_mango = fruits[-3:-1]  # doesn't include item at index 3
  orange_to_the_rest = fruits[-3:]
  ```

### Changing Tuples to Lists

Podemos cambiar tuplas a listas y listas a tuplas. La tupla es inmutable si queremos modificar una tupla debemos cambiarla por una lista.

```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
lst = list(tpl)
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
fruits = list(fruits)
fruits[0] = 'apple'
print(fruits)     # ['apple', 'orange', 'mango', 'lemon']
fruits = tuple(fruits)
print(fruits)     # ('apple', 'orange', 'mango', 'lemon')
```

### Checking an Item in a Tuple

Podemos comprobar si un elemento existe o no en una tupla utilizando _in_, que devuelve un booleano.

```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
'item2' in tpl # True
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
print('orange' in fruits) # True
print('apple' in fruits) # False
fruits[0] = 'apple' # TypeError: 'tuple' object does not support item assignment
```

### Joining Tuples

Podemos unir dos o más tuplas utilizando el operador +

```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
tpl2 = ('item4', 'item5','item6')
tpl3 = tpl1 + tpl2
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
vegetables = ('Tomato', 'Potato', 'Cabbage','Onion', 'Carrot')
fruits_and_vegetables = fruits + vegetables
```

### Deleting Tuples

No es posible eliminar un solo elemento de una tupla, pero sí es posible eliminar la propia tupla utilizando _del_.

```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
del tpl1

```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
del fruits
```

🌕 Eres muy valiente, has llegado hasta aquí. Acabas de completar el sexto día de desafíos y estás a seis pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y para tus músculos.

## 💻 Exercises: Day 6

### Exercises: Level 1

1. Crear una tupla vacía
2. Crea una tupla que contenga los nombres de tus hermanas y hermanos (los hermanos imaginarios están bien)
3. Unir las tuplas hermanos y hermanas y asignarlas a los hermanos
4. ¿Cuántos hermanos tienes?
5. Modifica la tupla siblings y añade el nombre de tu padre y tu madre y asígnalo a family_members

### Exercises: Level 2

1. Desempaquetar hermanos y padres de family_members
2. Crea las tuplas frutas, verduras y productos animales. Unir las tres tuplas y asignarlas a una variable llamada food_stuff_tp.
3. Cambiar la tupla about food_stuff_tp por una lista food_stuff_lt
4. Extraiga el elemento o elementos del medio de la tupla food_stuff_tp o de la lista food_stuff_lt.
5. Corte los tres primeros elementos y los tres últimos elementos de la lista food_staff_lt
6. Elimine la tupla food_staff_tp por completo
7. Compruebe si existe un elemento en la tupla:

- Compruebe si "Estonia" es un país nórdico
- Compruebe si "Iceland" es un país nórdico

  ```py
  nordic_countries = ('Denmark', 'Finland','Iceland', 'Norway', 'Sweden')
  ```


[<< Day 5](../05_Day_Lists/05_lists.md) | [Day 7 >>](../07_Day_Sets/07_sets.md)
