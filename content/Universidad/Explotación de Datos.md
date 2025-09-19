---
time: 2023-10-09 23:47
tags:
  - MOC
  - calendario
links:
  - "[[Tercer Año]]"
estado: cursando
código-materia: "07046"
correlativas:
  - "07017"
dictado: 2°C
año-carrera: Tercer año
schedule: Sábado, 08:00hs a 12:00hs
fechaPrimerParcial: 2025-09-27
fechaSegundoParcial: 2025-11-08
fechaPrimerRecuperatorio: 2025-11-22
---
Nota de inicio de la materia.

La profesora a cargo es **Silvia Pérez**.

---

## Notas asociadas

- [[Significado de R y R cuadrado]]

## Clase 1

Sitios para buscar bases de datos:

- https://data.buenosaires.gob.ar
- https://www.indec.gob.ar/indec/web/Institucional-Indec-BasesDeDatos
- https://www.datos.gob.ar/dataset
- https://www.google.com/publicdata/directory
- https://www.who.int/data/gho
- https://archive.ics.uci.edu/
- https://www.kaggle.com/datasets

### Qué es la Explotación de Datos

La **explotación de datos** es el proceso de analizar y utilizar grandes cantidades de datos (a menudo provenientes de diversas fuentes) para extraer información valiosa, patrones o tendencias que puedan ser aprovechados para tomar decisiones informadas. Es una parte clave de lo que se conoce como **ciencia de datos** y **análisis de datos**.

Este proceso puede incluir varias etapas, tales como:

1. **Recolección de datos**: Obtener datos de diversas fuentes (como bases de datos, sensores, redes sociales, etc.).
2. **Limpieza de datos**: Eliminar datos erróneos o irrelevantes.
3. **Análisis exploratorio**: Buscar patrones o insights iniciales.
4. **Modelado de datos**: Aplicar técnicas estadísticas o de machine learning para identificar relaciones y predecir comportamientos futuros.
5. **Visualización de datos**: Presentar los resultados de manera comprensible (gráficos, tablas, etc.).
6. **Toma de decisiones**: Usar los hallazgos para influir en decisiones estratégicas o operacionales.

En un contexto más técnico, la explotación de datos puede implicar el uso de algoritmos complejos, redes neuronales y otras herramientas avanzadas de inteligencia artificial para extraer valor de grandes volúmenes de datos no estructurados o semi-estructurados.

### Cómo se lleva a cabo la explotación de datos

Cada proceso de explotación de datos define un conjunto de información de entrada, un conjunto de transformaciones y un conjunto de información de salida.

**Ciclo de vida de los datos**:

![[Pasted image 20250818232740.png|400]]

---
## TP 1, enunciado parte B

Notas asociadas:

- [[Introducción a la estadística#Tipos de variables|Variables cuantitativas y variables cualitativas]].
- [[Explotación de datos - TP 1]]

---
## Clase 2

Notas: 

- [[Regresión lineal simple]].

## Base de datos de autos - Regresión lineal simple

Tarea que pidió hacer para la clase 13/09.

### 4. Analizar correlaciones para proponer un RLS

Antes de ajustar un modelo de regresión, es importante ver cómo las variables están correlacionadas entre sí, ya que esto te ayudará a decidir qué variables serán tus predictores y cuál será la variable dependiente.

Para hacer el análisis de correlación, se puede usar la función `cor()` en R para ver las correlaciones entre las variables numéricas. 

Por ejemplo:

```r
# Calcular la matriz de correlaciones
correlation_matrix <- cor(dataset[, sapply(dataset, is.numeric)], 
													use = "complete.obs")
correlation_matrix
```

**Nota**: Asegúrate de seleccionar solo las variables numéricas para evitar problemas. Si tienes variables categóricas, puedes optar por transformarlas o excluirlas en este paso.

Si buscamos la matriz de correlación en el dataset de auto obtendremos los siguientes valores en la terminal:

```
                    mpg displacement horsepower     weight acceleration
mpg           1.0000000   -0.8051269 -0.7784268 -0.8322442    0.4233285
displacement -0.8051269    1.0000000  0.8972570  0.9329944   -0.5438005
horsepower   -0.7784268    0.8972570  1.0000000  0.8645377   -0.6891955
weight       -0.8322442    0.9329944  0.8645377  1.0000000   -0.4168392
acceleration  0.4233285   -0.5438005 -0.6891955 -0.4168392    1.0000000
```

Esta **matriz de correlación**, muestra cómo se relacionan entre sí las variables numéricas en tu dataset. 

Si quisiéramos solo calcular entre dos variables, hacemos:

```r
correlation <- cor(cars_whitout_name$mpg, 
									cars_whitout_name$weight, 
									use = "complete.obs")
print(correlation)
```

En este caso, las variables son:

- **mpg**: Millas por galón (eficiencia de combustible)
- **displacement**: Desplazamiento del motor
- **horsepower**: Caballos de fuerza
- **weight**: Peso del vehículo
- **acceleration**: Aceleración

Cada celda de la matriz contiene el **coeficiente de correlación** entre dos variables. Este coeficiente varía entre **-1 y 1**, y su interpretación es la siguiente:

- **1**: Correlación perfecta positiva (si una variable sube, la otra también sube en la misma proporción).
- **0**: No hay correlación (las variables no tienen ninguna relación).
- **-1**: Correlación perfecta negativa (si una variable sube, la otra baja en la misma proporción).

#### Interpretación de las correlaciones

##### `mpg` (eficiencia de combustible)

- Con `displacement`: **-0.805**  
	**Significado**: Hay una correlación **negativa fuerte**. A medida que aumenta el **desplazamiento del motor**, el **mpg** tiende a disminuir. Es decir, los autos con motores más grandes suelen ser menos eficientes en cuanto al consumo de combustible.
- Con `horsepower`: **-0.778**  
	**Significado**: Hay una correlación **negativa fuerte**. A medida que los autos tienen más **caballos de fuerza**, el **mpg** tiende a ser más bajo. Es lógico, ya que los autos con motores más potentes suelen consumir más combustible.
- Con `weight`: **-0.832**  
    **Significado**: Hay una correlación **negativa fuerte**. A medida que el **peso** del vehículo aumenta, el **mpg** disminuye. Los vehículos más pesados suelen tener un rendimiento de combustible peor, ya que requieren más energía para moverse.
- Con `acceleration`: **0.423**  
    **Significado**: Hay una correlación **moderadamente positiva**. A medida que aumenta la **aceleración** (la capacidad de un vehículo para acelerar rápidamente), el **mpg** tiende a aumentar un poco. Sin embargo, esta relación no es tan fuerte como las otras.

##### `displacement` (desplazamiento del motor)

- **Con `horsepower`**: **0.897**  
    **Significado**: Hay una correlación **positiva muy fuerte**. Los motores con mayor **desplazamiento** generalmente tienen más **caballos de fuerza**, ya que un motor más grande puede generar más potencia.
- **Con `weight`**: **0.933**  
    **Significado**: Hay una correlación **muy fuerte positiva**. Los autos con motores de mayor **desplazamiento** tienden a ser más **pesados**. Esto se debe a que los motores grandes suelen estar en autos más grandes y pesados.
- **Con `acceleration`**: **-0.544**  
    **Significado**: Hay una correlación **negativa moderada**. A medida que aumenta el **desplazamiento**, la **aceleración** puede disminuir un poco. Los autos con motores grandes (aunque más potentes) no siempre son los más rápidos en términos de aceleración.

##### `horsepower` (caballos de fuerza)

- **Con `weight`**: **0.865**  
    **Significado**: Hay una correlación **positiva fuerte**. Los autos con más **caballos de fuerza** tienden a ser **más pesados**. Esto es lógico porque los autos con más potencia generalmente son más grandes y robustos.
- **Con `acceleration`**: **-0.689**  
    **Significado**: Hay una correlación **negativa moderada**. Los autos con más **caballos de fuerza** tienden a tener **menos aceleración**. Sin embargo, este efecto no es tan fuerte, y podría depender de otros factores como el diseño del vehículo.

##### `weight` (peso)

- **Con `acceleration`**: **-0.417**  
    **Significado**: Hay una correlación **negativa moderada**. Los autos más pesados tienden a tener **menos aceleración**. Los autos ligeros generalmente son más rápidos al acelerar, ya que tienen menos masa que mover.

##### Gráfico de dispersión

Gráfico de dispersión entre `mpg` y `weight`.

En este caso la variable dependiente sería la $y$ (mpg), y la independiente es $x$, que es peso del vehículo (weight). 

```r
# Gráfico de dispersión
library(ggplot2)

# Crear un gráfico de dispersión con la recta de regresión
ggplot(cars_whitout_name, aes(x = weight, y = mpg)) +
  geom_point() +  # Dibuja los puntos
  geom_smooth(method = "lm",
              se = FALSE,
              color = "blue") +  # Recta de regresión lineal
  labs(title = "Gráfico de dispersión: mpg vs weight", 
			x = "Peso del vehículo", 
			y = "Millas por galón (mpg)") +
			theme_minimal()
```

En este caso, podemos deducir que hay una correlación **negativa fuerte**. A medida que el **peso** del vehículo aumenta, el **mpg** disminuye. Los vehículos más pesados suelen tener un rendimiento de combustible peor, ya que requieren más energía para moverse.

La **recta de regresión** representa la mejor aproximación lineal de la relación entre las dos variables. Si la pendiente de la recta es **negativa** (lo que es esperado aquí), eso confirma que **a mayor peso, menor es el rendimiento de combustible**.

La relación entre el **peso del vehículo** (**weight**) y las **millas por galón** (**mpg**) es una de las más importantes al analizar la eficiencia del combustible de un automóvil. A partir del gráfico de dispersión con la recta de regresión que generaste, hay varias cosas que puedes mencionar:

###### Dirección de la relación

- **Relación negativa**: A partir de la gráfica y la recta de regresión, puedes observar que la relación entre **`weight`** y **`mpg`** es **negativa**. Esto significa que **a medida que el peso del vehículo aumenta, las millas por galón tienden a disminuir**.
- **Interpretación**: Los autos más pesados requieren más energía para moverse, lo que normalmente se traduce en un menor rendimiento de combustible. Es lógico, ya que los vehículos más grandes y pesados generalmente tienen motores más grandes que consumen más combustible.

###### Coeficiente de la recta de regresión

- La **recta de regresión** representa la mejor aproximación lineal de la relación entre las dos variables. Si la pendiente de la recta es **negativa** (lo que es esperado aquí), eso confirma que **a mayor peso, menor es el rendimiento de combustible**.
- **Valor de la pendiente**: Si la pendiente es, por ejemplo, **-0.007**, esto quiere decir que por cada aumento de **1 unidad en el peso (por ejemplo, 100 kg)**, el **mpg** disminuye en **0.007 unidades**.

###### Grado de la relación

- **Fuerza de la correlación**: Dependiendo de qué tan cerca estén los puntos de la recta de regresión (y de la densidad de los puntos en la gráfica), puedes observar la **fuerza de la relación**. Si los puntos están cerca de la línea, la correlación es fuerte. Si los puntos están dispersos, la relación es débil.
- $R^2$: El valor $R^2$ (que puedes obtener de un modelo de regresión) indica cuánta variabilidad de **`mpg`** se explica por el **peso** del vehículo. Si $R^2$ es cercano a 1, indica una relación fuerte, mientras que si es cercano a 0, indica que el peso explica poco sobre las variaciones en el mpg.

###### Posibles outliers

- Al observar el gráfico, verifica si hay **puntos atípicos** (outliers) que se alejan considerablemente de la recta. Estos pueden influir en el modelo y hacer que la relación no sea tan clara.
- Por ejemplo, si hay autos extremadamente ligeros con un **mpg** muy bajo o autos muy pesados con un **mpg** inusualmente alto, estos podrían ser outliers que afecten el análisis.

###### ¿Por qué existe esta relación?

- **Teoría detrás de la relación**: La relación negativa entre el peso y el mpg es bastante lógica desde un punto de vista físico. Los vehículos más pesados requieren más energía (y por lo tanto más combustible) para moverse, especialmente al momento de acelerar o mantener una velocidad constante. Los vehículos ligeros, por el contrario, necesitan menos energía y son generalmente más eficientes en cuanto a combustible.

###### Implicaciones prácticas

- **Diseño de vehículos**: Esta relación podría ser útil para los ingenieros y diseñadores de vehículos, ya que les permite optimizar el diseño y la eficiencia del combustible en función del peso del vehículo. Si la eficiencia del combustible es una prioridad, reducir el peso del automóvil podría ser una forma efectiva de mejorar el **mpg**.
- **Impacto ambiental y económico**: Los vehículos más ligeros no solo son más eficientes en términos de combustible, sino que también pueden ser **más sostenibles** y **económicos** para los consumidores, ya que pueden reducir las emisiones de gases contaminantes y los costos de operación.
#### Calculo de $R^{2}$

Se puede calcular el valor de $R^{2}$ (coeficiente de determinación) para la relación entre **`mpg`** y **`weight`** en R, lo cual te ayudará a entender qué tan bien el modelo de regresión lineal explica la variabilidad de **`mpg`** a partir de **`weight`**.

Pasos para calcular $R^{2}$ en R

1. **Ajusta un modelo de regresión lineal** utilizando **`lm()`** (que es la función para crear modelos lineales).
2. **Extrae el valor de R²** desde el resumen del modelo.

Código para calcular $R^{2}$:

```r
# Ajustar el modelo de regresión lineal
modelo <- lm(mpg ~ weight, data = cars_whitout_name)

# Resumen del modelo
summary(modelo)
```

Explicación:

- **`lm(mpg ~ weight, data = cars_whitout_name)`** ajusta un modelo de regresión lineal, donde **`mpg`** es la variable dependiente y **`weight`** es la variable independiente.
- **`summary(modelo)`** proporciona un resumen detallado del modelo de regresión, que incluye el valor de **R²**.

Cuando ejecutes `summary(modelo)`, verás una salida similar a esta:

```r
Call:
lm(formula = mpg ~ weight, data = cars_whitout_name)

Residuals:
    Min      1Q  Median      3Q     Max 
-10.521  -2.889  -0.543   2.128  15.643 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)
(Intercept)  37.2851     1.4165   26.32   <2e-16 ***
weight       -0.0074     0.0004  -18.50   <2e-16 ***

Residual standard error: 4.937 on 398 degrees of freedom
Multiple R-squared:  0.6932,	Adjusted R-squared:  0.6926 
F-statistic: 342.4 on 1 and 398 DF,  p-value: < 2.2e-16
```

- R-squared ($R^{2}$): En la línea que dice Multiple R-squared verás un valor como **0.6932**. Este es el coeficiente de determinación $R^{2}$.
    - $R^{2}$ = 0.6932 significa que **aproximadamente el 69.32% de la variabilidad en `mpg`** puede ser explicada por el **peso** del vehículo en este modelo lineal.
- **Adjusted R-squared**: Este valor ajusta $R^{2}$ para tener en cuenta el número de variables en el modelo, y es útil cuando se incluyen muchas variables. En modelos simples como este, suelen ser muy similares.

Interpretación de $R^{2}$:

- Si $R^{2}$ es **0.6932**, significa que **el peso del vehículo** explica **aproximadamente el 69.32%** de la variabilidad en el rendimiento de combustible (**mpg**).
- El resto de la variabilidad (aproximadamente el 30.68%) está influenciado por factores que no están en el modelo o por el error aleatorio.

#### El modelo es significativo?

Cuando se dice que el modelo es **significativo**, nos referimos a que la relación entre las variables independientes y dependientes es **estadísticamente significativa**, es decir, que el efecto de la variable independiente en la variable dependiente no es debido al azar.

Para verificar la **significancia** del modelo, debes observar el **valor p** (p-value) de la variable independiente (en tu caso, **`weight`**). Este valor te indica si el efecto de **`weight`** sobre **`mpg`** es significativo o no.

Si el valor p de la **pendiente** (coeficiente de **`weight`**) es menor que un umbral predefinido (normalmente 0.05), podemos concluir que la relación entre **`weight`** y **`mpg`** es **estadísticamente significativa**.

En el resumen de tu modelo (`summary(modelo)`), busca algo como esto:

```r
Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) 46.3173992  0.7962915   58.17   <2e-16 ***
weight      -0.0076766  0.0002578  -29.78   <2e-16 ***
```

La fila que corresponde al peso, el p valor corresponde a h_0 beta de peso  = 0, h_1 = beta de peso es distinto de 0. Rescribir. 

Intercepto (Intercept):

- **Estimate (46.3173992)**: Este es el valor estimado para el intercepto, es decir, el valor de **`mpg`** cuando **`weight`** es igual a 0.
    - **Interpretación**: Si el peso del vehículo fuera 0 (lo cual no es un escenario realista, pero es un valor matemático), el modelo predice que el **`mpg`** sería de **46.32**.
    - Sin embargo, este valor tiene poco sentido práctico porque no puede haber un vehículo con peso igual a 0, pero es importante para la ecuación de la regresión.
- **Std. Error (0.7962915)**: Es el error estándar del **intercepto**. Un error estándar pequeño indica que el valor estimado del intercepto es preciso.
- **t value (58.17)**: Es el valor t que se usa para probar si el intercepto es significativamente diferente de 0. En este caso, **58.17** es muy grande, lo que sugiere que el intercepto es **altamente significativo**.
- **Pr(>|t|) (<2e-16)**: Es el valor **p** para el intercepto. El valor **`<2e-16`** significa que el valor p es tan pequeño que es prácticamente **0**. Esto indica que el intercepto es **altamente significativo**.
2. **Peso (weight)**
	- **Estimate (-0.0076766)**: Este es el coeficiente de la variable **`weight`**, que indica cuánto cambia el **`mpg`** por cada aumento unitario en el peso del vehículo. En este caso:
	    - **Interpretación**: Por cada **aumento de 1 kg** en el peso del vehículo, el **`mpg`** disminuye en **0.0077 unidades**.
	    - Es decir, **los vehículos más pesados** tienen un **rendimiento de combustible peor**.
	- **Std. Error (0.0002578)**: Es el error estándar asociado al coeficiente de **`weight`**. Un error estándar pequeño indica que la estimación es precisa.
	- **t value (-29.78)**: El valor t para **`weight`** es **-29.78**, lo que es bastante grande en valor absoluto, indicando que el coeficiente de **`weight`** es **muy significativo** (es decir, no es 0).
	- **Pr(>|t|) (<2e-16)**: El valor p asociado a **`weight`** es también **`<2e-16`**, lo que significa que es **estadísticamente significativo** a un nivel muy alto (es decir, **el efecto de `weight` sobre `mpg` es muy fuerte y no es debido al azar**).

La notación **`2e-16`** es una forma compacta de escribir un número en notación científica. Es equivalente a $2 \times 10^{-16}$.

**2e-16** significa **0.0000000000000002** (es decir, el número **2** seguido de 16 ceros después del punto decimal).

En términos prácticos, **`<2e-16`** quiere decir que el valor p es **extremadamente pequeño**, mucho más pequeño que cualquier umbral típico de significancia (como **0.05**), lo que indica que los coeficientes son **altamente significativos**.

#### Analizar los supuestos del modelo

En regresión lineal, **hay varios supuestos** que debemos verificar para asegurarnos de que los resultados del modelo sean válidos. 

Los supuestos básicos para un modelo de **regresión lineal simple (RLS)** son:

- **Linealidad**: La relación entre la variable dependiente (**`mpg`**) y la independiente (**`weight`**) debe ser lineal. Puedes verificar la linealidad visualmente con un gráfico de dispersión (que ya generaste) y asegurarte de que los puntos siguen una tendencia lineal. Si la relación no es lineal, el modelo de regresión lineal no sería apropiado.
	Qué el $R^2$ sea aceptable.
- **Independencia de los errores (residuos)**: Los errores (residuos) deben ser independientes entre sí. Si hay patrones en los residuos, es posible que se violen los supuestos.
  
  **No la vamos a mirar, la asumimos según el origen de los datos**.
  
  Para verificar esto, puedes usar un **gráfico de residuos**:
  
	```r
	# Graficar los residuos vs los valores ajustados
	plot(modelo, which = 1)
	```

	Si los puntos se distribuyen de manera aleatoria y no muestran ningún patrón claro, esto indica que los residuos son independientes.
    
	Si observas patrones, como una forma curvilínea, podría indicar que el modelo no es adecuado y se necesita un modelo más complejo o una transformación de las variables.
-  **Homoscedasticidad**: La [[Varianza y desvio estandar#Varianza|varianza]] de los residuos debe ser constante a través de todos los niveles de la variable independiente (**`weight`**).
	  
	Puedes verificar la **homoscedasticidad** con el **gráfico de residuos vs valores ajustados**:
	
	Si los residuos tienen una dispersión constante a lo largo de todos los valores de **`weight`**, significa que hay homoscedasticidad.
    
	Si ves una "forma de embudo" o alguna tendencia en la dispersión, podría haber **heteroscedasticidad**, lo que indica que los residuos no tienen varianza constante.
- **Interpretar el coeficiente estimado de X (pendiente)**: El **coeficiente estimado de X** es el valor de la pendiente en la recta de regresión. En tu modelo, el coeficiente estimado de **`weight`** es:
  
	```r
	weight      -0.0076766  0.0002578  -29.78   <2e-16 ***
	```

	Esto significa que, por cada aumento de 1 unidad en **`weight`** (por ejemplo, un aumento de 1 kg), el **`mpg`** disminuye en **0.0076766 unidades**.

	En otras palabras:
	- Si un vehículo aumenta su peso en 1000 kg (1 tonelada), el **`mpg`** disminuiría en **7.6766 unidades**.

**Me falta el último, que los errores estén alrededor de 0**

#### Ver intervalos de confianza de los coeficientes

Los **intervalos de confianza** nos dicen el rango en el cual podemos estar relativamente seguros de que el valor del coeficiente real se encuentra. Para obtener los intervalos de confianza de los coeficientes en tu modelo, puedes hacer lo siguiente:

El comando `confint(model)` devuelve los intervalos de confianza para cada uno de los coeficientes de tu modelo de regresión. En este caso, has obtenido:

```r
                   2.5 %       97.5 %
(Intercept) 44.751899760 47.882898590
weight      -0.008183466 -0.007169746
```

Valor del intercepto: 46.32.

Intervalo de confianza (2.5 % - 97.5 %) para el intercepto: **\[44.75, 47.88\]**.

Esto significa que, con un nivel de confianza del **95%**, podemos afirmar que el verdadero valor del **intercepto** (el valor de **`mpg`** cuando el peso es 0) está en el rango **entre 44.75 y 47.88**. Es decir, estamos bastante seguros de que el intercepto real del modelo se encuentra dentro de este rango.

**Significado práctico**: Aunque en la práctica no tiene mucho sentido un vehículo con peso igual a 0, este intervalo nos dice que el valor del **`mpg`** para un vehículo de **peso 0** debe estar entre **44.75 y 47.88**, si es que seguimos la suposición del modelo.

Intervalo de confianza para el coeficiente de `weight`:

- **Valor estimado del coeficiente de `weight`**: **-0.0077**.
- **Intervalo de confianza (2.5 % - 97.5 %) para `weight`**: **\[-0.00818, -0.00717\]**.

Esto significa que, con un nivel de confianza del **95%**, podemos decir que el verdadero valor del coeficiente para **`weight`** se encuentra entre **-0.00818 y -0.00717**. En otras palabras, **la relación entre el peso y el rendimiento de combustible es negativa**, y **por cada kilogramo adicional de peso, el `mpg` disminuye entre 0.00717 y 0.00818 unidades**.

**Significado práctico**: En términos prácticos, este intervalo de confianza nos da un rango más preciso para el impacto del peso sobre el rendimiento de combustible. Aunque el valor estimado es **-0.0077**, sabemos que el verdadero valor puede ser ligeramente más negativo (hasta **-0.00818**) o menos negativo (hasta **-0.00717**), pero con un 95% de confianza.

#### Usar el modelo para predecir

Una vez que el modelo ha sido ajustado, puedes usarlo para predecir los valores de **`mpg`** para nuevos datos. 

Supón que tienes un nuevo valor de **`weight`** (por ejemplo, 3000 kg), y quieres predecir el **`mpg`**:

```r
# Predecir el mpg para un nuevo peso (por ejemplo, 3000 kg)
nuevo_dato <- data.frame(weight = 3000)
prediccion <- predict(modelo, nuevo_dato)
prediccion
```

##### Paso a paso

Ya has ajustado tu modelo con algo como esto:

```r
modelo <- lm(mpg ~ weight, data = autos)
```

Ahora que tienes el modelo, puedes usarlo para hacer predicciones.

Supón que quieres predecir el **`mpg`** para un vehículo cuyo **peso** es **3000 kg**. Necesitas crear un nuevo conjunto de datos con este valor de **`weight`**.

```r
# Crear un nuevo dato con el peso 3000 kg
nuevo_dato <- data.frame(weight = 3000)
```

Con el modelo ajustado (`modelo`), puedes usar la función `predict()` para predecir el valor de **`mpg`** para el nuevo dato.

```r
# Hacer la predicción para el nuevo dato
prediccion <- predict(modelo, nuevo_dato)

# Ver el resultado
prediccion
```

Este código te dará la predicción de **`mpg`** para un vehículo de **3000 kg** de peso.

Qué hace `predict()`:

- `predict()` toma el **modelo ajustado** (`modelo` en este caso) y un **nuevo conjunto de datos** (el valor de **`weight`** para el que quieres hacer la predicción) y te devuelve el valor predicho de **`mpg`**.
- El valor que devuelve **`predict()`** es el **valor ajustado de `mpg`** según la ecuación de la regresión.

Si el resultado de la predicción es:

```r
prediccion
[1] 23.28758
```

Esto significa que, según el modelo, un vehículo de **3000 kg** de peso tendría un rendimiento de combustible de **23.28758 mpg**.

Si también te gustaría obtener los **intervalos de predicción** (es decir, el rango en el que el valor predicho de **`mpg`** podría estar, con un nivel de confianza), puedes usar la opción `interval` en `predict()`:

```r
# Obtener los intervalos de predicción (por defecto al 95%)
intervalos <- predict(modelo, nuevo_dato, interval = "prediction")

# Ver los intervalos
intervalos
```

Esto te dará un intervalo **inferior** y **superior** para la predicción, indicando el rango dentro del cual se espera que se encuentre el valor real de **`mpg`** para ese valor de **`weight`**.

Ejemplo de resultado:

```r
           fit       lwr       upr
1 25.3421  24.1234  26.5608
```

- **fit**: Es la **predicción central** para el nuevo valor de **`weight`** (25.34 mpg en este caso).
- **lwr**: Es el **valor inferior** del intervalo (24.12 mpg).
- **upr**: Es el **valor superior** del intervalo (26.56 mpg).

Este intervalo te dice que, con un **95% de confianza**, el **mpg** real para un vehículo de **3000 kg** debería estar entre **24.12 mpg** y **26.56 mpg**.

#### Anotaciones

Para regresión simple, supuestos a controlar, coeficiente de correlación. Normalidad, varianza constante, residuales alrededor de cero.

qqplot para ver la normalidad. En el grafico vero que los puntos están cerca de la recta. Algunos valores se escapan. No se cumple muy bien la normalidad.

Las 3 cosas las podemos mirar por medio de una prueba de hipótesis.

---
## Clase 3

#### Multicolinealidad

La **multicolinealidad** es un fenómeno que ocurre en análisis de datos, especialmente en regresión múltiple, cuando dos o más variables independientes (predictoras) están altamente correlacionadas entre sí. Es decir, cuando hay una relación lineal fuerte entre algunas de las variables predictoras, lo que puede generar varios problemas en la estimación del modelo y en la interpretación de los resultados.

### Problemas que causa la multicolinealidad:

1. **Inestabilidad en los coeficientes**: Los coeficientes de las variables predictoras pueden volverse muy sensibles a pequeñas fluctuaciones en los datos. Esto significa que el modelo puede dar resultados muy distintos si se cambia un poco el conjunto de datos.
    
2. **Errores estándar elevados**: La multicolinealidad aumenta los errores estándar de los coeficientes estimados, lo que hace que sea más difícil determinar si un predictor tiene un efecto significativo sobre la variable dependiente. Esto puede llevar a la conclusión errónea de que una variable no tiene un impacto cuando en realidad sí lo tiene.
    
3. **Interpretación ambigua de los resultados**: Como las variables predictoras están muy relacionadas, puede ser difícil aislar el impacto de una variable en particular sobre la variable dependiente. Esto dificulta la interpretación de los coeficientes y las relaciones subyacentes entre las variables.
    
4. **Modelo menos confiable**: Los modelos con multicolinealidad pueden ser más propensos a sobreajustarse (overfitting), ya que el modelo puede aprender patrones espurios en los datos debido a la alta correlación entre las variables.
    

### ¿Cómo se detecta la multicolinealidad?

Algunos métodos comunes para detectar la multicolinealidad incluyen:

1. **Matriz de correlación**: Puedes calcular una matriz de correlación entre las variables independientes. Si encuentras que varias de ellas tienen correlaciones altas, eso es un indicio de multicolinealidad.
    
2. **Factor de inflación de la varianza (VIF, por sus siglas en inglés)**: El VIF mide cuánto aumenta la varianza de un coeficiente de regresión debido a la colinealidad con otras variables. Un valor de VIF superior a 10 (dependiendo de la fuente) puede indicar multicolinealidad severa.
    
3. **Condición del número**: Este es un diagnóstico técnico que examina la matriz de diseño del modelo para detectar multicolinealidad. Un valor de número de condición elevado (mayor que 30) sugiere un problema de multicolinealidad.
    

### ¿Cómo se maneja la multicolinealidad?

1. **Eliminar una de las variables correlacionadas**: Si tienes dos o más variables predictoras que están muy correlacionadas, puedes intentar eliminar una de ellas. Esto puede reducir la redundancia sin perder mucha información relevante.
    
2. **Combinar variables correlacionadas**: Si las variables están muy relacionadas, podrías combinarlas en una sola variable, como mediante la técnica de análisis de componentes principales (PCA), que reduce la dimensionalidad sin perder mucha información.
    
3. **Regularización**: Métodos como **Lasso** o **Ridge Regression** pueden ayudar a reducir el impacto de las variables correlacionadas al imponer penalizaciones en los coeficientes. Estos métodos son más robustos a la multicolinealidad.
    
4. **Transformaciones o creación de variables**: En algunos casos, puede ser útil transformar las variables (por ejemplo, usando logaritmos) o crear nuevas variables que capten la esencia de las variables correlacionadas de manera más compacta.
    

En resumen, la multicolinealidad es un problema común en la modelización estadística que afecta la precisión y la interpretabilidad de los modelos. Detectarla y gestionarla adecuadamente es fundamental para obtener resultados más confiables.