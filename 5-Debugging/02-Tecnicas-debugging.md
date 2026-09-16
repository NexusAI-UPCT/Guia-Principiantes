[02-Tecnicas-debugging.md](https://github.com/user-attachments/files/32293559/02-Tecnicas-debugging.md)
# Técnicas de Debugging

## 🎯 Objetivo

Aprender estrategias prácticas para encontrar y solucionar errores 
de forma metódica, en vez de cambiar código al azar esperando que 
funcione.

---

## 🖨️ Técnica 1: Debugging con `print()`

La técnica más simple y más usada: coloca `print()` en distintos 
puntos del código para ver qué está pasando realmente en cada paso.

```python
def calcular_promedio(numeros):
    print("Números recibidos:", numeros)   # 👀 Comprobación 1
    
    total = sum(numeros)
    print("Suma total:", total)            # 👀 Comprobación 2
    
    promedio = total / len(numeros)
    print("Promedio calculado:", promedio) # 👀 Comprobación 3
    
    return promedio

resultado = calcular_promedio([10, 20, 30])
```

Al ejecutar, ves exactamente qué valor tiene cada variable en cada 
paso, y puedes identificar en qué punto algo empieza a salir mal.

> 💡 **Buena práctica:** una vez que arreglas el error, **elimina** 
> los `print()` de depuración — no deben quedarse en el código final.

---

## 🦆 Técnica 2: "Rubber Duck Debugging" (explicárselo a un pato)

Suena raro, pero funciona increíblemente bien: **explica tu código 
en voz alta, línea por línea**, como si se lo estuvieras enseñando a 
alguien que no sabe nada (o a un pato de goma, literalmente — así se 
originó la técnica).

Muchas veces, el simple hecho de **verbalizar** lo que tu código 
"debería" hacer te hace notar dónde está el error, sin necesidad de 
que nadie más responda.

> 💡 En la asociación, puedes hacer esto con un compañero: 
> explícale tu código en voz alta antes de pedirle ayuda — a veces 
> encuentras el error tú mismo antes de terminar de explicarlo.

---

## ✂️ Técnica 3: Divide y vencerás

Si tienes un programa grande que falla, no intentes revisarlo todo 
de golpe. **Divide el problema** en partes más pequeñas y comprueba 
cada una por separado.

```python
# En vez de ejecutar todo el programa completo...
def procesar_datos(datos):
    limpios = limpiar_datos(datos)
    calculados = calcular_estadisticas(limpios)
    resultado = generar_reporte(calculados)
    return resultado

# ...prueba cada función por separado
datos_prueba = [1, 2, 3, "4", 5]

limpios = limpiar_datos(datos_prueba)
print(limpios)   # ¿Esto funciona bien?

calculados = calcular_estadisticas(limpios)
print(calculados)   # ¿Y esto?
```

Así identificas **exactamente** en qué función está el problema, en 
vez de sospechar de todo el programa.

---

## 🔬 Técnica 4: Reproducir el error con el caso más simple posible

Si tu error ocurre con datos complejos, intenta **reducirlo** al 
ejemplo más pequeño que aún produce el error.

```python
# Si esto falla con una lista de 1000 elementos...
procesar_lista(lista_de_1000_elementos)

# Prueba primero con el caso más simple posible
procesar_lista([1])
procesar_lista([1, 2])
procesar_lista([])
```

Esto te ayuda a descartar rápidamente si el problema es de lógica 
general, o solo ocurre en casos especiales (listas vacías, números 
negativos, texto vacío, etc.).

---

## 🧪 Técnica 5: Comprobar tus suposiciones con `assert`

A veces asumes que una variable tiene cierto valor o tipo, pero te 
equivocas sin darte cuenta. `assert` comprueba esa suposición y te 
avisa inmediatamente si es falsa.

```python
def dividir(a, b):
    assert b != 0, "b no puede ser cero"
    return a / b

print(dividir(10, 0))
```

```
AssertionError: b no puede ser cero
```

En vez de que el error aparezca más adelante (y de forma confusa), 
`assert` te avisa exactamente en el punto donde algo no cumple lo 
esperado.

---

## 📋 Técnica 6: Leer el error con calma, de abajo hacia arriba

Ya lo vimos en la lección anterior, pero merece repetirse: cuando 
aparece un traceback largo, **no lo escanees por encima**. Lee:

1. El **tipo de error** y su mensaje (última línea)
2. El **número de línea** exacto donde ocurrió
3. Si hace falta, sube por el traceback para ver el "camino" que 
   siguió el programa

---

## 🎯 Un proceso paso a paso para depurar

Cuando algo falla, sigue este orden:

1. **Lee el error completo** — no asumas que ya sabes qué dice
2. **Localiza la línea exacta** donde ocurre
3. **Añade `print()`** antes de esa línea para ver los valores reales
4. **Compara** lo que esperabas con lo que realmente está pasando
5. **Corrige** el código
6. **Vuelve a ejecutar** para confirmar que se solucionó
7. **Elimina** los `print()` de depuración que ya no necesites

---

## 🧪 Ejercicio práctico

Este código tiene un error de lógica. Cópialo en tu compilador 
online, ejecútalo, y usa las técnicas de esta lección para 
encontrarlo:

```python
def es_palindromo(palabra):
    palabra_invertida = palabra
    return palabra == palabra_invertida

print(es_palindromo("reconocer"))   # Debería dar True
print(es_palindromo("python"))      # Debería dar False (pero da True)
```

<details>
<summary>💡 Pista</summary>

Añade un `print()` para ver qué valor tiene realmente 
`palabra_invertida`. ¿De verdad se está invirtiendo la palabra en 
algún punto del código?

</details>

<details>
<summary>Ver solución</summary>

```python
def es_palindromo(palabra):
    palabra_invertida = palabra[::-1]   # Esto SÍ invierte la palabra
    return palabra == palabra_invertida

print(es_palindromo("reconocer"))   # True
print(es_palindromo("python"))      # False
```

El error: `palabra_invertida = palabra` solo copia la palabra, 
**no la invierte**. Para invertir un string en Python se usa 
`palabra[::-1]`.

</details>

---

## ✅ Para quedarte con esto

- `print()` en puntos clave te muestra qué está pasando realmente
- Explicar tu código en voz alta ayuda a encontrar errores de lógica
- Divide problemas grandes en partes pequeñas y pruébalas por separado
- Reduce el error al ejemplo más simple que lo reproduce
- `assert` comprueba tus suposiciones automáticamente

---

## 🎯 Siguiente paso

Ya conoces las estrategias. Ahora vamos a ver las **herramientas** 
que te hacen depurar aún más rápido:
**[Herramientas Útiles →](./03-Herramientas-utiles.md)**
