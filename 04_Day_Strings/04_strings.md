<div align="center">
  <h1> 30 Days Of Python: Day 4 - Strings</h1>
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

[<< Day 3](../03_Day_Operators/03_operators.md) | [Day 5 >>](../05_Day_Lists/05_lists.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [Day 4](#day-4)
  - [Strings](#strings)
    - [Creating a String](#creating-a-string)
    - [String Concatenation](#string-concatenation)
    - [Escape Sequences in Strings](#escape-sequences-in-strings)
    - [String formatting](#string-formatting)
      - [Old Style String Formatting (% Operator)](#old-style-string-formatting--operator)
      - [New Style String Formatting (str.format)](#new-style-string-formatting-strformat)
      - [String Interpolation / f-Strings (Python 3.6+)](#string-interpolation--f-strings-python-36)
    - [Python Strings as Sequences of Characters](#python-strings-as-sequences-of-characters)
      - [Unpacking Characters](#unpacking-characters)
      - [Accessing Characters in Strings by Index](#accessing-characters-in-strings-by-index)
      - [Slicing Python Strings](#slicing-python-strings)
      - [Reversing a String](#reversing-a-string)
      - [Skipping Characters While Slicing](#skipping-characters-while-slicing)
    - [String Methods](#string-methods)
  - [💻 Exercises - Day 4](#-exercises---day-4)

# Day 4

## Strings

El texto es un tipo de datos string. Cualquier tipo de dato escrito como texto es una string. Cualquier dato bajo comillas simples, dobles o triples son strings. Hay diferentes métodos de stringy funciones incorporadas para tratar los tipos de datos de string. Para comprobar la longitud de una string se utiliza el método **len()**.

### Creating a String

```py
letter = 'P'                # Una string puede ser un solo carácter o un grupo de textos
print(letter)               # P
print(len(letter))          # 1
greeting = 'Hello, World!'  # String puede hacerse con comillas simples o dobles,"Hello, World!"
print(greeting)             # Hello, World!
print(len(greeting))        # 13
sentence = "I hope you are enjoying 30 days of Python Challenge"
print(sentence)
```

El string multilínea se crea utilizando tres comillas simples (''') o tres comillas dobles ("""). Véase el ejemplo siguiente.

```py
multiline_string = '''Soy profesor y disfruto enseñando.
No encontré nada tan gratificante como capacitar a la gente.
Por eso he creado 30 días de python.'''
print(multiline_string)

# Another way of doing the same thing
multiline_string = """Soy profesor y disfruto enseñando.
No encontré nada tan gratificante como capacitar a la gente.
Por eso he creado 30 días de python."""
print(multiline_string)
```

### String Concatenation

Podemos conectar strings entre sí. La fusión o conexión de strings se denomina concatenación. Example:
```py
first_name = 'Asabeneh'
last_name = 'Yetayeh'
space = ' '
full_name = first_name  +  space + last_name
print(full_name) # Asabeneh Yetayeh
# Comprobación de la longitud de un string utilizando la función  len()
print(len(first_name))  # 8
print(len(last_name))   # 7
print(len(first_name) > len(last_name)) # True
print(len(full_name)) # 16
```

### Escape Sequences in Strings

En Python y otros lenguajes de programación, un carácter seguido de otro es una secuencia de escape. Veamos los caracteres de escape más comunes:

- \n: nueva línea
- \t: significa Tab (8 spaces)
- \\\\: Back slash
- \\': comilla simple (')
- \\": Doble comilla (")

Ahora, veamos el uso de las secuencias de escape anteriores con ejemplos.

```py
print('Espero que todo el mundo esté disfrutando del Reto Python.) # salto de línea
print('Days\tTopics\tExercises') # añadir un espacio de tabulación o 4 espacios 
print('Day 1\t3\t5')
print('Day 2\t3\t5')
print('Day 3\t3\t5')
print('Day 4\t3\t5')
print('Este es un símbolo de barra invertida (\\)') # Para escribir una barra invertida
print('En todos los lenguajes de programación se empieza por \"Hello, World!\"') # para escribir una comilla doble dentro de una comilla simple

# salida
Espero que todos estén disfrutando del Reto Python.

Days	Topics	Exercises
Day 1	5	    5
Day 2	6	    20
Day 3	5	    23
Day 4	1	    35
Esto es un símbolo de barra invertida (\)
En todos los lenguajes de programación se empieza por "Hello, World!"
```

### String formatting

#### Old Style String Formatting (% Operator)

En Python hay muchas formas de formatear Strings. En esta sección, cubriremos algunas de ellas.
El operador "%" se utiliza para formatear un conjunto de variables encerradas en una "tupla" (una lista de tamaño fijo), junto con un string de formato, que contiene texto normal junto con "argument specifiers", símbolos especiales como "%s", "%d", "%f", "%.<small>number of digits</small>f".

- %s - String (o cualquier objeto con representación de string, como los números)
- %d - Números enteros
- %f - Números de coma flotante
- "%.<small>number of digits</small>f" - Números de coma flotante con precisión fija

```py
# Solo Strings
first_name = 'Asabeneh'
last_name = 'Yetayeh'
language = 'Python'
formated_string = 'I am %s %s. I teach %s' %(first_name, last_name, language)
print(formated_string)

# Strings  y  numeros
radius = 10
pi = 3.14
area = pi * radius ** 2
formated_string = 'The area of circle with a radius %d is %.2f.' %(radius, area) # 2 se refiere a los dos dígitos significativos después del punto

python_libraries = ['Django', 'Flask', 'NumPy', 'Matplotlib','Pandas']
formated_string = 'The following are python libraries:%s' % (python_libraries)
print(formated_string) # "Las siguientes son bibliotecas de python:['Django', 'Flask', 'NumPy', 'Matplotlib','Pandas']"
```

#### New Style String Formatting (str.format)

Este formato se introduce en la versión 3 de Python.

```py

first_name = 'Asabeneh'
last_name = 'Yetayeh'
language = 'Python'
formated_string = 'I am {} {}. I teach {}'.format(first_name, last_name, language)
print(formated_string)
a = 4
b = 3

print('{} + {} = {}'.format(a, b, a + b))
print('{} - {} = {}'.format(a, b, a - b))
print('{} * {} = {}'.format(a, b, a * b))
print('{} / {} = {:.2f}'.format(a, b, a / b)) # lo limita a dos dígitos después del decimal
print('{} % {} = {}'.format(a, b, a % b))
print('{} // {} = {}'.format(a, b, a // b))
print('{} ** {} = {}'.format(a, b, a ** b))

# output
4 + 3 = 7
4 - 3 = 1
4 * 3 = 12
4 / 3 = 1.33
4 % 3 = 1
4 // 3 = 1
4 ** 3 = 64

# Strings  and numbers
radius = 10
pi = 3.14
area = pi * radius ** 2
formated_string = 'The area of a circle with a radius {} is {:.2f}.'.format(radius, area) # 2 dígitos después del decimal
print(formated_string)

```

#### String Interpolation / f-Strings (Python 3.6+)

Otro nuevo formato de string es la interpolación de strings, f-strings. Las string empiezan por f y podemos inyectar los datos en sus posiciones correspondientes.

```py
a = 4
b = 3
print(f'{a} + {b} = {a +b}')
print(f'{a} - {b} = {a - b}')
print(f'{a} * {b} = {a * b}')
print(f'{a} / {b} = {a / b:.2f}')
print(f'{a} % {b} = {a % b}')
print(f'{a} // {b} = {a // b}')
print(f'{a} ** {b} = {a ** b}')
```

### Python Strings as Sequences of Characters

Los strings de Python son secuencias de caracteres, y comparten sus métodos básicos de acceso con otras secuencias ordenadas de objetos de Python: listas y tuplas. La forma más sencilla de extraer caracteres individuales de las cadenas (y miembros individuales de cualquier secuencia) es desempaquetarlos en las variables correspondientes.

#### Unpacking Characters

```
language = 'Python'
a,b,c,d,e,f = language # unpacking secuencias de caracteres en variables
print(a) # P
print(b) # y
print(c) # t
print(d) # h
print(e) # o
print(f) # n
```

#### Accessing Characters in Strings by Index

En programación, el conteo comienza desde cero. Por lo tanto, la primera letra de una cadena está en el índice cero y la última letra de una cadena es la longitud de una cadena menos uno.

![String index](../images/string_index.png)

```py
language = 'Python'
first_letter = language[0]
print(first_letter) # P
second_letter = language[1]
print(second_letter) # y
last_index = len(language) - 1
last_letter = language[last_index]
print(last_letter) # n
```

Si queremos empezar por el extremo derecho podemos utilizar la indexación negativa. -1 es el último índice.

```py
language = 'Python'
last_letter = language[-1]
print(last_letter) # n
second_last = language[-2]
print(second_last) # o
```

#### Slicing Python Strings

En python podemos cortar strings en substrings.

```py
language = 'Python'
first_three = language[0:3] # comienza en el índice 0 y hasta 3 pero no incluye 3
print(first_three) #Pyt
last_three = language[3:6]
print(last_three) # hon
# Otra forma
last_three = language[-3:]
print(last_three)   # hon
last_three = language[3:]
print(last_three)   # hon
```

#### Reversing a String

Podemos invertir fácilmente las cadenas en python.

```py
greeting = 'Hello, World!'
print(greeting[::-1]) # !dlroW ,olleH
```

#### Skipping Characters While Slicing

Es posible omitir caracteres mientras se corta pasando el argumento del paso al método de corte.

```py
language = 'Python'
pto = language[0:6:2] #
print(pto) # Pto
```

### String Methods

Hay muchos métodos de cadena que nos permiten formatear cadenas. Vea algunos de los métodos de cadena en el siguiente ejemplo:

- capitalize(): Convierte el primer carácter del string en mayúscula

```py
challenge = 'thirty days of python'
print(challenge.capitalize()) # 'Thirty days of python'
```

- count(): retorna ocurrencias de substring en string, count(substring, start=.., end=..). El inicio es un índice inicial para contar y el final es el último índice para contar.

```py
challenge = 'thirty days of python'
print(challenge.count('y')) # 3
print(challenge.count('y', 7, 14)) # 1, 
print(challenge.count('th')) # 2`
```

- endswith(): Comprueba si un string termina con un final especificado

```py
challenge = 'thirty days of python'
print(challenge.endswith('on'))   # True
print(challenge.endswith('tion')) # False
```

- expandtabs(): Reemplaza el carácter de tabulación por espacios, el tamaño de tabulación por defecto es 8. Toma el argumento de tamaño de tabulación

```py
challenge = 'thirty\tdays\tof\tpython'
print(challenge.expandtabs())   # 'thirty  days    of      python'
print(challenge.expandtabs(10)) # 'thirty    days      of        python'
```

- find(): Devuelve el índice de la 1ra ocurrencia de una subcadena, si no se encuentra devuelve -1

```py
challenge = 'thirty days of python'
print(challenge.find('y'))  # 16
print(challenge.find('th')) # 17
```

- rfind(): Devuelve el índice de la última aparición de una subcadena, si no se encuentra devuelve -1

```py
challenge = 'thirty days of python'
print(challenge.rfind('y'))  # 5
print(challenge.rfind('th')) # 1
```

- format(): formatea el string en una salida más agradable  
   Para más info sobre el formato de strings consulte -> [link](https://www.programiz.com/python-programming/methods/string/format)

```py
first_name = 'Asabeneh'
last_name = 'Yetayeh'
age = 250
job = 'teacher'
country = 'Finland'
sentence = 'I am {} {}. I am a {}. I am {} years old. I live in {}.'.format(first_name, last_name, age, job, country)
print(sentence) # I am Asabeneh Yetayeh. I am 250 years old. I am a teacher. I live in Finland.

radius = 10
pi = 3.14
area = pi * radius ** 2
result = 'The area of a circle with radius {} is {}'.format(str(radius), str(area))
print(result) # The area of a circle with radius 10 is 314
```

- index(): Devuelve el índice más bajo de una subcadena, los argumentos adicionales indican el índice inicial y final (por defecto 0 y la longitud de la cadena - 1). Si no se encuentra la subcadena, genera un valueError. 

```py
challenge = 'thirty days of python'
sub_string = 'da'
print(challenge.index(sub_string))  # 7
print(challenge.index(sub_string, 9)) # error
```

- rindex(): Devuelve el índice más alto de una subcadena, los argumentos adicionales indican el índice inicial y final (por defecto 0 y longitud de la cadena - 1)

```py
challenge = 'thirty days of python'
sub_string = 'da'
print(challenge.rindex(sub_string))  # 8
print(challenge.rindex(sub_string, 9)) # error
```

- isalnum(): Comprueba los caracteres alfanuméricos

```py
challenge = 'ThirtyDaysPython'
print(challenge.isalnum()) # True

challenge = '30DaysPython'
print(challenge.isalnum()) # True

challenge = 'thirty days of python'
print(challenge.isalnum()) # False, el espacio no es un carácter alfanumérico

challenge = 'thirty days of python 2019'
print(challenge.isalnum()) # False
```

- isalpha(): Comprueba si todos los elementos del string son caracteres del alfabeto (a-z and A-Z)

```py
challenge = 'thirty days of python'
print(challenge.isalpha()) # False, el espacio se excluye una vez más
challenge = 'ThirtyDaysPython'
print(challenge.isalpha()) # True
num = '123'
print(num.isalpha())      # False
```

- isdecimal(): Comprueba si todos los caracteres de una cadena son decimales (0-9)

```py
challenge = 'thirty days of python'
print(challenge.isdecimal())  # False
challenge = '123'
print(challenge.isdecimal())  # True
challenge = '\u00B2'
print(challenge.isdigit())   # False
challenge = '12 3'
print(challenge.isdecimal())  # False, space not allowed
```

- isdigit(): Comprueba si todos los caracteres de un string son números (0-9 y algunos otros caracteres unicode para los números)

```py
challenge = 'Thirty'
print(challenge.isdigit()) # False
challenge = '30'
print(challenge.isdigit())   # True
challenge = '\u00B2'
print(challenge.isdigit())   # True
```

- isnumeric(): Comprueba si todos los caracteres de un string son números o están relacionados con ellos (al igual que isdigit(), sólo acepta más símbolos, como ½)

```py
num = '10'
print(num.isnumeric()) # True
num = '\u00BD' # ½
print(num.isnumeric()) # True
num = '10.5'
print(num.isnumeric()) # False
```

- isidentifier(): Comprueba un identificador válido - comprueba si un string es un nombre de variable válido

```py
challenge = '30DaysOfPython'
print(challenge.isidentifier()) # False, porque comienza con un número
challenge = 'thirty_days_of_python'
print(challenge.isidentifier()) # True
```

- islower(): Comprueba si todos los caracteres del alfabeto del string están en minúsculas

```py
challenge = 'thirty days of python'
print(challenge.islower()) # True
challenge = 'Thirty days of python'
print(challenge.islower()) # False
```

- isupper(): Comprueba si todos los caracteres del alfabeto del string están en mayúsculas

```py
challenge = 'thirty days of python'
print(challenge.isupper()) #  False
challenge = 'THIRTY DAYS OF PYTHON'
print(challenge.isupper()) # True
```

- join(): Devuelve un string concatenado

```py
web_tech = ['HTML', 'CSS', 'JavaScript', 'React']
result = ' '.join(web_tech)
print(result) # 'HTML CSS JavaScript React'
```

```py
web_tech = ['HTML', 'CSS', 'JavaScript', 'React']
result = '# '.join(web_tech)
print(result) # 'HTML# CSS# JavaScript# React'
```

- strip(): Elimina todos los caracteres dados empezando por el principio y el final del string

```py
challenge = 'thirty days of pythoonnn'
print(challenge.strip('noth')) # 'irty days of py'
```

- replace(): Sustituye un substring por un string dado

```py
challenge = 'thirty days of python'
print(challenge.replace('python', 'coding')) # 'thirty days of coding'
```

- split(): Divide el string, utilizando el string dado o el espacio como separador

```py
challenge = 'thirty days of python'
print(challenge.split()) # ['thirty', 'days', 'of', 'python']
challenge = 'thirty, days, of, python'
print(challenge.split(', ')) # ['thirty', 'days', 'of', 'python']
```

- title(): Devuelve un string como título

```py
challenge = 'thirty days of python'
print(challenge.title()) # Thirty Days Of Python
```

- swapcase(): Convierte todos los caracteres en mayúsculas en minúsculas y todos los caracteres en minúsculas en mayúsculas

```py
challenge = 'thirty days of python'
print(challenge.swapcase())   # THIRTY DAYS OF PYTHON
challenge = 'Thirty Days Of Python'
print(challenge.swapcase())  # tHIRTY dAYS oF pYTHON
```

- startswith(): Comprueba si el string comienza con el string especificado

```py
challenge = 'thirty days of python'
print(challenge.startswith('thirty')) # True

challenge = '30 days of python'
print(challenge.startswith('thirty')) # False
```

🌕 Eres una persona extraordinaria y tienes un potencial extraordinario. Acabas de completar los desafíos del día 4 y estás a cuatro pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Exercises - Day 4

1. Concatenar el string 'Thirty', 'Days', 'Of', 'Python' a un solo string, 'Thirty Days Of Python'.
2. Concatenar la cadena 'Coding', 'For' , 'All' a un solo string, 'Coding For All'.
3. Declarar una variable llamada empresa y asignarle un valor inicial "Coding For All".
4. Imprime la empresa variable utilizando _print()_.
5. Imprime la longitud de la cadena de la empresa utilizando el método _len()_ y _print()_.
6. Cambia todos los caracteres a mayúsculas utilizando el método _upper()_.
7. Cambia todos los caracteres a minúsculas utilizando el método _lower()_.
8. Utilice los métodos capitalize(), title(), swapcase() para formatear el valor de la cadena _Coding For All_.
9. Cortar la primera palabra de la cadena _Coding For All_.
10. Compruebe si el string _Coding For All_ contiene una palabra Codificación mediante el método index, find u otros métodos.
11. Sustituir la palabra Coding en la cadena 'Coding For All' por Python.
12. Cambie 'Python for Everyone' a 'Python for All' usando el metodo repalce o otros metodos
13. Dividir la cadena 'Coding For All' utilizando el espacio como separador (split()) .
14. "Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon" dividir la cadena en la coma.
15. Cuál es el carácter en el índice 0 de la cadena _Coding For All_.
16. Cuál es el último índice de la cadena _Coding For All_.
17. ¿Qué carácter está en el índice 10 en el string "Coding For All" .
18. Crear un acrónimo o una abreviatura del nombre 'Python For Everyone'.
19. Crear un acrónimo o una abreviatura del nombre 'Coding For All'.
20. Utilice el índice para determinar la posición de la primera aparición de C en 'Coding For All'.
21. Utilice el índice para determinar la posición de la primera aparición de F en Coding For All.
22. Utilice rfind para determinar la posición de la última aparición de 'l' en 'Coding For All People'.
23. Utilice el índice o la búsqueda para encontrar la posición de la primera aparición de la palabra 'because' en la siguiente frase: 'You cannot end a sentence with because because because is a conjunction'
24. Utilice rindex para encontrar la posición de la última aparición de la palabra 'because' en la siguiente frase: 'You cannot end a sentence with because because because is a conjunction'
25. Cortar la frase 'because because because' en la siguiente frase: 'You cannot end a sentence with because because because is a conjunction'
26. Encuentre la posición de la primera aparición de la palabra 'because' en la siguiente frase: 'You cannot end a sentence with because because because is a conjunction'
27. Cortar la frase 'because because because' en la siguiente frase: 'You cannot end a sentence with because because because is a conjunction'
28. ¿Comienza 'Coding For All' con una subcadena _Codificación_?
29. ¿'Coding For All' termina con una subcadena _codificación_?
30. '&nbsp;&nbsp; Coding For All &nbsp;&nbsp;&nbsp; &nbsp;' &nbsp;, elimina los espacios finales izquierdo y derecho de la cadena dada.
31. Cuál de las siguientes variables devuelve True cuando utilizamos el método isidentifier():
    - 30DaysOfPython
    - thirty_days_of_python
32. La siguiente lista contiene los nombres de algunas de las bibliotecas de Python: ['Django', 'Flask', 'Bottle', 'Pyramid', 'Falcon']. Unir la lista con un hash con cadena de espacio.
33. Utilice la secuencia de escape de línea nueva para separar las siguientes frases.
    ```py
    I am enjoying this challenge.
    I just wonder what is next.
    ```
34. Utilice una secuencia de tab escape para escribir las siguientes líneas.
    ```py
    Name      Age     Country   City
    Asabeneh  250     Finland   Helsinki
    ```
35. Utilice el método de formato de string para mostrar lo siguiente:

```sh
radius = 10
area = 3.14 * radius ** 2
The area of a circle with radius 10 is 314 meters square.
```

36. Haga lo siguiente utilizando métodos de formato de cadena:

```sh
8 + 6 = 14
8 - 6 = 2
8 * 6 = 48
8 / 6 = 1.33
8 % 6 = 2
8 // 6 = 1
8 ** 6 = 262144
```

🎉 CONGRATULATIONS ! 🎉

[<< Day 3](../03_Day_Operators/03_operators.md) | [Day 5 >>](../05_Day_Lists/05_lists.md)


