[02-Gestor-tareas.md](https://github.com/user-attachments/files/32293100/02-Gestor-tareas.md)
# Proyecto 2: Gestor de Tareas

## 🎯 Objetivo

Construir una aplicación de consola para gestionar tareas pendientes: 
añadir, ver, completar y eliminar tareas. Este proyecto usa listas, 
diccionarios y un menú interactivo — un paso más hacia programas 
reales.

---

## 📋 ¿Qué vamos a construir?

Un programa con un **menú** que se repite, donde el usuario puede:
1. Ver todas las tareas
2. Añadir una tarea nueva
3. Marcar una tarea como completada
4. Eliminar una tarea
5. Salir del programa

---

## 🧱 Paso 1: Guardar las tareas

Vamos a guardar cada tarea como un diccionario, y todas las tareas 
en una lista:

```python
tareas = []

# Ejemplo de cómo se verá una tarea:
# {"nombre": "Terminar la guía", "completada": False}
```

---

## 🧱 Paso 2: Función para añadir una tarea

```python
def agregar_tarea(tareas):
    nombre = input("Escribe la nueva tarea: ")
    tarea = {"nombre": nombre, "completada": False}
    tareas.append(tarea)
    print("Tarea agregada")
```

---

## 🧱 Paso 3: Función para ver las tareas

```python
def ver_tareas(tareas):
    if len(tareas) == 0:
        print("No tienes tareas pendientes")
        return

    print("\n--- Tus tareas ---")
    for i in range(len(tareas)):
        tarea = tareas[i]
        estado = "✅" if tarea["completada"] else "❌"
        print(i + 1, "-", estado, tarea["nombre"])
    print()
```

> 💡 Usamos el índice (`i + 1`) para que el usuario pueda referirse 
> a una tarea concreta por su número, empezando en 1 en vez de 0 
> (más natural para quien lo usa).

---

## 🧱 Paso 4: Función para completar una tarea

```python
def completar_tarea(tareas):
    ver_tareas(tareas)

    if len(tareas) == 0:
        return

    numero = int(input("¿Qué tarea quieres marcar como completada? (número): "))
    indice = numero - 1

    if indice >= 0 and indice < len(tareas):
        tareas[indice]["completada"] = True
        print("✅ Tarea marcada como completada")
    else:
        print("❌ Número de tarea no válido")
```

---

## 🧱 Paso 5: Función para eliminar una tarea

```python
def eliminar_tarea(tareas):
    ver_tareas(tareas)

    if len(tareas) == 0:
        return

    numero = int(input("¿Qué tarea quieres eliminar? (número): "))
    indice = numero - 1

    if indice >= 0 and indice < len(tareas):
        tarea_eliminada = tareas.pop(indice)
        print("🗑️ Tarea eliminada:", tarea_eliminada["nombre"])
    else:
        print("❌ Número de tarea no válido")
```

> 💡 `.pop(indice)` elimina un elemento de la lista por su posición, 
> y además te devuelve ese elemento eliminado.

---

## 🧱 Paso 6: El menú principal

Ahora juntamos todo con un bucle que muestra el menú y repite hasta 
que el usuario elija salir:

```python
def mostrar_menu():
    print("\n--- Gestor de Tareas ---")
    print("1. Ver tareas")
    print("2. Agregar tarea")
    print("3. Completar tarea")
    print("4. Eliminar tarea")
    print("5. Salir")


tareas = []
opcion = ""

while opcion != "5":
    mostrar_menu()
    opcion = input("Elige una opción: ")

    if opcion == "1":
        ver_tareas(tareas)
    elif opcion == "2":
        agregar_tarea(tareas)
    elif opcion == "3":
        completar_tarea(tareas)
    elif opcion == "4":
        eliminar_tarea(tareas)
    elif opcion == "5":
        print("¡Hasta luego!")
    else:
        print("❌ Opción no válida")
```

---

## 📄 Código completo

```python
def mostrar_menu():
    print("\n--- Gestor de Tareas ---")
    print("1. Ver tareas")
    print("2. Agregar tarea")
    print("3. Completar tarea")
    print("4. Eliminar tarea")
    print("5. Salir")


def ver_tareas(tareas):
    if len(tareas) == 0:
        print("No tienes tareas pendientes")
        return

    print("\n--- Tus tareas ---")
    for i in range(len(tareas)):
        tarea = tareas[i]
        estado = "✅" if tarea["completada"] else "❌"
        print(i + 1, "-", estado, tarea["nombre"])
    print()


def agregar_tarea(tareas):
    nombre = input("Escribe la nueva tarea: ")
    tarea = {"nombre": nombre, "completada": False}
    tareas.append(tarea)
    print("✅ Tarea agregada")


def completar_tarea(tareas):
    ver_tareas(tareas)
    if len(tareas) == 0:
        return

    numero = int(input("¿Qué tarea quieres marcar como completada? (número): "))
    indice = numero - 1

    if indice >= 0 and indice < len(tareas):
        tareas[indice]["completada"] = True
        print("✅ Tarea marcada como completada")
    else:
        print("❌ Número de tarea no válido")


def eliminar_tarea(tareas):
    ver_tareas(tareas)
    if len(tareas) == 0:
        return

    numero = int(input("¿Qué tarea quieres eliminar? (número): "))
    indice = numero - 1

    if indice >= 0 and indice < len(tareas):
        tarea_eliminada = tareas.pop(indice)
        print("🗑️ Tarea eliminada:", tarea_eliminada["nombre"])
    else:
        print("❌ Número de tarea no válido")


tareas = []
opcion = ""

while opcion != "5":
    mostrar_menu()
    opcion = input("Elige una opción: ")

    if opcion == "1":
        ver_tareas(tareas)
    elif opcion == "2":
        agregar_tarea(tareas)
    elif opcion == "3":
        completar_tarea(tareas)
    elif opcion == "4":
        eliminar_tarea(tareas)
    elif opcion == "5":
        print("¡Hasta luego!")
    else:
        print("❌ Opción no válida")
```

---

## 🖥️ Cómo probarlo

1. Crea un archivo `gestor_tareas.py` en VS Code
2. Copia el código completo de arriba
3. Ejecuta:

```bash
python gestor_tareas.py
```

4. Prueba añadir varias tareas, completarlas y eliminarlas

---

## 📤 Subirlo a GitHub

```bash
git add .
git commit -m "Agregar proyecto de gestor de tareas"
git push
```

---

## ⚠️ Una limitación importante

Si cierras el programa, **todas las tareas se pierden** — porque se 
guardan solo en memoria (en la lista `tareas`), no en ningún archivo.

> 💡 Esto es intencional en este proyecto, para centrarnos en la 
> lógica. Más adelante, cuando veas cómo leer y escribir archivos, 
> podrás guardar las tareas de forma permanente.

---

## 🚀 Mejoras opcionales (para ir más allá)

- 💾 Investiga el módulo `json` de Python para guardar las tareas en 
  un archivo y que no se pierdan al cerrar el programa
- 📅 Añade una fecha límite a cada tarea
- 🔼 Añade prioridades (alta, media, baja) y ordena las tareas por prioridad
- ✏️ Añade una opción para **editar** el nombre de una tarea existente

---

## ✅ Para quedarte con esto

- Una lista de diccionarios es perfecta para guardar colecciones de 
  datos estructurados
- Un menú con `while` permite que el programa se repita hasta que 
  el usuario decida salir
- Separar cada acción en su propia función hace el código más claro 
  y organizado

---

## 🎯 Siguiente paso

**[Proyecto 3: Web Scraper →](./03-Scraper-web.md)**
