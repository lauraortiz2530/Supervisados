# Comparación de Modelos Supervisados mediante Validación Cruzada

## Autor: Laura Ortiz Franco

## Descripción del Dataset

El conjunto de datos **Rice Type Classification** fue obtenido de [Kaggle](https://www.kaggle.com/datasets/mssmartypants/rice-type-classification) y está compuesto por 10.000 observaciones correspondientes a granos de dos variedades de arroz: **Cammeo y Osmancik**.

Cada registro representa un grano de arroz y contiene diferentes variables numéricas relacionadas con sus características físicas, las cuales fueron calculadas a partir del procesamiento de imágenes.

| Variable        | Descripción                                                                |
| --------------- | -------------------------------------------------------------------------- |
| Area            | Superficie ocupada por el grano, expresada en píxeles².                    |
| Perimeter       | Longitud del contorno del grano.                                           |
| MajorAxisLength | Longitud del eje principal de la elipse ajustada al grano.                 |
| MinorAxisLength | Longitud del eje secundario de la elipse ajustada.                         |
| Eccentricity    | Indicador que representa el nivel de alargamiento de la forma del grano.   |
| ConvexArea      | Superficie del casco convexo que contiene al grano.                        |
| Extent          | Proporción entre el área del grano y el área de su rectángulo delimitador. |
| Class           | Variedad de arroz correspondiente: Cammeo u Osmancik.                      |

---

## Objetivo del Trabajo

El objetivo es analizar y comparar el desempeño de diferentes modelos de clasificación supervisada mediante validación cruzada, buscando determinar cuál presenta una mejor capacidad para generalizar ante nuevos datos.

Para este análisis se implementaron cinco modelos de clasificación:

* Regresión Logística
* K-Nearest Neighbors (KNN)
* Árbol de Decisión
* Random Forest
* Support Vector Machine (SVM)

El dataset se dividió en tres subconjuntos: **entrenamiento, validación y prueba**, utilizando una distribución de **60/20/20**. Se aplicó estratificación con el propósito de conservar una proporción similar de las clases en cada uno de los conjuntos.

Adicionalmente, se realizó una estandarización de las variables mediante **StandardScaler**, incorporada dentro del pipeline de preprocesamiento.

## Principales Hallazgos y Conclusiones

* Los modelos evaluados presentaron un rendimiento muy elevado, con valores de **ROC AUC superiores a 0.99**, lo que evidencia que las características geométricas permiten distinguir de manera efectiva entre las dos variedades de arroz.
* **Random Forest** obtuvo el mejor desempeño general entre los modelos analizados, alcanzando un **ROC AUC de 1.0000** en entrenamiento, validación, validación cruzada y prueba.
* Los resultados muestran que el modelo mantiene un desempeño consistente en las diferentes etapas de evaluación, lo que indica una buena capacidad para generalizar.
* Las variables relacionadas con la forma y el tamaño de los granos resultaron ser altamente informativas para diferenciar las variedades **Cammeo** y **Osmancik**.
* En función de los resultados obtenidos, **Random Forest mostró el comportamiento más sólido para esta tarea de clasificación**, destacándose por su alto rendimiento y consistencia.
