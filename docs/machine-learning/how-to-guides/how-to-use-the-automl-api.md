---
title: Cómo usar la API de ML automatizada de ML.NET
description: La API de ML automatizada de ML.NET automatiza el proceso de compilación de modelos y genera un modelo listo para la implementación. Descubra las opciones que puede usar para configurar tareas de aprendizaje automático.
ms.date: 12/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b1ef526301e01e1e75e71e0646f4d11e68215d69
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540737"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a>Cómo usar la API de aprendizaje automático automatizada de ML.NET

El aprendizaje automático automatizado (AutoML) automatiza el proceso de aplicar aprendizaje automático en los datos. Dado un conjunto de datos, puede ejecutar un **experimento** de AutoML para iterar en diferentes caracterizaciones de datos, algoritmos de aprendizaje automático e hiperparámetros para seleccionar el mejor modelo.

> [!NOTE]
> Este tema hace referencia a la API de aprendizaje automático de ML.NET, que actualmente se encuentra en versión preliminar. El material puede estar sujetos a cambios.

## <a name="load-data"></a>Cargar los datos

El aprendizaje automático automatizado admite la carga de un conjunto de datos en un [IDataView](xref:Microsoft.ML.IDataView). Los datos pueden estar en forma de archivos de valores separados por tabulaciones (TSV) y archivos de valores separados por comas (CSV).

Ejemplo:

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a>Seleccionar el tipo de tarea de aprendizaje automático

Antes de crear un experimento, determine el tipo de problema de aprendizaje automático que desea resolver. El aprendizaje automático automatizado admite las siguientes tareas de ML:

* Clasificación binaria
* Clasificación multiclase
* Regresión
* Recomendación

## <a name="create-experiment-settings"></a>Crear una configuración de experimento

Cree una configuración de experimento para el tipo de tarea de ML determinada:

* Clasificación binaria

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* Clasificación multiclase

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* Regresión

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

* Recomendación

  ```csharp
  var experimentSettings = new RecommendationExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a>Establecer la configuración de experimento

Los experimentos son altamente configurables. Consulte los [documentos de la API de AutoML](/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) para obtener una lista completa de las opciones de configuración.

Estos son algunos ejemplos:

1. Especifique el tiempo máximo que se puede ejecutar el experimento.

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. Use un token de cancelación para cancelar el experimento antes de que se programe para finalizar.

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. Especifique una métrica de optimización diferente.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. La configuración `CacheDirectory` es un puntero a un directorio donde se guardarán todos los modelos entrenados durante la tarea de AutoML. Si `CacheDirectory` se establece en null, los modelos se mantendrán en memoria en lugar de que se escriban en el disco.

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. Indique a ML automatizado que no use ciertos instructores.

    Cada tarea explora una lista predeterminada de instructores para optimizar. Esta lista se puede modificar para cada experimento. Por ejemplo, los instructores que se ejecutan lentamente en el conjunto de datos pueden eliminarse de la lista. Para optimizar `experimentSettings.Trainers.Clear()` en una llamada específica de instructor, agregue el instructor que desea usar.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

La lista de instructores admitidos por la tarea de ML se encuentra en el siguiente vínculo correspondiente:

* [Algoritmos de clasificación binaria admitidos](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [Algoritmos de clasificación multiclase admitidos](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [Algoritmos de regresión admitidos](xref:Microsoft.ML.AutoML.RegressionTrainer)
* [Algoritmos de recomendación admitidos](xref:Microsoft.ML.AutoML.RecommendationTrainer)

## <a name="optimizing-metric"></a>Métrica de optimización

La métrica de optimización, tal como se muestra en el ejemplo anterior, determina la métrica que se optimizará durante el entrenamiento del modelo. La métrica de optimización que puede seleccionar viene determinada por el tipo de tarea que elija. Esta es una lista de las métricas disponibles.

|[Clasificación binaria](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [Clasificación multiclase](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[Regresión y recomendación](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|Exactitud| LogLoss | RSquared
|AreaUnderPrecisionRecallCurve | LogLossReduction | MeanAbsoluteError
|AreaUnderRocCurve | MacroAccuracy | MeanSquaredError
|F1Score | MicroAccuracy | RootMeanSquaredError
|NegativePrecision | TopKAccuracy
|NegativeRecall |
|PositivePrecision
|PositiveRecall

## <a name="data-pre-processing-and-featurization"></a>Caracterización y procesamiento previo de datos

> [!NOTE]
> La columna de características solo admitía los tipos de <xref:System.Boolean>, <xref:System.Single> y <xref:System.String>.

El procesamiento previo de datos se produce de forma predeterminada y los pasos siguientes se realizan automáticamente:

1. Quitar características sin información útil

    Quitar características sin información útil de los conjuntos de validación y entrenamiento. Estas incluyen características con todos los valores ausentes, el mismo valor en todas las filas o con una cardinalidad muy alta (p. ej., hashes, identificadores o GUID).

1. Imputación e indicación del valor ausente

    Rellene las celdas del valor ausente con el valor predeterminado para el tipo de datos. Anexe las características del indicador con el mismo número de ranuras que la columna de entrada. El valor de las características del indicador anexado es `1` si falta el valor de la columna de entrada y, en caso contrario, `0`.

1. Generar características adicionales

    Para las características de texto: Características de bolsa de palabras mediante unigramas y gramas de tres caracteres.

    Para características categóricas: La codificación "One-hot" para características de baja cardinalidad y la codificación de hash "One-hot" para características categóricas de alta cardinalidad.

1. Transformaciones y codificaciones

    Características de texto con muy pocos valores únicos que se transforman en características categóricas. En función de la cardinalidad de las características categóricas, realice una codificación "One-hot" o una codificación de hash "One-hot".

## <a name="exit-criteria"></a>Criterios de salida

Defina los criterios para completar la tarea:

1. Salida después de un período de tiempo: mediante `MaxExperimentTimeInSeconds` en la configuración del experimento puede definir cuántos segundos se debe seguir ejecutando una tarea.

1. Salida con un token de cancelación: puede usar un token de cancelación que le permita cancelar la tarea antes de que se programe para finalizar.

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a>Crear un experimento

Una vez que haya configurado las opciones del experimento, está listo para crearlo.

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a>Ejecutar el experimento

La ejecución del experimento desencadena el procesamiento previo de los datos, la selección del algoritmo de aprendizaje y el ajuste de los hiperparámetros. AutoML seguirá generando combinaciones de caracterización, algoritmos de aprendizaje e hiperparámetros hasta que se alcance `MaxExperimentTimeInSeconds` o se termine el experimento.

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

Explore otras sobrecargas para `Execute()` si desea pasar datos de validación, información de columna que indique el propósito de la columna o caracterizaciones previas.

## <a name="training-modes"></a>Modelo de entrenamiento

### <a name="training-dataset"></a>Conjunto de datos de entrenamiento

AutoML proporciona un método de ejecución de experimentos sobrecargados que permite proporcionar datos de entrenamiento. Internamente, ML automatizado divide los datos en divisiones de validación de entrenamiento.

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a>Conjunto de datos de validación personalizada

Use el conjunto de datos de validación personalizada si la división aleatoria no es aceptable, como suele ser el caso con los datos de serie temporal. Puede especificar su propio conjunto de datos de validación. El modelo se evaluará en el conjunto de datos de validación especificado, en lugar de uno o varios conjuntos de datos aleatorios.

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a>Explorar métricas de modelo

Después de cada iteración de un experimento de ML, se almacenan las métricas relacionadas con esa tarea.

Por ejemplo, podemos acceder a las métricas de validación de la mejor ejecución:

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

Las siguientes son todas las métricas disponibles por tarea de ML:

* [Métricas de clasificación binaria](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [Métricas de clasificación multiclase](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [Métricas de regresión y recomendación](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a>Vea también

Para ver los ejemplos de código completos y mucho más, visite el repositorio de GitHub [machinelearning-dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).
