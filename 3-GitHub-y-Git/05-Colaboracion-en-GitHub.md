[05-Colaboracion-en-GitHub.md](https://github.com/user-attachments/files/32292750/05-Colaboracion-en-GitHub.md)
# Colaboración en GitHub

## 🎯 Objetivo

Aprender a trabajar en equipo dentro de un mismo proyecto sin pisar 
el trabajo de tus compañeros: ramas, Pull Requests e Issues — las 
herramientas que usa la asociación para colaborar.

---

## 🌿 Ramas (Branches): trabajar sin romper nada

Hasta ahora has trabajado siempre en la rama principal, llamada 
`main`. El problema de trabajar directamente ahí en equipo es que 
si alguien sube un error, **afecta a todos** de inmediato.

La solución: crear una **rama** (una copia paralela del proyecto) 
para trabajar tranquilo, y luego juntarla con `main` cuando esté 
lista y revisada.

```
main:     A---B---C-------------F
                    \           /
tu-rama:             D---E-----
```

### Crear una rama nueva

```bash
git checkout -b nombre-de-tu-rama
```

Ejemplo:
```bash
git checkout -b agregar-seccion-debugging
```

Esto crea la rama y te cambia a ella automáticamente.

### Ver en qué rama estás

```bash
git branch
```

La rama actual aparece marcada con un asterisco `*`.

### Volver a la rama principal

```bash
git checkout main
```

### Subir tu rama a GitHub

```bash
git push -u origin nombre-de-tu-rama
```

> 💡 **Buena práctica:** usa nombres de rama descriptivos, como 
> `arreglar-error-login` o `agregar-tutorial-python`, no `rama1` o `prueba`.

---

## 🔀 Pull Requests (PR): proponer tus cambios

Un **Pull Request** es una solicitud para juntar los cambios de tu 
rama con la rama principal (`main`). Es el momento donde otros 
miembros **revisan tu código** antes de que se incorpore al proyecto.

### Cómo crear un Pull Request

1. Sube tu rama a GitHub (`git push -u origin tu-rama`, visto arriba)
2. Ve al repositorio en GitHub — verás un aviso: 
   **"tu-rama had recent pushes"** con un botón **Compare & pull request**
3. Haz clic en ese botón
4. Escribe un **título claro** y una **descripción** de qué cambiaste y por qué
5. Haz clic en **Create pull request**

### ¿Qué pasa después?

- Otros miembros pueden **comentar** tu código, sugerir cambios o 
  aprobarlo
- Si todo está bien, alguien con permisos hace clic en **Merge pull 
  request** — y tus cambios pasan a formar parte de `main`
- Si hace falta corregir algo, simplemente sigues haciendo commits 
  en tu rama: el Pull Request se actualiza solo

### ¿Por qué usar Pull Requests en vez de subir directo a `main`?

- ✅ Alguien revisa el código antes de que afecte a todos
- ✅ Se pueden detectar errores antes de que lleguen al proyecto principal
- ✅ Queda un registro de **por qué** se hizo cada cambio
- ✅ Es exactamente como funciona en empresas reales

---

## 🐛 Issues: reportar problemas y proponer tareas

Un **Issue** es como una "ficha de tarea": sirve para reportar un 
error, pedir una nueva función, o repartir trabajo entre el equipo.

### Crear un Issue

1. En el repositorio, ve a la pestaña **Issues**
2. Haz clic en **New issue**
3. Escribe un título claro (ej: "El README tiene un enlace roto")
4. Describe el problema o la tarea con el mayor detalle posible
5. Puedes **asignarlo** a un miembro concreto del equipo

### Buenas prácticas al escribir un Issue

```markdown
## Qué está pasando
El enlace a la sección de Python en el README no funciona.

## Dónde
Archivo: README.md, línea 15

## Cómo se soluciona
Cambiar el enlace de "/python" a "/2-Python"
```

Cuanto más claro seas, más rápido se puede resolver.

---

## ⚔️ Conflictos: cuando dos personas cambian lo mismo

A veces, tú y otro miembro modificáis la **misma línea** de un 
archivo al mismo tiempo. Git no puede decidir cuál de los dos 
cambios es el correcto, así que te avisa con un **conflicto**:

```
<<<<<<< HEAD
print("Versión de Kaiqi")
=======
print("Versión de Ana")
>>>>>>> rama-de-ana
```

### Cómo resolverlo

1. Abre el archivo en VS Code (marcará el conflicto visualmente)
2. Decide qué código quieres conservar (uno, el otro, o una mezcla)
3. Borra las líneas `<<<<<<<`, `=======` y `>>>>>>>`
4. Guarda, y continúa con el flujo normal:

```bash
git add .
git commit -m "Resolver conflicto"
git push
```

> 💡 Los conflictos son **completamente normales** en equipo — no 
> significan que hiciste algo mal.

---

## 📋 Buenas prácticas de colaboración en la asociación

- ✅ **Haz `git pull` antes de empezar** a trabajar cada día
- ✅ **Crea una rama nueva** para cada tarea o funcionalidad
- ✅ **Escribe mensajes de commit claros**: qué hiciste y por qué
- ✅ **Abre un Pull Request** en vez de subir directo a `main`
- ✅ **Revisa el código de tus compañeros** cuando te lo pidan
- ✅ **Usa Issues** para reportar errores o proponer tareas

---

## ✅ Para quedarte con esto

- Las **ramas** te permiten trabajar sin afectar el proyecto principal
- Los **Pull Requests** son la forma de proponer y revisar cambios
- Los **Issues** organizan tareas y reportan errores
- Los **conflictos** son normales y se resuelven editando el archivo

---

## 🎉 ¡Sección completada!

Has terminado toda la sección de GitHub y Git. Ya tienes las 
herramientas para trabajar en cualquier proyecto de la asociación 
de forma profesional: instalar tu entorno, guardar tu trabajo, y 
colaborar en equipo.

---

## 🎯 Siguiente paso

Con todo lo aprendido hasta ahora, es momento de construir algo real:
**[Continuar a Primeros Proyectos →](../4-Primeros-Proyectos)**
