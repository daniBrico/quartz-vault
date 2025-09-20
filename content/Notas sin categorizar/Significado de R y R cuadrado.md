---
date: 2025-09-12 16:28
---
$R$ y $R^2$ son dos medidas estadísticas muy utilizadas en análisis de regresión para evaluar la relación entre las variables y la calidad del modelo predictivo.

## R (Coeficiente de correlación lineal de Pearson)

El **coeficiente de correlación RR** mide la fuerza y la dirección de la relación lineal entre dos variables. Va de **-1** a **1**:

- $R = 1$: Correlación positiva perfecta (a medida que una variable aumenta, la otra también lo hace de manera perfecta).
- $R = -1$: Correlación negativa perfecta (a medida que una variable aumenta, la otra disminuye de manera perfecta).
- $R = 0$: No hay correlación lineal entre las dos variables.

**Fórmula del coeficiente de correlación R**:

$$\large R = \frac{\sum{(x_i - \bar{x})(y_i - \bar{y})}}{\sqrt{\sum{(x_i - \bar{x})^2}\sum{(y_i - \bar{y})^2}}}$$

Donde:

- $x_i$ y $y_i$ son los valores de las variables.
- $\bar{x}$ y $\bar{y}$ son las medias de las variables.

**Interpretación**: El coeficiente de correlación R indica si existe una relación lineal entre las dos variables y si esa relación es positiva o negativa. Cuanto más cercano a 1 o -1 sea el valor de R, más fuerte será la relación.

## $R^2$ (Coeficiente de determinación)

El **coeficiente de determinación $R^2$** es una medida que indica el porcentaje de la variabilidad de una variable dependiente que puede ser explicada por el modelo de regresión lineal. Se obtiene elevando al cuadrado el coeficiente de correlación $R$.

**Fórmula de $R^2$**:

$$\large R^2 = 1 - \frac{\sum{(y_i - \hat{y}_i)^2}}{\sum{(y_i - \bar{y})^2}}$$

Donde:

- $y_i$ son los valores observados.
- $\hat{y}_i$ son los valores predichos por el modelo.
- $\bar{y}$ es la media de los valores observados.

**Interpretación**:

- **4**: El modelo predice perfectamente los valores observados (100% de la variabilidad está explicada por el modelo).
- **$R^2 = 0$**: El modelo no explica nada de la variabilidad (el modelo es igual a una simple media de los datos).
- **$0 < R^2 < 1$**: El modelo explica una proporción de la variabilidad de los datos. Un valor más cercano a 1 indica un mejor ajuste del modelo.

Por ejemplo, si un modelo tiene $R^2 = 0.85$, significa que el 85% de la variabilidad en los datos de la variable dependiente se explica por el modelo, y el 15% restante es explicado por factores no considerados en el modelo o por errores aleatorios.