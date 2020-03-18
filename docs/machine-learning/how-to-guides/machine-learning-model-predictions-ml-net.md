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
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="44d8c-103">Realizar predicciones con un modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="44d8c-103">Make predictions with a trained model</span></span>

<span data-ttu-id="44d8c-104">Obtenga información sobre cómo usar un modelo entrenado para realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="44d8c-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="44d8c-105">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="44d8c-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="44d8c-106">Datos de entrada</span><span class="sxs-lookup"><span data-stu-id="44d8c-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="44d8c-107">Datos de salida</span><span class="sxs-lookup"><span data-stu-id="44d8c-107">Output data</span></span>

<span data-ttu-id="44d8c-108">Al igual que los nombres de las columnas de entrada `Features` y `Label`, ML.NET tiene nombres predeterminados para las columnas de valores de predicción que genera un modelo.</span><span class="sxs-lookup"><span data-stu-id="44d8c-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="44d8c-109">En función de la tarea, el nombre puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="44d8c-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="44d8c-110">Dado que el algoritmo utilizado en este ejemplo es un algoritmo de regresión lineal, el nombre predeterminado de la columna de salida es `Score`, que se define mediante el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) en la propiedad `PredictedPrice`.</span><span class="sxs-lookup"><span data-stu-id="44d8c-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="44d8c-111">Configuración de una canalización de predicción</span><span class="sxs-lookup"><span data-stu-id="44d8c-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="44d8c-112">Independientemente de si se crea una predicción única o por lotes, la canalización de predicción necesita cargarse en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="44d8c-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="44d8c-113">Esta canalización contiene las transformaciones del procesamiento previo de datos, así como el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="44d8c-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="44d8c-114">El siguiente fragmento de código carga la canalización de predicción desde un archivo denominado `model.zip`.</span><span class="sxs-lookup"><span data-stu-id="44d8c-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="44d8c-115">Predicción única</span><span class="sxs-lookup"><span data-stu-id="44d8c-115">Single prediction</span></span>

<span data-ttu-id="44d8c-116">Para realizar una sola predicción, cree un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) mediante la canalización de la predicción cargada.</span><span class="sxs-lookup"><span data-stu-id="44d8c-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="44d8c-117">A continuación, utilice el método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) y pase los datos de entrada como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="44d8c-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="44d8c-118">Tenga en cuenta que el uso del método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) no requiere que la entrada sea un [`IDataView`](xref:Microsoft.ML.IDataView)).</span><span class="sxs-lookup"><span data-stu-id="44d8c-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="44d8c-119">Esto se debe a que interioriza cómodamente la manipulación del tipo de datos de entrada para que pueda pasar un objeto del tipo de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="44d8c-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="44d8c-120">Además, dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.</span><span class="sxs-lookup"><span data-stu-id="44d8c-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

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

<span data-ttu-id="44d8c-121">Si accede a la propiedad `Score` del objeto `prediction`, debe obtener un valor similar a `150079`.</span><span class="sxs-lookup"><span data-stu-id="44d8c-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="44d8c-122">Varias predicciones</span><span class="sxs-lookup"><span data-stu-id="44d8c-122">Multiple predictions</span></span>

<span data-ttu-id="44d8c-123">Dados los siguientes datos, cárguelos en un [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="44d8c-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="44d8c-124">En este caso, el nombre de la [`IDataView`](xref:Microsoft.ML.IDataView) es `inputData`.</span><span class="sxs-lookup"><span data-stu-id="44d8c-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="44d8c-125">Dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.</span><span class="sxs-lookup"><span data-stu-id="44d8c-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

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

<span data-ttu-id="44d8c-126">A continuación, utilice el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) para aplicar las transformaciones de datos y generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="44d8c-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="44d8c-127">Inspeccione los valores de predicción mediante el método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="44d8c-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="44d8c-128">Los valores de predicción en la columna de puntuación deben ser similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="44d8c-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="44d8c-129">Observación</span><span class="sxs-lookup"><span data-stu-id="44d8c-129">Observation</span></span> | <span data-ttu-id="44d8c-130">Predicción</span><span class="sxs-lookup"><span data-stu-id="44d8c-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="44d8c-131">1</span><span class="sxs-lookup"><span data-stu-id="44d8c-131">1</span></span> | <span data-ttu-id="44d8c-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="44d8c-132">144638.2</span></span> |
| <span data-ttu-id="44d8c-133">2</span><span class="sxs-lookup"><span data-stu-id="44d8c-133">2</span></span> | <span data-ttu-id="44d8c-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="44d8c-134">150079.4</span></span> |
| <span data-ttu-id="44d8c-135">3</span><span class="sxs-lookup"><span data-stu-id="44d8c-135">3</span></span> | <span data-ttu-id="44d8c-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="44d8c-136">107789.8</span></span> |
