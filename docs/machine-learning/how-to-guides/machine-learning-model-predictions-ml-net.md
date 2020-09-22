---
title: Realizar predicciones con un modelo entrenado
description: Aprenda a realizar predicciones con un modelo entrenado
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2e8263db289bed50e7437b695134458b8c07e0e5
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679578"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="a2d5f-103">Realizar predicciones con un modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="a2d5f-103">Make predictions with a trained model</span></span>

<span data-ttu-id="a2d5f-104">Obtenga información sobre cómo usar un modelo entrenado para realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="a2d5f-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="a2d5f-105">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="a2d5f-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="a2d5f-106">Datos de entrada</span><span class="sxs-lookup"><span data-stu-id="a2d5f-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="a2d5f-107">Datos de salida</span><span class="sxs-lookup"><span data-stu-id="a2d5f-107">Output data</span></span>

<span data-ttu-id="a2d5f-108">Al igual que los nombres de las columnas de entrada `Features` y `Label`, ML.NET tiene nombres predeterminados para las columnas de valores de predicción que genera un modelo.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="a2d5f-109">En función de la tarea, el nombre puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="a2d5f-110">Dado que el algoritmo utilizado en este ejemplo es un algoritmo de regresión lineal, el nombre predeterminado de la columna de salida es `Score`, que se define mediante el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) en la propiedad `PredictedPrice`.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="a2d5f-111">Configuración de una canalización de predicción</span><span class="sxs-lookup"><span data-stu-id="a2d5f-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="a2d5f-112">Independientemente de si se crea una predicción única o por lotes, la canalización de predicción necesita cargarse en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="a2d5f-113">Esta canalización contiene las transformaciones del procesamiento previo de datos, así como el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="a2d5f-114">El siguiente fragmento de código carga la canalización de predicción desde un archivo denominado `model.zip`.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="a2d5f-115">Predicción única</span><span class="sxs-lookup"><span data-stu-id="a2d5f-115">Single prediction</span></span>

<span data-ttu-id="a2d5f-116">Para realizar una sola predicción, cree un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) mediante la canalización de la predicción cargada.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="a2d5f-117">A continuación, utilice el método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict%2A) y pase los datos de entrada como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict%2A) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="a2d5f-118">Tenga en cuenta que el uso del método [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict%2A) no requiere que la entrada sea un [`IDataView`](xref:Microsoft.ML.IDataView)).</span><span class="sxs-lookup"><span data-stu-id="a2d5f-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict%2A) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="a2d5f-119">Esto se debe a que interioriza cómodamente la manipulación del tipo de datos de entrada para que pueda pasar un objeto del tipo de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="a2d5f-120">Además, dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

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

<span data-ttu-id="a2d5f-121">Si accede a la propiedad `Score` del objeto `prediction`, debe obtener un valor similar a `150079`.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="a2d5f-122">Varias predicciones</span><span class="sxs-lookup"><span data-stu-id="a2d5f-122">Multiple predictions</span></span>

<span data-ttu-id="a2d5f-123">Dados los siguientes datos, cárguelos en un [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="a2d5f-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="a2d5f-124">En este caso, el nombre de la [`IDataView`](xref:Microsoft.ML.IDataView) es `inputData`.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="a2d5f-125">Dado que `CurrentPrice` es el destino o la etiqueta que intenta predecir mediante datos nuevos, se asume que en este momento no hay ningún valor para este.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

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

<span data-ttu-id="a2d5f-126">A continuación, utilice el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) para aplicar las transformaciones de datos y generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="a2d5f-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="a2d5f-127">Inspeccione los valores de predicción mediante el método [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A).</span><span class="sxs-lookup"><span data-stu-id="a2d5f-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="a2d5f-128">Los valores de predicción en la columna de puntuación deben ser similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2d5f-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="a2d5f-129">Observación</span><span class="sxs-lookup"><span data-stu-id="a2d5f-129">Observation</span></span> | <span data-ttu-id="a2d5f-130">Predicción</span><span class="sxs-lookup"><span data-stu-id="a2d5f-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="a2d5f-131">1</span><span class="sxs-lookup"><span data-stu-id="a2d5f-131">1</span></span> | <span data-ttu-id="a2d5f-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="a2d5f-132">144638.2</span></span> |
| <span data-ttu-id="a2d5f-133">2</span><span class="sxs-lookup"><span data-stu-id="a2d5f-133">2</span></span> | <span data-ttu-id="a2d5f-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="a2d5f-134">150079.4</span></span> |
| <span data-ttu-id="a2d5f-135">3</span><span class="sxs-lookup"><span data-stu-id="a2d5f-135">3</span></span> | <span data-ttu-id="a2d5f-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="a2d5f-136">107789.8</span></span> |
