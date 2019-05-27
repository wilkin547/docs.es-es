---
title: Entrenamiento y evaluación de un modelo
description: Descubra cómo entrenar y evaluar modelos de aprendizaje automático en ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 3a3f1f672ed078754162dc377cf5c239d206b715
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557851"
---
# <a name="train-and-evaluate-a-model"></a><span data-ttu-id="912ac-103">Entrenamiento y evaluación de un modelo</span><span class="sxs-lookup"><span data-stu-id="912ac-103">Train and evaluate a model</span></span>

<span data-ttu-id="912ac-104">Aprenda a compilar modelos de aprendizaje automático, extraer parámetros aprendidos y medir el rendimiento con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="912ac-104">Learn how to build machine learning models, extract learned parameters and measure performance with ML.NET.</span></span> <span data-ttu-id="912ac-105">Aunque este ejemplo entrena un modelo de regresión, los conceptos se aplican en casi todos los demás algoritmos.</span><span class="sxs-lookup"><span data-stu-id="912ac-105">Although this sample trains a regression model, the concepts are applicable throughout a majority of the other algorithms.</span></span>

## <a name="split-data-for-training-and-testing"></a><span data-ttu-id="912ac-106">Dividir datos para entrenamiento y pruebas</span><span class="sxs-lookup"><span data-stu-id="912ac-106">Split data for training and testing</span></span>

<span data-ttu-id="912ac-107">El objetivo de un modelo de aprendizaje automático es identificar patrones en los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="912ac-107">The goal of a machine learning model is to identify patterns within training data.</span></span> <span data-ttu-id="912ac-108">Estos patrones se usan para realizar predicciones con datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="912ac-108">These patterns are used to make predictions using new data.</span></span>

<span data-ttu-id="912ac-109">Dado el modelo de datos siguiente:</span><span class="sxs-lookup"><span data-stu-id="912ac-109">Given the following data model:</span></span>

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

<span data-ttu-id="912ac-110">Cargue los datos en un [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="912ac-110">Load the data into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
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
```

<span data-ttu-id="912ac-111">Use el método [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) para dividir los datos en conjuntos de entrenamiento y pruebas.</span><span class="sxs-lookup"><span data-stu-id="912ac-111">Use the [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) method to split the data into train and test sets.</span></span> <span data-ttu-id="912ac-112">El resultado será un objeto [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) que contiene dos miembros de [`IDataView`](xref:Microsoft.ML.IDataView): uno para el conjunto de entrenamiento y otro para el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="912ac-112">The result will be a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object which contains two [`IDataView`](xref:Microsoft.ML.IDataView) members, one for the train set and the other for the test set.</span></span> <span data-ttu-id="912ac-113">El porcentaje de división de datos viene determinado por el parámetro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="912ac-113">The data split percentage is determined by the `testFraction` parameter.</span></span> <span data-ttu-id="912ac-114">El siguiente fragmento está reteniendo el 20 por ciento de los datos originales para el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="912ac-114">The snippet below is holding out 20 percent of the original data for the test set.</span></span>

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a><span data-ttu-id="912ac-115">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="912ac-115">Prepare the data</span></span>

<span data-ttu-id="912ac-116">Los datos deben procesarse antes de entrenar un modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="912ac-116">The data needs to be pre-processed before training a machine learning model.</span></span> <span data-ttu-id="912ac-117">Puede encontrar más información sobre la preparación de los datos en el [artículo de procedimientos de preparación de datos](prepare-data-ml-net.md), así como en la [`transforms page`](../resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="912ac-117">More information on data preparation can be found on the [data prep how-to article](prepare-data-ml-net.md) as well as the [`transforms page`](../resources/transforms.md).</span></span>

<span data-ttu-id="912ac-118">Los algoritmos de ML.NET tienen restricciones en los tipos de columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="912ac-118">ML.NET algorithms have constraints on input column types.</span></span> <span data-ttu-id="912ac-119">Además, se usan valores predeterminados para los nombres de columna de entrada y salida cuando no se especifica ningún valor.</span><span class="sxs-lookup"><span data-stu-id="912ac-119">Additionally, default values are used for input and output column names when no values are specified.</span></span>

### <a name="working-with-expected-column-types"></a><span data-ttu-id="912ac-120">Trabajar con tipos de columna esperados</span><span class="sxs-lookup"><span data-stu-id="912ac-120">Working with expected column types</span></span>

<span data-ttu-id="912ac-121">Los algoritmos de aprendizaje automático en ML.NET esperan un vector de punto flotante de tamaño conocido como entrada.</span><span class="sxs-lookup"><span data-stu-id="912ac-121">The machine learning algorithms in ML.NET expect a float vector of known size as input.</span></span> <span data-ttu-id="912ac-122">Aplique el atributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) al modelo de datos cuando todos los datos ya están en formato numérico y están pensados para procesarse juntos (es decir, píxeles de imagen).</span><span class="sxs-lookup"><span data-stu-id="912ac-122">Apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to your data model when all of the data is already in numerical format and is intended to be processed together (i.e. image pixels).</span></span> 

<span data-ttu-id="912ac-123">Si todos los datos no son numéricos y desea aplicar diferentes transformaciones de datos en cada una de las columnas individualmente, utilice el método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) después de que todas las columnas se hayan procesado para combinar todas las columnas individuales en un vector de característica única que se genera en una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="912ac-123">If data is not all numerical and you want to apply different data transformations on each of the columns individually, use the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method after all of the columns have been processed to combine all of the individual columns into a single feature vector that is output to a new column.</span></span> 

<span data-ttu-id="912ac-124">El siguiente fragmento de código combina las columnas `Size` y `HistoricalPrices` en un vector de característica única cuya salida es una nueva columna denominada `Features`.</span><span class="sxs-lookup"><span data-stu-id="912ac-124">The following snippet combines the `Size` and `HistoricalPrices` columns into a single feature vector that is output to a new column called `Features`.</span></span> <span data-ttu-id="912ac-125">Dado que hay una diferencia en escalas, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) se aplica a la columna `Features` para normalizar los datos.</span><span class="sxs-lookup"><span data-stu-id="912ac-125">Because there is a difference in scales, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to normalize the data.</span></span>

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply tranforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a><span data-ttu-id="912ac-126">Trabajar con nombres de columna predeterminados</span><span class="sxs-lookup"><span data-stu-id="912ac-126">Working with default column names</span></span>

<span data-ttu-id="912ac-127">Los algoritmos de ML.NET utilizan nombres de columna predeterminados cuando no se especifica ninguno.</span><span class="sxs-lookup"><span data-stu-id="912ac-127">ML.NET algorithms use default column names when none are specified.</span></span> <span data-ttu-id="912ac-128">Todos los instructores tienen un parámetro denominado `featureColumnName` para las entradas del algoritmo y, si corresponde, también tienen un parámetro para el valor esperado `labelColumnName`.</span><span class="sxs-lookup"><span data-stu-id="912ac-128">All trainers have a parameter called `featureColumnName` for the inputs of the algorithm and when applicable they also have a parameter for the expected value called `labelColumnName`.</span></span> <span data-ttu-id="912ac-129">De forma predeterminada, estos valores son `Features` y `Label`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="912ac-129">By default those values are `Features` and `Label` respectively.</span></span> 

<span data-ttu-id="912ac-130">Mediante el uso del método [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) durante el preprocesamiento para crear una nueva columna denominada `Features`, no es necesario especificar el nombre de columna de característica en los parámetros del algoritmo porque ya existe en el `IDataView` procesado previamente.</span><span class="sxs-lookup"><span data-stu-id="912ac-130">By using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method during pre-processing to create a new column called `Features`, there is no need to specify the feature column name in the parameters of the algorithm since it already exists in the pre-processed `IDataView`.</span></span> <span data-ttu-id="912ac-131">La columna de etiqueta es `CurrentPrice`, pero dado que el atributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) se usa en el modelo de datos, ML.NET cambia el nombre de la columna `CurrentPrice` a `Label`, lo cual elimina la necesidad de proporcionar el parámetro `labelColumnName` para el estimador de algoritmo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="912ac-131">The label column is `CurrentPrice`, but since the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute is used in the data model, ML.NET renames the `CurrentPrice` column to `Label` which removes the need to provide the `labelColumnName` parameter to the machine learning algorithm estimator.</span></span> 

<span data-ttu-id="912ac-132">Si no desea usar los nombres de columna predeterminada, pase los nombres de las columnas de característica y etiqueta como parámetros al definir el estimador de algoritmo de aprendizaje automático, tal como se demuestra en el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="912ac-132">If you don't want to use the default column names, pass in the names of the feature and label columns as parameters when defining the machine learning algorithm estimator as demonstrated by the subsequent snippet:</span></span>

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a><span data-ttu-id="912ac-133">Entrenar el modelo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="912ac-133">Train the machine learning model</span></span>

<span data-ttu-id="912ac-134">Una vez que se hayan procesado previamente los datos, utilice el método [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) para entrenar el modelo de aprendizaje automático con el algoritmo de regresión [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer).</span><span class="sxs-lookup"><span data-stu-id="912ac-134">Once the data is pre-processed, use the [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) method to train the machine learning model with the [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) regression algorithm.</span></span>

```csharp
// Define StochasticDualCoodrinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a><span data-ttu-id="912ac-135">Extraer parámetros del modelo</span><span class="sxs-lookup"><span data-stu-id="912ac-135">Extract model parameters</span></span>

<span data-ttu-id="912ac-136">Una vez entrenado el modelo, extraiga el [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) entrenado para su inspección o para volver a entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="912ac-136">After the model has been trained, extract the learned [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) for inspection or re-training.</span></span> <span data-ttu-id="912ac-137">Los parámetros [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) proporcionan los coeficientes aprendidos y de sesgo, o los pesos del modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="912ac-137">The [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) provide the bias and learned coefficients or weights of the trained model.</span></span> 

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> <span data-ttu-id="912ac-138">Otros modelos disponen de parámetros que son específicos para sus tareas.</span><span class="sxs-lookup"><span data-stu-id="912ac-138">Other models have parameters that are specific to their tasks.</span></span> <span data-ttu-id="912ac-139">Por ejemplo, el [algoritmo K-Means](xref:Microsoft.ML.Trainers.KMeansTrainer) coloca datos en clúster en función de centroides y [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contiene una propiedad que almacena estos centroides aprendidos.</span><span class="sxs-lookup"><span data-stu-id="912ac-139">For example, the [K-Means algorithm](xref:Microsoft.ML.Trainers.KMeansTrainer) puts data into cluster based on centroids and the [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contains a property that stores these learned centroids.</span></span> <span data-ttu-id="912ac-140">Para obtener más información, visite la [`Microsoft.ML.Trainers` documentación de la API](xref:Microsoft.ML.Trainers) y busque las clases que contienen `ModelParameters` en su nombre.</span><span class="sxs-lookup"><span data-stu-id="912ac-140">To learn more, visit the [`Microsoft.ML.Trainers` API Documentation](xref:Microsoft.ML.Trainers) and look for classes that contain `ModelParameters` in their name.</span></span> 

## <a name="evaluate-model-quality"></a><span data-ttu-id="912ac-141">Evaluar la calidad del modelo</span><span class="sxs-lookup"><span data-stu-id="912ac-141">Evaluate model quality</span></span>

<span data-ttu-id="912ac-142">Para ayudar a elegir el mejor modelo de rendimiento, es esencial evaluar su rendimiento en datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="912ac-142">To help choose the best performing model, it is essential to evaluate its performance on test data.</span></span> <span data-ttu-id="912ac-143">Use el método [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) para medir diversas métricas para el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="912ac-143">Use the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method, to measure various metrics for the trained model.</span></span>

> [!NOTE]
> <span data-ttu-id="912ac-144">El método `Evaluate` genera diferentes métricas en función de la tarea de aprendizaje automático que se realizó.</span><span class="sxs-lookup"><span data-stu-id="912ac-144">The `Evaluate` method produces different metrics depending on which machine learning task was was performed.</span></span> <span data-ttu-id="912ac-145">Para obtener más información, visite la [`Microsoft.ML.Data` documentación de la API](xref:Microsoft.ML.Data) y busque las clases que contienen `Metrics` en su nombre.</span><span class="sxs-lookup"><span data-stu-id="912ac-145">For more details, visit the [`Microsoft.ML.Data` API Documentation](xref:Microsoft.ML.Data) and look for classes that contain `Metrics` in their name.</span></span> 

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

<span data-ttu-id="912ac-146">En el ejemplo de código anterior:</span><span class="sxs-lookup"><span data-stu-id="912ac-146">In the previous code sample:</span></span>  
1. <span data-ttu-id="912ac-147">El conjunto de datos de prueba está procesado previamente mediante transformaciones de preparación de datos definidas con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="912ac-147">Test data set is pre-processed using the data preparation transforms previously defined.</span></span> 
2. <span data-ttu-id="912ac-148">El modelo de aprendizaje automático entrenado se utiliza para realizar predicciones sobre los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="912ac-148">The trained machine learning model is used to make predictions on the test data.</span></span>
3. <span data-ttu-id="912ac-149">En el método `Evaluate`, los valores de la columna `CurrentPrice` del conjunto de datos de prueba se comparan con la columna `Score` de las predicciones recientemente generadas para calcular las métricas del modelo de regresión, una de las cuales, R cuadrado, se almacena en la variable `rSquared`.</span><span class="sxs-lookup"><span data-stu-id="912ac-149">In the `Evaluate` method, the values in the `CurrentPrice` column of the test data set are compared against the `Score` column of the newly output predictions to calculate the metrics for the regression model, one of which, R-Squared is stored in the `rSquared` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="912ac-150">En este pequeño ejemplo, el valor de R cuadrado es un número que no está comprendido entre 0 y 1, debido al tamaño limitado de los datos.</span><span class="sxs-lookup"><span data-stu-id="912ac-150">In this small example, the R-Squared is a number not in the range of 0-1 because of the limited size of the data.</span></span> <span data-ttu-id="912ac-151">En un escenario real, debería ver un valor comprendido entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="912ac-151">In a real-world scenario, you should expect to see a value between 0 and 1.</span></span>
