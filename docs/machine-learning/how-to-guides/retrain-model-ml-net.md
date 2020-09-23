---
title: Nuevo entrenamiento de un modelo
description: Obtenga información sobre cómo volver a entrenar un modelo de ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 50f35e3511acc344339b1e150b47d7ce6de94254
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679565"
---
# <a name="re-train-a-model"></a>Nuevo entrenamiento de un modelo

Obtenga información sobre cómo volver a entrenar un modelo de Machine Learning en ML.NET.

El mundo y los datos alrededor de este cambian a un ritmo constante. Por lo tanto, los modelos también deben cambiar y actualizarse. ML.NET proporciona funcionalidad para modelos de nuevo entrenamiento mediante parámetros de modelo aprendidos como un punto inicial para compilar continuamente en la experiencia anterior, en lugar de hacerlo cada vez desde el principio.

Los algoritmos siguientes se pueden volver a entrenar en ML.NET:

- [AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [LbfgsLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [LbfgsMaximumEntropyMulticlassTrainer](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [LbfgsPoissonRegressionTrainer](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [LinearSvmTrainer](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [SgdCalibratedTrainer](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [SgdNonCalibratedTrainer](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [SymbolicSgdLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a>Carga del modelo previamente entrenado

En primer lugar, cargue el modelo previamente entrenado en la aplicación. Para obtener más información sobre la carga de modelos y canalizaciones de entrenamiento, consulte [Guardar y cargar modelos entrenados](save-load-machine-learning-models-ml-net.md).

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a>Extracción de parámetros del modelo previamente entrenado

Una vez que se ha cargado el modelo, extraiga los parámetros del modelo entrenado accediendo a la propiedad [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase%601.Model%2A) del modelo previamente entrenado. El modelo previamente entrenado se ha entrenado con el modelo de regresión lineal [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer), que crea un objeto [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) que genera [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters). Estos parámetros del modelo de regresión lineal contienen el sesgo aprendido y pesos o coeficientes del modelo. Estos valores se usarán como punto inicial para el nuevo modelo entrenado.

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a>Volver a entrenar el modelo

El proceso para volver a entrenar un modelo es similar al de entrenamiento de un modelo. La única diferencia es que el método [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer%602.Fit%2A), además de los datos, también toma como entrada los parámetros del modelo entrenado original y los usa como punto inicial en el proceso de nuevo entrenamiento.

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel =
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a>Comparar parámetros del modelo

¿Cómo saber si realmente se produjo el nuevo entrenamiento? Una manera sería comparar si los parámetros del modelo entrenado son diferentes a los del modelo original. El siguiente ejemplo de código compara el original con los pesos del modelo que se volvió a entrenar y los genera en la consola.

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs =
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

En la siguiente tabla se muestra el aspecto que podría tener la salida.

|Original | Vuelto a entrenar | Diferencia |
|---|---|---|
| 33039.86 | 56293.76 | -23253.9 |
| 29099.14 | 49586.03 | -20486.89 |
| 28938.38 | 48609.23 | -19670.85 |
| 30484.02 | 53745.43 | -23261.41 |
