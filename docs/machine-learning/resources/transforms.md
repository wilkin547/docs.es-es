---
title: 'Transformaciones de datos de aprendizaje automático: ML.NET'
description: Explore los componentes de ingeniería de características que se admiten en ML.NET.
author: JRAlexander
ms.custom: seodec18
ms.date: 01/14/2019
ms.openlocfilehash: 54dffec37318b79edf546ba1f6e1145e35782bfb
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415356"
---
# <a name="machine-learning-data-transforms---mlnet"></a>Transformaciones de datos de aprendizaje automático: ML.NET

Las tablas siguientes contienen información sobre todas las transformaciones de datos que se admiten en ML.NET.

> [!NOTE]
> ML.NET se encuentra actualmente en versión preliminar. En la actualidad no se admiten todas las transformaciones de datos. Para enviar una solicitud para una transformación determinada, abra un tema en el repositorio [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) de GitHub.

## <a name="combiners-and-segregators"></a>Combinadores y segregadores

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | Agrupa los valores de una columna escalar en un vector en función de un identificador de grupo contiguo. |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | Desagrupa todas las columnas de vector en secuencias de filas; es la transformación inversa a Group. |

## <a name="conversions"></a>Conversiones 

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | Aplica algoritmos hash a columnas con un solo valor o columnas de vector. Para las columnas de vector, aplica un algoritmo hash a cada ranura por separado. Puede aplicar un algoritmo hash a valores de texto o de clave. |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | Convierte varios valores de columna en valores hash. Esta transformación acepta entradas numéricas y de texto, en columnas de un solo valor y de valores de vector. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | Convierte una clave en una columna de vectores binarios. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | Usa metadatos de KeyValues para asignar índices de clave a los valores correspondientes en los metadatos de KeyValues. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | Convierte una clave en una columna de vectores. |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | Cambia el tipo de columna subyacente siempre que el tipo se pueda convertir. |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | Convierte valores de entrada (palabras, números, etc.) en el índice de un diccionario. |


## <a name="deep-learning"></a>Aprendizaje profundo

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Proporciona datos a un modelo ONNX existente y devuelve la puntuación (predicción). |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Puede puntuar con un modelo de TensorFlow previamente entrenado o volver a entrenar el modelo de TensorFlow. |

## <a name="feature-extraction"></a>Extracción de características

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | Quita la lista especificada de palabras irrelevantes mediante la comparación de tokens individuales (comparación sin distinción entre mayúsculas y minúsculas) con las palabras irrelevantes.| 
| <xref:Microsoft.ML.ImageAnalytics.ImageGrayscaleTransform> | Toma una o varias columnas de tipo de imagen y las convierte en una representación de escala de grises de la misma imagen.|
| <xref:Microsoft.ML.ImageAnalytics.ImageLoaderTransform> | Toma una o varias columnas ReadOnlyMemory y las carga como un tipo de imagen. |
| <xref:Microsoft.ML.ImageAnalytics.ImagePixelExtractorTransform> | Toma una o varias columnas de tipo de imagen y las convierte en una representación vectorial.|
| <xref:Microsoft.ML.ImageAnalytics.ImageResizerTransform> | Toma una o varias columnas de tipo de imagen y cambia su tamaño al alto y ancho proporcionados.|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | Implementa LightLDA, una implementación de última generación de la asignación Dirichlet latente.|
| <xref:Microsoft.ML.Transforms.LoadTransform> | Carga transformaciones específicas desde el archivo de modelo especificado. Permite transformaciones de selección exclusiva ("cherry picking") desde una cadena serializada, o bien aplicar una transformación previamente entrenada a otra vista de datos (pero que sigue siendo compatible). |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | Genera un contenedor de los recuentos de n-gramas (secuencias de valores consecutivos de longitud 1-n) en un vector de claves especificado. Lo hace mediante la creación de un diccionario de n-gramas y con el identificador del diccionario como el índice del contenedor. | 
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | Convierte una colección de texto acortado (vector de ReadOnlyMemory) o vectores de claves en vectores de característica numéricos. Los vectores de característica son recuentos de n-gramas (secuencias de tokens consecutivos, palabras o claves, de longitud 1-n). | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | Convierte una colección de texto acortado (vector de ReadOnlyMemory) en vectores de característica numéricos mediante hash. | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | Genera un contenedor de los recuentos de n-gramas (secuencias de palabras consecutivas de longitud 1-n) en un texto especificado. | 
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | Convierte el valor categórico en una matriz de indicador mediante la creación de un diccionario de categorías en función de los datos y con el identificador del diccionario como el índice de la matriz. |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | Calcula la proyección del vector de característica en un subespacio de rango bajo. |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | Usa un modelo de opinión previamente entrenado para puntuar las cadenas de entrada. |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | Quita la lista específica del idioma de palabras irrelevantes (las más comunes) mediante la comparación de tokens individuales (comparación sin distinción entre mayúsculas y minúsculas) con las palabras irrelevantes. |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | Genera un contenedor de los recuentos de n-gramas (secuencias de palabras consecutivas) en un texto especificado. Lo hace mediante la creación de un diccionario de n-gramas y con el identificador del diccionario como el índice del contenedor. |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | Genera un contenedor de los recuentos de n-gramas (secuencias de palabras consecutivas de longitud 1-n) en un texto especificado. Para ello, se aplica un algoritmo hash a cada n-grama y se usa el valor de hash como índice en el contenedor. |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | Divide el texto en palabras mediante el carácter separador. |


## <a name="image-model-featurizers"></a>Caracterizadores de modelo de imagen

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | Se trata de un método de extensión que se usará con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> para poder utilizar un modelo [AlexNet](https://en.wikipedia.org/wiki/AlexNet) previamente entrenado. Se garantiza que el paquete NuGet que contiene esta extensión también incluye el archivo de modelo binario. | 
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | Se trata de un método de extensión que se usará con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> para utilizar un modelo ResNet18 previamente entrenado. Se garantiza que el paquete NuGet que contiene esta extensión también incluye el archivo de modelo binario. |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | Se trata de un método de extensión que se usará con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> para utilizar un modelo ResNet50 previamente entrenado. Se garantiza que el paquete NuGet que contiene esta extensión también incluye el archivo de modelo binario. |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | Se trata de un método de extensión que se usará con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> para utilizar un modelo ResNet101 previamente entrenado. Se garantiza que el paquete NuGet que contiene esta extensión también incluye el archivo de modelo binario. |

## <a name="label-parsing"></a>Análisis de etiquetas

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  Convierte las etiquetas. |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | Reasigna etiquetas multiclase a etiquetas binarias True y False, principalmente para su uso con OVA.|

## <a name="missing-values"></a>Valores ausentes

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | Quita los valores que faltan de las columnas. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | Crea una columna de salida booleana con el mismo número de ranuras que la columna de entrada, donde el valor de salida es true si falta el valor en la columna de entrada. |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | Controla los valores que faltan y los sustituye por el valor predeterminado o el valor medio, mínimo o máximo (solo para las columnas que no sean de texto). |

## <a name="normalization"></a>Normalización

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | Transformación de normalización (vector o modo de fila) de norma Lp. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | Calcula la media y la varianza para una columna con valores de vector. Realiza el seguimiento de la media actual y el de M2 (suma de las diferencias al cuadrado de los valores de la media), el número de NaN y el número de elementos distintos de cero. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | Calcula la media y la varianza para una columna con valores de vector. Realiza el seguimiento de la media actual y el de M2 (suma de las diferencias al cuadrado de los valores de la media), el número de NaN y el número de elementos distintos de cero. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | Realiza el seguimiento del valor mínimo, máximo, el número de valores no dispersos (vCount) y el número de llamadas a ProcessValue() (trainCount) para una columna con valores de vector. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | Estandariza los intervalos de características. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |Estandariza los intervalos de características. |

## <a name="onnx"></a>Onnx

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Puntúa modelos ONNX previamente entrenados que usan el estándar ONNX v1.2 |

## <a name="preprocessing"></a>Preprocesando
| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | Muestreo de arranque aproximado mediante muestreo de Poisson. |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | Genera la característica de Fourier aleatoria. |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Tokenizador orientado a caracteres donde el texto se considera una secuencia de caracteres. |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | Simplifica la optimización para ayudar a identificar los pesos. |

## <a name="row-filters"></a>Filtros de fila

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | Ordena aleatoriamente un intento de cursor aleatorio para realizarlo con un grupo de un número determinado de filas.  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | Permite limitar la entrada a un subconjunto de filas mediante la omisión de un número de filas. |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | Permite limitar la entrada a un subconjunto de filas con un desplazamiento opcional. Se puede usar para implementar la paginación de datos. Cuando se crea con SkipTakeFilter.SkipArguments se comporta como `SkipFilter`.
| <xref:Microsoft.ML.Transforms.TakeFilter> | Permite limitar la entrada a un subconjunto de filas tomando las primeras N filas. |


## <a name="schema"></a>Schema

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | Duplica las columnas del conjunto de datos.|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | Selecciona un conjunto de columnas que se van a eliminar o conservar de una entrada determinada. |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | Quita ranuras de las columnas.|
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | Crea una columna con el tipo y los valores predeterminados especificados. |
| <xref:Microsoft.ML.Transforms.RangeFilter> | Filtra una vista de datos en una columna de tipo Single, Double o Key (contigua). Mantiene los valores que se encuentran en el intervalo mínimo y máximo especificado. Los valores NaN se filtran siempre. Si la entrada es un tipo de clave, los valores mínimo y máximo se consideran porcentajes del número de valores. |

## <a name="tensorflow"></a>TensorFlow

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Puntúa con un modelo de TensorFlow previamente entrenado o vuelve a entrenar el modelo de TensorFlow. |

## <a name="text-processing-and-featurization"></a>Características y procesamiento de texto

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | Una transformación de normalización de texto que permite la normalización de mayúsculas y minúsculas, quitar marcas diacríticas, signos de puntuación o números. La transformación funciona en la entrada de texto, así como en vectores de tokens y texto (vector de ReadOnlyMemory). |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Tokenizador orientado a caracteres donde el texto se considera una secuencia de caracteres. |

## <a name="time-series"></a>Serie temporal

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesProcessing.ExponentialAverageTransform> | Toma una media ponderada de los valores: ExpAvg(y_t) = a * y_t + (1-a) * ExpAvg(y_(t-1)). |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidChangePointDetector> | Implementa la transformación de detector de punto de cambio para una secuencia i.i.d. (muestra aleatoria) a partir de la estimación de la densidad de kernel adaptable y las martingalas. |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidSpikeDetector> | Implementa la transformación de detector de picos para una secuencia i.i.d. (muestra aleatoria) a partir de la estimación de la densidad de kernel adaptable. |
| <xref:Microsoft.ML.TimeSeriesProcessing.MovingAverageTransform> | Proporciona un promedio ponderado de los valores de la ventana deslizante. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PercentileThresholdTransform> | Decide si el valor actual de la serie temporal pertenece el percentil de valores superiores de ventana deslizante. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PValueTransform> | Calcula el valor p empírico del valor actual de la serie en función de los otros valores en la ventana deslizante. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SlidingWindowTransform> | Genera una ventana deslizante en una serie temporal de tipo Single. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaChangePointDetector> | Implementa la transformación de detector de punto de cambio en función del modelado de espectro de singularidad de la serie temporal. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaSpikeDetector> | Implementa la transformación de detector de pico en función del modelado de espectro de singularidad de la serie temporal. |

## <a name="miscellaneous"></a>Varios

| Transformación | de esquema JSON |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | Crea una transformación de datos compuesta. |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | Genera columnas adicionales para el elemento `IDataView` proporcionado. No cambia el número de filas y se puede ver como resultado de la aplicación de la función del usuario a todas las filas de los datos de entrada.|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | Agrega una columna con una secuencia de números generada. |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | Genera una columna con el identificador del cursor como una columna. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Genera un número aleatorio. |
