[03-Herramientas-utiles.md](https://github.com/user-attachments/files/32293659/03-Herramientas-utiles.md)
# Herramientas Útiles para Debugging

## 🎯 Objetivo

Conocer el depurador visual de VS Code y otras herramientas que te 
van a ahorrar muchísimo tiempo al encontrar errores, más allá de usar 
solo `print()`.

---

## 🛑 El Depurador de VS Code (Debugger)

Hasta ahora usaste `print()` para ver qué pasaba en tu código. El 
**depurador** de VS Code hace algo más potente: **pausa tu programa 
en el punto exacto que tú elijas**, y te deja inspeccionar todas las 
variables en ese momento, sin escribir ni un solo `print()`.

### Paso 1: Poner un "breakpoint" (punto de parada)

1. Abre tu archivo `.py` en VS Code
2. Haz clic justo a la izquierda del número de línea donde quieres 
   que el programa se detenga (aparecerá un punto rojo 🔴)

```python
def calcular_promedio(numeros):
    total = sum(numeros)          # 🔴 Pon el breakpoint aquí
    promedio = total / len(numeros)
    return promedio

resultado = calcular_promedio([10, 20, 30])
print(resultado)
```

### Paso 2: Ejecutar en modo depuración

1. Ve a la pestaña de **Run and Debug** (el icono de "play" con un 
   bicho, en la barra lateral izquierda)
2. Haz clic en **Run and Debug** → selecciona **Python File**

El programa se ejecutará y **se detendrá automáticamente** cuando 
llegue a tu breakpoint.

### Paso 3: Inspeccionar variables

Cuando el programa está pausado, verás en el panel lateral:
- **Variables**: todos los valores actuales (`numeros`, `total`, etc.)
- **Watch**: puedes añadir expresiones concretas para vigilar
- **Call Stack**: el camino que siguió el programa hasta llegar ahí

### Paso 4: Controlar la ejecución

En la barra que aparece arriba, tienes botones para:

| Botón | Qué hace |
|---|---|
| ▶️ **Continue** | Sigue ejecutando hasta el siguiente breakpoint |
| ⤵️ **Step Over** | Ejecuta la línea actual y pasa a la siguiente |
| ⬇️ **Step Into** | Entra dentro de una función para ver qué hace por dentro |
| ⬆️ **Step Out** | Sale de la función actual, vuelve a donde la llamaron |
| ⏹️ **Stop** | Detiene la depuración |

> 💡 Con esto puedes avanzar **línea por línea** y ver exactamente 
> cómo cambian tus variables — mucho más potente que ir añadiendo 
> `print()` manualmente.

---

## 🧹 Linters: detectar errores antes de ejecutar

Un **linter** revisa tu código en busca de errores de sintaxis, 
malas prácticas o variables sin usar — **antes** de que ejecutes el 
programa.

VS Code ya incluye esto con la extensión de Python que instalaste. 
Verás líneas subrayadas en rojo o amarillo directamente mientras 
escribes:

```python
def saludar(nombre)   # ⚠️ VS Code detecta que falta ":"
    print("Hola", nombre)
```

> 💡 Pasa el cursor por encima del subrayado para ver una 
> explicación del problema.

---

## 🐍 Python Tutor: visualizar el código paso a paso

[pythontutor.com](https://pythontutor.com/) es una herramienta online 
que **dibuja visualmente** cómo cambian las variables mientras tu 
programa se ejecuta, línea por línea. Muy útil cuando algo no tiene 
sentido y quieres "ver" qué está pasando de verdad.

1. Pega tu código en [pythontutor.com](https://pythontutor.com/)
2. Haz clic en **Visualize Execution**
3. Usa **Next >** para avanzar paso a paso y ver el estado del programa

---

## 🤖 Usar IA como ayuda para depurar

Como asociación de IA, es natural aprovechar herramientas como 
ChatGPT, Claude o GitHub Copilot para depurar código. Son muy útiles, 
pero con una condición importante:

> ⚠️ **No copies y pegues el error sin entenderlo.** Usa la IA para 
> **entender por qué** ocurre el error, no solo para que te dé la 
> solución. Si no entiendes el "por qué", volverás a cometer el mismo 
> error la próxima vez.

### Cómo pedir ayuda de forma efectiva:

```
❌ Mal: "Arregla esto: [pego 200 líneas de código]"

✅ Bien: "Tengo este error: [mensaje de error completo]. 
Este es mi código: [la función concreta que falla]. 
¿Puedes explicarme por qué ocurre, sin darme directamente 
la solución?"
```

---

## 🔎 `dir()` y `help()`: explorar sobre la marcha

Dos funciones integradas en Python muy útiles cuando no recuerdas 
qué puedes hacer con algo:

```python
lista = [1, 2, 3]

print(dir(lista))    # Muestra todos los métodos disponibles para una lista
print(help(lista.append))   # Explica qué hace un método concreto
```

---

## 📌 Resumen: ¿qué herramienta usar en cada caso?

| Situación | Herramienta recomendada |
|---|---|
| Quiero ver rápido un valor concreto | `print()` |
| El programa falla en un punto que no localizo | Depurador de VS Code |
| Quiero entender bien cómo cambia el estado paso a paso | Python Tutor |
| Tengo un error y no sé qué significa | Buscarlo, o preguntar a una IA (entendiendo la respuesta) |
| Quiero saber qué puedo hacer con un objeto | `dir()` / `help()` |

---

## ✅ Para quedarte con esto

- El **depurador de VS Code** te permite pausar tu programa e 
  inspeccionar variables sin usar `print()`
- Los **linters** detectan errores antes de ejecutar el código
- **Python Tutor** visualiza la ejecución paso a paso
- La **IA es una gran ayuda**, siempre que la uses para entender, no 
  solo para copiar soluciones

---

## 🎉 ¡Sección completada!

Ya tienes las herramientas y técnicas para enfrentarte a cualquier 
error con calma y método, en vez de frustración.

---

## 🎯 Siguiente paso

Es momento de entrar en el tema que probablemente te trajo a esta 
asociación:
**[Continuar a Introducción a la IA →](../6-Introduccion-IA)**
