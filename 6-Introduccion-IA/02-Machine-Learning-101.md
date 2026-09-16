[02-Machine-Learning-101.md](https://github.com/user-attachments/files/32293966/02-Machine-Learning-101.md)
# Machine Learning 101

## 🎯 Objetivo

Entender, sin fórmulas complicadas, cómo una máquina "aprende" a 
partir de datos, y conocer el vocabulario básico que vas a encontrar 
constantemente en este campo.

---

## 🧠 La idea central del Machine Learning

En programación tradicional, un humano escribe **reglas exactas**:

```
SI la temperatura > 30 ENTONCES enciende el aire acondicionado
```

En Machine Learning, en cambio, **le das ejemplos a la máquina** y 
ella misma descubre el patrón:

```
Le muestras 1000 casas con su tamaño y su precio de venta,
y la máquina "aprende" la relación entre ambos,
para poder predecir el precio de una casa nueva.
```

**No le dices la fórmula** — la máquina la deduce a partir de los 
datos que le diste.

---

## 📊 Vocabulario esencial

| Término | Qué significa |
|---|---|
| **Dataset** | El conjunto de datos que usas para entrenar |
| **Features** (características) | Las variables de entrada (ej: tamaño de una casa, número de habitaciones) |
| **Label** (etiqueta) | El resultado que quieres predecir (ej: el precio) |
| **Modelo** | El "programa" resultante, que ya aprendió el patrón |
| **Entrenamiento (training)** | El proceso de "enseñarle" al modelo con los datos |
| **Predicción** | Usar el modelo ya entrenado para adivinar un resultado nuevo |

### Ejemplo aplicado:

Si quieres predecir el precio de una casa:
- **Features**: tamaño (m²), número de habitaciones, ubicación
- **Label**: precio de venta
- **Dataset**: una tabla con cientos de casas ya vendidas, con sus 
  features y su precio real

---

## 🎓 Los dos tipos principales de aprendizaje

### 1. Aprendizaje Supervisado

Le das al modelo **datos ya etiquetados** (con la respuesta 
correcta incluida), y aprende la relación entre las entradas y esa 
respuesta.

**Ejemplo:** miles de correos marcados como "spam" o "no spam". El 
modelo aprende qué características tienen los correos spam, para 
poder clasificar correos nuevos.

Dos tareas típicas dentro del aprendizaje supervisado:

- **Clasificación**: predecir una categoría (¿spam o no spam? ¿gato 
  o perro?)
- **Regresión**: predecir un número (¿cuánto costará esta casa? 
  ¿cuántos grados hará mañana?)

### 2. Aprendizaje No Supervisado

Le das al modelo datos **sin etiquetar** (sin la respuesta 
correcta), y él mismo busca patrones o agrupaciones por su cuenta.

**Ejemplo:** una tienda online agrupa a sus clientes en distintos 
"tipos de comprador" según su comportamiento de compra, sin que 
nadie le diga de antemano cuáles son esos grupos.

---

## 🔄 El proceso completo, paso a paso

```
1. Recopilar datos
   ↓
2. Limpiar y preparar los datos
   ↓
3. Dividir los datos: entrenamiento y prueba
   ↓
4. Entrenar el modelo (con los datos de entrenamiento)
   ↓
5. Evaluar el modelo (con los datos de prueba, que no ha visto antes)
   ↓
6. Usar el modelo para hacer predicciones nuevas
```

### ¿Por qué dividir los datos en dos partes?

Si evalúas el modelo con los **mismos datos** que usaste para 
entrenarlo, es como corregir un examen dándole las respuestas al 
alumno de antemano — no sabes si realmente "aprendió" o solo 
"memorizó".

Por eso se separan:
- **Datos de entrenamiento** (normalmente 70-80%): para que el 
  modelo aprenda
- **Datos de prueba** (normalmente 20-30%): para comprobar si 
  funciona bien con datos que **nunca ha visto**

---

## ⚠️ Un problema común: el "overfitting"

El **overfitting** (sobreajuste) ocurre cuando un modelo 
**"memoriza" demasiado** los datos de entrenamiento, incluyendo su 
ruido y casos particulares, en vez de aprender el patrón general.

### Analogía

Imagina un estudiante que memoriza las respuestas exactas de los 
exámenes de años anteriores, palabra por palabra, en vez de entender 
la asignatura. Le irá genial si le repiten el mismo examen, pero 
fatal ante preguntas nuevas.

Un modelo con overfitting funciona **muy bien con los datos que ya 
conoce**, pero **mal con datos nuevos** — justo lo contrario de lo 
que queremos.

---

## 🎯 ¿Qué necesitas para hacer Machine Learning?

En la práctica, no programas el algoritmo matemático desde cero — 
se usan librerías ya construidas por la comunidad. Las más comunes 
en Python:

| Librería | Para qué se usa |
|---|---|
| **pandas** | Cargar y manipular datos en tablas |
| **numpy** | Cálculos matemáticos y con arrays |
| **scikit-learn** | Entrenar modelos de Machine Learning "clásico" |
| **matplotlib / seaborn** | Visualizar datos con gráficos |
| **tensorflow / pytorch** | Deep Learning (redes neuronales) |

En la próxima lección usarás **scikit-learn**, la librería más 
usada para empezar en Machine Learning.

---

## ✅ Para quedarte con esto

- El ML aprende patrones **a partir de datos**, no de reglas escritas a mano
- **Features** son las entradas, **label** es lo que quieres predecir
- El aprendizaje puede ser **supervisado** (con respuestas) o **no 
  supervisado** (sin respuestas)
- Los datos se dividen en **entrenamiento** y **prueba**, para 
  comprobar que el modelo realmente aprendió, no solo memorizó
- El **overfitting** es cuando un modelo memoriza en vez de generalizar

---

## 🎯 Siguiente paso

Teoría suficiente — vamos a entrenar tu primer modelo real con 
Python:
**[Tu Primer Modelo →](./03-Tu-primer-modelo.md)**
