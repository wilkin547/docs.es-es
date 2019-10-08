---
title: Explicación de las predicciones del modelo mediante la importancia de características de permutación
description: Descripción de la importancia de características de modelos con importancia de característica de permutación en ML.NET
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 8090e4565a7e55aaa9cc9939e61eb728a169de8d
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736873"
---
# <a name="explain-model-predictions-using-permutation-feature-importance"></a><span data-ttu-id="b0665-103">Explicación de las predicciones del modelo mediante la importancia de características de permutación</span><span class="sxs-lookup"><span data-stu-id="b0665-103">Explain model predictions using Permutation Feature Importance</span></span>

<span data-ttu-id="b0665-104">Obtenga información sobre cómo explicar predicciones del modelo de Machine Learning de ML.NET al comprender que las características de contribución deben realizar predicciones mediante la importancia de características de permutación (PFI).</span><span class="sxs-lookup"><span data-stu-id="b0665-104">Learn how to explain ML.NET machine learning model predictions by understanding the contribution features have to predictions using Permutation Feature Importance (PFI).</span></span>

<span data-ttu-id="b0665-105">A menudo se piensa en los modelos de Machine Learning como cajas negras que toman entradas y generan salidas.</span><span class="sxs-lookup"><span data-stu-id="b0665-105">Machine learning models are often thought of as black boxes that take inputs and generate an output.</span></span> <span data-ttu-id="b0665-106">Rara vez se entienden los pasos intermedios o las interacciones entre las características que afectan a la salida.</span><span class="sxs-lookup"><span data-stu-id="b0665-106">The intermediate steps or interactions among the features that influence the output are rarely understood.</span></span> <span data-ttu-id="b0665-107">A medida que el aprendizaje automático se introduce en otros aspectos de la vida diaria como la asistencia sanitaria, es de vital importancia comprender por qué un modelo de Machine Learning toma esas decisiones.</span><span class="sxs-lookup"><span data-stu-id="b0665-107">As machine learning is introduced into more aspects of everyday life such as healthcare, it's of utmost importance to understand why a machine learning model makes the decisions it does.</span></span> <span data-ttu-id="b0665-108">Por ejemplo, si un modelo de Machine Learning realiza diagnósticos, los profesionales sanitarios necesitan una forma de buscar en los factores que se incluyeron en la realización de dicho diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b0665-108">For example, if diagnoses are made by a machine learning model, healthcare professionals need a way to look into the factors that went into making that diagnoses.</span></span> <span data-ttu-id="b0665-109">Proporcionar el diagnóstico correcto puede marcar una gran diferencia en el hecho de que un paciente tenga una recuperación rápida o no.</span><span class="sxs-lookup"><span data-stu-id="b0665-109">Providing the right diagnosis could make a great difference on whether a patient has a speedy recovery or not.</span></span> <span data-ttu-id="b0665-110">Por lo tanto, cuanto mayor sea el nivel de explicación en un modelo, mayor será la confianza que tengan los profesionales sanitarios para aceptar o rechazar las decisiones tomadas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="b0665-110">Therefore the higher the level of explainability in a model, the greater confidence healthcare professionals have to accept or reject the decisions made by the model.</span></span>

<span data-ttu-id="b0665-111">Se utilizan diversas técnicas para explicar modelos, una de los cuales es PFI.</span><span class="sxs-lookup"><span data-stu-id="b0665-111">Various techniques are used to explain models, one of which is PFI.</span></span> <span data-ttu-id="b0665-112">PFI es una técnica utilizada para explicar los modelos de clasificación y regresión que se inspira en el [artículo *Random Forests* de Breiman](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (consulte la sección 10).</span><span class="sxs-lookup"><span data-stu-id="b0665-112">PFI is a technique used to explain classification and regression models that is inspired by [Breiman's *Random Forests* paper](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (see section 10).</span></span> <span data-ttu-id="b0665-113">En un nivel alto, esto funciona de manera es revolviendo los datos de manera aleatoria en una característica a la vez para todo el conjunto de datos y calculando cuánto se reduce la métrica de rendimiento de interés.</span><span class="sxs-lookup"><span data-stu-id="b0665-113">At a high level, the way it works is by randomly shuffling data one feature at a time for the entire dataset and calculating how much the performance metric of interest decreases.</span></span> <span data-ttu-id="b0665-114">Cuanto mayor sea el cambio, más importante será esa característica.</span><span class="sxs-lookup"><span data-stu-id="b0665-114">The larger the change, the more important that feature is.</span></span> 

<span data-ttu-id="b0665-115">Además, al resaltar las características más importantes, los compiladores del modelo pueden centrarse en el uso de un subconjunto de características más significativas que potencialmente pueden reducir el ruido y el tiempo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="b0665-115">Additionally, by highlighting the most important features, model builders can focus on using a subset of more meaningful features which can potentially reduce noise and training time.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="b0665-116">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="b0665-116">Load the data</span></span>

<span data-ttu-id="b0665-117">Las características del conjunto de datos que se usa para este ejemplo están en las columnas 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="b0665-117">The features in the dataset being used for this sample are in columns 1-12.</span></span> <span data-ttu-id="b0665-118">El objetivo es predecir `Price`.</span><span class="sxs-lookup"><span data-stu-id="b0665-118">The goal is to predict `Price`.</span></span> 

| <span data-ttu-id="b0665-119">Columna</span><span class="sxs-lookup"><span data-stu-id="b0665-119">Column</span></span> | <span data-ttu-id="b0665-120">Característica</span><span class="sxs-lookup"><span data-stu-id="b0665-120">Feature</span></span> | <span data-ttu-id="b0665-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0665-121">Description</span></span> 
| --- | --- | --- |
| <span data-ttu-id="b0665-122">1</span><span class="sxs-lookup"><span data-stu-id="b0665-122">1</span></span> | <span data-ttu-id="b0665-123">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="b0665-123">CrimeRate</span></span> | <span data-ttu-id="b0665-124">Tasa de criminalidad per cápita</span><span class="sxs-lookup"><span data-stu-id="b0665-124">Per capita crime rate</span></span>
| <span data-ttu-id="b0665-125">2</span><span class="sxs-lookup"><span data-stu-id="b0665-125">2</span></span> | <span data-ttu-id="b0665-126">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="b0665-126">ResidentialZones</span></span> | <span data-ttu-id="b0665-127">Zonas residenciales en la ciudad</span><span class="sxs-lookup"><span data-stu-id="b0665-127">Residential zones in town</span></span>
| <span data-ttu-id="b0665-128">3</span><span class="sxs-lookup"><span data-stu-id="b0665-128">3</span></span> | <span data-ttu-id="b0665-129">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="b0665-129">CommercialZones</span></span> | <span data-ttu-id="b0665-130">Zonas no residenciales en la ciudad</span><span class="sxs-lookup"><span data-stu-id="b0665-130">Non-residential zones in town</span></span>
| <span data-ttu-id="b0665-131">4</span><span class="sxs-lookup"><span data-stu-id="b0665-131">4</span></span> | <span data-ttu-id="b0665-132">NearWater</span><span class="sxs-lookup"><span data-stu-id="b0665-132">NearWater</span></span> | <span data-ttu-id="b0665-133">Proximidad a un cuerpo de agua</span><span class="sxs-lookup"><span data-stu-id="b0665-133">Proximity to body of water</span></span>
| <span data-ttu-id="b0665-134">5</span><span class="sxs-lookup"><span data-stu-id="b0665-134">5</span></span> | <span data-ttu-id="b0665-135">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="b0665-135">ToxicWasteLevels</span></span> | <span data-ttu-id="b0665-136">Niveles de toxicidad (PPM)</span><span class="sxs-lookup"><span data-stu-id="b0665-136">Toxicity levels (PPM)</span></span>
| <span data-ttu-id="b0665-137">6</span><span class="sxs-lookup"><span data-stu-id="b0665-137">6</span></span> | <span data-ttu-id="b0665-138">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="b0665-138">AverageRoomNumber</span></span> | <span data-ttu-id="b0665-139">Número promedio de salas en casa</span><span class="sxs-lookup"><span data-stu-id="b0665-139">Average number of rooms in house</span></span>
| <span data-ttu-id="b0665-140">7</span><span class="sxs-lookup"><span data-stu-id="b0665-140">7</span></span> | <span data-ttu-id="b0665-141">HomeAge</span><span class="sxs-lookup"><span data-stu-id="b0665-141">HomeAge</span></span> | <span data-ttu-id="b0665-142">Antigüedad de la casa</span><span class="sxs-lookup"><span data-stu-id="b0665-142">Age of home</span></span>
| <span data-ttu-id="b0665-143">8</span><span class="sxs-lookup"><span data-stu-id="b0665-143">8</span></span> | <span data-ttu-id="b0665-144">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="b0665-144">BusinessCenterDistance</span></span> | <span data-ttu-id="b0665-145">Distancia al distrito comercial más cercano</span><span class="sxs-lookup"><span data-stu-id="b0665-145">Distance to nearest business district</span></span>
| <span data-ttu-id="b0665-146">9</span><span class="sxs-lookup"><span data-stu-id="b0665-146">9</span></span> | <span data-ttu-id="b0665-147">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="b0665-147">HighwayAccess</span></span> | <span data-ttu-id="b0665-148">Proximidad a las autopistas</span><span class="sxs-lookup"><span data-stu-id="b0665-148">Proximity to highways</span></span>
| <span data-ttu-id="b0665-149">10</span><span class="sxs-lookup"><span data-stu-id="b0665-149">10</span></span> | <span data-ttu-id="b0665-150">TaxRate</span><span class="sxs-lookup"><span data-stu-id="b0665-150">TaxRate</span></span> | <span data-ttu-id="b0665-151">Tasa de impuestos sobre la propiedad</span><span class="sxs-lookup"><span data-stu-id="b0665-151">Property tax rate</span></span>
| <span data-ttu-id="b0665-152">11</span><span class="sxs-lookup"><span data-stu-id="b0665-152">11</span></span> | <span data-ttu-id="b0665-153">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="b0665-153">StudentTeacherRatio</span></span> | <span data-ttu-id="b0665-154">Proporción de alumnos por profesores</span><span class="sxs-lookup"><span data-stu-id="b0665-154">Ratio of students to teachers</span></span>
| <span data-ttu-id="b0665-155">12</span><span class="sxs-lookup"><span data-stu-id="b0665-155">12</span></span> | <span data-ttu-id="b0665-156">PercentPopulationBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="b0665-156">PercentPopulationBelowPoverty</span></span> | <span data-ttu-id="b0665-157">Porcentaje de la población que vive por debajo de pobreza</span><span class="sxs-lookup"><span data-stu-id="b0665-157">Percent of population living below poverty</span></span>
| <span data-ttu-id="b0665-158">13</span><span class="sxs-lookup"><span data-stu-id="b0665-158">13</span></span> | <span data-ttu-id="b0665-159">Price</span><span class="sxs-lookup"><span data-stu-id="b0665-159">Price</span></span> | <span data-ttu-id="b0665-160">Precio de la vivienda</span><span class="sxs-lookup"><span data-stu-id="b0665-160">Price of the home</span></span>

<span data-ttu-id="b0665-161">A continuación, se muestra un ejemplo del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="b0665-161">A sample of the dataset is shown below:</span></span>

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

<span data-ttu-id="b0665-162">Los datos en este ejemplo se pueden modelar mediante una clase como `HousingPriceData` y se pueden cargar en [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="b0665-162">The data in this sample can be modeled by a class like `HousingPriceData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
class HousingPriceData
{
    [LoadColumn(0)]
    public float CrimeRate { get; set; }

    [LoadColumn(1)]
    public float ResidentialZones { get; set; }

    [LoadColumn(2)]
    public float CommercialZones { get; set; }

    [LoadColumn(3)]
    public float NearWater { get; set; }

    [LoadColumn(4)]
    public float ToxicWasteLevels { get; set; }

    [LoadColumn(5)]
    public float AverageRoomNumber { get; set; }

    [LoadColumn(6)]
    public float HomeAge { get; set; }

    [LoadColumn(7)]
    public float BusinessCenterDistance { get; set; }

    [LoadColumn(8)]
    public float HighwayAccess { get; set; }

    [LoadColumn(9)]
    public float TaxRate { get; set; }

    [LoadColumn(10)]
    public float StudentTeacherRatio { get; set; }

    [LoadColumn(11)]
    public float PercentPopulationBelowPoverty { get; set; }

    [LoadColumn(12)]
    [ColumnName("Label")]
    public float Price { get; set; }
}
```

## <a name="train-the-model"></a><span data-ttu-id="b0665-163">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="b0665-163">Train the model</span></span>

<span data-ttu-id="b0665-164">El ejemplo de código siguiente ilustra el proceso de entrenamiento de un modelo de regresión lineal para predecir los precios de la vivienda.</span><span class="sxs-lookup"><span data-stu-id="b0665-164">The code sample below illustrates the process of training a linear regression model to predict house prices.</span></span>

```csharp
// 1. Get the column name of input features.
string[] featureColumnNames = 
    data.Schema
        .Select(column => column.Name)
        .Where(columnName => columnName != "Label").ToArray();

// 2. Define estimator with data pre-processing steps
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", featureColumnNames)
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// 3. Create transformer using the data pre-processing estimator
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// 4. Pre-process the training data
IDataView preprocessedTrainData = dataPrepTransformer.Transform(data);

// 5. Define Stochastic Dual Coordinate Ascent machine learning estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// 6. Train machine learning model
var sdcaModel = sdcaEstimator.Fit(preprocessedTrainData);
```

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a><span data-ttu-id="b0665-165">Explicar el modelo con la importancia de características de permutación (PFI)</span><span class="sxs-lookup"><span data-stu-id="b0665-165">Explain the model with Permutation Feature Importance (PFI)</span></span>

<span data-ttu-id="b0665-166">En ML.NET, use el método [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) para la tarea correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b0665-166">In ML.NET use the [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) method for your respective task.</span></span>

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance = 
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

<span data-ttu-id="b0665-167">El resultado del uso de [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) en el conjunto de datos de entrenamiento es un [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) de objetos [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics).</span><span class="sxs-lookup"><span data-stu-id="b0665-167">The result of using [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) on the training dataset is an [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) of [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) objects.</span></span> <span data-ttu-id="b0665-168">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) proporciona estadísticas de resumen, como desviación media y estándar para diversas observaciones de [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equivalentes al número de permutaciones especificadas por el parámetro `permutationCount`.</span><span class="sxs-lookup"><span data-stu-id="b0665-168">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) provides summary statistics like mean and standard deviation for multiple observations of [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equal to the number of permutations specified by the `permutationCount` parameter.</span></span>

<span data-ttu-id="b0665-169">La importancia o, en este caso, la disminución de la media absoluta de la métrica de R cuadrado calculada con [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions), se puede ordenar de las más importante a la menos importante.</span><span class="sxs-lookup"><span data-stu-id="b0665-169">The importance, or in this case, the absolute average decrease in R-squared metric calculated by [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) can then be ordered from most important to least important.</span></span>  

```csharp
// Order features by importance
var featureImportanceMetrics =
    permutationFeatureImportance
        .Select((metric, index) => new { index, metric.RSquared })
        .OrderByDescending(myFeatures => Math.Abs(myFeatures.RSquared.Mean));

Console.WriteLine("Feature\tPFI");

foreach (var feature in featureImportanceMetrics)
{
    Console.WriteLine($"{featureColumnNames[feature.index],-20}|\t{feature.RSquared.Mean:F6}");
}
```

<span data-ttu-id="b0665-170">Imprimir los valores para cada una de las características de `featureImportanceMetrics` generaría resultados similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="b0665-170">Printing the values for each of the features in `featureImportanceMetrics` would generate output similar to that below.</span></span> <span data-ttu-id="b0665-171">Tenga en cuenta que debe esperar para ver resultados diferentes porque estos valores varían en función de los datos que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="b0665-171">Keep in mind that you should expect to see different results because these values vary based on the data that they are given.</span></span>  

| <span data-ttu-id="b0665-172">Característica</span><span class="sxs-lookup"><span data-stu-id="b0665-172">Feature</span></span> | <span data-ttu-id="b0665-173">Cambiar a R cuadrado</span><span class="sxs-lookup"><span data-stu-id="b0665-173">Change to R-Squared</span></span> |
|:--|:--:|
<span data-ttu-id="b0665-174">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="b0665-174">HighwayAccess</span></span>       |   <span data-ttu-id="b0665-175">-0,042731</span><span class="sxs-lookup"><span data-stu-id="b0665-175">-0.042731</span></span>
<span data-ttu-id="b0665-176">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="b0665-176">StudentTeacherRatio</span></span> |   <span data-ttu-id="b0665-177">-0,012730</span><span class="sxs-lookup"><span data-stu-id="b0665-177">-0.012730</span></span>
<span data-ttu-id="b0665-178">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="b0665-178">BusinessCenterDistance</span></span>| <span data-ttu-id="b0665-179">-0,010491</span><span class="sxs-lookup"><span data-stu-id="b0665-179">-0.010491</span></span>
<span data-ttu-id="b0665-180">TaxRate</span><span class="sxs-lookup"><span data-stu-id="b0665-180">TaxRate</span></span>             |   <span data-ttu-id="b0665-181">-0,008545</span><span class="sxs-lookup"><span data-stu-id="b0665-181">-0.008545</span></span>
<span data-ttu-id="b0665-182">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="b0665-182">AverageRoomNumber</span></span>   |   <span data-ttu-id="b0665-183">-0,003949</span><span class="sxs-lookup"><span data-stu-id="b0665-183">-0.003949</span></span>
<span data-ttu-id="b0665-184">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="b0665-184">CrimeRate</span></span>           |   <span data-ttu-id="b0665-185">-0,003665</span><span class="sxs-lookup"><span data-stu-id="b0665-185">-0.003665</span></span>
<span data-ttu-id="b0665-186">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="b0665-186">CommercialZones</span></span>     |   <span data-ttu-id="b0665-187">0,002749</span><span class="sxs-lookup"><span data-stu-id="b0665-187">0.002749</span></span>
<span data-ttu-id="b0665-188">HomeAge</span><span class="sxs-lookup"><span data-stu-id="b0665-188">HomeAge</span></span>             |   <span data-ttu-id="b0665-189">-0,002426</span><span class="sxs-lookup"><span data-stu-id="b0665-189">-0.002426</span></span>
<span data-ttu-id="b0665-190">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="b0665-190">ResidentialZones</span></span>    |   <span data-ttu-id="b0665-191">-0,002319</span><span class="sxs-lookup"><span data-stu-id="b0665-191">-0.002319</span></span>
<span data-ttu-id="b0665-192">NearWater</span><span class="sxs-lookup"><span data-stu-id="b0665-192">NearWater</span></span>           |   <span data-ttu-id="b0665-193">0,000203</span><span class="sxs-lookup"><span data-stu-id="b0665-193">0.000203</span></span>
<span data-ttu-id="b0665-194">PercentPopulationLivingBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="b0665-194">PercentPopulationLivingBelowPoverty</span></span>|    <span data-ttu-id="b0665-195">0,000031</span><span class="sxs-lookup"><span data-stu-id="b0665-195">0.000031</span></span>
<span data-ttu-id="b0665-196">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="b0665-196">ToxicWasteLevels</span></span>    |   <span data-ttu-id="b0665-197">-0,000019</span><span class="sxs-lookup"><span data-stu-id="b0665-197">-0.000019</span></span>

<span data-ttu-id="b0665-198">Al echar un vistazo a las cinco características más importantes de este conjunto de datos, el precio de una casa previsto por este modelo viene determinado por su proximidad a las autopistas, la proporción de alumnos por profesores en la zona, la proximidad a los principales centros de empleo, la tasa de impuestos sobre la propiedad y el número promedio de dormitorios en una casa.</span><span class="sxs-lookup"><span data-stu-id="b0665-198">Taking a look at the five most important features for this dataset, the price of a house predicted by this model is influenced by its proximity to highways, student teacher ratio of schools in the area, proximity to major employment centers, property tax rate and average number of rooms in the home.</span></span>
