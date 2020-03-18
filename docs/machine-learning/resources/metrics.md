---
title: Métricas de ML.NET
description: Introducción a las métricas que se utilizan para evaluar el rendimiento de un modelo de ML.NET
ms.date: 12/17/2019
ms.openlocfilehash: 8e823fd8cc344c1b8e0ecd709b527137368cbfa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397804"
---
# <a name="evaluate-your-mlnet-model-with-metrics"></a>Evaluación de su modelo de ML.NET con métricas

Comprenda las métricas empleadas para evaluar un modelo de ML.NET.

Las métricas de evaluación son específicas del tipo de tarea de aprendizaje automático que realiza un modelo.

Por ejemplo, para la tarea de clasificación, el modelo se evalúa midiendo el grado de coincidencia de una categoría predicha con la categoría real. Y, para la agrupación en clústeres, la evaluación se basa en lo próximos que están unos de otros los elementos agrupados y en el grado de separación existente entre los clústeres.

## <a name="evaluation-metrics-for-binary-classification"></a>Métricas de evaluación para la clasificación binaria

| Métricas   |      Descripción      |  Buscar |
|-----------|-----------------------|-----------|
| **Precisión** |  La [precisión](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) es la proporción de predicciones correctas con un conjunto de datos de prueba. Es la relación entre el número de predicciones correctas y el número total de ejemplos de entrada. Funciona bien si hay un número similar de muestras que pertenecen a cada clase.| **Cuanto más cerca de 1,00, mejor**. Pero exactamente 1,00 indica un problema (normalmente: fuga de etiqueta/destino, sobreajuste o pruebas con datos de entrenamiento). Cuando los datos de prueba están desequilibrados (donde la mayoría de las instancias pertenece a una de las clases), el conjunto de datos es pequeño o las puntuaciones se acercan a 0,00 o 1,00, la precisión no captura realmente la eficacia de un clasificador y es necesario comprobar métricas adicionales. |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) o *Área bajo la curva* mide el área bajo la curva que se creó limpiando la tasa de positivos verdaderos frente a la tasa de falsos positivos.  |   **Cuanto más cerca de 1,00, mejor**. Debe ser mayor que 0,50 para que un modelo sea aceptable. Un modelo con AUC de 0,50 o menos no tiene ningún valor. |
| **AUCPR** | [aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) o *Área bajo la curva de una curva de precisión-recuperación*: Medida útil de éxito de predicción cuando las clases están poco equilibradas (conjuntos de datos muy sesgados). |  **Cuanto más cerca de 1,00, mejor**. Las puntuaciones altas cercanas a 1,00 muestran que el clasificador devuelve resultados precisos (alta precisión), así como una mayoría de todos los resultados positivos (recuperación alta). |
| **Puntuación F1** | La [puntuación F1](https://en.wikipedia.org/wiki/F1_score) también se denomina *puntuación F equilibrada o F medida F*. Es la media armónica de la precisión y la recuperación. La puntuación F1 resulta útil cuando desea buscar un equilibrio entre la precisión y la recuperación.| **Cuanto más cerca de 1,00, mejor**.  Una puntuación F1 alcanza el mejor valor en 1,00 y la peor puntuación en 0,00. Indica cuán preciso es el clasificador. |

Para obtener más información sobre las métricas de clasificación binaria, lea los artículos siguientes:

- [¿Exactitud, precisión, recuperación o F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)
- [Clase de métricas para la clasificación binaria](xref:Microsoft.ML.Data.BinaryClassificationMetrics)
- [La relación entre precisión-recuperación y curvas de ROC](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)

## <a name="evaluation-metrics-for-multi-class-classification"></a>Métricas de evaluación para la clasificación multiclase

| Métricas   |      Descripción      |  Buscar |
|-----------|-----------------------|-----------|
| **Microprecisión** |  La [precisión de micropromedio](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MicroAccuracy) agrega las contribuciones de todas las clases para calcular la métrica promedio. Es la fracción de instancias que se predijeron correctamente. El micropromedio no tiene en cuenta la pertenencia a una clase. Básicamente, todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión. | **Cuanto más cerca de 1,00, mejor**. En una tarea de clasificación multiclase, la microprecisión es preferible a la macroprecisión si se sospecha que podría haber un desequilibrio de clases (por ejemplo, podría tener muchos más ejemplos de una clase que de otras clases).|
| **Macroprecisión** | La [precisión de macropromedio](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MacroAccuracy) es la precisión promedio en el nivel de clase. La precisión de cada clase se calcula y la macroprecisión es el promedio de estas precisiones. Básicamente, todas las clases contribuyen del mismo modo a la métrica de precisión. Las clases minoritarias tienen el mismo peso que las clases más grandes. La métrica de macropromedio proporciona el mismo peso a cada clase, independientemente de cuántas instancias de esa clase contiene el conjunto de datos. |  **Cuanto más cerca de 1,00, mejor**.  Calcula la métrica de forma independiente para cada clase y, a continuación, toma la media (por lo tanto, se consideran todas las clases de igual forma) |
| **Pérdida de registro**| La [pérdida logarítmica](http://wiki.fast.ai/index.php/Log_Loss) mide el rendimiento de un modelo de clasificación donde la entrada de predicción es un valor de probabilidad de entre 0,00 y 1,00. La pérdida de registro aumenta a medida que la probabilidad de predicción difiere de la etiqueta real. | **Cuanto más cerca de 0,00, mejor**. Un modelo perfecto tendría una pérdida de registro de 0,00. El objetivo de nuestros modelos de Machine Learning es minimizar este valor.|
| **Reducción de pérdida logarítmica** | La [reducción de pérdida logarítmica](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.LogLossReduction) se puede interpretar como la ventaja del clasificador sobre una predicción aleatoria.| **Parte de -inf y 1,00, donde 1,00 equivale a una predicción perfecta, y 0,00 indica una predicción aproximada**. Por ejemplo, si el valor equivale a 0,20, se puede interpretar como "la probabilidad de que una predicción correcta sea 20 % mejor que el cálculo aleatorio"|

Por lo general, la microprecisión se alinea mejor con las necesidades empresariales de predicciones de ML. Si desea seleccionar una sola métrica para elegir la calidad de una tarea de clasificación multiclase, normalmente debería ser la de microprecisión.

Ejemplo, para una tarea de clasificación de incidencias de soporte técnico: (asigna incidencias entrantes a los equipos de soporte técnico)

- Microprecisión: ¿con qué frecuencia se clasifica una incidencia entrante en el equipo adecuado?
- Macroprecisión: para un equipo promedio, ¿con qué frecuencia es correcta una incidencia entrante para su equipo?

La macroprecisión proporciona más peso a los equipos pequeños en este ejemplo: un equipo pequeño que obtiene solo 10 incidencias al año cuenta tanto como un equipo grande con 10 000 incidencias al año. En este caso, la microprecisión se correlaciona mejor con la necesidad empresarial que se pregunta "cuánto tiempo y dinero puede ahorrar la compañía automatizando mi proceso de enrutamiento de incidencias".

Para obtener más información sobre las métricas de clasificación multiclase, lea los artículos siguientes:

- [Micropromedio y macropromedio de precisión, recuperación y puntuación F](https://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)
- [Clasificación multiclase con un conjunto de datos desequilibrado](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)

## <a name="evaluation-metrics-for-regression-and-recommendation"></a>Métricas de evaluación de regresión y recomendación

Las tareas de regresión y las de recomendación predicen un número. En caso de regresión, el número puede ser cualquier propiedad de salida influida por las propiedades de entrada. En caso de recomendación, el número suele ser un valor de clasificación (entre 1 y 5, por ejemplo) o una recomendación de sí/no (representada por 1 y 0, respectivamente).

| Métrica   |      Descripción      |  Buscar |
|----------|-----------------------|-----------|
| **R cuadrado** |  [R cuadrado (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination), o el *coeficiente de determinación* representan la eficacia predictiva del modelo como un valor comprendido entre -inf y 1,00. 1,00 significa que hay un ajuste perfecto y, dado que el ajuste puede ser arbitrariamente deficiente, las puntuaciones pueden ser negativas. Una puntuación de 0,00 significa que el modelo consiste en adivinar el valor esperado para la etiqueta. R2 mide la proximidad de los valores de datos de prueba reales a los valores de predicción. | **Cuanto más cerca de 1,00, es mejor la calidad**. Sin embargo, a veces valores bajos de R cuadrado (por ejemplo, 0,50) pueden ser completamente normales o lo suficientemente buenos en un escenario, y los valores altos de R cuadrado no siempre son buenos y pueden ser sospechosos. |
| **Pérdida absoluta** |  La [pérdida absoluta](https://en.wikipedia.org/wiki/Mean_absolute_error) o la *desviación media (MAE)* mide la proximidad de las predicciones a los resultados reales. Se trata de la media de todos los errores del modelo, donde el error del modelo es la distancia absoluta entre el valor de la etiqueta predicho y el valor de la etiqueta correcto. Este error de predicción se calcula para cada registro del conjunto de datos de prueba. Por último, el valor medio se calcula para todas las desviaciones medias registradas.| **Cuanto más cerca de 0,00, es mejor la calidad.** La desviación media utiliza la misma escala que los datos que se van a medir (no se normaliza en un intervalo específico). La pérdida absoluta, la pérdida cuadrática y la pérdida de RMS solo pueden usarse para realizar comparaciones entre los modelos del mismo conjunto de datos o el conjunto de datos y una distribución de valores de etiqueta similar. |
| **Pérdida cuadrática** |  La [pérdida cuadrática](https://en.wikipedia.org/wiki/Mean_squared_error) o *error cuadrático medio (MSE)* , también denominado *desviación cuadrática media (MSD)* indica la proximidad de una línea de regresión a un conjunto de valores de datos de prueba midiendo las distancias desde los puntos a la línea de regresión (estas distancias son los errores E) elevándolas al cuadrado. El cuadrado proporciona más peso a las grandes diferencias. | Siempre es un valor no negativo y los **valores próximos a 0,00 son mejores**. En función de los datos, puede resultar imposible obtener un valor muy pequeño para el error cuadrático medio.|
| **Pérdida de RMS** |  La [pérdida de RMS](https://en.wikipedia.org/wiki/Root-mean-square_deviation) o el *error de raíz cuadrada media (RMSE)* (también denominado *desviación de raíz cuadrada media, RMSD*), mide la diferencia entre los valores predichos por un modelo y los valores que se observan en el entorno que se está modelando. La pérdida de RMS es la raíz cuadrada de la pérdida cuadrática y tiene las mismas unidades de la etiqueta, similar a la pérdida absoluta aunque proporciona más peso a las grandes diferencias. El error de raíz cuadrada media se usa habitualmente en la climatología, la previsión y el análisis de regresión para comprobar resultados experimentales. | Siempre es un valor no negativo y los **valores próximos a 0,00 son mejores**. RMSD es una medida de precisión para comparar errores de previsión de diferentes modelos en determinado conjunto de datos y no entre conjuntos de datos, ya que es dependiente de la escala.|

Para obtener más información sobre las métricas de regresión, lea los artículos siguientes:

- [Análisis de regresión: ¿Cómo se puede interpretar el R cuadrado y evaluar la adecuación del ajuste?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)
- [Cómo interpretar el R cuadrado en el análisis de regresión](https://statisticsbyjim.com/regression/interpret-r-squared-regression)
- [Definición de R cuadrado](https://www.investopedia.com/terms/r/r-squared.asp)
- [Definición de error de raíz cuadrada media](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)
- [¿Qué son el error cuadrático medio y el error de raíz cuadrada media?](https://www.vernier.com/til/1014/)

## <a name="evaluation-metrics-for-clustering"></a>Métricas de evaluación para la agrupación en clústeres

| Métrica   |      Descripción      |  Buscar |
|----------|-----------------------|-----------|
|**Distancia media**|Promedio de la distancia entre los puntos de datos y el centro de su clúster asignado. La distancia media es una medida de proximidad de los puntos de datos a los centroides de clúster. Es una medida del grado de "ajuste" del clúster.|Los valores más próximos a **0** son mejores. Cuanto más se acerque a cero la distancia media, más agrupados estarán los datos. Tenga en cuenta, sin embargo, que esta métrica disminuirá si se aumenta el número de clústeres y, en el caso extremo (en el que cada uno de los distintos puntos de datos es su propio clúster) será igual a cero.
|**Índice de Davies Bouldin**|La relación media entre las distancias dentro del clúster y las distancias entre clústeres. Cuanto más ajustado sea el clúster y más separados estén los clústeres, más bajo será este valor.|Los valores más próximos a **0** son mejores. Los clústeres que estén más separados y menos dispersos generarán una mejor puntuación.|
|**Información mutua normalizada**|Se puede usar si los datos de entrenamiento usados para entrenar el modelo de agrupación en clústeres se incluyen también con etiquetas verdaderas (es decir, agrupación en clústeres supervisada). La métrica de información mutua normalizada mide si se asignan puntos de datos similares al mismo clúster y puntos de datos dispares a clústeres distintos. La información mutua normalizada es un valor entre 0 y 1|Los valores más próximos a **1** son mejores|

## <a name="evaluation-metrics-for-ranking"></a>Métricas de evaluación para la clasificación

| Métrica   |      Descripción      |  Buscar |
|----------|-----------------------|-----------|
|**Ganancias acumuladas descontadas**|Las ganancias acumuladas descontadas (DCG) son una medida de calidad de la clasificación. Se derivan de dos suposiciones. Una: los elementos altamente pertinentes resultan más útiles si aparecen más arriba en orden de clasificación. Dos: la utilidad realiza un seguimiento de la pertinencia, es decir, cuanto mayor es la pertinencia, más útil es un artículo. Las ganancias acumuladas descontadas se calculan para conseguir una posición determinada en el orden de clasificación. Suma la calificación de pertinencia dividida por el logaritmo del índice de clasificación hasta la posición de interés. Se calcula mediante $\sum_{i=0}^{p} \frac {rel_i} {\log_{e}{i+1}}$ Las calificaciones de pertinencia se proporcionan a un algoritmo de entrenamiento de clasificación como etiquetas verdaderas. Un valor de DCG se proporciona para cada posición de la tabla de clasificación, de ahí el nombre de **ganancias** acumuladas descontadas. |**Los valores más altos son mejores**|
|**Ganancias acumuladas descontadas normalizadas**|La normalización de DCG permite la comparación de la métrica para las listas de clasificación de diferentes longitudes|**Los valores más próximos a 1 son mejores**|

## <a name="evaluation-metrics-for-anomaly-detection"></a>Métricas de evaluación de detección de anomalías

| Métrica   |      Descripción      |  Buscar |
|----------|-----------------------|-----------|
|**Área bajo la curva de ROC**|El área bajo la curva receptor-operador mide el grado de eficacia del modelo al separar los puntos de datos anómalos y los habituales.|**Los valores más próximos a 1 son mejores**. Solo los valores mayores que 0,5 muestran la eficacia del modelo. Los valores de 0,5 o menos indican que el modelo no es mejor que la asignación aleatoria de las entradas a categorías anómalas y habituales|
|**Tasa de detección en el recuento de falsos positivos**|La tasa de detección en el recuento de falsos positivos es la relación entre el número de anomalías identificadas correctamente y el número total de anomalías de un conjunto de prueba, indexada por cada falso positivo. Es decir, hay un valor de la tasa de detección en el recuento de falsos positivos para cada elemento de falsos positivos.|**Los valores más próximos a 1 son mejores**. Si no hay ningún falso positivo, este valor será 1|
