---
title: Entrenamiento de un modelo de aprendizaje automático con validación cruzada
description: Obtenga información sobre cómo usar la validación cruzada para compilar modelos de aprendizaje automático más eficaces en ML.NET. La validación cruzada es una técnica de evaluación de modelos y entrenamiento que divide los datos en diversas particiones y entrena varios algoritmos en estas particiones.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 87eae789478752423f3e682d4db6cead0391aa6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976924"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a>Entrenamiento de un modelo de aprendizaje automático con validación cruzada

Obtenga información sobre cómo usar la validación cruzada para entrenar modelos de aprendizaje automático más eficaces en ML.NET.

La validación cruzada es una técnica de evaluación de modelos y entrenamiento que divide los datos en diversas particiones y entrena varios algoritmos en estas particiones. Esta técnica mejora la estabilidad del modelo que contiene datos del proceso de entrenamiento. Además de mejorar el rendimiento en observaciones no vistas y en entornos con limitaciones de datos, puede ser una herramienta eficaz para el entrenamiento de modelos con un conjunto de datos más pequeño.

## <a name="the-data-and-data-model"></a>Los datos y el modelo de datos

Dados los datos desde un archivo que tiene el formato siguiente:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

Los datos se pueden modelar mediante una clase como `HousingData` y cargarlos en [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

## <a name="prepare-the-data"></a>Preparar los datos

Procese previamente los datos antes de usarlos para compilar el modelo de aprendizaje automático. En este ejemplo, las columnas `Size` y `HistoricalPrices` se combinan en un vector de característica única, que se muestra en una nueva columna denominada `Features` con el método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*). Además, para obtener los datos en el formato esperado por los algoritmos de ML.NET, la concatenación de columnas optimiza las operaciones posteriores en la canalización aplicando la operación una vez para la columna concatenada, en lugar de cada una de las columnas independientes.

Una vez que se han combinado las columnas en un vector único, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) se aplica a la columna `Features` para obtener `Size` y `HistoricalPrices` en el mismo intervalo entre 0 y 1.

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a>Entrenamiento de modelos con validación cruzada

Una vez que se han procesado previamente los datos, es hora de entrenar el modelo. En primer lugar, seleccione el algoritmo que mejor se adapte a la tarea de aprendizaje automático que debe realizarse. Dado que el valor de predicción es un valor numérico continuo, la tarea es la regresión. Uno de los algoritmos de regresión implementados por ML.NET es el algoritmo [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer). Para entrenar el modelo con la validación cruzada, use el método [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*).

> [!NOTE]
> Aunque en este ejemplo se usa un modelo de regresión lineal, la validación cruzada se aplica a las demás tareas de aprendizaje automático en ML.NET, excepto la detección de anomalías.

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) lleva a cabo las operaciones siguientes:

1. Divide los datos en un número de particiones iguales al valor especificado en el parámetro `numberOfFolds`. El resultado de cada partición es un objeto [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).
1. Se entrena un modelo en cada una de las particiones con el estimador del algoritmo de aprendizaje automático especificado en el conjunto de datos de entrenamiento.
1. El rendimiento de cada modelo se evalúa con el método [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) en el conjunto de datos de prueba.
1. El modelo, junto con sus métricas, se devuelve para cada uno de los modelos.

El resultado almacenado en `cvResults` es una colección de objetos [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601). Este objeto incluye el modelo entrenado, así como las métricas que son accesibles desde las propiedades [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) y [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) respectivamente. En este ejemplo, la propiedad `Model` es de tipo [`ITransformer`](xref:Microsoft.ML.ITransformer) y la propiedad `Metrics` es de tipo [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).

## <a name="evaluate-the-model"></a>Evaluar el modelo

Las métricas de los diferentes modelos entrenados se pueden acceder a través de la propiedad `Metrics` del objeto [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) individual. En este caso, la [métrica de R cuadrado](https://en.wikipedia.org/wiki/Coefficient_of_determination) se accede y almacena en la variable `rSquared`.

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

Si examina el contenido de la variable `rSquared`, la salida debe tener cinco valores comprendidos entre 0 y 1, donde el valor más cercano a 1 es mejor. Mediante métricas como R cuadrado, seleccione los modelos de mejor a peor rendimiento. A continuación, seleccione el mejor modelo con el que realizará predicciones u operaciones adicionales.

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
