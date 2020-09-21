---
title: Tareas de aprendizaje automático
description: Explore las diferentes tareas de aprendizaje automático y las tareas asociadas que se admiten en ML.NET.
ms.date: 12/23/2019
ms.openlocfilehash: 56cdb5f3162614d0bf2fb1e5bd9e774b5548b238
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679487"
---
# <a name="machine-learning-tasks-in-mlnet"></a>Tareas de aprendizaje automático en ML.NET

Una tarea de aprendizaje automático es el tipo de predicción o inferencia que se está realizando, en función del problema o la pregunta que se está formulando, y los datos disponibles. Por ejemplo, la tarea de clasificación asigna datos a categorías y la tarea de agrupación en clústeres agrupa datos según su similitud.

Las tareas de aprendizaje automático se basan en patrones de los datos en lugar de programarse explícitamente.

En este artículo se describen las diferentes tareas de aprendizaje automático que puede elegir en ML.NET y algunos casos de uso comunes.

Cuando haya decidido qué tarea funciona en su escenario, debe elegir el mejor algoritmo para entrenar el modelo. Los algoritmos disponibles se muestran en la sección correspondiente a cada tarea.

## <a name="binary-classification"></a>Clasificación binaria

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir a cuál de las dos clases (categorías) pertenece una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta, donde cada etiqueta es un número entero de 0 o 1. El resultado de un algoritmo de clasificación binaria es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación binaria están los siguientes:

* [Comprensión del sentimiento de comentarios de Twitter](../tutorials/sentiment-analysis.md) en tanto que "positivos" o "negativos".
* Diagnosticar si un paciente tiene una determinada enfermedad o no.
* Tomar una decisión para marcar un correo electrónico como no deseado o no.
* Determinar si una fotografía contiene un elemento determinado o no, como un perro o una fruta.

Para obtener más información, consulte el artículo de Wikipedia [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) (Clasificación binaria).

### <a name="binary-classification-trainers"></a>Instructores de clasificación binaria

Puede entrenar un modelo de clasificación binaria mediante los algoritmos siguientes:

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a>Entradas y salidas de clasificación binaria

Para obtener los mejores resultados con la clasificación binaria, los datos de entrenamiento deben estar equilibrados (es decir, igual número de datos de entrenamiento positivos y negativos). Los valores que faltan se deben controlar antes del entrenamiento.

Los datos de la columna de etiquetas de entrada deben ser <xref:System.Boolean>.
Los datos de la columna de características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.

Estos instructores generan las columnas siguientes:

| Nombre de columna de salida | Tipo de columna | Descripción|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Puntuación sin procesar calculada por el modelo|
| `PredictedLabel` | <xref:System.Boolean> | Etiqueta de predicción, según el signo de la puntuación. Una puntuación negativa se asigna a `false` y una positiva a `true`.|

## <a name="multiclass-classification"></a>Clasificación multiclase

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir la clase (categoría) de una instancia de datos. La entrada de un algoritmo de clasificación es un conjunto de ejemplos con etiqueta. Cada etiqueta se inicia normalmente como texto. Luego se ejecuta mediante TermTransform, que lo convierte al tipo de clave (numérico). El resultado de un algoritmo de clasificación es un clasificador, que puede usar para predecir la clase de nuevas instancias sin etiqueta. Entre los ejemplos de escenarios de clasificación multiclase están los siguientes:

* Determinar la raza de un perro como "husky siberiano", "labrador", "caniche", etc.
* Comprender las críticas de películas como "positivas", "neutrales" o "negativas".
* Categorizar las reseñas de hoteles en función de factores como "ubicación", "precio", "limpieza", etc.

Para obtener más información, consulte el artículo de Wikipedia [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) (Clasificación multiclase).

>[!NOTE]
>Uno frente a todos actualiza los [mecanismos de aprendizaje de clasificación binaria](#binary-classification) para que actúen en conjuntos de datos multiclase. Más información en [Wikipedia](https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-trainers"></a>Instructores de clasificación multiclase

Puede entrenar un modelo de clasificación multiclase mediante los siguientes algoritmos de aprendizaje:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>
* <xref:Microsoft.ML.Vision.ImageClassificationTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a>Entradas y salidas de clasificación multiclase

Los datos de la columna de etiquetas de entrada deben ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).
La columna de características debe ser un vector de tamaño fijo de <xref:System.Single>.

Este instructor produce lo siguiente:

| Nombre de archivo de salida | Tipo | Descripción|
| -- | -- | -- |
| `Score` | Vector de <xref:System.Single> | Puntuaciones de todas las clases. Un valor más alto indica mayor probabilidad de que caigan en la clase asociada. Si el elemento i-th tiene el valor más grande, el índice de la etiqueta de predicción sería i. Tenga en cuenta que i es el índice de base cero. |
| `PredictedLabel` | Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType) | Índice de la etiqueta de predicción. Si su valor es i, la etiqueta real sería la categoría de i-th en el tipo de etiqueta de entrada con valores de clave. |

## <a name="regression"></a>Regresión

Una tarea de [aprendizaje automatizado supervisado](glossary.md#supervised-machine-learning) que se usa para predecir el valor de la etiqueta a partir de un conjunto de características relacionadas. La etiqueta puede tener cualquier valor real y no proviene de un conjunto finito de valores como en las tareas de clasificación. Los algoritmos de regresión modelan la dependencia de la etiqueta de sus características relacionadas para determinar cómo cambiará la etiqueta a medida que varíen los valores de las características. La entrada de un algoritmo de regresión es un conjunto de ejemplos con etiquetas de valores conocidos. El resultado de un algoritmo de regresión es una función, que puede utilizar para predecir el valor de etiqueta para cualquier nuevo conjunto de características de entrada. Estos son algunos ejemplos de escenarios de regresión:

* Predecir los precios de la vivienda según los atributos de la casa, como el número de habitaciones, la ubicación o el tamaño.
* Predecir los precios de las acciones futuras en función de los datos históricos y las tendencias del mercado actual.
* Predecir las ventas de un producto en función del presupuesto para publicidad.

### <a name="regression-trainers"></a>Instructores de regresión

Puede entrenar un modelo de regresión mediante los siguientes algoritmos:

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a>Entradas y salidas de regresión

Los datos de la columna de etiquetas de entrada deben ser <xref:System.Single>.

Los instructores para esta tarea producen lo siguiente:

| Nombre de archivo de salida | Tipo | Descripción|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Puntuación sin procesar que el modelo predijo |

## <a name="clustering"></a>Agrupación en clústeres

Una tarea de [aprendizaje automático no supervisado](glossary.md#unsupervised-machine-learning) que se usa para agrupar instancias de datos en clústeres que contienen características similares. La agrupación en clústeres también se puede utilizar para identificar relaciones en un conjunto de datos que podrían no detectarse lógicamente mediante la exploración o la simple observación. Las entradas y salidas de un algoritmo de agrupación en clústeres dependen de la metodología elegida. Puede tomar un enfoque de distribución, centroide, de conectividad o de densidad. ML.NET admite actualmente un enfoque basado en centroide mediante la agrupación en clústeres K-Means. Entre los ejemplos de escenarios de agrupación en clústeres están los siguientes:

* Comprender los segmentos de los huéspedes de un hotel según los hábitos y las características de las opciones de hotel.
* Identificar segmentos y datos demográficos de clientes para ayudar a crear campañas publicitarias específicas.
* Categorizar un inventario tomando como base las métricas de fabricación.

### <a name="clustering-trainer"></a>Instructor de agrupación en clústeres

Puede entrenar un modelo de agrupación en clústeres mediante el siguiente algoritmo:

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a>Entradas y salidas de agrupación en clústeres

Los datos de las características de entrada deben ser <xref:System.Single>. No se necesita ninguna etiqueta.

Este instructor produce lo siguiente:

| Nombre de archivo de salida | Tipo | Descripción|
| -- | -- | -- |
| `Score` | Vector de <xref:System.Single> | Las distancias de los datos especificados apuntan a todos los centroides de los clústeres |
| `PredictedLabel` | Tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType) | El índice del clúster más cercano predicho por el modelo. |

## <a name="anomaly-detection"></a>Detección de anomalías

Esta tarea crea un modelo de detección de anomalías mediante el uso de análisis de componentes principales (PCA). La detección de anomalías basada en PCA le permite generar un modelo en escenarios donde resulta sencillo obtener datos de entrenamiento de una clase, como transacciones válidas, pero difícil obtener muestras suficientes de las anomalías de destino.

Una técnica establecida en aprendizaje automático, el PCA se suele usar en el análisis de datos exploratorios porque revela la estructura interna de los datos y explica la variación en los datos. El PCA funciona analizando datos que contienen varias variables. Busca correlaciones entre las variables y determina la combinación de valores que mejor recoge las diferencias en los resultados. Estos valores de características combinados se usan para crear un espacio de características más compactas llamadas componentes principales.

La detección de anomalías engloba muchas tareas importantes de aprendizaje automático:

* La identificación de transacciones potencialmente fraudulentas.
* El aprendizaje de patrones que indican que se ha producido una intrusión de red.
* La búsqueda de clústeres anómalos de pacientes.
* La comprobación de los valores especificados en un sistema.

Dado que las anomalías son eventos excepcionales por definición, puede ser difícil recopilar una muestra representativa de datos que usar en el modelado. Los algoritmos que se incluyen en esta categoría se han diseñado especialmente para abordar los principales desafíos de compilar y entrenar modelos mediante el uso de conjuntos de datos desequilibrados.

### <a name="anomaly-detection-trainer"></a>Instructor de detección de anomalías

Puede entrenar un modelo de detección de anomalías mediante el siguiente algoritmo:

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a>Salidas y entradas de detección de anomalías

Las características de entrada deben ser un vector de tamaño fijo de <xref:System.Single>.

Este instructor produce lo siguiente:

| Nombre de archivo de salida | Tipo | Descripción|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Puntuación no negativa sin enlazar que ha calculado el modelo de detección de anomalías |
| `PredictedLabel` | <xref:System.Boolean> | Un valor true o false que representa si la entrada es una anomalía (PredictedLabel=true) o no (PredictedLabel=false) |

## <a name="ranking"></a>Clasificación

Una tarea de clasificación construye un clasificador a partir de un conjunto de ejemplos etiquetados. Este conjunto de ejemplos consta de grupos de instancias que se pueden puntuar con un criterio determinado. Las etiquetas de clasificación son {0, 1, 2, 3, 4} para cada instancia.  El clasificador está entrenado para clasificar nuevos grupos de instancias con puntuaciones desconocidas para cada instancia. Los mecanismos de aprendizaje de clasificación de ML.NET se basan en la [clasificación aprendida automáticamente](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-training-algorithms"></a>Algoritmos de aprendizaje de clasificación

Puede entrenar un modelo de clasificación mediante los algoritmos siguientes:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a>Salidas y entradas de clasificación

El tipo de datos de la etiqueta de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType) o <xref:System.Single>. El valor de la etiqueta determina la relevancia, donde los valores más altos indican mayor relevancia. Si la etiqueta es de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType), entonces el índice de la clave es el valor de relevancia, donde el índice más pequeño es el menos relevante. Si la etiqueta es un <xref:System.Single>, los valores mayores indican mayor relevancia.

Los datos de la característica deben ser un vector de tamaño fijo de <xref:System.Single> y la columna de grupo de filas de entrada debe ser de tipo de [clave](xref:Microsoft.ML.Data.KeyDataViewType).

Este instructor produce lo siguiente:

| Nombre de archivo de salida | Tipo | Descripción|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Puntuación sin enlazar que ha calculado el modelo para determinar la predicción |

## <a name="recommendation"></a>Recomendación

Una tarea de recomendación permite generar una lista de productos o servicios recomendados. ML.NET utiliza la [factorización matricial (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), un algoritmo de [filtrado de colaboración](https://en.wikipedia.org/wiki/Collaborative_filtering) de las recomendaciones cuando hay datos históricos de clasificación de productos en el catálogo. Por ejemplo, tiene datos históricos de clasificación de películas para los usuarios y desea recomendar otras películas que puedan ver a continuación.

### <a name="recommendation-training-algorithms"></a>Algoritmos de aprendizaje de recomendación

Puede entrenar un modelo de recomendación mediante el siguiente algoritmo:

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>

## <a name="forecasting"></a>Previsión

La tarea de previsión usa datos de serie temporal pasados para realizar predicciones sobre el comportamiento futuro. Los escenarios aplicables a la previsión incluyen previsiones meteorológicas, predicciones de ventas estacionales y mantenimiento predictivo.

### <a name="forecasting-trainers"></a>Instructores de previsión

Puede entrenar un modelo de previsión con el algoritmo siguiente:

<xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A>
