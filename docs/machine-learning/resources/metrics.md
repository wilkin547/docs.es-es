---
title: Métricas de ML.NET
description: Introducción a las métricas que se utilizan para evaluar el rendimiento de un modelo de ML.NET
ms.date: 04/29/2019
author: ''
ms.openlocfilehash: d76cab0b56085ebf2ee69f4d9d12c9685c3cb021
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452693"
---
# <a name="model-evaluation-metrics-in-mlnet"></a>Métricas de evaluación de modelos en ML.NET

## <a name="metrics-for-binary-classification"></a>Métricas para la clasificación binaria

| Métricas   |      Descripción      |  Buscar |
|-----------|-----------------------|-----------|
| **Precisión** |  La [precisión](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) es la proporción de predicciones correctas con un conjunto de datos de prueba. Es la relación entre el número de predicciones correctas y el número total de ejemplos de entrada. Funciona bien solo si hay un número similar de muestras que pertenecen a cada clase.| **Cuanto más cerca de 1,00, mejor**. Pero exactamente 1,00 indica un problema (normalmente: fuga de etiqueta/destino, sobreajuste o pruebas con datos de entrenamiento). Cuando los datos de prueba están desequilibrados (donde la mayoría de las instancias pertenece a una de las clases), el conjunto de datos es muy pequeño o las puntuaciones se acercan a 0,00 o 1,00, la precisión no captura realmente la eficacia de un clasificador y es necesario comprobar métricas adicionales. |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) o *Área bajo la curva*: Esto mide el área bajo la curva que se creó limpiando la tasa de positivos verdaderos frente a la tasa de falsos positivos.  |   **Cuanto más cerca de 1,00, mejor**. Para que un modelo sea aceptable, debe ser superior a 0,50. Un modelo con AUC de 0,50 o menos no tiene ningún valor. |
| **AUCPR** | [aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) o *Área bajo la curva de una curva de precisión-recuperación*: Medida útil de éxito de predicción cuando las clases están muy poco equilibradas (conjuntos de datos muy sesgados). |  **Cuanto más cerca de 1,00, mejor**. Las puntuaciones altas cercanas a 1,00 muestran que el clasificador devuelve resultados precisos (alta precisión), así como una mayoría de todos los resultados positivos (recuperación alta). |
| **Puntuación F1** | La [puntuación F1](https://en.wikipedia.org/wiki/F1_score) también se denomina *puntuación F equilibrada o F medida F*. Es la media armónica de la precisión y la recuperación. La puntuación F1 resulta útil cuando desea buscar un equilibrio entre la precisión y la recuperación.| **Cuanto más cerca de 1,00, mejor**.  Una puntuación F1 alcanza el mejor valor en 1,00 y la peor puntuación en 0,00. Indica cuán preciso es el clasificador. |

Para obtener más información sobre las métricas de clasificación binaria, lea los artículos siguientes:

- [¿Exactitud, precisión, recuperación o F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)
- [Clase de métricas para la clasificación binaria](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.binaryclassificationmetrics?view=ml-dotnet)
- [La relación entre precisión-recuperación y curvas de ROC](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)

## <a name="metrics-for-multi-class-classification"></a>Métricas para la clasificación multiclase

| Métricas   |      Descripción      |  Buscar |
|-----------|-----------------------|-----------|
| **Microprecisión** |  La [precisión de micropromedio](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.microaccuracy?view=ml-dotnet) agrega las contribuciones de todas las clases para calcular la métrica promedio. Es la fracción de instancias que se predijeron correctamente. El micropromedio no tiene en cuenta la pertenencia a una clase. Básicamente, todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión. | **Cuanto más cerca de 1,00, mejor**. En una tarea de clasificación multiclase, la microprecisión es preferible a la macroprecisión si se sospecha que podría haber un desequilibrio de clases (por ejemplo, podría tener muchos más ejemplos de una clase que de otras clases).|
| **Macroprecisión** | La [precisión de macropromedio](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.macroaccuracy?view=ml-dotnet) es la precisión promedio en el nivel de clase. La precisión de cada clase se calcula y la macroprecisión es el promedio de estas precisiones. Básicamente, todas las clases contribuyen del mismo modo a la métrica de precisión. Las clases minoritarias tienen el mismo peso que las clases más grandes. La métrica de macropromedio proporciona el mismo peso a cada clase, independientemente de cuántas instancias de esa clase contiene el conjunto de datos. |  **Cuanto más cerca de 1,00, mejor**.  Calcula la métrica de forma independiente para cada clase y, a continuación, toma la media (por lo tanto, se consideran todas las clases de igual forma) |
| **Pérdida de registro**| La [pérdida logarítmica](http://wiki.fast.ai/index.php/Log_Loss) mide el rendimiento de un modelo de clasificación donde la entrada de predicción es un valor de probabilidad de entre 0,00 y 1,00. La pérdida de registro aumenta a medida que la probabilidad de predicción difiere de la etiqueta real. | **Cuanto más cerca de 0,00, mejor**. Un modelo perfecto tendría una pérdida de registro de 0,00. El objetivo de nuestros modelos de Machine Learning es minimizar este valor.|
| **Reducción de pérdida logarítmica** | La [reducción de pérdida logarítmica](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.loglossreduction?view=ml-dotnet) se puede interpretar como la ventaja del clasificador sobre una predicción aleatoria.| **Parte de -inf y 1,00, donde 1,00 equivale a una predicción perfecta, y 0,00 indica una predicción aproximada**. Por ejemplo, si el valor equivale a 0,20, se puede interpretar como "la probabilidad de que una predicción correcta sea 20 % mejor que el cálculo aleatorio"|

Por lo general, la microprecisión se alinea mejor con las necesidades empresariales de predicciones de ML. Si desea seleccionar una sola métrica para elegir la calidad de una tarea de clasificación multiclase, normalmente debería ser la de microprecisión.

Ejemplo, para una tarea de clasificación de incidencias de soporte técnico: (asigna incidencias entrantes a los equipos de soporte técnico)

- Microprecisión: ¿con qué frecuencia se clasifica una incidencia entrante en el equipo adecuado?
- Macroprecisión: para un equipo promedio, ¿con qué frecuencia es correcta una incidencia entrante para su equipo?

La macroprecisión proporciona más peso a los equipos pequeños en este ejemplo: un equipo pequeño que obtiene solo 10 incidencias al año cuenta tanto como un equipo grande con 10 000 incidencias al año. En este caso, la microprecisión se correlaciona mejor con la necesidad empresarial que se pregunta "cuánto tiempo y dinero puede ahorrar la compañía automatizando mi proceso de enrutamiento de incidencias".

Para obtener más información sobre las métricas de clasificación multiclase, lea los artículos siguientes:

- [Micropromedio y macropromedio de precisión, recuperación y puntuación F](http://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)
- [Clasificación multiclase con un conjunto de datos desequilibrado](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)

## <a name="metrics-for-regression"></a>Métricas de regresión

| Métricas   |      Descripción      |  Buscar |
|-----------|-----------------------|-----------|
| **R cuadrado** |  [R cuadrado (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination), o el *coeficiente de determinación* representan la eficacia predictiva del modelo como un valor comprendido entre -inf y 1,00. 1,00 significa que hay un ajuste perfecto y, dado que el ajuste puede ser arbitrariamente deficiente, las puntuaciones pueden ser negativas. Una puntuación de 0,00 significa que el modelo consiste en adivinar el valor esperado para la etiqueta. R2 mide la proximidad de los valores de datos de prueba reales a los valores de predicción. | **Cuanto más cerca de 1,00, es mejor la calidad**. Sin embargo, a veces valores bajos de R cuadrado (por ejemplo, 0,50) pueden ser completamente normales o lo suficientemente buenos en un escenario, y los valores altos de R cuadrado no siempre son buenos y pueden ser sospechosos. |
| **Pérdida absoluta** |  La [pérdida absoluta](https://en.wikipedia.org/wiki/Mean_absolute_error) o la *desviación media (MAE)* mide la proximidad de las predicciones a los resultados reales. Se trata de la media de todos los errores del modelo, donde el error del modelo es la distancia absoluta entre el valor de la etiqueta predicho y el valor de la etiqueta correcto. Este error de predicción se calcula para cada registro del conjunto de datos de prueba. Por último, el valor medio se calcula para todas las desviaciones medias registradas.| **Cuanto más cerca de 0,00, es mejor la calidad.** Tenga en cuenta que la desviación media utiliza la misma escala que los datos que se van a medir (no se normaliza en un intervalo específico). La pérdida absoluta, la pérdida cuadrática y la pérdida de RMS solo pueden usarse para realizar comparaciones entre los modelos del mismo conjunto de datos o el conjunto de datos y una distribución de valores de etiqueta similar. |
| **Pérdida cuadrática** |  La [pérdida cuadrática](https://en.wikipedia.org/wiki/Mean_squared_error) o el *error cuadrático medio (MSE)*, también denominado *desviación cuadrática media (MSD)* indica la proximidad de una línea de regresión a un conjunto de valores de datos de prueba. Esto se logra midiendo las distancias desde los puntos a la línea de regresión (estas distancias son los "errores") elevándolas al cuadrado. El cuadrado proporciona más peso a las grandes diferencias. | Siempre es un valor no negativo y los **valores próximos a 0,00 son mejores**. En función de los datos, puede resultar imposible obtener un valor muy pequeño para el error cuadrático medio.|
| **Pérdida de RMS** |  La [pérdida de RMS](https://en.wikipedia.org/wiki/Root-mean-square_deviation) o el *error de raíz cuadrada media (RMSE)* (también denominado *desviación de raíz cuadrada media, RMSD*), mide la diferencia entre los valores predichos por un modelo y los valores que realmente se observan en el entorno que se está modelando. La pérdida de RMS es la raíz cuadrada de la pérdida cuadrática y tiene las mismas unidades de la etiqueta, similar a la pérdida absoluta aunque proporciona más peso a las grandes diferencias. El error de raíz cuadrada media se usa habitualmente en la climatología, la previsión y el análisis de regresión para comprobar resultados experimentales. | Siempre es un valor no negativo y los **valores próximos a 0,00 son mejores**. RMSD es una medida de precisión para comparar errores de previsión de diferentes modelos en determinado conjunto de datos y no entre conjuntos de datos, ya que es dependiente de la escala.|

Para obtener más información sobre las métricas de regresión, lea los artículos siguientes:

- [Análisis de regresión: ¿Cómo se puede interpretar el R cuadrado y evaluar la adecuación del ajuste?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)
- [Cómo interpretar el R cuadrado en el análisis de regresión](https://statisticsbyjim.com/regression/interpret-r-squared-regression)
- [Definición de R cuadrado](https://www.investopedia.com/terms/r/r-squared.asp)
- [Definición de error de raíz cuadrada media](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)
- [¿Qué son el error cuadrático medio y el error de raíz cuadrada media?](https://www.vernier.com/til/1014/)
