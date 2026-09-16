[03-Estructuras-datos.md](https://github.com/user-attachments/files/32283647/03-Estructuras-datos.md)
# Estructuras de Datos

## 🎯 Objetivo

Aprender a guardar **colecciones de información** (no solo un dato 
suelto) usando listas, diccionarios y tuplas — las estructuras que 
más vas a usar en Python.

---

## 🌐 ¿Dónde pruebo el código?

Todos los ejemplos de esta página los puedes escribir y ejecutar 
directamente en el navegador, sin instalar nada:

👉 [Abrir compilador online (Programiz)](https://www.programiz.com/python-programming/online-compiler/)

---

## 📋 Listas: colecciones ordenadas

Una **lista** guarda varios valores en un orden concreto, dentro de 
corchetes `[ ]`.

```python
frutas = ["manzana", "plátano", "naranja"]
print(frutas)
```

Resultado:
```
['manzana', 'plátano', 'naranja']
```

### Acceder a un elemento (por posición / índice)

En Python, la numeración **empieza en 0**:

```python
frutas = ["manzana", "plátano", "naranja"]

print(frutas[0])   # manzana
print(frutas[1])   # plátano
print(frutas[2])   # naranja
print(frutas[-1])  # naranja (el índice -1 es el último elemento)
```

### Modificar una lista

```python
frutas = ["manzana", "plátano", "naranja"]

frutas.append("uva")        # Añade al final
print(frutas)

frutas.remove("plátano")    # Elimina un elemento
print(frutas)

frutas[0] = "pera"          # Cambia un elemento por su posición
print(frutas)
```

### Recorrer una lista

```python
frutas = ["manzana", "plátano", "naranja"]

for fruta in frutas:
    print(fruta)
```

### Otras operaciones útiles

```python
frutas = ["manzana", "plátano", "naranja"]

print(len(frutas))               # 3 → número de elementos
print("plátano" in frutas)       # True → ¿está en la lista?
frutas.sort()                    # Ordena alfabéticamente
print(frutas)
```

---

## 📖 Diccionarios: pares clave-valor

Un **diccionario** guarda información asociando una **clave** con un 
**valor**, dentro de llaves `{ }`. Es como una ficha con datos.

```python
persona = {
    "nombre": "Kaiqi",
    "edad": 35,
    "carrera": "Ciencia de Datos"
}

print(persona)
```

### Acceder a un valor (por su clave, no por posición)

```python
persona = {
    "nombre": "Kaiqi",
    "edad": 35,
    "carrera": "Ciencia de Datos"
}

print(persona["nombre"])    # Kaiqi
print(persona["edad"])      # 35
```

### Modificar y añadir datos

```python
persona = {"nombre": "Kaiqi", "edad": 35}

persona["edad"] = 26              # Modifica un valor existente
persona["universidad"] = "UPCT"   # Añade una nueva clave-valor

print(persona)
```

### Recorrer un diccionario

```python
persona = {"nombre": "Kaiqi", "edad":35, "carrera": "Ciencia de Datos"}

for clave, valor in persona.items():
    print(clave, ":", valor)
```

Resultado:
```
nombre : Kaiqi
edad : 35
carrera : Ciencia de Datos
```

---

## 🔒 Tuplas: listas que no cambian

Una **tupla** es parecida a una lista, pero **no se puede modificar** 
una vez creada. Se usan paréntesis `( )`.

```python
coordenadas = (40.7128, -74.0060)
print(coordenadas[0])   # 40.7128
```

```python
coordenadas = (40.7128, -74.0060)
coordenadas[0] = 10   # ❌ Error: las tuplas no se pueden modificar
```

> 💡 **¿Cuándo usar una tupla en vez de una lista?** Cuando quieras 
> asegurarte de que esos datos no cambien accidentalmente durante el 
> programa (por ejemplo, coordenadas fijas o los días de la semana).

---

## 🆚 Resumen: ¿cuál elegir?

| Estructura | Símbolo | ¿Se puede modificar? | ¿Cuándo usarla? |
|---|---|---|---|
| **Lista** | `[ ]` | ✅ Sí | Colección de datos que puede cambiar |
| **Diccionario** | `{ }` | ✅ Sí | Datos con nombre (clave → valor) |
| **Tupla** | `( )` | ❌ No | Datos fijos que no deben cambiar |

---

## 🧠 Estructuras dentro de estructuras

Puedes combinarlas. Por ejemplo, una lista de diccionarios (muy 
común en proyectos reales):

```python
miembros = [
    {"nombre": "Inma", "rol": "Presidente"},
    {"nombre": "Ana", "rol": "Secretaria"},
    {"nombre": "Luis", "rol": "Tesorero"}
]

for miembro in miembros:
    print(miembro["nombre"], "-", miembro["rol"])
```

Resultado:
```
Inma - Presidente
Ana - Secretaria
Luis - Tesorero
```

---

## 🧪 Ejercicio práctico

Copia esto en tu compilador online y complétalo:

```python
# Lista de proyectos de la asociación
proyectos = ["CelebrIA", "Laberinto-PyGames", "Proyecto-rtv7"]

# 1. Imprime el primer proyecto de la lista
print(proyectos[0])

# 2. Añade un nuevo proyecto a la lista
proyectos.append("Nuevo-Proyecto-2026")

# 3. Recorre e imprime todos los proyectos
for proyecto in proyectos:
    print(proyecto)

# 4. Crea un diccionario con tus propios datos
mis_datos = {
    "nombre": "Tu nombre",
    "asociacion": "NexusAI-UPCT"
}
print(mis_datos)
```

---

## ✅ Para quedarte con esto

- **Listas** `[ ]`: colecciones ordenadas y modificables
- **Diccionarios** `{ }`: datos organizados por clave y valor
- **Tuplas** `( )`: como las listas, pero no se pueden modificar
- Puedes combinar estructuras (listas de diccionarios, por ejemplo)

---

## 🎯 Siguiente paso

Ya tienes las bases de Python. Es momento de ponerlas en práctica:
**[Ejercicios Prácticos →](./04-Ejercicios-practicos.md)**
