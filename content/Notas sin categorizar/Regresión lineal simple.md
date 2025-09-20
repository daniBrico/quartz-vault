---
date: 2025-09-18 14:32
---
# Regresión lineal simple

La **regresión lineal simple** es uno de los modelos estadísticos más básicos y comunes para analizar la relación entre dos variables cuantitativas. El objetivo es encontrar la relación lineal entre una variable independiente ($X$) y una variable dependiente ($Y$).

La regresión lineal simple busca modelar la relación entre estas dos variables con una ecuación de la forma:

$$\large Y = \beta_0 + \beta_1 X + \huge{\varepsilon}$$

Donde:

- $Y$: es la variable dependiente (lo que queremos predecir).
- $X$: es la variable independiente (la que usamos para hacer la predicción).
- $\beta_0$: es la intersección o el valor de $Y$ cuando $X = 0$ (también conocida como el "**intercepto**").
- $\beta_1$: es la pendiente de la línea de regresión (indica cómo cambia $Y$ cuando $X$ aumenta en una unidad).
- $\huge \varepsilon$: es el término de error, que representa las diferencias entre los valores predichos y los valores reales de $Y$.

![[Regresión lineal, fórmula.excalidraw.png]]

## ¿Cómo se interpreta la regresión lineal simple?

1. **Intercepción ($\beta_0$)**: Es el valor de $Y$ cuando $X = 0$. A veces no tiene sentido interpretarlo dependiendo del contexto de los datos (por ejemplo, si $X = 0$ no es posible o no tiene sentido físico).
2. **Pendiente ($\beta_1$)**: Representa el cambio promedio en $Y$ por cada unidad de cambio en $X$. Si $\beta_1 = 2$, significa que por cada unidad que aumente $X$, $Y$ aumentará en 2 unidades.

## ¿Cómo se obtiene la ecuación?

Para encontrar los valores de $\beta_0$ y $\beta_1$, generalmente se usa el **método de los mínimos cuadrados** ([[Interpretación de los mínimos cuadrados - recta de regresión]]). Este método busca minimizar la suma de los errores al cuadrar la diferencia entre los valores observados ($Y$) y los valores predichos ($\hat{Y}$):

$$\large \text{Suma de errores} = \sum (Y_i - \hat{Y}_i)^2$$

Donde $\hat{Y}_i$ es el valor predicho de $Y$ para un valor específico de $X_i$. La técnica de mínimos cuadrados encuentra los valores de $\beta_0$ y $\beta_1$ que minimizan esta suma.

## Para qué sirve el análisis de regresión

El análisis de regresión tiene varios propósitos clave.

### Describir/modelar la relación entre $X$ e $Y$

El análisis de regresión permite **comprender y modelar** cómo una variable dependiente ($Y$) está relacionada con una o más variables independientes ($X$). Esta relación puede ser tanto de tipo lineal (en el caso de regresión lineal) como no lineal (en modelos más complejos).

**Objetivo**: A través del análisis de regresión, podemos describir cómo un cambio en $X$ afecta a $Y$, y la forma de esa relación. En el caso de la regresión lineal, esto sería en términos de la pendiente de la línea de regresión, que indica cómo $Y$ cambia cuando $X$ cambia en una unidad.

### Predecir valores de $Y$ a partir de $X$

Una de las aplicaciones más comunes del análisis de regresión es la **predicción**.

**Objetivo**: Una vez que hemos modelado la relación entre $X$ e $Y$, podemos utilizar la ecuación de la regresión para **predecir** valores futuros de $Y$ dado un nuevo valor de $X$.

Por ejemplo, si tenemos un modelo que predice el precio de una casa en función de su tamaño, podemos usar el modelo para predecir el precio de casas de tamaños específicos que no estén en el conjunto de datos original.

### Probar hipótesis acerca de los parámetros del modelo

La regresión también permite **probar hipótesis estadísticas** sobre los parámetros del modelo, como los coeficientes ($\beta_0$, $\beta_1$, etc.).

**Objetivo**: Queremos saber si los coeficientes de la regresión son **estadísticamente significativos**. Es decir, si existe evidencia suficiente para afirmar que un cambio en $X$ realmente tiene un impacto en $Y$.

Por ejemplo, podríamos tener la hipótesis de que el tamaño de la casa ($X$) tiene un efecto significativo sobre su precio ($Y$). Usamos el análisis de regresión para determinar si el coeficiente asociado a $X$ es estadísticamente significativo (generalmente mediante un valor p).

Además, podemos probar **hipótesis sobre la relación entre las variables** (por ejemplo, si la pendiente es positiva o negativa, o si existe una relación nula entre $X$ y $Y$).

## ¿Cómo evaluamos el modelo?

Una vez que tienes la ecuación de la regresión, puedes evaluarla con algunos indicadores como:

1. **[[R-cuadrado]] ($R^2$)**: Mide el porcentaje de la variabilidad total de $Y$ que se puede explicar por el modelo. Va de $0$ a $1$, donde $1$ indica que el modelo explica completamente la variabilidad de $Y$.
2. **Error estándar**: Mide la cantidad promedio de error que comete el modelo al predecir los valores de $Y$.
3. **Valor p**: Indica si las variables en el modelo son estadísticamente significativas. Si el valor p de $\beta_1$ es pequeño (por lo general menor que 0.05), entonces se considera que hay una relación significativa entre $X$ y $Y$.

## ¿Cuándo usarla?

La regresión lineal simple es adecuada cuando:

- Existe una relación aproximada lineal entre las dos variables.
- Los residuos (errores) del modelo se distribuyen de manera aproximadamente normal.
- No hay mucha [[Multicolinealidad]] (en este caso solo hay una variable independiente).

## Interpretación de los coeficientes de regresión

### Pendiente ($\beta_1$):

La **pendiente** en un modelo de regresión lineal muestra cuánto cambia la variable dependiente (respuesta) por cada **aumento de una unidad** en la variable independiente (predictora).

**Interpretación**: Si $\beta_1 = 3$, significa que por cada unidad que aumente $X$ (la variable predictora), $Y$ (la variable de respuesta) aumenta en **3 unidades**. Es el **cambio promedio** en $Y$ asociado a un cambio unitario en $X$.

### Intercepto ($\beta_0$)

El **intercepto** es el valor de la variable dependiente $Y$ cuando la variable independiente $X = 0$.

**Interpretación**: Si $\beta_0 = 5$, significa que cuando $X = 0$, el valor de $Y$ es **5**. Es el valor de $Y$ donde la línea de regresión corta el eje $Y$.

#### Ejemplo

Si la ecuación de la regresión es:

$$\large Y = 2 + 3X$$

- **Intercepto** ($\beta_0 = 2$): Cuando $X = 0$, $Y = 2$.
- **Pendiente** ($beta_1 = 3$): Por cada aumento de 1 unidad en $X$, $Y$ aumenta en 3 unidades.

Es como si $X$ tuviera un impacto directo sobre $Y$ y el intercepto te da el punto de partida.