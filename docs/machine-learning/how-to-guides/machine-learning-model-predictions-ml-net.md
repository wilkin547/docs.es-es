---
title: Realizar predicciones con un modelo entrenado
description: Aprenda a realizar predicciones con un modelo entrenado
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977045"
---
# <a name="make-predictions-with-a-trained-model"></a>Realizar predicciones con un modelo entrenado

Obtenga información sobre cómo usar un modelo entrenado para realizar predicciones

## <a name="create-data-models"></a>Creación de modelos de datos

### <a name="input-data"></a>Datos de entrada

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

### <a name="output-data"></a>Datos de salida

Al igual que los nombres de las columnas de entrada `Features` y `Label`, ML.NET tiene nombres predeterminados para las columnas de valores de predicción que genera un modelo. En función de la tarea, el nombre puede ser diferente.

Dado que el algoritmo utilizado en este ejemplo es un algoritmo de regresión lineal, el nombre predeterminado de la columna de salida es `Score`, que se define mediante el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) en la propiedad `PredictedPrice`.

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a>Configuración de una canalización de predicción

Independientemente de si se crea una predicción única o por lotes, la canalización de predicción necesita cargarse en la aplicación. Esta canalización contiene las transformaciones del procesamiento previo de datos, así como el modelo entrenado. El siguiente fragmento de código carga la canalización de predicción desde un archivo denominado `model.zip`.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a>Predicción única

Para realizar una sola predicción, cree un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) mediante la canalización de la predicción cargada.

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

A continuación, utilice el método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) y pase los datos de entrada como un parámetro. Tenga en cuenta que el uso del método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) no requiere que la entrada sea un [`IDataView`](xref:Microsoft.ML.IDataView)). Esto se debe a que interioriza cómodamente la manipulación del tipo de datos de entrada para que pueda pasar un objeto del tipo de datos de entrada. Además, dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

Si accede a la propiedad `Score` del objeto `prediction`, debe obtener un valor similar a `150079`.

## <a name="multiple-predictions"></a>Varias predicciones

Dados los siguientes datos, cárguelos en un [`IDataView`](xref:Microsoft.ML.IDataView). En este caso, el nombre de la [`IDataView`](xref:Microsoft.ML.IDataView) es `inputData`. Dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

A continuación, utilice el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) para aplicar las transformaciones de datos y generar predicciones.

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

Inspeccione los valores de predicción mediante el método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

Los valores de predicción en la columna de puntuación deben ser similares a los siguientes:

| Observación | Predicción |
|---|---|
| 1 | 144638.2 |
| 2 | 150079.4 |
| 3 | 107789.8 |
