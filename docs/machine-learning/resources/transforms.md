---
title: Transformaciones de datos
description: Explore los componentes de ingeniería de características que se admiten en ML.NET.
ms.date: 04/02/2019
ms.openlocfilehash: ca410b475c556db5ad4c3862fb79755b455d6830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397756"
---
# <a name="data-transformations"></a>Transformaciones de datos

Las transformaciones de datos se usan para:

- Preparar datos para el entrenamiento de modelos.
- Aplicar un modelo importado en formato de TensorFlow o de ONNX.
- Realizar el procesamiento posterior de los datos una vez pasados a través de un modelo.

Las transformaciones de esta guía devuelven clases que implementan la interfaz [IEstimator](xref:Microsoft.ML.IEstimator%601). Las transformaciones de datos se pueden encadenar juntas. Cada transformación espera y genera datos de tipos y formatos específicos, que se especifican en la documentación de referencia vinculada.

Algunas transformaciones de datos requieren datos de aprendizaje para calcular sus parámetros. Por ejemplo, el transformador <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> calcula el medio y la varianza de los datos de aprendizaje durante la operación `Fit()` y usa esos parámetros en la operación `Transform()`.

Otras transformaciones de datos no requieren datos de aprendizaje. Por ejemplo, la transformación <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> puede realizar la operación `Transform()` sin haber visto ningún dato de aprendizaje durante la operación `Fit()`.

## <a name="column-mapping-and-grouping"></a>Agrupación y asignación de columnas

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | Concatenar una o más columnas de entrada en una columna de salida nueva |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | Copiar y cambiar el nombre de una o más columnas de entrada |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | Quitar una o más columnas de entrada |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | Seleccionar una o más columnas para conservar a partir de los datos de entrada |

## <a name="normalization-and-scaling"></a>Normalización y escalado

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | Restar la media (de los datos de aprendizaje) y dividir por la varianza (de los datos de aprendizaje) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | Normalizar en función del logaritmo de los datos de aprendizaje |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | Escalar los vectores de entrada por su [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), donde p es 1, 2 o infinito. Se establece de manera predeterminada en la norma l2 (distancia euclidiana) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | Escalar cada valor de una fila al restar la media de los datos de la fila y dividir por la desviación estándar o la norma l2 (de los datos de la fila) y multiplicar por un factor de escala configurable (valor predeterminado 2) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | Asignar el valor de entrada a un índice de discretización por el número de discretizaciones para generar un valor flotante entre 0 y 1. Los límites de discretización se calculan para distribuir de manera uniforme los datos de aprendizaje entre las discretizaciones |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | Asignar el valor de entrada a una discretización en función de su correlación con la columna de etiqueta |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | Escalar la entrada por la diferencia entre los valores mínimo y máximo de los datos de aprendizaje |

## <a name="conversions-between-data-types"></a>Conversiones entre los tipos de datos

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | Convertir el tipo de una columna de entrada en un tipo nuevo |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue%2A> | Asignar valores a claves (categorías) en función del diccionario de asignaciones suministrado |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> | Asignar valores a claves (categorías) mediante la creación de la asignación a partir de los datos de entrada |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A> | Convertir claves de vuelta a sus valores originales |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector%2A> | Convertir claves de vuelta a vectores de los valores originales |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector%2A> | Convertir claves de vuelta a un vector binario de valores originales |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A> | Aplicar un algoritmo hash al valor de la columna de entrada |

## <a name="text-transformations"></a>Transformaciones de texto

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText%2A> | Transformar una columna de texto en una matriz flotante de recuentos de n-gramas y char-gramas normalizados |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A> | Dividir una o más columnas de texto en palabras individuales |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys%2A> | Dividir una o más columnas de texto en flotantes de caracteres individuales sobre un conjunto de temas |
| <xref:Microsoft.ML.TextCatalog.NormalizeText%2A> | Cambiar mayúsculas y minúsculas, quitar marcas diacríticas, signos de puntuación y números |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams%2A> | Transformar una columna de texto en un contenedor de recuentos de n-gramas (secuencias de palabras consecutivas)|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags%2A> | Transformar una columna de texto en un contenedor de recuentos de vector de n-gramas |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams%2A> | Transformar una columna de texto en un vector de recuentos de n-gramas con algoritmo hash |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags%2A> | Transformar una columna de texto en un contenedor de recuentos de n-gramas con algoritmo hash |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords%2A>  | Quitar las palabras irrelevantes predeterminadas para el idioma especificado de las columnas de entrada |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords%2A> | Quitar las palabras irrelevantes especificadas de las columnas de entrada |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation%2A> | Transformar un documento (representado como vector de flotantes) en un vector de flotantes sobre un conjunto de temas |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding%2A> | Convertir vectores de tokens de texto en vectores de oraciones con un modelo entrenado previamente |

## <a name="image-transformations"></a>Transformaciones de imagen

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> | Convertir una imagen en escala de grises |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage%2A> | Convertir un vector de píxeles en <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A> | Convertir píxeles de una imagen de entrada en un vector de números |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A> | Cargar imágenes de una carpeta en memoria |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A> | Cambiar el tamaño de imágenes |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage%2A> | Aplicar un modelo de red neuronal profunda (DNN) previamente entrenado para transformar una imagen de entrada en un vector de características |

## <a name="categorical-data-transformations"></a>Transformaciones de datos categóricos

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A> | Convertir una o más columnas de texto en vectores codificados [one-hot](https://en.wikipedia.org/wiki/One-hot) |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding%2A> | Convertir una o más columnas de texto en vectores codificados one-hot basados en hash |

## <a name="time-series-data-transformations"></a>Transformaciones de datos de serie temporal

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn%2A> | Detectar anomalías en los datos de serie temporal de entrada con el algoritmo de valor residual espectral (SR) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa%2A> | Detectar puntos de cambio en los datos de serie temporal con el análisis de espectro singular (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint%2A> | Detectar puntos de cambio en los datos de serie temporal independientes y distribuidos de manera idéntica (IID) con puntuaciones de Martingala y estimaciones de densidad de kernel adaptable |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A> | Pronosticar los datos de serie temporal con el análisis de espectro singular (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa%2A> | Detectar picos en los datos de serie temporal con el análisis de espectro singular (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike%2A> | Detectar picos en los datos de serie temporal independientes y distribuidos de manera idéntica (IID) con puntuaciones de Martingala y estimaciones de densidad de kernel adaptable |

## <a name="missing-values"></a>Valores ausentes

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues%2A> | Crear una columna de salida booleana nueva cuyo valor es true cuando falta el valor en la columna de entrada |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A> | Crear una columna de salida nueva cuyo valor se establece en un valor predeterminado si falta el valor de la columna de entrada y, de otro modo, el valor de entrada |

## <a name="feature-selection"></a>Selección de características

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount%2A> | Seleccionar las características con valores no predeterminados que sobrepasan un umbral |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation%2A> | Seleccionar las características de las que más dependen los datos de la columna de etiqueta |

## <a name="feature-transformations"></a>Transformaciones de características

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap%2A> | Asignar cada vector de entrada a un espacio de característica dimensional inferior, donde los productos internos se aproximan a una función kernel, para que las características se puedan usar como entradas en los algoritmos lineales |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents%2A> | Reducir las dimensiones del vector de característica de entrada mediante la aplicación del algoritmo Análisis de componentes principales |

## <a name="explainability-transformations"></a>Transformaciones de explicación

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution%2A> | Calcular las puntuaciones de contribución para cada elemento de un vector de característica |

## <a name="calibration-transformations"></a>Transformaciones de calibración

| Transformación | Definición |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | Transforma la puntuación sin procesar de un clasificador binario en una probabilidad de clase mediante la regresión logística con parámetros estimados usando los datos de entrenamiento |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | Transforma la puntuación sin procesar de un clasificador binario en una probabilidad de clase mediante la regresión logística con parámetros fijos |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive%2A> | Transforma la puntuación sin procesar de un clasificador binario en una probabilidad de clase mediante la asignación de puntuaciones a los intervalos y el cálculo de la probabilidad según la distribución entre los intervalos |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic%2A> | Transforma la puntuación sin procesar de un clasificador binario en una probabilidad de clase mediante la asignación de puntuaciones a los intervalos, donde la posición de los límites y el tamaño de los intervalos se calculan usando los datos de entrenamiento  |

## <a name="deep-learning-transformations"></a>Transformaciones de aprendizaje profundo

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A> | Transforma los datos de entrada con un modelo importado de ONNX |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel%2A> | Transforma los datos de entrada con un modelo importado de TensorFlow |

## <a name="custom-transformations"></a>Transformaciones personalizadas

| Transformación | Definición |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping%2A> | Transformar las columnas existentes en columnas nuevas con una asignación definida por el usuario |
