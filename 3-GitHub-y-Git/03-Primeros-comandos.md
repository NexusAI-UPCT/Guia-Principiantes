[03-Primeros-comandos.md](https://github.com/user-attachments/files/32292532/03-Primeros-comandos.md)
# Primeros Comandos de Git

## 🎯 Objetivo

Aprender los comandos básicos de Git que vas a usar **todos los 
días** como programador: guardar cambios, revisar el historial, y 
sincronizar con GitHub.

---

## 🧭 El flujo básico de Git

Antes de ver comandos sueltos, entiende el flujo general. Git 
funciona en 3 "zonas":

```
Tu carpeta  →  Área de preparación  →  Historial guardado
(archivos)      (staging area)          (commit)
```

1. **Editas** tus archivos normalmente
2. Le dices a Git **cuáles cambios quieres guardar** (`git add`)
3. **Guardas** esos cambios con un mensaje (`git commit`)
4. **Subes** ese historial a GitHub (`git push`)

Vamos a ver cada comando en detalle.

---

## 📁 `git init` — Iniciar un repositorio

Convierte una carpeta normal en un repositorio Git (activa el 
seguimiento de cambios).

```bash
git init
```

> 💡 Solo se ejecuta **una vez**, al principio de un proyecto nuevo.

---

## 👀 `git status` — Ver el estado actual

Te dice qué archivos han cambiado, cuáles están listos para 
guardarse y cuáles no.

```bash
git status
```

Es el comando que más vas a usar — **cuando tengas duda de qué está 
pasando, ejecuta `git status`**.

---

## ➕ `git add` — Preparar cambios

Le dice a Git qué archivos quieres incluir en el próximo guardado 
(commit).

```bash
# Añadir un archivo concreto
git add hola.py

# Añadir todos los archivos modificados
git add .
```

> 💡 `git add .` (con el punto) añade **todo** lo que hayas cambiado 
> en la carpeta actual. Es el más usado al empezar.

---

## 💾 `git commit` — Guardar cambios

Guarda una "foto" de tu proyecto con un mensaje describiendo qué 
cambiaste.

```bash
git commit -m "Agregar función de saludo"
```

> 💡 El mensaje (`-m "..."`) debe ser **claro y corto**, explicando 
> qué hiciste. Ejemplos buenos: `"Corregir error en cálculo de edad"`, 
> `"Añadir sección de ejercicios"`.

---

## 📜 `git log` — Ver el historial

Muestra todos los commits que se han hecho en el proyecto.

```bash
git log
```

Salida de ejemplo:
```
commit a1b2c3d4e5f6...
Author: Kaiqi <tu-correo@gmail.com>
Date:   Mon Sep 15 10:30:00 2026

    Agregar función de saludo
```

Para una vista más resumida:

```bash
git log --oneline
```

---

## ⬆️ `git push` — Subir cambios a GitHub

Envía tus commits guardados localmente hacia el repositorio en 
GitHub.

```bash
git push
```

---

## ⬇️ `git pull` — Bajar cambios de GitHub

Descarga a tu computadora los cambios que otros hayan subido a 
GitHub (o los que tú mismo subiste desde otro dispositivo).

```bash
git pull
```

> ⚠️ **Buena práctica:** haz siempre `git pull` **antes** de empezar 
> a trabajar, para asegurarte de tener la última versión.

---

## 📥 `git clone` — Descargar un repositorio existente

Copia un repositorio completo de GitHub a tu computadora (con todo 
su historial incluido).

```bash
git clone https://github.com/NexusAI-UPCT/Guia-Principiantes.git
```

Esto crea una carpeta nueva con el nombre del repositorio, lista 
para trabajar.

---

## 🗂️ Resumen visual del flujo completo

```bash
# 1. Revisa qué ha cambiado
git status

# 2. Prepara los cambios
git add .

# 3. Guarda los cambios con un mensaje
git commit -m "Descripción de lo que hice"

# 4. Sube los cambios a GitHub
git push
```

Este ciclo (`status → add → commit → push`) lo repetirás 
**constantemente** mientras programas.

---

## ⚠️ Errores comunes

### "fatal: not a git repository"
Estás intentando usar un comando de Git en una carpeta que no es un 
repositorio. Soluciones:
- Si es un proyecto nuevo: ejecuta `git init`
- Si es un proyecto existente: asegúrate de estar dentro de la 
  carpeta correcta (`cd nombre-carpeta`)

### "Please tell me who you are"
Te falta configurar tu nombre y correo (lo vimos en la lección 
anterior):
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-correo@gmail.com"
```

### `git push` pide usuario y contraseña, y falla
GitHub ya no acepta contraseñas normales para esto — necesitas un 
**Personal Access Token** o conectar con SSH. Lo veremos paso a paso 
en la siguiente lección, al crear tu primer repositorio.

---

## ✅ Para quedarte con esto

| Comando | Qué hace |
|---|---|
| `git init` | Convierte una carpeta en repositorio |
| `git status` | Muestra el estado actual |
| `git add .` | Prepara los cambios para guardar |
| `git commit -m "..."` | Guarda los cambios con un mensaje |
| `git push` | Sube los cambios a GitHub |
| `git pull` | Baja los cambios de GitHub |
| `git clone [url]` | Descarga un repositorio existente |

---

## 🎯 Siguiente paso

Ya conoces los comandos. Ahora vamos a usarlos de verdad, creando 
tu propio repositorio desde cero:
**[Tu Primer Repositorio →](./04-Tu-primer-repositorio.md)**
