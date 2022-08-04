<div align="center">
  <h1> 30 Days Of Python: Day 7 - Sets</h1>
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

[<< Day 6](../06_Day_Tuples/06_tuples.md) | [Day 8 >>](../08_Day_Dictionaries/08_dictionaries.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 Day 7](#-day-7)
  - [Sets](#sets)
    - [Creating a Set](#creating-a-set)
    - [Getting Set's Length](#getting-sets-length)
    - [Accessing Items in a Set](#accessing-items-in-a-set)
    - [Checking an Item](#checking-an-item)
    - [Adding Items to a Set](#adding-items-to-a-set)
    - [Removing Items from a Set](#removing-items-from-a-set)
    - [Clearing Items in a Set](#clearing-items-in-a-set)
    - [Deleting a Set](#deleting-a-set)
    - [Converting List to Set](#converting-list-to-set)
    - [Joining Sets](#joining-sets)
    - [Finding Intersection Items](#finding-intersection-items)
    - [Checking Subset and Super Set](#checking-subset-and-super-set)
    - [Checking the Difference Between Two Sets](#checking-the-difference-between-two-sets)
    - [Finding Symmetric Difference Between Two Sets](#finding-symmetric-difference-between-two-sets)
    - [Joining Sets](#joining-sets-1)
  - [💻 Exercises: Day 7](#-exercises-day-7)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📘 Day 7

## Sets

Un Set (conjunto) es una colección de elementos. Permíteme que te lleve de vuelta a tu lección de matemáticas de la escuela primaria o secundaria. La definición matemática de un conjunto se puede aplicar también en Python. Un conjunto es una colección de elementos distintos no ordenados y no indexados. En Python el conjunto se utiliza para almacenar elementos únicos, y es posible encontrar la _union_, _intersection_, _difference_, _symmetric difference_, _subset_, _super set_ y  _disjoint set_ entre conjuntos.

### Creating a Set

Utilizamos llaves, {} para crear un conjunto o la función integrada *set()*.

- Creación de un conjunto vacío

```py
# syntax
st = {}
# or
st = set()
```

- Creación de un conjunto con elementos iniciales

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
```

**Example:**

```py
# syntax
fruits = {'banana', 'orange', 'mango', 'lemon'}
```

### Getting Set's Length

Utilizamos el método **len()** para encontrar la longitud de un conjunto.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
len(set)
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
len(fruits)
```

### Accessing Items in a Set

Utilizamos bucles para acceder a los elementos. Lo veremos en la sección de bucles

### Checking an Item

Para comprobar si un elemento existe en una lista utilizamos el operador de pertenencia _in_.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
print("Does set st contain item3? ", 'item3' in st) # ¿El set st contiene el item3? Verdadero
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
print('mango' in fruits ) # True
```

### Adding Items to a Set

Una vez creado un conjunto, no podemos cambiar ningún elemento y también podemos añadir elementos adicionales.

- Add one item using _add()_

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.add('item5')
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.add('lime')
```

- Añadir múltiples elementos mediante _update()_
  La función *update()* permite añadir múltiples elementos a un conjunto. La función *update()* toma un argumento de lista.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.update(['item5','item6','item7'])
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = ('tomato', 'potato', 'cabbage','onion', 'carrot')
fruits.update(vegetables)
```

### Removing Items from a Set

Podemos eliminar un elemento de un conjunto utilizando el método _remove()_. Si el elemento no se encuentra, el método _remove()_ dará lugar a errores, por lo que es bueno comprobar si el elemento existe en el conjunto dado. Sin embargo, el método _discard()_ no genera ningún error.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.remove('item2')
```

Los métodos pop() eliminan un elemento aleatorio de una lista y devuelven el elemento eliminado.

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.pop()  # elimina un elemento aleatorio del conjunto
```

Si estamos interesados en el elemento eliminado.

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
removed_item = fruits.pop() 
```


### Clearing Items in a Set

Si queremos borrar o vaciar el conjunto utilizamos el método _clear_.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.clear()
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.clear()
print(fruits) # set()
```

### Deleting a Set

Si queremos borrar el propio conjunto utilizamos el operador _del_.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
del st
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
del fruits
```

### Converting List to Set

Podemos convertir lista en conjunto y conjunto en lista. La conversión de lista a conjunto elimina los duplicados y sólo se reservarán los elementos únicos.

```py
# syntax
lst = ['item1', 'item2', 'item3', 'item4', 'item1']
st = set(lst)  # {'item2', 'item4', 'item1', 'item3'} - the order is random, because sets in general are unordered
```

**Example:**

```py
fruits = ['banana', 'orange', 'mango', 'lemon','orange', 'banana']
fruits = set(fruits) # {'mango', 'lemon', 'banana', 'orange'}
```

### Joining Sets

Podemos unir dos conjuntos utilizando el método _union()_ o _update()_.

- Union -> Este método devuelve un nuevo conjunto

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st3 = st1.union(st2)
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
print(fruits.union(vegetables)) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

- Update
  Este método inserta un conjunto en un conjunto dado

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st1.update(st2) # st2 contents are added to st1
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
fruits.update(vegetables)
print(fruits) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

### Finding Intersection Items

La intersección devuelve un conjunto de elementos que están en ambos conjuntos. Véase el ejemplo

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item3', 'item2'}
st1.intersection(st2) # {'item3', 'item2'}
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.intersection(even_numbers) # {0, 2, 4, 6, 8, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.intersection(dragon)     # {'o', 'n'}
```

### Checking Subset and Super Set

Un set puede ser un subset o un super set de otros sets:

- Subset: _issubset()_
- Super set: _issuperset_

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.issubset(st1) # True
st1.issuperset(st2) # True
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.issubset(even_numbers) # False, because it is a super set
whole_numbers.issuperset(even_numbers) # True

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.issubset(dragon)     # False
```

### Checking the Difference Between Two Sets

Devuelve la diferencia entre dos conjuntos.

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.difference(st1) # set()
st1.difference(st2) # {'item1', 'item4'} => st1\st2
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.difference(even_numbers) # {1, 3, 5, 7, 9}

python = {'p', 'y', 't', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.difference(dragon)     # {'p', 'y', 't'}  - the result is unordered (characteristic of sets)
dragon.difference(python)     # {'d', 'r', 'a', 'g'}
```

### Finding Symmetric Difference Between Two Sets

Devuelve la diferencia simétrica entre dos conjuntos. Significa que devuelve un conjunto que contiene todos los elementos de ambos conjuntos, excepto los elementos que están presentes en ambos conjuntos, matemáticamente: (A\B) ∪ (B\A)

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
# it means (A\B)∪(B\A)
st2.symmetric_difference(st1) # {'item1', 'item4'}
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
some_numbers = {1, 2, 3, 4, 5}
whole_numbers.symmetric_difference(some_numbers) # {0, 6, 7, 8, 9, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.symmetric_difference(dragon)  # {'r', 't', 'p', 'y', 'g', 'a', 'd', 'h'}
```

### Joining Sets

Si dos conjuntos no tienen un elemento o elementos comunes los llamamos conjuntos disjuntos. Podemos comprobar si dos conjuntos son conjuntos o disjuntos utilizando el método _isdisjoint()_.

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.isdisjoint(st1) # False
```

**Example:**

```py
even_numbers = {0, 2, 4 ,6, 8}
even_numbers = {1, 3, 5, 7, 9}
even_numbers.isdisjoint(odd_numbers) # True, porque ningún elemento común

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.isdisjoint(dragon)  # False, hay elementos comunes {'o', 'n'}
```

🌕 Eres una estrella en ascenso. Acabas de completar los desafíos del día 7 y estás 7 pasos adelante en tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Exercises: Day 7

```py
# sets
it_companies = {'Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'}
A = {19, 22, 24, 20, 25, 26}
B = {19, 22, 20, 25, 26, 24, 28, 27}
age = [22, 19, 24, 25, 26, 24, 25, 24]
```

### Exercises: Level 1

1. Hallar la longitud del conjunto it_companies
2. Añadir 'Twitter' a it_companies
3. Insertar varias empresas IT a la vez en el conjunto it_companies
4. Eliminar una de las empresas del conjunto it_companies
5. Cuál es la diferencia entre eliminar y descartar

### Exercises: Level 2

1. Unir A y B
2. Encuentre la intersección de A con B
3. Es A subconjunto de B
4. ¿Son A y B conjuntos disjuntos?
5. Une A con B y B con A
6. Cuál es la diferencia simétrica entre A y B
7. Elimina los conjuntos por completo

### Exercises: Level 3

1. Convierte las edades en un conjunto y compara la longitud de la lista y del conjunto, ¿cuál es mayor?
2. Explica la diferencia entre los siguientes tipos de datos: cadena, lista, tupla y conjunto
3. _I am a teacher and I love to inspire and teach people._ ¿Cuántas palabras únicas se han utilizado en la frase? Utiliza los métodos de división y conjunto para obtener las palabras únicas.


🎉 CONGRATULATIONS ! 🎉

[<< Day 6](../06_Day_Tuples/06_tuples.md) | [Day 8 >>](../08_Day_Dictionaries/08_dictionaries.md)
