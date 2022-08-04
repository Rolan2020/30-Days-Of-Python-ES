<div align="center">
  <h1> 30 Days Of Python: Day 3 - Operators</h1>
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

[<< Day 2](../02_Day_Variables_builtin_functions/02_variables_builtin_functions.md) | [Day 4 >>](../04_Day_Strings/04_strings.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 Day 3](#-day-3)
  - [Boolean](#boolean)
  - [Operators](#operators)
    - [Assignment Operators](#assignment-operators)
    - [Arithmetic Operators:](#arithmetic-operators)
    - [Comparison Operators](#comparison-operators)
    - [Logical Operators](#logical-operators)
  - [💻 Exercises - Day 3](#-exercises---day-3)

# 📘 Day 3

## Boolean

Un tipo de dato booleano representa uno de los dos valores: _True_ o _False_. El uso de estos tipos de datos quedará claro una vez que empecemos a utilizar el operador de comparación. La primera letra **T** para Verdadero y **F** para Falso debe ser mayúscula a diferencia de JavaScript.

**Example: Boolean Values**

```py
print(True)
print(False)
```

## Operators

El lenguaje Python soporta varios tipos de operadores. En esta sección, nos centraremos en algunos de ellos.

### Assignment Operators

Los operadores de asignación se utilizan para asignar valores a las variables. Tomemos = como ejemplo. El signo igual en matemáticas muestra que dos valores son iguales, sin embargo en Python significa que estamos almacenando un valor en una determinada variable y lo llamamos asignación o un valor de asignación a una variable. La siguiente tabla muestra los diferentes tipos de operadores de asignación en Python, tomados de [w3school](https://www.w3schools.com/python/python_operators.asp).

![Assignment Operators](../images/assignment_operators.png)

### Arithmetic Operators:

- Adición (+): a + b
- Sustracción (-): a - b
- Multiplicación (*): a * b
- Division (/): a / b
- Módulo (%): a % b
- Floor division (//): a // b (devuelve una aprox entera)
- Potenciacion (**): a ** b

![Arithmetic Operators](../images/arithmetic_operators.png)

**Example:Integers**

```py
# Operaciones aritméticas en Python
# Números enteros

print('Addition: ', 1 + 2)        # 3
print('Subtraction: ', 2 - 1)     # 1
print('Multiplication: ', 2 * 3)  # 6
print ('Division: ', 4 / 2)       # 2.0 división en Python da un número flotante
print('Division: ', 6 / 2)        # 3.0         
print('Division: ', 7 / 2)        # 3.5
print('Division without the remainder: ', 7 // 2)   # 3,  devuelve sin el número flotante o sin el resto
print ('Division without the remainder: ',7 // 3)   # 2
print('Modulus: ', 3 % 2)         # 1, devuelve el resto
print('Exponentiation: ', 2 ** 3) # 9 significa 2 * 2 * 2
```

**Example:Floats**

```py
# Números flotantes
print('Floating Point Number, PI', 3.14)
print('Floating Point Number, gravity', 9.81)
```

**Example:Complex numbers**

```py
# Números complejos
print('Complex number: ', 1 + 1j)
print('Multiplying complex numbers: ',(1 + 1j) * (1 - 1j))
```

Vamos a declarar una variable y asignarle un tipo de dato numérico. Voy a utilizar una variable de un solo carácter, pero recuerda que no debes desarrollar el hábito de declarar este tipo de variables. Los nombres de las variables deben ser siempre nemótecnicos.

**Example:**

```python
# Declarar primero la variable en la parte superior

a = 3 # a es un nombre de variable y 3 es un tipo de dato entero
b = 2 # b es un nombre de variable y 3 es un tipo de dato entero

# Operaciones aritméticas y asignación del resultado a una variable
total = a + b
diff = a - b
product = a * b
division = a / b
remainder = a % b
floor_division = a // b
exponential = a ** b

# Debería haber utilizado la suma en lugar del total, pero la suma es una función incorporada.
print(total) # si no etiquetas el print con algun string, nunca sabrás de dónde viene el resultado
print('a + b = ', total)
print('a - b = ', diff)
print('a * b = ', product)
print('a / b = ', division)
print('a % b = ', remainder)
print('a // b = ', floor_division)
print('a ** b = ', exponentiation)
```

**Example:**

```py
print('== Addition, Subtraction, Multiplication, Division, Modulus ==')

# Declarar los valores y organizarlos juntos
num_one = 3
num_two = 4

# Operaciones aritméticas
total = num_one + num_two
diff = num_two - num_one
product = num_one * num_two
div = num_two / num_one
remainder = num_two % num_one

# Impresión de valores con etiqueta
print('total: ', total)
print('difference: ', diff)
print('product: ', product)
print('division: ', div)
print('remainder: ', remainder)
```

Empecemos a unir los puntos y a utilizar lo que ya sabemos para calcular (area, volume,density,  weight, perimeter, distance, force).

**Example:**

```py
# Calcular el área de un círculo
radius = 10    # radio de un círculo
area_of_circle = 3.14 * radius ** 2    # dos astericos * significa exponente o potencia
print('Area of a circle:', area_of_circle)

# Calcular el área de un rectángulo
length = 10
width = 20
area_of_rectangle = length * width
print('Area of rectangle:', area_of_rectangle)

# Calcular el peso de un objeto
mass = 75
gravity = 9.81
weight = mass * gravity
print(weight, 'N')    # Añadir la unidad al peso

# Calcular la densidad de un líquido
mass = 75 # en Kg
volume = 0.075 # en metro cúbico
density = mass / volume # 1000 Kg/m^3

```

### Comparison Operators

En programación comparamos valores, utilizamos operadores de comparación para comparar dos valores. Comprobamos si un valor es mayor o menor o igual a otro valor. La siguiente tabla muestra los operadores de comparación de Python, tomados de [w3shool](https://www.w3schools.com/python/python_operators.asp).

![Comparison Operators](../images/comparison_operators.png)
**Example: Comparison Operators**

```py
print(3 > 2)     # True, porque 3 es mayor que 2
print(3 >= 2)    # True, porque 3 es mayor que 2
print(3 < 2)     # False, porque 3 es mayor que 2
print(2 < 3)     # True, porque 2 es menos que 3
print(2 <= 3)    # True, porque 2 es menos que 3
print(3 == 2)    # False, porque 3 no es igual a 2
print(3 != 2)    # True, porque 3 no es igual a 2
print(len('mango') == len('avocado'))  # False
print(len('mango') != len('avocado'))  # True
print(len('mango') < len('avocado'))   # True
print(len('milk') != len('meat'))      # False
print(len('milk') == len('meat'))      # True
print(len('tomato') == len('potato'))  # True
print(len('python') > len('dragon'))   # False


# Al comparar algo se obtiene un True o False

print('True == True: ', True == True)
print('True == False: ', True == False)
print('False == False:', False == False)
```

Además del operador de comparación anterior, Python utiliza

- **_is_**: Devuelve true si ambas variables son el mismo objeto(x es y)
- **_is not_**: Devuelve true si ambas variables no son el mismo objeto(x no es y)
- **_in_**: Devuelve True si la lista consultada contiene un determinado elemento(x en y)
- **_not in_**: Devuelve True si la lista consultada no tiene un determinado elemento(x en y)

```py
print('1 is 1', 1 is 1)                   # True - porque los valores de los datos son los mismos
print('1 is not 2', 1 is not 2)           # True - porque 1 no es 2
print('A in Asabeneh', 'A' in 'Asabeneh') # True - A encontrado en la cadena
print('B in Asabeneh', 'B' in 'Asabeneh') # False - no existe la B mayúscula
print('coding' in 'coding for all') # True - porque codificación para todos tiene la palabra codificación
print('a in an:', 'a' in 'an')      # True
print('4 is 2 ** 2:', 4 is 2 ** 2)   # True
```

### Logical Operators

A diferencia de otros lenguajes, python utiliza las palabras clave **_and_**, **_or_** y **_not_** para los operadores lógicos. Los operadores lógicos se utilizan para combinar declaraciones condicionales:

![Logical Operators](../images/logical_operators.png)

```py
print(3 > 2 and 4 > 3) # True - porque ambas afirmaciones son ciertas
print(3 > 2 and 4 < 3) # False - porque la segunda afirmación es falsa
print(3 < 2 and 4 < 3) # False - porque ambas afirmaciones son falsas
print('True and True: ', True and True)
print(3 > 2 or 4 > 3)  # True - porque ambas afirmaciones son ciertas
print(3 > 2 or 4 < 3)  # True - porque una de las afirmaciones es verdadera
print(3 < 2 or 4 < 3)  # False - porque ambas afirmaciones son falsas
print('True or False:', True or False)
print(not 3 > 2)     # False - porque 3 > 2 es True, entonces si no es verdadero es False
print(not True)      # False - Negación, el operador not convierte lo verdadero en falso
print(not False)     # True
print(not not True)  # True
print(not not False) # False

```

🌕 Tienes una energía ilimitada. Acabas de completar los desafíos del día 3 y estás tres pasos adelante en tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Exercises - Day 3

1. Declare tu edad como variable entera
2. Declara tu altura como una variable float
3. Declare una variable que almacene un número complejo
4. Escribe un script que pida al usuario que introduzca la base y la altura del triángulo y calcule el área de este triángulo (área = 0,5 x b x h).

```py
    Enter base: 20
    Enter height: 10
    The area of the triangle is 100
```

5. Escribe un script que pida al usuario que introduzca el lado a, el lado b y el lado c del triángulo. Calcule el perímetro del triángulo (perimeter = a + b + c).

```py
Enter side a: 5
Enter side b: 4
Enter side c: 3
The perimeter of the triangle is 12
```

6. Obtén la longitud y la anchura de un rectángulo utilizando el prompt. Calcular su área (area = length x width) y el perímetro (perimeter = 2 x (length + width))
7. Obtener el radio de un círculo usando prompt. Calcular el área (area = pi x r x r) y la circunferencia (c = 2 x pi x r) con pi = 3.14.
8. Calcular la pendiente, x-intercept and y-intercept of y = 2x -2
9. La pendiente es (m = y2-y1/x2-x1). Find the slope and [Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance#:~:text=In%20mathematics%2C%20the%20Euclidean%20distance,being%20called%20the%20Pythagorean%20distance.) entre el punto (2, 2) y el punto (6,10) 
10. Compare the slopes in tasks 8 and 9.
11. Calculate the value of y (y = x^2 + 6x + 9). Intenta utilizar diferentes valores de x y averigua a qué valor de x. y va a ser 0.
12. Encuentra la longitud de 'python' y 'dragon' y haz una declaración de comparación falsa.
13. Utilice el operador _and_ para comprobar si 'on' se encuentra tanto en 'python' como en 'dragon'
14. _Espero que este curso no esté lleno de jergas_. Utiliza el operador _in_ para comprobar si _jergas_ está en la frase.
15. No hay "on" tanto en dragon como en python
16. Encontrar la longitud del texto _python_ y convertir el valor a float y convertirlo a string
17. Los números pares son divisibles por 2 y el resto es cero. Cómo se comprueba si un número es par o no usando python?
18. Comprueba si floor division de 7 entre 3 es igual al valor int convertido de 2,7.
19. Comprueba si el tipo de '10' es igual al tipo de 10
20. Comprueba si int('9.8') es igual a 10
21. Escribir un script que pida al usuario que introduzca las horas y la tarifa por hora. Calcule el salario de la persona?

```py
Enter hours: 40
Enter rate per hour: 28
Your weekly earning is 1120
```

22. Escribe un script que pida al usuario que introduzca el número de años. Calcula el número de segundos que puede vivir una persona. Suponga que una persona puede vivir cien años

```py
Enter number of years you have lived: 100
You have lived for 3153600000 seconds.
```

23. Escribe un script en Python que muestre la siguiente tabla

```py
1 1 1 1 1
2 1 2 4 8
3 1 3 9 27
4 1 4 16 64
5 1 5 25 125
```

🎉 CONGRATULATIONS ! 🎉

[<< Day 2](../02_Day_Variables_builtin_functions/02_variables_builtin_functions.md) | [Day 4 >>](../04_Day_Strings/04_strings.md)
