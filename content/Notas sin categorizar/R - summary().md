---
date: 2025-09-18 16:57
tags:
  - r
---
La función `summary()` en R es muy útil para obtener una **descripción general** de los datos, mostrando información resumida sobre el contenido de un objeto (como un vector, data frame, modelo, etc.). Dependiendo del tipo de objeto que le pases, `summary()` te devolverá diferentes tipos de estadísticas y resumen.

## Resumen de los principales usos de `summary()`

### Para un vector numérico

Cuando usas `summary()` con un vector numérico, te da un conjunto de estadísticas descriptivas básicas:

- **Mínimo (Min)**: El valor más bajo.
- **1er cuartil (1st Qu.)**: El valor por debajo del cual se encuentra el 25% de los datos.
- **Mediana (Median)**: El valor que divide la mitad de los datos (el 50%).
- **Media (Mean)**: Promedio de los datos.
- **3er cuartil (3rd Qu.)**: El valor por debajo del cual se encuentra el 75% de los datos.
- **Máximo (Max)**: El valor más alto.

Ejemplo:

```R
datos <- c(2, 4, 6, 8, 10)
summary(datos)
```

Salida:

```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
      2       4       6       6       8      10 
```

### Para un vector de caracteres

Si pasas un vector de caracteres a `summary()`, te da un resumen de las **frecuencias** de los distintos valores en el vector.

Ejemplo:

```R
nombres <- c("Juan", "Ana", "Pedro", "Juan", "Ana")
summary(nombres)
```

Salida:

```
   Length     Class      Mode 
        5    character    character 
```

(Nota: La salida en este caso es más informativa sobre el tipo de objeto, ya que es un vector de caracteres).

### Para un `data.frame`

Cuando usas `summary()` con un `data.frame`, devuelve un resumen estadístico para **cada columna** del data frame, proporcionando estadísticas similares a las que te da con un vector numérico (como Min, 1er cuartil, Media, etc.), pero también incluirá información de las variables categóricas (factor o texto), donde mostrará la **frecuencia** de cada nivel.

Ejemplo:

```R
df <- data.frame(
  Edad = c(25, 30, 35, 40),
  Nombre = c("Juan", "Ana", "Pedro", "Maria"),
  Ciudad = factor(c("Madrid", "Barcelona", "Madrid", "Sevilla"))
)

summary(df)
```

Salida:

```
     Edad         Nombre       Ciudad    
 Min.   :25.0   Length:4     Madrid   :2  
 1st Qu.:27.5   Class :character Barcelona:1  
 Median :32.5   Mode  :character Sevilla  :1  
 Mean   :32.5                    
 3rd Qu.:37.5                    
 Max.   :40.0                    
```

### Para modelos (como regresión)

Si usas `summary()` sobre un modelo (por ejemplo, un modelo de regresión), te proporciona un resumen detallado de las estadísticas del modelo, incluyendo:

- **Coeficientes**: Los estimados de los parámetros del modelo (por ejemplo, las pendientes y la intersección en una regresión lineal).
- **Errores estándar**.
- **Valor p** para cada coeficiente.
- **Estadísticas de ajuste**: Como el R-cuadrado, el error estándar residual, etc.

Ejemplo:

```R
modelo <- lm(Edad ~ Ciudad, data = df)
summary(modelo)
```

Salida:

```
Call:
lm(formula = Edad ~ Ciudad, data = df)

Residuals:
   Min     1Q Median     3Q    Max 
-7.500 -3.750  0.000  3.750  7.500 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)
(Intercept)    25.000      2.500   10.000  0.0025 **
CiudadBarcelona  5.000      3.000    1.667  0.1677
CiudadSevilla   7.500      4.000    1.875  0.1291

Residual standard error: 4.375 on 2 degrees of freedom
Multiple R-squared:  0.785,	Adjusted R-squared:  0.607
F-statistic: 8.5 on 2 and 2 DF,  p-value: 0.086
```