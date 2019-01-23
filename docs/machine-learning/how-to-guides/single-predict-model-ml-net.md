---
title: 'Uso de PredictionEngine para realizar una predicción cada vez: ML.NET'
description: Información sobre cómo usar PredictionEngine de ML.NET para hacer una predicción cada vez
ms.date: 01/15/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0b3f60038fe7f49ffbff3c63fd2862ba67adb506
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333647"
---
# <a name="use-the-predictionengine-to-make-one-prediction-at-a-time---mlnet"></a><span data-ttu-id="042f5-103">Uso de PredictionEngine para realizar una predicción cada vez: ML.NET</span><span class="sxs-lookup"><span data-stu-id="042f5-103">Use the PredictionEngine to make one prediction at a time - ML.NET</span></span> 

<span data-ttu-id="042f5-104">Dado que todo modelo de ML.NET es un transformador, puede usar `model.Transform` para aplicar el modelo a `DataView` con el fin de hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="042f5-104">Since any ML.NET model is a transformer, you use `model.Transform` to apply the model to the `DataView` to make predictions.</span></span> 

<span data-ttu-id="042f5-105">Sin embargo, un caso más típico es cuando no quiere hacer una predicción sobre un "conjunto de datos", sino que, en su lugar, recibe un ejemplo a la vez.</span><span class="sxs-lookup"><span data-stu-id="042f5-105">A more typical case, though, is when there is no 'dataset' that you want to predict on, but instead you receive one example at a time.</span></span> <span data-ttu-id="042f5-106">Por ejemplo, puede ejecutar el modelo como parte del sitio web de ASP.NET y debe hacer una predicción respecto de una solicitud HTTP entrante.</span><span class="sxs-lookup"><span data-stu-id="042f5-106">For instance, you run the model as part of your ASP.NET website, and need to make a prediction for an incoming HTTP request.</span></span>

<span data-ttu-id="042f5-107">`PredictionEngine` ejecuta un ejemplo a la vez a través de la canalización de predicción.</span><span class="sxs-lookup"><span data-stu-id="042f5-107">The `PredictionEngine` runs one example at a time through the prediction pipeline.</span></span>

<span data-ttu-id="042f5-108">Este es el ejemplo completo con un modelo de datos de predicción de Iris creado previamente:</span><span class="sxs-lookup"><span data-stu-id="042f5-108">Here is the full example using a prebuilt Iris prediction dataset model:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(new TextLoader.Arguments
{
    Column = new[] {
        new TextLoader.Column("SepalLength", DataKind.R4, 0),
        new TextLoader.Column("SepalWidth", DataKind.R4, 1),
        new TextLoader.Column("PetalLength", DataKind.R4, 2),
        new TextLoader.Column("PetalWidth", DataKind.R4, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Retrieve the training data.
var trainData = reader.Read(irisDataPath);

// Build the training pipeline.
var pipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Categorical.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent())
    // Apply the inverse conversion from 'PredictedLabel' column back to string value.
    .Append(mlContext.Transforms.Conversion.MapKeyToValue(("PredictedLabel", "Data")));

// Train the model.
var model = pipeline.Fit(trainData);
```

<span data-ttu-id="042f5-109">Para usar la [comprensión de esquema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) para hacer una predicción, defina un par de clases como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="042f5-109">To use [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) for prediction, define a pair of classes like the following:</span></span>

```csharp
private class IrisInput
{
    // Unfortunately, we still need the dummy 'Label' column to be present.
    [ColumnName("Label")]
    public string IgnoredLabel { get; set; }
    public float SepalLength { get; set; }
    public float SepalWidth { get; set; }
    public float PetalLength { get; set; }
    public float PetalWidth { get; set; }
}

private class IrisPrediction
{
    [ColumnName("Data")]
    public string PredictedClass { get; set; }
}
```

<span data-ttu-id="042f5-110">El código de la predicción ahora es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="042f5-110">The prediction code now looks as follows:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Use the model for one-time prediction.
// Make the prediction function object. Note that, on average, this call takes around 200x longer
// than one prediction, so you might want to cache and reuse the prediction engine, instead of
// creating one per prediction.
var predictionEngine = model.CreatePredictionEngine<IrisInput, IrisPrediction>(mlContext);

// Obtain the prediction. Remember that 'Predict' is not reentrant. If you want to use multiple threads
// for simultaneous prediction, make sure each thread is using its own PredictionEngine.
var prediction = predictionEngine.Predict(new IrisInput
{
    SepalLength = 4.1f,
    SepalWidth = 0.1f,
    PetalLength = 3.2f,
    PetalWidth = 1.4f
});
```
