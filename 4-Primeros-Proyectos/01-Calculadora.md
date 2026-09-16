[01-Calculadora.md](https://github.com/user-attachments/files/32293001/01-Calculadora.md)
# Proyecto 1: Calculadora

## 🎯 Objetivo

Construir tu primer programa completo: una calculadora por consola 
que aplica lo aprendido en las secciones anteriores — variables, 
funciones, condicionales y bucles — todo junto en un proyecto real.

---

## 📋 ¿Qué vamos a construir?

Un programa que:
1. Le pide al usuario dos números y una operación (`+`, `-`, `*`, `/`)
2. Calcula el resultado
3. Lo muestra en pantalla
4. Pregunta si quiere hacer otra operación, y repite hasta que diga que no

---

## 🆕 Herramienta nueva: `input()`

Hasta ahora tus programas no interactuaban con quien los ejecuta. 
La función `input()` le pide al usuario que escriba algo:

```python
nombre = input("¿Cómo te llamas? ")
print("Hola,", nombre)
```

> ⚠️ **Importante:** `input()` siempre devuelve **texto** (`str`), 
> aunque el usuario escriba un número. Si necesitas usarlo como 
> número, tienes que convertirlo:

```python
edad_texto = input("¿Cuántos años tienes? ")
edad = int(edad_texto)   # Ahora sí es un número
print("El año que viene tendrás", edad + 1)
```

---

## 🧱 Paso 1: Las funciones de cada operación

Empezamos definiendo una función por cada operación matemática:

```python
def sumar(a, b):
    return a + b

def restar(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b == 0:
        return "Error: no se puede dividir entre 0"
    return a / b
```

> 💡 Fíjate en `dividir()`: comprobamos si `b` es 0 antes de dividir, 
> porque dividir entre cero da error en matemáticas (y en programación).

---

## 🧱 Paso 2: Pedir los datos al usuario

```python
num1 = float(input("Introduce el primer número: "))
operacion = input("Elige una operación (+, -, *, /): ")
num2 = float(input("Introduce el segundo número: "))
```

> 💡 Usamos `float()` en vez de `int()` para poder trabajar también 
> con decimales (ej: 3.5).

---

## 🧱 Paso 3: Decidir qué función usar

```python
if operacion == "+":
    resultado = sumar(num1, num2)
elif operacion == "-":
    resultado = restar(num1, num2)
elif operacion == "*":
    resultado = multiplicar(num1, num2)
elif operacion == "/":
    resultado = dividir(num1, num2)
else:
    resultado = "Operación no válida"

print("Resultado:", resultado)
```

---

## 🧱 Paso 4: Repetir hasta que el usuario quiera salir

Juntamos todo dentro de un bucle `while`:

```python
def sumar(a, b):
    return a + b

def restar(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b == 0:
        return "Error: no se puede dividir entre 0"
    return a / b


continuar = "s"

while continuar == "s":
    num1 = float(input("Introduce el primer número: "))
    operacion = input("Elige una operación (+, -, *, /): ")
    num2 = float(input("Introduce el segundo número: "))

    if operacion == "+":
        resultado = sumar(num1, num2)
    elif operacion == "-":
        resultado = restar(num1, num2)
    elif operacion == "*":
        resultado = multiplicar(num1, num2)
    elif operacion == "/":
        resultado = dividir(num1, num2)
    else:
        resultado = "Operación no válida"

    print("Resultado:", resultado)

    continuar = input("¿Quieres hacer otra operación? (s/n): ")

print("¡Gracias por usar la calculadora!")
```

---

## 🖥️ Cómo probarlo

1. Crea un archivo `calculadora.py` en VS Code
2. Copia el código completo del Paso 4
3. Ejecuta desde la terminal:

```bash
python calculadora.py
```

4. Prueba con distintas operaciones y comprueba que funciona

---

## 📤 Subirlo a GitHub

Sigue el flujo que ya conoces:

```bash
git add .
git commit -m "Agregar proyecto de calculadora"
git push
```

> 💡 Si es un repositorio nuevo, recuerda primero crearlo en GitHub 
> y hacer `git clone`, tal como viste en 
> [Tu Primer Repositorio](../3-GitHub-y-Git/04-Tu-primer-repositorio.md).

---

## 🚀 Mejoras opcionales (para ir más allá)

Si quieres seguir practicando, intenta añadir:

- ➕ Una operación más: potencia (`**`) o módulo (`%`)
- 🛡️ Manejo de errores si el usuario escribe letras en vez de números 
  (pista: investiga `try` / `except`)
- 📜 Un historial que muestre todas las operaciones hechas en la sesión
- 🎨 Mensajes más claros usando f-strings: `f"Resultado: {resultado}"`

---

## ✅ Para quedarte con esto

- `input()` permite que el usuario interactúe con tu programa
- Todo lo que devuelve `input()` es texto: conviértelo si necesitas números
- Combinar funciones, condicionales y bucles te permite construir 
  programas reales
- Ya tienes tu primer proyecto completo subido a GitHub 🎉

---

## 🎯 Siguiente paso

**[Proyecto 2: Gestor de Tareas →](./02-Gestor-tareas.md)**
