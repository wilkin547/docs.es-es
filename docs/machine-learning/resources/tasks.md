---
title: 'Tareas de aprendizaje automático: ML.NET'
description: Explore las diferentes tareas de aprendizaje automático y los mecanismos de aprendizaje asociados que se admiten en ML.NET.
ms.custom: seodec18
ms.date: 11/29/2018
author: jralexander
ms.openlocfilehash: 4b333fb8c954c94ed84033d9858a496f591f2169
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126593"
---
# <a name="machine-learning-tasks-in-mlnet"></a>Tareas de aprendizaje automático en ML.NET

Cuando se crea un modelo de aprendizaje automático, primero debe definir lo que espera lograr con sus datos. Después, puede elegir la tarea de aprendizaje automático adecuada para su situación. La siguiente lista describe las diferentes tareas de aprendizaje automático que puede elegir y algunos casos de uso comunes.

> [!NOTE]
> ML.NET se encuentra actualmente en versión preliminar. No todas las tareas de aprendizaje automático se admiten actualmente. Para enviar una solicitud para una tarea determinada, abra un tema en el [repositorio dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="binary-classification"></a>Clasificación binaria

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1. El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación binaria están los siguientes:

* [Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".
* Diagnosticar si un paciente tiene una determinada enfermedad o no.
* Tomar una decisión para marcar un correo electrónico como no deseado o no.
* Determinar si una foto contiene un perro o una fruta.

Para obtener más información, consulte el artículo de Wikipedia [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) (Clasificación binaria).

Mecanismos de aprendizaje recomendados para clasificación binaria:

* AveragedPerceptronTrainer
* StochasticGradientDescentClassificationTrainer
* LightGbmBinaryTrainer
* FastTreeBinaryClassificationTrainer
* SymSgdClassificationTrainer

### <a name="binary-classification-learners"></a>Mecanismos de aprendizaje de clasificación binaria

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de clasificación binaria:

* [AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.Online.AveragedPerceptronTrainer)
* [BinaryClassificationGamTrainer](xref:Microsoft.ML.Trainers.FastTree.BinaryClassificationGamTrainer)
* [FastForestClassification](xref:Microsoft.ML.Trainers.FastTree.FastForestClassification)
* [FastTreeBinaryClassificationTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer)
* [FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.Runtime.FactorizationMachine.FieldAwareFactorizationMachineTrainer)
* [LightGbmBinaryTrainer](xref:Microsoft.ML.Runtime.LightGBM.LightGbmBinaryTrainer)
* [LinearSvm](xref:Microsoft.ML.Trainers.Online.LinearSvm)
* [PriorTrainer](xref:Microsoft.ML.Trainers.PriorTrainer)
* [RandomTrainer](xref:Microsoft.ML.Trainers.RandomTrainer)
* [StochasticGradientDescentClassificationTrainer](xref:Microsoft.ML.Trainers.StochasticGradientDescentClassificationTrainer)
* [SymSgdClassificationTrainer](xref:Microsoft.ML.Trainers.SymSgd.SymSgdClassificationTrainer)

## <a name="multiclass-classification"></a>Clasificación multiclase

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta. Cada etiqueta se inicia normalmente como texto. Luego se ejecuta mediante TermTransform, que lo convierte al tipo de clave (numérico). El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:

* Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.
* Comprender las críticas de películas como "positivas", "neutrales" o "negativas".
* Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.

Para obtener más información, consulte el artículo de Wikipedia [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) (Clasificación multiclase).

Mecanismos de aprendizaje recomendados para multiclase:

* OVA-AveragedPerceptronTrainer
* SdcaMultiClassTrainer
* LightGbmMulticlassTrainer
* OVA-FastTreeBinaryClassificationTrainer

>[!NOTE]
>OVA y PKPD actualizan los [mecanismos de aprendizaje de clasificación binaria](#binary-classification) para que actúen en conjunto de datos multiclase. Obtenga más información sobre [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-learners"></a>Mecanismos de aprendizaje de clasificación multiclase

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de clasificación multiclase:

* [LightGbmMulticlassTrainer](xref:Microsoft.ML.Runtime.LightGBM.LightGbmMulticlassTrainer)
* [MetaMulticlassTrainer<TTransformer,TModel>](xref:Microsoft.ML.Runtime.Learners.MetaMulticlassTrainer%602)
* [MultiClassClassificationTrainers](xref:Microsoft.ML.Trainers.MultiClassClassificationTrainers)
* [MultiClassNaiveBayesTrainer](xref:Microsoft.ML.Trainers.MultiClassNaiveBayesTrainer)
* [Ova](xref:Microsoft.ML.Trainers.Ova)
* [Pkpd](xref:Microsoft.ML.Trainers.Pkpd)
* [SdcaMultiClassTrainer](xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer)

## <a name="regression"></a>Regresión

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas. La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación. Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características. La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos. El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada. Estos son algunos ejemplos de escenarios de regresión:

* Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.
* Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.
* Predecir las ventas de un producto en función del presupuesto para publicidad.

Mecanismos de aprendizaje recomendados para regresión:

* FastTreeTweedieTrainer 
* LightGbmRegressorTrainer 
* SdcaRegressionTrainer 
* FastTreeRegressionTrainer

### <a name="regression-learners"></a>Mecanismos de aprendizaje de regresión

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de regresión:

* [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer)
* [FastTreeRegressionFastTreeTrainer](xref:Microsoft.ML.Runtime.FastTreeRegressionFastTreeTrainer)
* [FastTreeTweedieRegressionFastTreeTrainer](xref:Microsoft.ML.Runtime.FastTreeTweedieRegressionFastTreeTrainer)
* [FastTreeTweedieTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer)
* [LightGbmRegressorTrainer](xref:Microsoft.ML.Runtime.LightGBM.LightGbmRegressorTrainer)
* [LogisticRegression](xref:Microsoft.ML.Runtime.Learners.LogisticRegression)
* [OlsLinearRegressionTrainer](xref:Microsoft.ML.Trainers.HalLearners.OlsLinearRegressionTrainer)
* [OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.Online.OnlineGradientDescentTrainer)
* [PoissonRegression](xref:Microsoft.ML.Trainers.PoissonRegression)
* [RegressionGamTrainer](xref:Microsoft.ML.Trainers.FastTree.RegressionGamTrainer)
* [SdcaRegressionTrainer](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)
* [FastTree.SingleTrainer](xref:Microsoft.ML.Trainers.FastTree.SingleTrainer)
* [LightGBM.SingleTrainer](xref:Microsoft.ML.Runtime.LightGBM.SingleTrainer)

## <a name="clustering"></a>Agrupación en clústeres

Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares. La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación. Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida. Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad. ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means. Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:

* Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.
* Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.
* Categorizar un inventario tomando como base las métricas de fabricación.

### <a name="clustering-learners"></a>Mecanismos de aprendizaje de agrupación en clústeres

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de agrupación en clústeres:

* [KMeansPlusPlusTrainer](xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer)

## <a name="anomaly-detection"></a>Detección de anomalías

Esta tarea crea un modelo de detección de anomalías mediante el uso de análisis de componentes principales (PCA). La detección de anomalías basada en PCA le permite generar un modelo en escenarios donde resulta sencillo obtener datos de entrenamiento de una clase, como transacciones válidas, pero difícil obtener muestras suficientes de las anomalías de destino.

Una técnica establecida en aprendizaje automático, el PCA se suele usar en el análisis de datos exploratorios porque revela la estructura interna de los datos y explica la variación en los datos. El PCA funciona analizando datos que contienen varias variables. Busca correlaciones entre las variables y determina la combinación de valores que mejor recoge las diferencias en los resultados. Estos valores de características combinados se usan para crear un espacio de características más compactas llamadas componentes principales.

La detección de anomalías engloba muchas tareas importantes de aprendizaje automático:

* La identificación de transacciones potencialmente fraudulentas.
* El aprendizaje de patrones que indican que se ha producido una intrusión de red.
* La búsqueda de clústeres anómalos de pacientes.
* La comprobación de los valores especificados en un sistema.

Dado que las anomalías son eventos excepcionales por definición, puede ser difícil recopilar una muestra representativa de datos que usar en el modelado. Los algoritmos que se incluyen en esta categoría se han diseñado especialmente para abordar los principales desafíos de compilar y entrenar modelos mediante el uso de conjuntos de datos desequilibrados.

### <a name="anomaly-detection-learners"></a>Mecanismos de aprendizaje de detección de anomalías

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de detección de anomalías:

* [RandomizedPcaTrainer](xref:Microsoft.ML.Trainers.PCA.RandomizedPcaTrainer)

## <a name="ranking"></a>Clasificación

Una tarea de clasificación construye un clasificador a partir de un conjunto de ejemplos etiquetados. Este conjunto de ejemplos consta de grupos de instancias que se pueden puntuar con un criterio determinado. Las etiquetas de clasificación son {0, 1, 2, 3, 4} para cada instancia.  El clasificador está entrenado para clasificar nuevos grupos de instancias con puntuaciones desconocidas para cada instancia. Los mecanismos de aprendizaje de clasificación de ML.NET se basan en la [clasificación aprendida automáticamente](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-learners"></a>Mecanismos de aprendizaje de clasificación

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de clasificación:

* [FastTreeRankingFastTreeTrainer](xref:Microsoft.ML.Runtime.FastTreeRankingFastTreeTrainer)
* [FastTreeRankingTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer)
* [LightGbmRankingTrainer](xref:Microsoft.ML.Runtime.LightGBM.LightGbmRankingTrainer)

## <a name="recommendation"></a>Recomendación

Una tarea de recomendación permite generar una lista de productos o servicios recomendados. ML.NET utiliza la [factorización matricial (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), un algoritmo de [filtrado de colaboración](https://en.wikipedia.org/wiki/Collaborative_filtering) de las recomendaciones cuando hay datos históricos de clasificación de productos en el catálogo. Por ejemplo, tiene datos históricos de clasificación de películas para los usuarios y desea recomendar otras películas que puedan ver a continuación.

### <a name="recommendation-learners"></a>Mecanismos de aprendizaje de recomendación

Los mecanismos de aprendizaje siguientes están disponibles para las tareas de recomendación:

* [MatrixFactorizationTrainer](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer)
* [MatrixFactorizationPredictionTransformer](xref:Microsoft.ML.Trainers.Recommender.MatrixFactorizationPredictionTransformer)
