# Análisis de Datos de Airbnb en Hawái

##  Introducción

En el contexto del turismo digital, plataformas como Airbnb generan grandes volúmenes de datos que permiten analizar el comportamiento del mercado turístico. El objetivo de este proyecto es realizar un análisis de los alojamientos de Airbnb en **Hawái**, identificando patrones relacionados con precios, valoraciones, disponibilidad y distribución geográfica.

Para ello, se han utilizado datos públicos obtenidos desde la plataforma *Inside Airbnb*, aplicando técnicas de análisis exploratorio, limpieza de datos, visualización y diseño de una base de datos.

---

## Descripción de los datos

Se han utilizado **dos datasets**, que fueron posteriormente unificados en un único DataFrame.  
El conjunto de datos final incluye información sobre:
- Identificadores de alojamientos y anfitriones
- Tipo de alojamiento
- Ubicación por barrios
- Precio
- Número de reseñas
- Disponibilidad anual
- Información de licencias

Tras la limpieza, el dataset final cuenta con:
- **33.132 alojamientos**
- **13 variables**

---

##  Fase 1: Análisis Exploratorio de Datos (EDA)

###  Número de alojamientos únicos
El dataset contiene **33.457 alojamientos únicos**, identificados mediante el campo `id`.

---

### Tipos de alojamiento
Se identificaron cuatro tipos de alojamiento:
- Entire home/apt
- Private room
- Hotel room
- Shared room

El tipo más común es **Entire home/apt**, representando la gran mayoría de la oferta en Hawái.

---

### Distribución por barrios
Los barrios con mayor número de alojamientos son:
- Primary Urban Center
- Lahaina
- Kihei-Makena
- North Kona

Estas zonas concentran más del 60 % de los alojamientos, lo que refleja una clara concentración de la oferta turística.

---

###  Valores nulos
Las columnas con mayor proporción de valores nulos son:
- `last_review`
- `reviews_per_month`
- `license`

Los valores nulos en reseñas se deben principalmente a alojamientos sin opiniones, mientras que la ausencia de licencia puede deberse a diferencias regulatorias.

---

### Valores atípicos en el precio
Se detectaron **3.796 valores atípicos** en la variable precio.  
El precio medio es de **945,49 $**, mientras que la mediana es de **233 $**, lo que indica que los valores extremos influyen fuertemente en la media.

---

## Fase 2: Transformación y limpieza de los datos

Las principales acciones realizadas fueron:
- Sustitución de valores nulos en `host_name` por `"unknown"`
- Eliminación de filas con precio nulo
- Eliminación de columnas irrelevantes (`latitude`, `longitude`, `neighbourhood_group`, etc.)
- Conversión de `id` y `host_id` a tipo categórico
- Normalización del texto (minúsculas y eliminación de espacios)

Los valores nulos en `license` se mantuvieron por su posible valor informativo.

---

## Fase 3: Análisis y Visualización

###  Análisis de precios

#### Precio medio y mediano
- Precio medio: **945,49 $**
- Precio mediano: **233,00 $**

La diferencia entre ambos indica una distribución asimétrica con presencia de alojamientos de lujo.

---

#### Precio según tipo de alojamiento
- Hotel room: precios extremadamente altos
- Entire home/apt: precios intermedios
- Private room: precios moderados
- Shared room: opción más económica

---

#### Precio por barrio
Los barrios más caros son:
- Primary Urban Center
- Lahaina
- North Kona

Los más baratos:
- Molokai
- Kau
- Puna

---

### Valoraciones y reseñas

Dado que no se dispone de una puntuación directa, se utilizó el **número de reseñas** como proxy de valoración.

#### Valoración media
El número medio de reseñas por alojamiento es de **42,13**.

---

#### Valoraciones según tipo de alojamiento
- Shared room: mayor número medio de reseñas
- Private room y Entire home/apt: valores similares
- Hotel room: menor número de reseñas

---

#### Relación entre número de reseñas y valoración
La mayoría de los alojamientos se concentran en rangos bajos y medios de reseñas, mientras que unos pocos concentran un gran volumen, indicando alta demanda o antigüedad.

---

#### Barrios mejor valorados
Los barrios con mayor número medio de reseñas son:
- Hana
- Lanai
- Waimea-Kekaha
- Paia-Haiku

---

#### Relación entre precio y valoración
No se observa una relación directa entre precio y valoración.  
Los alojamientos de precio medio concentran más reseñas, mientras que los muy caros o muy baratos tienden a tener menos.

---

### Disponibilidad y comportamiento de la oferta

#### Distribución de la disponibilidad
La disponibilidad anual muestra una gran variabilidad, desde alojamientos con alta ocupación hasta otros disponibles casi todo el año.

---

#### Barrios con mayor disponibilidad
Los barrios con mayor disponibilidad media son:
- Wailuku-Kahului
- Lanai
- Molokai
- Makawao-Pukalani-Kula

---

#### Disponibilidad por tipo de alojamiento
- Shared room presenta la mayor disponibilidad
- Private room la menor
- Entire home/apt y Hotel room valores intermedios

---

#### Relación entre disponibilidad y precio
Los alojamientos con menor disponibilidad tienden a tener precios más altos, lo que sugiere una mayor demanda.


---

## Conclusiones

Este proyecto ha permitido analizar de forma integral la oferta de Airbnb en Hawái.  
Los resultados muestran que el precio está fuertemente influenciado por el tipo de alojamiento y la ubicación, mientras que la valoración y la disponibilidad reflejan patrones de demanda y comportamiento de los usuarios.

El análisis proporciona información relevante que puede apoyar la toma de decisiones estratégicas en el sector del alquiler turístico.

---
