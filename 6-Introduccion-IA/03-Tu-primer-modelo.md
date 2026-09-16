[03-Tu-primer-modelo.md](https://github.com/user-attachments/files/32293994/03-Tu-primer-modelo.md)
# Tu Primer Modelo de Machine Learning

## 🎯 Objetivo

Entrenar tu primer modelo real de Machine Learning con Python, 
usando `scikit-learn` — la librería más usada para empezar en este 
campo. Vamos a construir un clasificador que identifica especies de 
flores según sus medidas.

---

## 🌸 El dataset: Iris

Vamos a usar el **dataset Iris**, uno de los más famosos en Machine 
Learning (perfecto para aprender, porque viene ya incluido en 
scikit-learn, sin necesidad de descargar nada).

Contiene 150 flores de 3 especies distintas (`setosa`, `versicolor`, 
`virginica`), cada una con 4 medidas:

- Longitud del sépalo
- Anchura del sépalo
- Longitud del pétalo
- Anchura del pétalo

**El objetivo:** entrenar un modelo que, dadas esas 4 medidas, 
prediga a qué especie pertenece una flor.

---

## 📦 Paso 1: Instalar scikit-learn

```bash
pip install scikit-learn pandas
```

---

## 🧱 Paso 2: Cargar y explorar los datos

```python
from sklearn.datasets import load_iris
import pandas as pd

# Cargar el dataset
iris = load_iris()

# Convertirlo a una tabla más fácil de leer
datos = pd.DataFrame(iris.data, columns=iris.feature_names)
datos["especie"] = iris.target

print(datos.head())    # Muestra las primeras 5 filas
print(datos.shape)     # (150, 5) → 150 flores, 5 columnas
```

> 💡 `iris.target` contiene números (0, 1, 2) representando cada 
> especie. `iris.target_names` te dice a qué nombre corresponde 
> cada número.

---

## 🧱 Paso 3: Separar features y label

```python
X = iris.data        # Features: las 4 medidas de cada flor
y = iris.target      # Label: la especie (0, 1 o 2)
```

> 💡 Es una convención muy extendida llamar `X` a las features (en 
> mayúscula) y `y` al label — las verás así en casi cualquier 
> proyecto de Machine Learning.

---

## 🧱 Paso 4: Dividir en entrenamiento y prueba

Tal como vimos en la lección anterior, separamos los datos para 
poder comprobar si el modelo realmente aprendió:

```python
from sklearn.model_selection import train_test_split

X_entrenamiento, X_prueba, y_entrenamiento, y_prueba = train_test_split(
    X, y, test_size=0.2, random_state=42
)

print("Datos de entrenamiento:", len(X_entrenamiento))
print("Datos de prueba:", len(X_prueba))
```

> 💡 `test_size=0.2` significa que el 20% de los datos se reserva 
> para prueba, y el 80% para entrenamiento. `random_state=42` 
> asegura que la división sea siempre la misma cada vez que 
> ejecutes el código (para que sea reproducible).

---

## 🧱 Paso 5: Entrenar el modelo

Vamos a usar un algoritmo llamado **K-Vecinos más Cercanos (KNN)**: 
para clasificar una flor nueva, mira las flores **más parecidas** 
que ya conoce, y le asigna la especie más común entre ellas.

```python
from sklearn.neighbors import KNeighborsClassifier

modelo = KNeighborsClassifier(n_neighbors=3)
modelo.fit(X_entrenamiento, y_entrenamiento)
```

> 💡 `.fit()` es el método que **entrena** el modelo: le muestra los 
> datos de entrenamiento para que aprenda el patrón. `n_neighbors=3` 
> significa que mirará las 3 flores más parecidas para decidir.

---

## 🧱 Paso 6: Evaluar el modelo

Ahora comprobamos qué tan bien funciona con los datos de prueba 
(que el modelo **nunca vio** durante el entrenamiento):

```python
from sklearn.metrics import accuracy_score

predicciones = modelo.predict(X_prueba)
precision = accuracy_score(y_prueba, predicciones)

print("Precisión del modelo:", precision)
```

Con este dataset, es normal obtener una precisión muy alta (por 
encima del 90%) — es un dataset ideal para aprender.

---

## 🧱 Paso 7: Predecir una flor nueva

Ahora usemos el modelo para predecir la especie de una flor con 
medidas inventadas:

```python
flor_nueva = [[5.1, 3.5, 1.4, 0.2]]   # Longitud/anchura sépalo, longitud/anchura pétalo

prediccion = modelo.predict(flor_nueva)
especie_predicha = iris.target_names[prediccion[0]]

print("La flor pertenece a la especie:", especie_predicha)
```

---

## 📄 Código completo

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score

# 1. Cargar los datos
iris = load_iris()
X = iris.data
y = iris.target

# 2. Dividir en entrenamiento y prueba
X_entrenamiento, X_prueba, y_entrenamiento, y_prueba = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# 3. Entrenar el modelo
modelo = KNeighborsClassifier(n_neighbors=3)
modelo.fit(X_entrenamiento, y_entrenamiento)

# 4. Evaluar el modelo
predicciones = modelo.predict(X_prueba)
precision = accuracy_score(y_prueba, predicciones)
print("Precisión del modelo:", precision)

# 5. Predecir una flor nueva
flor_nueva = [[5.1, 3.5, 1.4, 0.2]]
prediccion = modelo.predict(flor_nueva)
especie_predicha = iris.target_names[prediccion[0]]
print("La flor pertenece a la especie:", especie_predicha)
```

---

## 🖥️ Cómo probarlo

1. Crea un archivo `mi_primer_modelo.py` en VS Code
2. Copia el código completo
3. Ejecuta:

```bash
python mi_primer_modelo.py
```

🎉 **¡Acabas de entrenar y usar tu primer modelo de Machine Learning!**

---

## 📤 Subirlo a GitHub

```bash
git add .
git commit -m "Agregar primer modelo de Machine Learning"
git push
```

---

## 🚀 Mejoras opcionales (para ir más allá)

- 🔢 Prueba a cambiar `n_neighbors` por otros valores (1, 5, 10) y 
  observa cómo cambia la precisión
- 🌳 Prueba otro algoritmo: `from sklearn.tree import 
  DecisionTreeClassifier` — la forma de usarlo es casi idéntica
- 📊 Usa `matplotlib` para graficar las flores y ver visualmente 
  cómo se agrupan por especie
- 📁 Prueba con otro dataset incluido en scikit-learn: 
  `load_wine()` o `load_digits()`

---

## ✅ Para quedarte con esto

- `scikit-learn` te permite entrenar modelos reales con muy pocas líneas de código
- El flujo siempre es parecido: cargar datos → dividir → entrenar 
  (`.fit()`) → evaluar → predecir (`.predict()`)
- Ya sabes entrenar y usar un modelo de clasificación real

---

## 🎉 ¡Felicidades, has completado la Guía de Principiantes! 🎉

Empezaste sin saber qué era la programación, y ahora sabes:

✅ Fundamentos de programación  
✅ Python: sintaxis, funciones, estructuras de datos  
✅ Git y GitHub, y cómo colaborar en equipo  
✅ Construir proyectos completos de principio a fin  
✅ Depurar errores como un programador experimentado  
✅ Los conceptos base de Inteligencia Artificial y Machine Learning  

Este es solo el comienzo. Ahora es momento de seguir aprendiendo 
participando en los proyectos activos de la asociación, revisando 
la carpeta [`proyectos/`](../../proyectos) y sumándote a las 
próximas reuniones.

**¡Bienvenido de verdad al mundo de la programación y la IA!** 🚀
