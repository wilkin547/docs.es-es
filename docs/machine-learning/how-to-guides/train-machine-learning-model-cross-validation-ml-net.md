---
title: Entrenamiento de un modelo de aprendizaje automático con validación cruzada
description: Obtenga información sobre cómo usar la validación cruzada para compilar modelos de aprendizaje automático más eficaces en ML.NET. La validación cruzada es una técnica de evaluación de modelos y entrenamiento que divide los datos en diversas particiones y entrena varios algoritmos en estas particiones.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 02cec3d22588d8f10d36216422bc19faafffe94b
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679526"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="5f975-104">Entrenamiento de un modelo de aprendizaje automático con validación cruzada</span><span class="sxs-lookup"><span data-stu-id="5f975-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="5f975-105">Obtenga información sobre cómo usar la validación cruzada para entrenar modelos de aprendizaje automático más eficaces en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="5f975-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span>

<span data-ttu-id="5f975-106">La validación cruzada es una técnica de evaluación de modelos y entrenamiento que divide los datos en diversas particiones y entrena varios algoritmos en estas particiones.</span><span class="sxs-lookup"><span data-stu-id="5f975-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="5f975-107">Esta técnica mejora la estabilidad del modelo que contiene datos del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5f975-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="5f975-108">Además de mejorar el rendimiento en observaciones no vistas y en entornos con limitaciones de datos, puede ser una herramienta eficaz para el entrenamiento de modelos con un conjunto de datos más pequeño.</span><span class="sxs-lookup"><span data-stu-id="5f975-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="5f975-109">Los datos y el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="5f975-109">The data and data model</span></span>

<span data-ttu-id="5f975-110">Dados los datos desde un archivo que tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f975-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="5f975-111">Los datos se pueden modelar mediante una clase como `HousingData` y cargarlos en [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="5f975-111">The data can be modeled by a class like `HousingData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

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

## <a name="prepare-the-data"></a><span data-ttu-id="5f975-112">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="5f975-112">Prepare the data</span></span>

<span data-ttu-id="5f975-113">Procese previamente los datos antes de usarlos para compilar el modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="5f975-113">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="5f975-114">En este ejemplo, las columnas `Size` y `HistoricalPrices` se combinan en un vector de característica única, que se muestra en una nueva columna denominada `Features` con el método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A).</span><span class="sxs-lookup"><span data-stu-id="5f975-114">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="5f975-115">Además, para obtener los datos en el formato esperado por los algoritmos de ML.NET, la concatenación de columnas optimiza las operaciones posteriores en la canalización aplicando la operación una vez para la columna concatenada, en lugar de cada una de las columnas independientes.</span><span class="sxs-lookup"><span data-stu-id="5f975-115">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span>

<span data-ttu-id="5f975-116">Una vez que se han combinado las columnas en un vector único, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) se aplica a la columna `Features` para obtener `Size` y `HistoricalPrices` en el mismo intervalo entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="5f975-116">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span>

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

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="5f975-117">Entrenamiento de modelos con validación cruzada</span><span class="sxs-lookup"><span data-stu-id="5f975-117">Train model with cross validation</span></span>

<span data-ttu-id="5f975-118">Una vez que se han procesado previamente los datos, es hora de entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5f975-118">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="5f975-119">En primer lugar, seleccione el algoritmo que mejor se adapte a la tarea de aprendizaje automático que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="5f975-119">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="5f975-120">Dado que el valor de predicción es un valor numérico continuo, la tarea es la regresión.</span><span class="sxs-lookup"><span data-stu-id="5f975-120">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="5f975-121">Uno de los algoritmos de regresión implementados por ML.NET es el algoritmo [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer).</span><span class="sxs-lookup"><span data-stu-id="5f975-121">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="5f975-122">Para entrenar el modelo con la validación cruzada, use el método [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A).</span><span class="sxs-lookup"><span data-stu-id="5f975-122">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) method.</span></span>

> [!NOTE]
> <span data-ttu-id="5f975-123">Aunque en este ejemplo se usa un modelo de regresión lineal, la validación cruzada se aplica a las demás tareas de aprendizaje automático en ML.NET, excepto la detección de anomalías.</span><span class="sxs-lookup"><span data-stu-id="5f975-123">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="5f975-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) lleva a cabo las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f975-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) performs the following operations:</span></span>

1. <span data-ttu-id="5f975-125">Divide los datos en un número de particiones iguales al valor especificado en el parámetro `numberOfFolds`.</span><span class="sxs-lookup"><span data-stu-id="5f975-125">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="5f975-126">El resultado de cada partición es un objeto [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).</span><span class="sxs-lookup"><span data-stu-id="5f975-126">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="5f975-127">Se entrena un modelo en cada una de las particiones con el estimador del algoritmo de aprendizaje automático especificado en el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5f975-127">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="5f975-128">El rendimiento de cada modelo se evalúa con el método [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) en el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f975-128">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method on the test data set.</span></span>
1. <span data-ttu-id="5f975-129">El modelo, junto con sus métricas, se devuelve para cada uno de los modelos.</span><span class="sxs-lookup"><span data-stu-id="5f975-129">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="5f975-130">El resultado almacenado en `cvResults` es una colección de objetos [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601).</span><span class="sxs-lookup"><span data-stu-id="5f975-130">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="5f975-131">Este objeto incluye el modelo entrenado, así como las métricas que son accesibles desde las propiedades [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) y [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5f975-131">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="5f975-132">En este ejemplo, la propiedad `Model` es de tipo [`ITransformer`](xref:Microsoft.ML.ITransformer) y la propiedad `Metrics` es de tipo [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span><span class="sxs-lookup"><span data-stu-id="5f975-132">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="5f975-133">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5f975-133">Evaluate the model</span></span>

<span data-ttu-id="5f975-134">Las métricas de los diferentes modelos entrenados se pueden acceder a través de la propiedad `Metrics` del objeto [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) individual.</span><span class="sxs-lookup"><span data-stu-id="5f975-134">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="5f975-135">En este caso, la [métrica de R cuadrado](https://en.wikipedia.org/wiki/Coefficient_of_determination) se accede y almacena en la variable `rSquared`.</span><span class="sxs-lookup"><span data-stu-id="5f975-135">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span>

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="5f975-136">Si examina el contenido de la variable `rSquared`, la salida debe tener cinco valores comprendidos entre 0 y 1, donde el valor más cercano a 1 es mejor.</span><span class="sxs-lookup"><span data-stu-id="5f975-136">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="5f975-137">Mediante métricas como R cuadrado, seleccione los modelos de mejor a peor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5f975-137">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="5f975-138">A continuación, seleccione el mejor modelo con el que realizará predicciones u operaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="5f975-138">Then, select the top model to make predictions or perform additional operations with.</span></span>

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
