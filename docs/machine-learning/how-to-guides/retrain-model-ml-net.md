---
title: Nuevo entrenamiento de un modelo
description: Obtenga información sobre cómo volver a entrenar un modelo de ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 735782a4a0877a917b6e1885f009aa49d834170f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976962"
---
# <a name="re-train-a-model"></a><span data-ttu-id="d5081-103">Nuevo entrenamiento de un modelo</span><span class="sxs-lookup"><span data-stu-id="d5081-103">Re-train a model</span></span>

<span data-ttu-id="d5081-104">Obtenga información sobre cómo volver a entrenar un modelo de Machine Learning en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d5081-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="d5081-105">El mundo y los datos alrededor de este cambian a un ritmo constante.</span><span class="sxs-lookup"><span data-stu-id="d5081-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="d5081-106">Por lo tanto, los modelos también deben cambiar y actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d5081-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="d5081-107">ML.NET proporciona funcionalidad para modelos de nuevo entrenamiento mediante parámetros de modelo aprendidos como un punto inicial para compilar continuamente en la experiencia anterior, en lugar de hacerlo cada vez desde el principio.</span><span class="sxs-lookup"><span data-stu-id="d5081-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>

<span data-ttu-id="d5081-108">Los algoritmos siguientes se pueden volver a entrenar en ML.NET:</span><span class="sxs-lookup"><span data-stu-id="d5081-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="d5081-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="d5081-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="d5081-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="d5081-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="d5081-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="d5081-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="d5081-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="d5081-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="d5081-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="d5081-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="d5081-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="d5081-119">Carga del modelo previamente entrenado</span><span class="sxs-lookup"><span data-stu-id="d5081-119">Load pre-trained model</span></span>

<span data-ttu-id="d5081-120">En primer lugar, cargue el modelo previamente entrenado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5081-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="d5081-121">Para obtener más información sobre la carga de modelos y canalizaciones de entrenamiento, consulte [Guardar y cargar modelos entrenados](save-load-machine-learning-models-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d5081-121">To learn more about loading training pipelines and models, see [Save and load a trained model](save-load-machine-learning-models-ml-net.md).</span></span>

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

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="d5081-122">Extracción de parámetros del modelo previamente entrenado</span><span class="sxs-lookup"><span data-stu-id="d5081-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="d5081-123">Una vez que se ha cargado el modelo, extraiga los parámetros del modelo entrenado accediendo a la propiedad [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) del modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="d5081-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="d5081-124">El modelo previamente entrenado se entrenó con el modelo de regresión lineal [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer), que crea un [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) que genera [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span><span class="sxs-lookup"><span data-stu-id="d5081-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="d5081-125">Estos parámetros del modelo de regresión lineal contienen el sesgo aprendido y pesos o coeficientes del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5081-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="d5081-126">Estos valores se usarán como punto inicial para el nuevo modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="d5081-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="d5081-127">Volver a entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d5081-127">Re-train model</span></span>

<span data-ttu-id="d5081-128">El proceso para volver a entrenar un modelo es similar al de entrenamiento de un modelo.</span><span class="sxs-lookup"><span data-stu-id="d5081-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="d5081-129">La única diferencia es que el método [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*), además de los datos, también toma como entrada los parámetros del modelo entrenado original y los usa como punto inicial en el proceso de nuevo entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="d5081-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>

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

## <a name="compare-model-parameters"></a><span data-ttu-id="d5081-130">Comparar parámetros del modelo</span><span class="sxs-lookup"><span data-stu-id="d5081-130">Compare model parameters</span></span>

<span data-ttu-id="d5081-131">¿Cómo saber si realmente se produjo el nuevo entrenamiento?</span><span class="sxs-lookup"><span data-stu-id="d5081-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="d5081-132">Una manera sería comparar si los parámetros del modelo entrenado son diferentes a los del modelo original.</span><span class="sxs-lookup"><span data-stu-id="d5081-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="d5081-133">El siguiente ejemplo de código compara el original con los pesos del modelo que se volvió a entrenar y los genera en la consola.</span><span class="sxs-lookup"><span data-stu-id="d5081-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

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

<span data-ttu-id="d5081-134">En la siguiente tabla se muestra el aspecto que podría tener la salida.</span><span class="sxs-lookup"><span data-stu-id="d5081-134">The table below shows what the output might look like.</span></span>

|<span data-ttu-id="d5081-135">Original</span><span class="sxs-lookup"><span data-stu-id="d5081-135">Original</span></span> | <span data-ttu-id="d5081-136">Vuelto a entrenar</span><span class="sxs-lookup"><span data-stu-id="d5081-136">Retrained</span></span> | <span data-ttu-id="d5081-137">Diferencia</span><span class="sxs-lookup"><span data-stu-id="d5081-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="d5081-138">33039.86</span><span class="sxs-lookup"><span data-stu-id="d5081-138">33039.86</span></span> | <span data-ttu-id="d5081-139">56293.76</span><span class="sxs-lookup"><span data-stu-id="d5081-139">56293.76</span></span> | <span data-ttu-id="d5081-140">-23253.9</span><span class="sxs-lookup"><span data-stu-id="d5081-140">-23253.9</span></span> |
| <span data-ttu-id="d5081-141">29099.14</span><span class="sxs-lookup"><span data-stu-id="d5081-141">29099.14</span></span> | <span data-ttu-id="d5081-142">49586.03</span><span class="sxs-lookup"><span data-stu-id="d5081-142">49586.03</span></span> | <span data-ttu-id="d5081-143">-20486.89</span><span class="sxs-lookup"><span data-stu-id="d5081-143">-20486.89</span></span> |
| <span data-ttu-id="d5081-144">28938.38</span><span class="sxs-lookup"><span data-stu-id="d5081-144">28938.38</span></span> | <span data-ttu-id="d5081-145">48609.23</span><span class="sxs-lookup"><span data-stu-id="d5081-145">48609.23</span></span> | <span data-ttu-id="d5081-146">-19670.85</span><span class="sxs-lookup"><span data-stu-id="d5081-146">-19670.85</span></span> |
| <span data-ttu-id="d5081-147">30484.02</span><span class="sxs-lookup"><span data-stu-id="d5081-147">30484.02</span></span> | <span data-ttu-id="d5081-148">53745.43</span><span class="sxs-lookup"><span data-stu-id="d5081-148">53745.43</span></span> | <span data-ttu-id="d5081-149">-23261.41</span><span class="sxs-lookup"><span data-stu-id="d5081-149">-23261.41</span></span> |
