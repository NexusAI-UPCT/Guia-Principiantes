[01-Sintaxis-basica.md](https://github.com/user-attachments/files/32283464/01-Sintaxis-basica.md)
# Sintaxis Básica de Python

## 🎯 Objetivo

Aprender cómo Python organiza su código, y las dos herramientas más 
importantes para controlar lo que hace un programa: **condicionales** 
(decisiones) y **bucles** (repeticiones).

---

## 🌐 ¿Dónde pruebo el código?

Todos los ejemplos de esta página los puedes escribir y ejecutar 
directamente en el navegador, sin instalar nada:

👉 [Abrir compilador online (Programiz)](https://www.programiz.com/python-programming/online-compiler/)

> 💡 Si vienes de la lección anterior ya conoces esta herramienta. 
> Si has llegado directo aquí, solo entra al enlace, borra lo que 
> haya escrito y pega el código de cada ejemplo para probarlo.

---

## 📐 La indentación: la regla más importante de Python

A diferencia de otros lenguajes, Python usa **espacios** (indentación) 
para saber qué código pertenece a qué bloque. No usa llaves `{}` como 
otros lenguajes.

```python
if True:
    print("Esto está dentro del if")
    print("Esto también")
print("Esto está fuera del if")
```

> ⚠️ **Muy importante:** la indentación no es "estética" — si te 
> equivocas, tu programa da error o funciona mal. Usa siempre 
> **4 espacios** por nivel (la mayoría de editores lo hacen automático).

---

## 🔀 Condicionales: tomar decisiones

Un programa necesita tomar decisiones según lo que pase. Para eso 
se usan `if`, `elif` y `else`.

```python
edad = 20

if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
```

### Con varias condiciones:

```python
nota = 7

if nota >= 9:
    print("Sobresaliente")
elif nota >= 7:
    print("Notable")
elif nota >= 5:
    print("Aprobado")
else:
    print("Suspenso")
```

### Operadores de comparación:

| Operador | Significado |
|---|---|
| `==` | Igual a |
| `!=` | Distinto de |
| `>` | Mayor que |
| `<` | Menor que |
| `>=` | Mayor o igual que |
| `<=` | Menor o igual que |

> ⚠️ **Error común:** usar `=` en vez de `==` para comparar. 
> `=` asigna un valor, `==` compara dos valores.

### Combinar condiciones: `and`, `or`, `not`

```python
edad = 20
tiene_carnet = True

if edad >= 18 and tiene_carnet:
    print("Puede conducir")

if edad < 18 or not tiene_carnet:
    print("No puede conducir")
```

---

## 🔁 Bucles: repetir acciones

### Bucle `for` (repetir un número de veces conocido)

```python
for i in range(5):
    print("Vuelta número", i)
```

Resultado:
```
Vuelta número 0
Vuelta número 1
Vuelta número 2
Vuelta número 3
Vuelta número 4
```

> 💡 `range(5)` genera los números del 0 al 4 (5 números en total, 
> empezando en 0).

### Recorrer una lista con `for`

```python
frutas = ["manzana", "plátano", "naranja"]

for fruta in frutas:
    print(fruta)
```

### Bucle `while` (repetir mientras se cumpla una condición)

```python
contador = 0

while contador < 5:
    print("Contador:", contador)
    contador = contador + 1
```

> ⚠️ **Cuidado con los bucles infinitos:** si olvidas actualizar la 
> variable de control (`contador = contador + 1`), el bucle nunca 
> termina. Si esto pasa en el compilador online, recarga la página.

---

## 🛑 Controlar bucles: `break` y `continue`

```python
# break: termina el bucle por completo
for numero in range(10):
    if numero == 5:
        break
    print(numero)
```

```python
# continue: salta a la siguiente vuelta, sin terminar el bucle
for numero in range(5):
    if numero == 2:
        continue
    print(numero)
```

---

## 💬 Comentarios

Los comentarios son texto que Python **ignora** al ejecutar. Sirven 
para explicar tu código.

```python
# Esto es un comentario de una línea

edad = 20  # También se puede comentar al final de una línea

"""
Esto es un comentario
de varias líneas
"""
```

**Buena práctica:** comenta el "por qué", no el "qué" (el código ya 
dice qué hace).

---

## 🧪 Ejercicio práctico

Copia esto en tu compilador online y compruébalo:

```python
# Programa: comprobar si un número es par o impar
numero = 7

if numero % 2 == 0:
    print(numero, "es par")
else:
    print(numero, "es impar")

# Programa: contar del 1 al 10
for i in range(1, 11):
    print(i)
```

> 💡 `%` es el operador **módulo**: da el resto de una división. 
> Si el resto de dividir entre 2 es 0, el número es par.

---

## ✅ Para quedarte con esto

- Python usa **indentación** (espacios) para organizar el código
- `if / elif / else` permiten tomar decisiones
- `for` repite un número conocido de veces (o recorre una lista)
- `while` repite mientras se cumpla una condición
- `break` corta el bucle, `continue` salta a la siguiente vuelta

---

## 🎯 Siguiente paso

Ahora que controlas decisiones y repeticiones, vamos a aprender a 
**organizar el código en bloques reutilizables**:
**[Funciones →](./02-Funciones.md)**
