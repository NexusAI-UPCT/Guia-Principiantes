[03-Variables-y-tipos-datos.md](https://github.com/user-attachments/files/32282671/03-Variables-y-tipos-datos.md)
# Variables y Tipos de Datos

## 🎯 Objetivo

Aprender a **guardar información** en tu programa usando variables, 
y conocer los tipos de datos más comunes en Python.

---

## 📦 ¿Qué es una variable?

Una **variable** es como una caja donde guardas información para 
usarla después. Le pones un nombre y le asignas un valor.

```python
nombre = "María"
edad = 20
```

Aquí:
- `nombre` es una variable que guarda el texto `"María"`
- `edad` es una variable que guarda el número `20`

El símbolo `=` no significa "igual" como en matemáticas — significa 
**"asignar"**: "guarda este valor en esta variable".

---

## 🧪 Pruébalo tú mismo

Abre tu compilador online (Programiz o el que uses) y escribe:

```python
nombre = "María"
print(nombre)
```

Resultado:
```
María
```

Ahora prueba combinar variables:

```python
nombre = "María"
edad = 20
print("Me llamo", nombre, "y tengo", edad, "años")
```

Resultado:
```
Me llamo María y tengo 20 años
```

> 💡 `print()` puede recibir varias cosas separadas por comas, y 
> las muestra todas seguidas.

---

## 🏷️ Reglas para nombrar variables

- ✅ Puede tener letras, números y guion bajo: `edad_usuario`
- ✅ Debe empezar con una letra (no un número): `edad2` ✔️, `2edad` ❌
- ✅ Python distingue mayúsculas: `Nombre` y `nombre` son diferentes
- ❌ No puede tener espacios: usa `mi_nombre`, no `mi nombre`
- ❌ No puede ser una palabra reservada de Python: `print`, `if`, `for`, etc.

**Buena práctica:** usa nombres descriptivos.

```python
# Poco claro
x = 20

# Claro
edad = 20
```

---

## 🔢 Tipos de datos básicos

Python tiene varios tipos de datos. Estos son los 4 más importantes 
para empezar:

### 1. `str` (texto / string)
Cualquier texto, siempre entre comillas.

```python
nombre = "María"
ciudad = 'Cartagena'
```

### 2. `int` (número entero)
Números sin decimales.

```python
edad = 20
año = 2026
```

### 3. `float` (número decimal)
Números con parte decimal.

```python
altura = 1.75
precio = 9.99
```

### 4. `bool` (booleano)
Solo puede ser `True` (verdadero) o `False` (falso).

```python
es_estudiante = True
tiene_coche = False
```

---

## 🔍 ¿Cómo saber el tipo de una variable?

Usa la función `type()`:

```python
edad = 20
print(type(edad))
```

Resultado:
```
<class 'int'>
```

Pruébalo con distintos valores:

```python
print(type("Hola"))     # str
print(type(20))         # int
print(type(1.75))       # float
print(type(True))       # bool
```

---

## ➕ Operaciones básicas

### Con números:

```python
a = 10
b = 3

print(a + b)   # Suma → 13
print(a - b)   # Resta → 7
print(a * b)   # Multiplicación → 30
print(a / b)   # División → 3.333...
```

### Con texto (concatenar):

```python
nombre = "María"
saludo = "Hola, " + nombre
print(saludo)
```

Resultado:
```
Hola, María
```

> ⚠️ **Cuidado:** no puedes sumar texto con número directamente:
>
> ```python
> edad = 20
> print("Tengo " + edad + " años")  # ❌ Error
> ```
>
> Tienes que convertir el número a texto primero:
>
> ```python
> edad = 20
> print("Tengo " + str(edad) + " años")  # ✅ Correcto
> ```

---

## 🧠 Convertir entre tipos

A veces necesitas cambiar un tipo de dato a otro. Se llama **casting**:

```python
edad_texto = "20"
edad_numero = int(edad_texto)   # Convierte texto → número

precio = 9
precio_decimal = float(precio)  # Convierte entero → decimal

numero = 20
numero_texto = str(numero)      # Convierte número → texto
```

---

## 🎯 Ejercicio práctico

Copia esto en tu compilador online y complétalo con tus propios datos:

```python
nombre = "Tu nombre aquí"
edad = 0  # Pon tu edad
ciudad = "Tu ciudad aquí"

print("Me llamo", nombre)
print("Tengo", edad, "años")
print("Vivo en", ciudad)
print("El tipo de 'edad' es:", type(edad))
```

---

## ✅ Para quedarte con esto

- Una **variable** guarda información con un nombre
- Los tipos básicos son: `str` (texto), `int` (entero), `float` (decimal), `bool` (verdadero/falso)
- `type()` te dice qué tipo de dato tienes
- No puedes mezclar texto y número directamente sin convertir

---

## 🎯 ¡Sección completada! 🎉

Ya terminaste **Fundamentos de Programación**. Ahora es momento de 
profundizar en Python:

**[Continuar a la sección de Python →](../2-Python)**
