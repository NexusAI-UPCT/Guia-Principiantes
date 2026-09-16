[04-Ejercicios-practicos.md](https://github.com/user-attachments/files/32283837/04-Ejercicios-practicos.md)
# Ejercicios Prácticos

## 🎯 Objetivo

Poner en práctica todo lo aprendido en esta sección: variables, 
condicionales, bucles, funciones y estructuras de datos. La única 
forma de aprender a programar de verdad es **programando**.

---

## 🌐 ¿Dónde pruebo el código?

👉 [Abrir compilador online (Programiz)](https://www.programiz.com/python-programming/online-compiler/)

---

## 📝 Cómo usar esta página

Cada ejercicio tiene:
1. Un **enunciado** (el problema a resolver)
2. Un espacio para que lo intentes **tú primero**
3. Una **solución** oculta, para que la compruebes después

> 💡 **Consejo:** intenta resolver cada ejercicio durante al menos 
> 10-15 minutos antes de mirar la solución. Equivocarte y corregir 
> es la parte donde realmente se aprende.

---

## 🥉 Nivel 1: Básico

### Ejercicio 1 — Par o impar

Escribe una función `es_par(numero)` que reciba un número y devuelva 
`True` si es par y `False` si es impar.

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
def es_par(numero):
    return numero % 2 == 0

print(es_par(4))   # True
print(es_par(7))   # False
```

</details>

---

### Ejercicio 2 — Saludo personalizado

Escribe una función `saludar(nombre, hora)` que:
- Si `hora` es menor de 12, imprima `"Buenos días, [nombre]"`
- Si `hora` está entre 12 y 19, imprima `"Buenas tardes, [nombre]"`
- Si `hora` es 19 o más, imprima `"Buenas noches, [nombre]"`

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
def saludar(nombre, hora):
    if hora < 12:
        print("Buenos días,", nombre)
    elif hora < 19:
        print("Buenas tardes,", nombre)
    else:
        print("Buenas noches,", nombre)

saludar("Pedro", 9)
saludar("Pedro", 15)
saludar("Pedro", 21)
```

</details>

---

## 🥈 Nivel 2: Intermedio

### Ejercicio 3 — Suma de una lista

Escribe una función `sumar_lista(numeros)` que reciba una lista de 
números y devuelva la suma de todos ellos, **sin usar** la función 
`sum()` de Python (hazlo con un bucle).

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
def sumar_lista(numeros):
    total = 0
    for numero in numeros:
        total = total + numero
    return total

print(sumar_lista([1, 2, 3, 4, 5]))   # 15
```

</details>

---

### Ejercicio 4 — Contar miembros por rol

Tienes esta lista de diccionarios con los miembros de la asociación:

```python
miembros = [
    {"nombre": "Inma", "rol": "Presidente"},
    {"nombre": "Ana", "rol": "Socio"},
    {"nombre": "Luis", "rol": "Socio"},
    {"nombre": "María", "rol": "Tesorera"},
    {"nombre": "Pablo", "rol": "Socio"}
]
```

Escribe código que cuente **cuántos miembros hay con el rol "Socio"** 
e imprima el resultado.

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
miembros = [
    {"nombre": "Inma", "rol": "Presidente"},
    {"nombre": "Ana", "rol": "Socio"},
    {"nombre": "Luis", "rol": "Socio"},
    {"nombre": "María", "rol": "Tesorera"},
    {"nombre": "Pablo", "rol": "Socio"}
]

contador = 0
for miembro in miembros:
    if miembro["rol"] == "Socio":
        contador = contador + 1

print("Número de socios:", contador)   # 3
```

</details>

---

## 🥇 Nivel 3: Avanzado (para este punto)

### Ejercicio 5 — El número más alto y más bajo

Escribe una función `maximo_minimo(numeros)` que reciba una lista de 
números y devuelva **dos valores**: el más alto y el más bajo — 
sin usar las funciones `max()` ni `min()` de Python.

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
def maximo_minimo(numeros):
    mayor = numeros[0]
    menor = numeros[0]
    
    for numero in numeros:
        if numero > mayor:
            mayor = numero
        if numero < menor:
            menor = numero
    
    return mayor, menor

mayor, menor = maximo_minimo([5, 12, 3, 8, 20, 1])
print("Mayor:", mayor)   # 20
print("Menor:", menor)   # 1
```

> 💡 En Python, una función puede devolver **varios valores** 
> separados por comas con `return`.

</details>

---

### Ejercicio 6 — Reto: contador de palabras

Escribe una función `contar_palabras(texto)` que reciba una frase 
(un string) y devuelva **cuántas palabras** tiene.

Pista: investiga la función `.split()` de los strings — no la hemos 
visto antes, pero es un buen ejercicio para acostumbrarte a buscar 
documentación por tu cuenta, algo que todo programador hace 
constantemente.

```python
# Escribe tu código aquí
```

<details>
<summary>Ver solución</summary>

```python
def contar_palabras(texto):
    palabras = texto.split()   # Separa el texto por espacios
    return len(palabras)

frase = "Esta es una frase de ejemplo"
print(contar_palabras(frase))   # 6
```

</details>

---

## 🎉 ¡Sección completada!

Si has llegado hasta aquí y resuelto (o al menos intentado) todos 
los ejercicios, ya tienes las bases sólidas de programación en 
Python: variables, condicionales, bucles, funciones y estructuras 
de datos.

Es normal si no todos te salieron a la primera — todos los 
programadores buscan ayuda, revisan documentación y prueban varias 
veces antes de que algo funcione.

---

## 🎯 Siguiente paso

Ahora toca aprender la herramienta que usan todos los programadores 
para guardar y compartir su código, y a instalar Python en tu propia 
computadora:

**[Continuar a GitHub y Git →](../3-GitHub-y-Git)**
