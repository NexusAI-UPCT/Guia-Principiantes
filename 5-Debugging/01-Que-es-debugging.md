[01-Que-es-debugging.md](https://github.com/user-attachments/files/32293516/01-Que-es-debugging.md)
# ¿Qué es el Debugging?

## 🎯 Objetivo

Entender qué es depurar código, conocer los tipos de errores más 
comunes, y aprender a leer los mensajes de error de Python sin 
entrar en pánico.

---

## 🐞 ¿Qué significa "debugging"?

**Debugging** (depuración) es el proceso de **encontrar y corregir 
errores** en un programa. La palabra viene de "bug" (insecto en 
inglés) — cuenta la leyenda que en los años 40, un fallo en una 
computadora fue causado literalmente por una polilla atrapada dentro 
de la máquina.

> 💡 **Dato real:** todos los programadores, sin excepción — 
> incluidos los más expertos — pasan buena parte de su tiempo 
> depurando código. No es un signo de que "no sabes programar", es 
> **parte normal** del trabajo.

---

## 🔍 Los 3 tipos de errores

### 1. Errores de sintaxis (Syntax Errors)

Ocurren cuando escribes código que Python **no puede entender** — 
como una falta de ortografía en un idioma.

```python
print("Hola"    # Falta cerrar el paréntesis
```

```
SyntaxError: '(' was never closed
```

**Cómo se detectan:** Python ni siquiera llega a ejecutar el 
programa — te avisa antes de empezar.

---

### 2. Errores de ejecución (Runtime Errors)

El código está bien escrito (sintaxis correcta), pero **falla 
mientras se ejecuta**, normalmente porque intentas hacer algo 
imposible.

```python
numero = 10
resultado = numero / 0   # No se puede dividir entre 0
```

```
ZeroDivisionError: division by zero
```

Otro ejemplo común:

```python
lista = [1, 2, 3]
print(lista[10])   # La lista no tiene un elemento en la posición 10
```

```
IndexError: list index out of range
```

**Cómo se detectan:** el programa se ejecuta, pero se detiene de 
golpe cuando llega a la línea con el problema.

---

### 3. Errores de lógica (Logic Errors)

**El más difícil de detectar**: el programa se ejecuta sin errores, 
pero el resultado **no es el esperado**. Python no te avisa de nada, 
porque técnicamente no hiciste nada "inválido" — solo escribiste 
algo distinto a lo que querías.

```python
def calcular_promedio(a, b, c):
    return a + b + c / 3   # ❌ Error de lógica: falta paréntesis

print(calcular_promedio(9, 9, 9))   # Debería dar 9, pero da 21
```

El problema: por las reglas matemáticas, `c / 3` se calcula antes 
que la suma. Lo correcto sería:

```python
def calcular_promedio(a, b, c):
    return (a + b + c) / 3   # ✅ Correcto

print(calcular_promedio(9, 9, 9))   # Ahora sí da 9
```

**Cómo se detectan:** revisando manualmente si el resultado tiene 
sentido, o con pruebas (lo veremos en la siguiente lección).

---

## 📖 Cómo leer un mensaje de error (Traceback)

Cuando Python encuentra un error de ejecución, muestra un 
**traceback**: información detallada de qué pasó y dónde. Da miedo 
la primera vez, pero es tu mejor amigo para solucionar problemas.

```python
def dividir(a, b):
    return a / b

resultado = dividir(10, 0)
print(resultado)
```

```
Traceback (most recent call last):
  File "programa.py", line 4, in <module>
    resultado = dividir(10, 0)
  File "programa.py", line 2, in dividir
    return a / b
ZeroDivisionError: division by zero
```

### Cómo leerlo, de abajo hacia arriba:

1. **Última línea** (`ZeroDivisionError: division by zero`) → 
   **el tipo de error y qué pasó exactamente**. Empieza siempre por aquí.
2. **Líneas anteriores** → el "camino" que siguió el programa hasta 
   llegar al error (qué línea llamó a qué función)
3. **Números de línea** (`line 4`, `line 2`) → **dónde exactamente** 
   está el problema en tu archivo

> 💡 **Consejo:** cuando veas un error, no entres en pánico por la 
> cantidad de texto. Lee siempre **la última línea primero** — ahí 
> está la información más importante.

---

## 🧠 Tipos de errores más comunes en Python

| Error | Qué significa |
|---|---|
| `SyntaxError` | Código mal escrito, Python no lo entiende |
| `NameError` | Usas una variable que no existe o no has creado |
| `TypeError` | Mezclas tipos incompatibles (ej: texto + número) |
| `IndexError` | Intentas acceder a una posición que no existe en una lista |
| `KeyError` | Intentas acceder a una clave que no existe en un diccionario |
| `ZeroDivisionError` | Divides entre cero |
| `ValueError` | El valor no es válido para la operación (ej: `int("hola")`) |
| `AttributeError` | Usas un método que no existe para ese tipo de dato |

---

## 🧘 El mindset correcto ante un error

- ✅ Un error **no es un fracaso** — es información útil
- ✅ Leer el traceback **te dice exactamente** dónde está el problema
- ✅ Buscar el mensaje de error en Google (o preguntar a otro miembro 
  de la asociación) es una práctica **totalmente normal**, no hace 
  falta memorizar todo
- ✅ Cuanto más programes, más rápido reconocerás los errores comunes

---

## ✅ Para quedarte con esto

- **Debugging** es encontrar y corregir errores — parte normal de programar
- Hay 3 tipos: **sintaxis** (código mal escrito), **ejecución** 
  (falla al correr) y **lógica** (funciona pero da resultado incorrecto)
- El **traceback** te dice qué pasó y dónde — léelo de abajo hacia arriba
- Buscar ayuda ante un error es señal de buen criterio, no de debilidad

---

## 🎯 Siguiente paso

Ahora que entiendes los errores, vamos a ver **estrategias concretas** 
para encontrarlos y solucionarlos:
**[Técnicas de Debugging →](./02-Tecnicas-debugging.md)**
