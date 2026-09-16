[04-Tu-primer-repositorio.md](https://github.com/user-attachments/files/32292643/04-Tu-primer-repositorio.md)
# Tu Primer Repositorio

## 🎯 Objetivo

Crear tu propio repositorio en GitHub, conectarlo con tu computadora, 
y subir tu primer código usando los comandos que aprendiste en la 
lección anterior.

---

## 1️⃣ Crear el repositorio en GitHub

1. Entra en [github.com](https://github.com) con tu cuenta
2. Haz clic en el botón **+** (arriba a la derecha) → **New repository**
3. Rellena:
   - **Repository name**: `mis-practicas` (o el nombre que prefieras)
   - **Description**: "Mi primer repositorio de práctica"
   - **Visibility**: Public o Private, como prefieras
   - **Add a README file**: ✅ actívalo
4. Haz clic en **Create repository**

¡Ya tienes tu repositorio creado en la nube!

---

## 2️⃣ Descargar el repositorio a tu computadora (`clone`)

1. En la página de tu repositorio, haz clic en el botón verde **Code**
2. Copia la URL que aparece (algo como 
   `https://github.com/tu-usuario/mis-practicas.git`)
3. Abre una terminal en tu computadora, en la carpeta donde quieras 
   guardar tus proyectos
4. Ejecuta:

```bash
git clone https://github.com/tu-usuario/mis-practicas.git
```

5. Entra a la carpeta que se creó:

```bash
cd mis-practicas
```

Ya tienes una copia local, conectada con GitHub.

---

## 3️⃣ Hacer tu primer cambio

1. Abre la carpeta en VS Code:

```bash
code .
```

> 💡 Si el comando `code .` no funciona, abre VS Code manualmente y 
> usa **File → Open Folder**.

2. Crea un archivo nuevo llamado `saludo.py`
3. Escribe:

```python
print("Este es mi primer repositorio en GitHub")
```

4. Guarda el archivo

---

## 4️⃣ Subir el cambio a GitHub

De vuelta en la terminal (dentro de la carpeta del proyecto), sigue 
el flujo que ya conoces:

```bash
git status
```

Verás que `saludo.py` aparece como archivo nuevo, sin guardar aún.

```bash
git add .
git commit -m "Agregar primer archivo de práctica"
git push
```

### 🔑 Si te pide usuario y contraseña

GitHub ya no permite usar tu contraseña normal desde la terminal. 
Necesitas un **Personal Access Token** (una especie de contraseña 
especial):

1. Ve a [github.com/settings/tokens](https://github.com/settings/tokens)
2. Haz clic en **Generate new token** → **Generate new token (classic)**
3. Dale un nombre (ej: "mi-computadora"), marca la casilla **repo**
4. Haz clic en **Generate token**
5. **Copia el token inmediatamente** (no lo podrás ver de nuevo)
6. Cuando la terminal te pida la contraseña, **pega el token** (no 
   se verá nada al pegarlo, es normal — dale Enter)

> 💡 Tu computadora recordará el token después de la primera vez, 
> así que solo tendrás que hacer esto una vez por dispositivo.

---

## 5️⃣ Comprueba que funcionó

1. Ve a tu repositorio en GitHub (en el navegador)
2. Recarga la página
3. Deberías ver el archivo `saludo.py` ahí

🎉 **¡Felicidades! Acabas de completar tu primer ciclo completo: 
crear, programar, guardar y subir un proyecto a GitHub.**

---

## 🔄 A partir de ahora: tu flujo de trabajo diario

Cada vez que quieras trabajar en un proyecto:

```bash
# 1. Entra a la carpeta del proyecto
cd mis-practicas

# 2. Baja los últimos cambios (por si acaso)
git pull

# 3. Trabaja, edita tus archivos...

# 4. Guarda y sube tus cambios
git add .
git commit -m "Descripción de lo que hiciste"
git push
```

---

## ⚠️ Errores comunes

### "remote: Support for password authentication was removed"
Necesitas usar un Personal Access Token en vez de tu contraseña 
(ver el paso 4 de esta lección).

### "Updates were rejected because the remote contains work..."
Significa que hay cambios en GitHub que no tienes en tu computadora. 
Soluciona con:
```bash
git pull
```
Y después vuelve a intentar `git push`.

### Olvidé el token y no puedo iniciar sesión
Genera uno nuevo repitiendo el paso 4 — puedes tener varios tokens 
activos sin problema.

---

## ✅ Para quedarte con esto

- Un repositorio se crea en GitHub y se descarga con `git clone`
- El flujo diario es: `pull` → editar → `add` → `commit` → `push`
- Para autenticarte necesitas un **Personal Access Token**, no tu 
  contraseña normal
- Ya completaste el ciclo completo de trabajo con Git y GitHub 🎉

---

## 🎯 Siguiente paso

Ya sabes trabajar solo. Ahora vamos a ver cómo colaborar con otros 
miembros de la asociación en el mismo proyecto:
**[Colaboración en GitHub →](./05-Colaboracion-en-GitHub.md)**
