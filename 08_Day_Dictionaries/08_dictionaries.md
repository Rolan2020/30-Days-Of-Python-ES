<div align="center">
  <h1> 30 Days Of Python: Day 8 - Dictionaries</h1>
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

[<< Day 7 ](../07_Day_Sets/07_sets.md) | [Day 9 >>](../09_Day_Conditionals/09_conditionals.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 Day 8](#-day-8)
  - [Dictionaries](#dictionaries)
    - [Creating a Dictionary](#creating-a-dictionary)
    - [Dictionary Length](#dictionary-length)
    - [Accessing Dictionary Items](#accessing-dictionary-items)
    - [Adding Items to a Dictionary](#adding-items-to-a-dictionary)
    - [Modifying Items in a Dictionary](#modifying-items-in-a-dictionary)
    - [Checking Keys in a Dictionary](#checking-keys-in-a-dictionary)
    - [Removing Key and Value Pairs from a Dictionary](#removing-key-and-value-pairs-from-a-dictionary)
    - [Changing Dictionary to a List of Items](#changing-dictionary-to-a-list-of-items)
    - [Clearing a Dictionary](#clearing-a-dictionary)
    - [Deleting a Dictionary](#deleting-a-dictionary)
    - [Copy a Dictionary](#copy-a-dictionary)
    - [Getting Dictionary Keys as a List](#getting-dictionary-keys-as-a-list)
    - [Getting Dictionary Values as a List](#getting-dictionary-values-as-a-list)
  - [💻 Exercises: Day 8](#-exercises-day-8)

# 📘 Day 8

## Dictionaries

Un diccionario es una colección de datos desordenados, modificables (mutable) y emparejados (key: value).


### Creating a Dictionary

Para crear un diccionario utilizamos corchetes, {} o la función incorporada *dict()*.

```py
# syntax
empty_dict = {}
# Diccionario con valores de datos
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
```

El diccionario anterior muestra que un valor puede ser de cualquier tipo de datos: string, boolean, list, tuple, set o un dictionary.

### Dictionary Length

Comprueba el número de pares 'key: value' en el diccionario.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(len(dct)) # 4
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(len(person)) # 7

```

### Accessing Dictionary Items

Podemos acceder a los elementos del diccionario haciendo referencia a su key name (nombre clave).

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct['key1']) # value1
print(dct['key4']) # value4
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person['first_name']) # Asabeneh
print(person['country'])    # Finland
print(person['skills'])     # ['JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person['skills'][0])  # JavaScript
print(person['address']['street']) # Space street
print(person['city'])       # Error
```

Acceder a un elemento por el nombre de la key genera un error si la key no existe. Para evitar este error primero tenemos que comprobar si la key existe o podemos utilizar el método _get_. El método get devuelve None, que es un tipo de datos del objeto NoneType, si la key no existe.
```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person.get('first_name')) # Asabeneh
print(person.get('country'))    # Finland
print(person.get('skills')) #['HTML','CSS','JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person.get('city'))   # None
```

### Adding Items to a Dictionary

Podemos añadir nuevos pares de key y valores a un diccionario

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key5'] = 'value5'
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
        }
}
person['job_title'] = 'Instructor'
person['skills'].append('HTML')
print(person)
```

### Modifying Items in a Dictionary

Podemos modificar los elementos de un diccionario

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key1'] = 'value-one'
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person['first_name'] = 'Eyob'
person['age'] = 252
```

### Checking Keys in a Dictionary

 _in_ -> para comprobar si una key existe en un diccionario

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print('key2' in dct) # True
print('key5' in dct) # False
```

### Removing Key and Value Pairs from a Dictionary
(Eliminación de pares de keys y valores de un diccionario)

- _pop(key)_: elimina el elemento con el nombre key especificado:
- _popitem()_: elimina el último elemento
- _del_: elimina un elemento con el nombre key especificado

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.pop('key1') # Elimina el elemento key1
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.popitem() # elimina el último elemento
del dct['key2'] # elimina el elemento key2
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person.pop('first_name')        # Elimina el elemento firstname
person.popitem()                # Elimina el elemento address
del person['is_married']        # Elimina el elemento is_married
```

### Changing Dictionary to a List of Items
(Cambiar el diccionario por una lista de elementos)

El método _items()_ cambia el diccionario por una lista de tuplas.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.items()) # dict_items([('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'), ('key4', 'value4')])
```

### Clearing a Dictionary

Si no queremos los elementos de un diccionario podemos borrarlos usando el método _clear()_.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.clear()) # None
```

### Deleting a Dictionary

If we do not use the dictionary we can delete it completely

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
del dct
```

### Copy a Dictionary

Podemos copiar un diccionario utilizando el método _copy()_. Usando la copia podemos evitar la mutación del diccionario original.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct_copy = dct.copy() # {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

### Getting Dictionary Keys as a List

El método _keys()_ nos da todas las keys de un diccionario como una lista.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
keys = dct.keys()
print(keys)     # dict_keys(['key1', 'key2', 'key3', 'key4'])
```

### Getting Dictionary Values as a List

El método _values_ nos da todos los valores de un diccionario como una lista.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
values = dct.values()
print(values)     # dict_values(['value1', 'value2', 'value3', 'value4'])
```

🌕 Eres asombroso. Ahora, estás súper cargado con el poder de los diccionarios. Acabas de completar los desafíos del día 8 y estás a 8 pasos de tu camino a la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Exercises: Day 8

1. Crear un diccionario vacío llamado perro
2. Añade nombre, color, raza, patas y edad al diccionario de perros
3. Cree un diccionario de estudiantes y añada nombre, apellido, sexo, edad, estado civil, habilidades, país, ciudad y dirección como keys del diccionario
4. Obtenga la longitud del diccionario del estudiante
5. Obtenga el valor de las habilidades y compruebe el tipo de datos, debe ser una lista
6. Modifica los valores de las habilidades añadiendo una o dos habilidades
7. Obtenga las keys del diccionario como una lista
8. Obtener los valores del diccionario como una lista
9. Cambiar el diccionario a una lista de tuplas utilizando el método _items()_.
10. Eliminar uno de los elementos del diccionario
11. Borrar uno de los diccionarios

🎉 CONGRATULATIONS ! 🎉

[<< Day 7 ](../07_Day_Sets/07_sets.md) | [Day 9 >>](../09_Day_Conditionals/09_conditionals.md)
