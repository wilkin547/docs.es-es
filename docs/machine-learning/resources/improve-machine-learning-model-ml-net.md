---
title: Uso Mejora de la precisión del modelo
description: Aprenda cómo mejorar la precisión del modelo
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc
ms.openlocfilehash: 8f3b283de378a37bfe429688207ea9fb52f9ca7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75739573"
---
# <a name="improve-mlnet-model-accuracy"></a>Mejora de la precisión del modelo de ML.NET

Aprenda cómo mejorar la precisión del modelo.

## <a name="reframe-the-problem"></a>Replantear el problema

En ocasiones, es posible que mejorar un modelo no tenga nada que ver con los datos o las técnicas utilizadas para entrenar el modelo. En su lugar, puede que solo se esté haciendo la pregunta incorrecta. Considere la posibilidad de abordar el problema desde distintos ángulos y aproveche los datos para extraer los indicadores latentes y las relaciones ocultas para refinar la pregunta.

## <a name="provide-more-data-samples"></a>Proporcionar más ejemplos de datos

Como los humanos, cuantos más algoritmos de aprendizaje se obtengan, mayor es la probabilidad de que aumente el rendimiento. Una manera de mejorar el rendimiento del modelo es proporcionar más ejemplos de datos de entrenamiento para los algoritmos. Cuanto mayor sea el número de datos del que se aprende, más casos será capaz de identificar correctamente.

## <a name="add-context-to-the-data"></a>Agregar contexto a los datos

El significado de un único punto de datos puede ser difícil de interpretar. Crear contexto en torno a los puntos de datos ayuda a los algoritmos, así como a los expertos en la materia a tomar mejores decisiones. Por ejemplo, el solo hecho de que una casa tenga tres dormitorios no es un buen indicador de su precio. Sin embargo, si agrega el contexto y ahora ya sabe que se encuentra en un vecindario suburbano de las afueras de un área metropolitana importante donde la edad media es de 38 años, los ingresos medios por hogar son de 80 000 dólares y las escuelas están en el percentil 20 superior, el algoritmo proporciona más información en la cual poder basar sus decisiones. Todo este contexto se puede agregar como entrada al modelo de Machine Learning como características.

## <a name="use-meaningful-data-and-features"></a>Usar características y datos significativos

Aunque más muestras de datos y características pueden ayudar a mejorar la precisión del modelo, también es posible introducir ruido ya que no todos los datos y las características son significativos. Por lo tanto, es importante entender qué características son las que tienen mayor impacto en las decisiones que toma el algoritmo. El uso de técnicas como la importancia de características de permutación (PFI) puede ayudar a identificar esas características más destacadas y no solo ayuda a explicar el modelo, sino también a usar la salida como un método de selección de características para reducir la cantidad de características ruidosas que entran en el proceso de entrenamiento.

Para obtener más información sobre cómo usar PFI, consulte [Explicación de las predicciones del modelo mediante la importancia de características de permutación](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md).

## <a name="cross-validation"></a>Validación cruzada

La validación cruzada es una técnica de evaluación de modelos y entrenamiento que divide los datos en diversas particiones y entrena varios algoritmos en estas particiones. Esta técnica mejora la estabilidad del modelo que contiene datos del proceso de entrenamiento. Además de mejorar el rendimiento en observaciones no vistas y en entornos con limitaciones de datos, puede ser una herramienta eficaz para el entrenamiento de modelos con un conjunto de datos más pequeño.

Visite el siguiente vínculo para obtener información sobre [cómo utilizar la validación cruzada en ML.NET](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)

## <a name="hyperparameter-tuning"></a>Ajuste de hiperparámetros

El entrenamiento de modelos de aprendizaje automático es un proceso iterativo y exploratorio. Por ejemplo, ¿cuál es el número óptimo de clústeres al entrenar un modelo con el algoritmo K-Means? La respuesta depende de muchos factores, como la estructura de los datos. Para buscar ese número se necesitaría experimentar con diferentes valores de k y después evaluar el rendimiento para determinar qué valor es el mejor. La práctica de ajuste de estos parámetros para buscar un modelo óptimo se conoce como ajuste de hiperparámetros.

## <a name="choose-a-different-algorithm"></a>Elegir un algoritmo diferente

Las tareas de aprendizaje automático, como la clasificación y la regresión, contienen diversas implementaciones de algoritmos. Puede ser el caso de que el problema que intenta resolver y la manera en que sus datos están estructurados no se ajusten bien en el algoritmo actual. En este caso, considere el uso de un algoritmo diferente en la tarea para ver si aprende mejor de los datos.

El siguiente vínculo proporciona más [ayuda sobre qué algoritmo elegir](../how-to-choose-an-ml-net-algorithm.md).
