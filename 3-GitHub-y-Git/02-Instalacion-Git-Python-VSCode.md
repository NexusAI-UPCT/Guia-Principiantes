[02-Instalacion-Git-Python-VSCode.md](https://github.com/user-attachments/files/32292431/02-Instalacion-Git-Python-VSCode.md)
# Instalación de Git, Python y VS Code

## 🎯 Objetivo

Instalar en tu computadora las tres herramientas que necesitas para 
programar como un profesional: **Python** (el lenguaje), **VS Code** 
(el editor de código) y **Git** (para guardar y compartir tu trabajo).

> 💡 Hasta ahora programabas desde el navegador. A partir de aquí, 
> todo lo harás desde tu propia computadora.

---

## 1️⃣ Instalar Python

### Windows / Mac

1. Ve a [python.org/downloads](https://www.python.org/downloads/)
2. Descarga la última versión (recomendado: Python 3.11 o superior)
3. Abre el instalador
4. **Muy importante en Windows:** marca la casilla 
   ✅ **"Add python.exe to PATH"** antes de darle a instalar
5. Sigue las opciones por defecto hasta terminar

### Linux

La mayoría de distribuciones ya traen Python instalado. Comprueba 
la versión con el comando de verificación de abajo. Si necesitas 
instalarlo:

```bash
sudo apt update
sudo apt install python3
```

### ✅ Verifica que se instaló bien

Abre una terminal (o "símbolo del sistema" en Windows) y escribe:

```bash
python --version
```

Si ves algo como `Python 3.11.5`, ¡ya está instalado correctamente!

> 💡 **Mac/Linux:** si `python` no funciona, prueba con `python3`.

---

## 2️⃣ Instalar Visual Studio Code (VS Code)

VS Code es el editor de código más usado del mundo: gratuito, 
ligero y con soporte para todos los lenguajes.

1. Ve a [code.visualstudio.com](https://code.visualstudio.com/)
2. Descarga la versión para tu sistema operativo
3. Instala con las opciones por defecto

### Extensión recomendada: Python

Una vez abierto VS Code:

1. Haz clic en el icono de **Extensiones** (los cuadraditos, en la 
   barra lateral izquierda)
2. Busca **"Python"** (la extensión oficial de Microsoft)
3. Haz clic en **Install**

Esto le da a VS Code todo lo necesario para ejecutar y depurar 
código Python cómodamente.

---

## 3️⃣ Instalar Git

### Windows

1. Ve a [git-scm.com/downloads](https://git-scm.com/downloads)
2. Descarga el instalador para Windows
3. Ejecuta el instalador — puedes dejar todas las opciones por 
   defecto (dale a "Next" en cada paso)

### Mac

Abre la terminal y escribe:

```bash
git --version
```

Si no lo tienes instalado, macOS te ofrecerá instalarlo automáticamente. 
Si no, instálalo con [Homebrew](https://brew.sh/):

```bash
brew install git
```

### Linux

```bash
sudo apt update
sudo apt install git
```

### ✅ Verifica que se instaló bien

En cualquier sistema, abre una terminal y escribe:

```bash
git --version
```

Deberías ver algo como `git version 2.42.0`.

---

## 4️⃣ Configurar Git (solo se hace una vez)

Git necesita saber quién eres, para dejar constancia de tus cambios. 
Abre una terminal y escribe (sustituyendo por tus datos):

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-correo@gmail.com"
```

> 💡 Usa el mismo correo con el que te registraste en GitHub, así 
> tus cambios quedarán vinculados correctamente a tu cuenta.

### Comprueba que quedó bien configurado:

```bash
git config --list
```

Deberías ver tu nombre y correo en la lista.

---

## 🖥️ Ejecutar tu primer archivo Python desde VS Code

Ahora que tienes todo instalado, vamos a probarlo:

1. Abre VS Code
2. Crea una carpeta nueva en tu computadora (ej: `mis-practicas`)
3. En VS Code: **File → Open Folder** y selecciona esa carpeta
4. Crea un archivo nuevo llamado `hola.py`
5. Escribe:

```python
print("¡Hola desde mi computadora!")
```

6. Guarda el archivo (`Ctrl + S` / `Cmd + S`)
7. Abre la terminal integrada de VS Code: **Terminal → New Terminal**
8. Escribe:

```bash
python hola.py
```

Deberías ver:
```
¡Hola desde mi computadora!
```

🎉 **¡Ya tienes tu entorno de programación completo funcionando!**

---

## ⚠️ Problemas comunes

### "python no se reconoce como un comando" (Windows)
Significa que no se marcó "Add to PATH" al instalar. Solución: 
desinstala Python y vuelve a instalarlo marcando esa casilla.

### "git no se reconoce como un comando"
Cierra y vuelve a abrir la terminal (a veces no detecta la 
instalación hasta reiniciarla). Si sigue sin funcionar, reinicia 
la computadora.

### La terminal de VS Code no encuentra Python
Asegúrate de haber abierto la **carpeta del proyecto** con 
**File → Open Folder**, no solo el archivo suelto.

---

## ✅ Para quedarte con esto

- **Python** es el lenguaje: se ejecuta con `python archivo.py`
- **VS Code** es el editor donde escribes tu código
- **Git** es la herramienta que va a permitir guardar y compartir tu trabajo
- Ya configuraste tu nombre y correo en Git — solo se hace una vez

---

## 🎯 Siguiente paso

Con todo instalado, es hora de aprender los comandos básicos de Git:
**[Primeros Comandos →](./03-Primeros-comandos.md)**
