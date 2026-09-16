[02-Funciones.md](https://github.com/user-attachments/files/32283546/02-Funciones.md)
# Funciones

## 🎯 Objetivo

Aprender a crear **funciones**: bloques de código reutilizables que 
te permiten organizar tu programa y evitar repetir el mismo código 
una y otra vez.

---

## 🌐 ¿Dónde pruebo el código?

Todos los ejemplos de esta página los puedes escribir y ejecutar 
directamente en el navegador, sin instalar nada:

👉 [Abrir compilador online (Programiz)](https://www.programiz.com/python-programming/online-compiler/)

---

## 📦 ¿Qué es una función?

Una **función** es un bloque de código con un nombre, que puedes 
"llamar" (ejecutar) cuantas veces quieras, sin tener que reescribirlo.

Ya has usado funciones antes: `print()`, `type()`, `int()`... todas 
esas son funciones que Python ya trae preparadas. Ahora vas a crear 
las tuyas propias.

### Analogía: una máquina de café

Piensa en una función como una máquina de café:
- Le metes ingredientes (**parámetros**): agua, café
- La máquina hace su trabajo (**el código de la función**)
- Te devuelve un resultado (**el valor de retorno**): una taza de café

No necesitas saber cómo funciona por dentro cada vez que la usas — 
solo le das lo que necesita y usas lo que te devuelve.

---

## ✍️ Crear tu primera función

Se define con la palabra `def` (de "define"):

```python
def saludar():
    print("¡Hola! Bienvenido a la asociación")
```

Para **ejecutarla**, la "llamas" por su nombre:

```python
def saludar():
    print("¡Hola! Bienvenido a la asociación")

saludar()
```

Resultado:
```
¡Hola! Bienvenido a la asociación
```

> 💡 Fíjate: **definir** una función no la ejecuta. Solo la ejecutas 
> cuando la "llamas" escribiendo su nombre seguido de `()`.

---

## 📥 Funciones con parámetros

Un **parámetro** es información que le pasas a la función para que 
la use.

```python
def saludar(nombre):
    print("¡Hola,", nombre, "!")

saludar("Kaiqi")
saludar("María")
```

Resultado:
```
¡Hola, Kaiqi !
¡Hola, María !
```

### Varios parámetros:

```python
def presentar(nombre, edad):
    print("Me llamo", nombre, "y tengo", edad, "años")

presentar("Kaiqi", 20)
```

---

## 📤 Funciones que devuelven un valor: `return`

Hasta ahora, las funciones solo mostraban texto con `print()`. Pero 
muchas veces necesitas que una función **calcule algo y te lo 
devuelva** para usarlo después.

```python
def sumar(a, b):
    resultado = a + b
    return resultado

total = sumar(5, 3)
print(total)
```

Resultado:
```
8
```

> ⚠️ **Diferencia clave:** `print()` solo **muestra** algo en pantalla. 
> `return` **devuelve** un valor que puedes guardar en una variable y 
> seguir usando.

```python
def sumar(a, b):
    return a + b

# Puedes usar el resultado directamente
print(sumar(10, 5))

# O guardarlo en una variable
resultado = sumar(10, 5)
print(resultado)

# O usarlo en otra operación
doble = sumar(10, 5) * 2
print(doble)
```

---

## 🎛️ Parámetros con valor por defecto

Puedes darle a un parámetro un valor "por defecto" que se usa si no 
le pasas nada:

```python
def saludar(nombre="amigo"):
    print("¡Hola,", nombre, "!")

saludar("Kaiqi")   # ¡Hola, Kaiqi !
saludar()          # ¡Hola, amigo !
```

---

## 🧠 ¿Por qué usar funciones?

- ✅ **Evitas repetir código**: escribes una vez, usas muchas veces
- ✅ **Organización**: cada función hace una cosa concreta
- ✅ **Más fácil de corregir**: si hay un error, lo arreglas en un solo lugar
- ✅ **Más fácil de leer**: el nombre de la función explica qué hace

### Sin funciones (repetitivo):

```python
print("Área del rectángulo 1:", 5 * 3)
print("Área del rectángulo 2:", 8 * 2)
print("Área del rectángulo 3:", 10 * 4)
```

### Con funciones (limpio y reutilizable):

```python
def area_rectangulo(base, altura):
    return base * altura

print("Área del rectángulo 1:", area_rectangulo(5, 3))
print("Área del rectángulo 2:", area_rectangulo(8, 2))
print("Área del rectángulo 3:", area_rectangulo(10, 4))
```

---

## ⚠️ Errores comunes

```python
# ❌ Olvidar los paréntesis al llamar la función
def saludar():
    print("Hola")

saludar  # Esto no ejecuta la función, solo la "menciona"
```

```python
# ❌ Usar una variable que solo existe dentro de la función
def calcular():
    resultado = 10 + 5

print(resultado)  # Error: 'resultado' no existe fuera de la función
```

> 💡 Las variables creadas **dentro** de una función solo existen 
> **dentro** de ella. Si necesitas usar el valor fuera, usa `return`.

---

## 🧪 Ejercicio práctico

Copia esto en tu compilador online y complétalo:

```python
def es_par(numero):
    if numero % 2 == 0:
        return True
    else:
        return False

# Prueba la función con distintos números
print(es_par(4))   # True
print(es_par(7))   # False

# Ahora crea tú una función que reciba dos números 
# y devuelva el mayor de los dos
def mayor(a, b):
    # Escribe tu código aquí
    pass

print(mayor(10, 25))
```

---

## ✅ Para quedarte con esto

- Una **función** es un bloque de código reutilizable con un nombre
- Se define con `def nombre():` y se ejecuta llamándola: `nombre()`
- Los **parámetros** son información que le pasas a la función
- `return` devuelve un valor que puedes usar después (distinto de `print`)
- Las funciones evitan repetir código y organizan tu programa

---

## 🎯 Siguiente paso

Ahora que sabes organizar código en funciones, vamos a aprender a 
**guardar colecciones de datos**:
**[Estructuras de Datos →](./03-Estructuras-datos.md)**
