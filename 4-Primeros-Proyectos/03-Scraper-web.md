[03-Scraper-web.md](https://github.com/user-attachments/files/32293206/03-Scraper-web.md)
# Proyecto 3: Web Scraper

## 🎯 Objetivo

Construir un programa que **extrae información automáticamente** de 
una página web. Es tu primer contacto con librerías externas de 
Python y con datos del mundo real.

---

## 🕸️ ¿Qué es el web scraping?

**Web scraping** significa "extraer" información de páginas web de 
forma automática, en vez de copiarla a mano. Por ejemplo: precios de 
productos, noticias, resultados deportivos, o citas célebres (lo que 
haremos aquí).

> ⚠️ **Nota ética importante:** no todas las páginas permiten hacer 
> scraping. Antes de extraer datos de un sitio real, revisa su 
> archivo `robots.txt` (ej: `pagina.com/robots.txt`) y sus términos 
> de uso. En esta lección usaremos una página creada específicamente 
> para practicar, así que no hay ningún problema.

---

## 📦 Paso 1: Instalar las librerías necesarias

Vamos a usar dos librerías que no vienen incluidas en Python por 
defecto:

- **`requests`**: para descargar el contenido de una página web
- **`beautifulsoup4`**: para leer y extraer información del HTML

Desde la terminal, instálalas con `pip` (el gestor de paquetes de Python):

```bash
pip install requests beautifulsoup4
```

> 💡 **`pip`** es a Python lo que una tienda de aplicaciones es a tu 
> móvil: te permite instalar librerías que otros programadores ya 
> crearon, para no reinventar la rueda.

---

## 🌐 El sitio que vamos a usar

Usaremos [quotes.toscrape.com](http://quotes.toscrape.com/), una 
página creada específicamente para practicar web scraping sin 
ningún problema ético o legal. Contiene citas célebres con su autor.

---

## 🧱 Paso 2: Descargar el contenido de la página

```python
import requests

url = "http://quotes.toscrape.com/"
respuesta = requests.get(url)

print(respuesta.status_code)   # 200 significa que fue exitoso
print(respuesta.text[:500])    # Muestra los primeros 500 caracteres del HTML
```

> 💡 El código `200` significa "todo salió bien". Si ves `404`, la 
> página no existe; si ves `403`, no tienes permiso para acceder.

---

## 🧱 Paso 3: Analizar el HTML con BeautifulSoup

El HTML descargado es difícil de leer directamente. BeautifulSoup lo 
convierte en algo que podemos recorrer fácilmente:

```python
import requests
from bs4 import BeautifulSoup

url = "http://quotes.toscrape.com/"
respuesta = requests.get(url)

sopa = BeautifulSoup(respuesta.text, "html.parser")

print(sopa.title)   # Muestra el título de la página
```

---

## 🧱 Paso 4: Extraer las citas

Cada cita en esa página está dentro de una etiqueta HTML con la 
clase `"quote"`. Vamos a buscarlas todas:

```python
import requests
from bs4 import BeautifulSoup

url = "http://quotes.toscrape.com/"
respuesta = requests.get(url)
sopa = BeautifulSoup(respuesta.text, "html.parser")

citas = sopa.find_all("div", class_="quote")

print("Se encontraron", len(citas), "citas")
```

---

## 🧱 Paso 5: Extraer el texto y el autor de cada cita

```python
for cita in citas:
    texto = cita.find("span", class_="text").text
    autor = cita.find("small", class_="author").text
    print(texto, "-", autor)
```

---

## 📄 Código completo

```python
import requests
from bs4 import BeautifulSoup

url = "http://quotes.toscrape.com/"
respuesta = requests.get(url)

if respuesta.status_code == 200:
    sopa = BeautifulSoup(respuesta.text, "html.parser")
    citas = sopa.find_all("div", class_="quote")

    print("Se encontraron", len(citas), "citas:\n")

    for cita in citas:
        texto = cita.find("span", class_="text").text
        autor = cita.find("small", class_="author").text
        print(texto)
        print("-", autor)
        print()
else:
    print("Error al acceder a la página:", respuesta.status_code)
```

---

## 💾 Extra: guardar los resultados en un archivo

```python
import requests
from bs4 import BeautifulSoup

url = "http://quotes.toscrape.com/"
respuesta = requests.get(url)
sopa = BeautifulSoup(respuesta.text, "html.parser")
citas = sopa.find_all("div", class_="quote")

with open("citas.txt", "w", encoding="utf-8") as archivo:
    for cita in citas:
        texto = cita.find("span", class_="text").text
        autor = cita.find("small", class_="author").text
        archivo.write(texto + " - " + autor + "\n\n")

print("Citas guardadas en citas.txt")
```

> 💡 `with open(...) as archivo:` abre un archivo, escribe en él, y 
> lo cierra automáticamente al terminar — la forma correcta de 
> trabajar con archivos en Python.

---

## 🖥️ Cómo probarlo

1. Asegúrate de haber instalado las librerías (`pip install requests beautifulsoup4`)
2. Crea un archivo `scraper.py` en VS Code
3. Copia el código completo
4. Ejecuta:

```bash
python scraper.py
```

Deberías ver todas las citas de la página impresas en tu terminal.

---

## 📤 Subirlo a GitHub

```bash
git add .
git commit -m "Agregar proyecto de web scraper"
git push
```

> 💡 Si guardaste el archivo `citas.txt`, también se subirá — es 
> normal, forma parte del resultado de tu programa.

---

## ⚠️ Errores comunes

### `ModuleNotFoundError: No module named 'bs4'`
No instalaste la librería. Ejecuta:
```bash
pip install beautifulsoup4
```

### `ConnectionError` o el programa se queda colgado
Puede ser tu conexión a internet, o que la página esté caída. 
Comprueba que puedes abrir la URL en tu navegador normalmente.

### `AttributeError: 'NoneType' object has no attribute 'text'`
Significa que `find()` no encontró el elemento que buscabas — 
probablemente la página cambió su estructura HTML, o hay un error 
en el nombre de la clase que buscas.

---

## 🚀 Mejoras opcionales (para ir más allá)

- 📄 La página tiene varias páginas (`/page/2/`, `/page/3/`...) — 
  intenta recorrerlas todas con un bucle
- 🏷️ Extrae también las **etiquetas (tags)** de cada cita
- 📊 Cuenta cuántas citas hay por autor y muestra un resumen
- 🌍 Prueba con otra página pensada para practicar, como 
  [books.toscrape.com](http://books.toscrape.com/)

---

## ✅ Para quedarte con esto

- El **web scraping** extrae información de páginas web automáticamente
- `requests` descarga el HTML, `BeautifulSoup` lo analiza
- Siempre revisa que tienes permiso antes de hacer scraping en un sitio real
- Ya sabes instalar y usar librerías externas con `pip` — una 
  habilidad que usarás constantemente en programación

---

## 🎉 ¡Sección completada!

Has construido tres proyectos completos: una calculadora, un gestor 
de tareas, y un web scraper. Ya tienes experiencia real programando 
de principio a fin.

---

## 🎯 Siguiente paso

Todo programador se encuentra con errores constantemente. Vamos a 
aprender a encontrarlos y solucionarlos de forma eficiente:
**[Continuar a Debugging →](../5-Debugging)**
