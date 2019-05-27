---
title: Cómo usar la API de ML automatizada de ML.NET
description: La API de ML automatizada de ML.NET automatiza el proceso de compilación de modelos y genera un modelo listo para la implementación. Descubra las opciones que puede usar para configurar tareas de aprendizaje automático.
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 23410a11f94ab6052ab64bd8968f0ed127441898
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065618"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="cb305-104">Cómo usar la API de aprendizaje automático automatizada de ML.NET</span><span class="sxs-lookup"><span data-stu-id="cb305-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="cb305-105">El aprendizaje automático automatizado (AutoML) automatiza el proceso de aplicar aprendizaje automático en los datos.</span><span class="sxs-lookup"><span data-stu-id="cb305-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="cb305-106">Dado un conjunto de datos, puede ejecutar un **experimento** de AutoML para iterar en diferentes caracterizaciones de datos, algoritmos de aprendizaje automático e hiperparámetros para seleccionar el mejor modelo.</span><span class="sxs-lookup"><span data-stu-id="cb305-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="cb305-107">Este tema hace referencia a la API de aprendizaje automático de ML.NET, que actualmente se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="cb305-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="cb305-108">El material puede estar sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="cb305-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="cb305-109">Cargar los datos</span><span class="sxs-lookup"><span data-stu-id="cb305-109">Load data</span></span>

<span data-ttu-id="cb305-110">El aprendizaje automático automatizado admite la carga de un conjunto de datos en un [IDataView](https://docs.microsoft.com/dotnet/api/microsoft.ml.idataview?view=ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="cb305-110">Automated machine learning supports loading a dataset into an [IDataView](https://docs.microsoft.com/dotnet/api/microsoft.ml.idataview?view=ml-dotnet).</span></span> <span data-ttu-id="cb305-111">Los datos pueden estar en forma de archivos de valores separados por tabulaciones (TSV) y archivos de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="cb305-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="cb305-112">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb305-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="cb305-113">Seleccionar el tipo de tarea de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="cb305-113">Select the machine learning task type</span></span>
<span data-ttu-id="cb305-114">Antes de crear un experimento, determine el tipo de problema de aprendizaje automático que desea resolver.</span><span class="sxs-lookup"><span data-stu-id="cb305-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="cb305-115">El aprendizaje automático automatizado admite las siguientes tareas de ML:</span><span class="sxs-lookup"><span data-stu-id="cb305-115">Automated machine learning supports the following ML tasks:</span></span>
* <span data-ttu-id="cb305-116">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="cb305-116">Binary Classification</span></span>
* <span data-ttu-id="cb305-117">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="cb305-117">Multiclass Classification</span></span>
* <span data-ttu-id="cb305-118">Regresión</span><span class="sxs-lookup"><span data-stu-id="cb305-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="cb305-119">Crear una configuración de experimento</span><span class="sxs-lookup"><span data-stu-id="cb305-119">Create experiment settings</span></span>

<span data-ttu-id="cb305-120">Cree una configuración de experimento para el tipo de tarea de ML determinada:</span><span class="sxs-lookup"><span data-stu-id="cb305-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="cb305-121">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="cb305-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="cb305-122">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="cb305-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="cb305-123">Regresión</span><span class="sxs-lookup"><span data-stu-id="cb305-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="cb305-124">Establecer la configuración de experimento</span><span class="sxs-lookup"><span data-stu-id="cb305-124">Configure experiment settings</span></span>

<span data-ttu-id="cb305-125">Los experimentos son altamente configurables.</span><span class="sxs-lookup"><span data-stu-id="cb305-125">Experiments are highly configurable.</span></span> <span data-ttu-id="cb305-126">Consulte los [documentos de la API de AutoML](https://docs.microsoft.com/dotnet/api/microsoft.ml.auto?view=ml-dotnet) para obtener una lista completa de las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="cb305-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/microsoft.ml.auto?view=ml-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="cb305-127">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="cb305-127">Some examples include:</span></span>

1. <span data-ttu-id="cb305-128">Especifique el tiempo máximo que se puede ejecutar el experimento.</span><span class="sxs-lookup"><span data-stu-id="cb305-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="cb305-129">Use un token de cancelación para cancelar el experimento antes de que se programe para finalizar.</span><span class="sxs-lookup"><span data-stu-id="cb305-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="cb305-130">Especifique una métrica de optimización diferente.</span><span class="sxs-lookup"><span data-stu-id="cb305-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="cb305-131">La configuración `CacheDirectory` es un puntero a un directorio donde se guardarán todos los modelos entrenados durante la tarea de AutoML.</span><span class="sxs-lookup"><span data-stu-id="cb305-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="cb305-132">Si `CacheDirectory` se establece en null, los modelos se mantendrán en memoria en lugar de que se escriban en el disco.</span><span class="sxs-lookup"><span data-stu-id="cb305-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>
 
    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="cb305-133">Indique a ML automatizado que no use ciertos instructores.</span><span class="sxs-lookup"><span data-stu-id="cb305-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="cb305-134">Cada tarea explora una lista predeterminada de instructores para optimizar.</span><span class="sxs-lookup"><span data-stu-id="cb305-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="cb305-135">Esta lista se puede modificar para cada experimento.</span><span class="sxs-lookup"><span data-stu-id="cb305-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="cb305-136">Por ejemplo, los instructores que se ejecutan lentamente en el conjunto de datos pueden eliminarse de la lista.</span><span class="sxs-lookup"><span data-stu-id="cb305-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="cb305-137">Para optimizar `experimentSettings.Trainers.Clear()` en una llamada específica de instructor, agregue el instructor que desea usar.</span><span class="sxs-lookup"><span data-stu-id="cb305-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="cb305-138">La lista de instructores admitidos por la tarea de ML se encuentra en el siguiente vínculo correspondiente:</span><span class="sxs-lookup"><span data-stu-id="cb305-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>
* [<span data-ttu-id="cb305-139">Algoritmos de clasificación binaria admitidos</span><span class="sxs-lookup"><span data-stu-id="cb305-139">Supported Binary Classification Algorithms</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.binaryclassificationtrainer?view=automl-dotnet)
* [<span data-ttu-id="cb305-140">Algoritmos de clasificación multiclase admitidos</span><span class="sxs-lookup"><span data-stu-id="cb305-140">Supported Multiclass Classification Algorithms</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.multiclassclassificationtrainer?view=automl-dotnet)
* [<span data-ttu-id="cb305-141">Algoritmos de regresión admitidos</span><span class="sxs-lookup"><span data-stu-id="cb305-141">Supported Regression Algorithms</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.regressiontrainer?view=automl-dotnet)

## <a name="optimizing-metric"></a><span data-ttu-id="cb305-142">Métrica de optimización</span><span class="sxs-lookup"><span data-stu-id="cb305-142">Optimizing metric</span></span>

<span data-ttu-id="cb305-143">La métrica de optimización, tal como se muestra en el ejemplo anterior, determina la métrica que se optimizará durante el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="cb305-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="cb305-144">La métrica de optimización que puede seleccionar viene determinada por el tipo de tarea que elija.</span><span class="sxs-lookup"><span data-stu-id="cb305-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="cb305-145">Esta es una lista de las métricas disponibles.</span><span class="sxs-lookup"><span data-stu-id="cb305-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="cb305-146">Clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="cb305-146">Binary Classification</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.binaryclassificationmetric?view=automl-dotnet) | [<span data-ttu-id="cb305-147">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="cb305-147">Multiclass Classification</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.multiclassclassificationmetric?view=automl-dotnet) | [<span data-ttu-id="cb305-148">Regresión</span><span class="sxs-lookup"><span data-stu-id="cb305-148">Regression</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.regressionmetric?view=automl-dotnet)
|-- |-- |--
|<span data-ttu-id="cb305-149">Exactitud</span><span class="sxs-lookup"><span data-stu-id="cb305-149">Accuracy</span></span>| <span data-ttu-id="cb305-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="cb305-150">LogLoss</span></span> | <span data-ttu-id="cb305-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="cb305-151">RSquared</span></span>
|<span data-ttu-id="cb305-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="cb305-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="cb305-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="cb305-153">LogLossReduction</span></span> | <span data-ttu-id="cb305-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="cb305-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="cb305-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="cb305-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="cb305-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="cb305-156">MacroAccuracy</span></span> | <span data-ttu-id="cb305-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="cb305-157">MeanSquaredError</span></span>
|<span data-ttu-id="cb305-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="cb305-158">F1Score</span></span> | <span data-ttu-id="cb305-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="cb305-159">MicroAccuracy</span></span> | <span data-ttu-id="cb305-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="cb305-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="cb305-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="cb305-161">NegativePrecision</span></span> | <span data-ttu-id="cb305-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="cb305-162">TopKAccuracy</span></span>
|<span data-ttu-id="cb305-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="cb305-163">NegativeRecall</span></span> |
|<span data-ttu-id="cb305-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="cb305-164">PositivePrecision</span></span>
|<span data-ttu-id="cb305-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="cb305-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="cb305-166">Caracterización y procesamiento previo de datos</span><span class="sxs-lookup"><span data-stu-id="cb305-166">Data pre-processing and featurization</span></span>

<span data-ttu-id="cb305-167">El procesamiento previo de datos se produce de forma predeterminada y los pasos siguientes se realizan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="cb305-167">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="cb305-168">Quitar características sin información útil</span><span class="sxs-lookup"><span data-stu-id="cb305-168">Drop features with no useful information</span></span>

    <span data-ttu-id="cb305-169">Quitar características sin información útil de los conjuntos de validación y entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="cb305-169">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="cb305-170">Estas incluyen características con todos los valores ausentes, el mismo valor en todas las filas o con una cardinalidad muy alta (p. ej., hashes, identificadores o GUID).</span><span class="sxs-lookup"><span data-stu-id="cb305-170">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="cb305-171">Imputación e indicación del valor ausente</span><span class="sxs-lookup"><span data-stu-id="cb305-171">Missing value indication and imputation</span></span>

    <span data-ttu-id="cb305-172">Rellene las celdas del valor ausente con el valor predeterminado para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="cb305-172">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="cb305-173">Anexe las características del indicador con el mismo número de ranuras que la columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="cb305-173">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="cb305-174">El valor de las características del indicador anexado es `1` si falta el valor de la columna de entrada y, en caso contrario, `0`.</span><span class="sxs-lookup"><span data-stu-id="cb305-174">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="cb305-175">Generar características adicionales</span><span class="sxs-lookup"><span data-stu-id="cb305-175">Generate additional features</span></span>
    
    <span data-ttu-id="cb305-176">Para las características de texto: Características de bolsa de palabras mediante unigramas y gramas de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="cb305-176">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>
    
    <span data-ttu-id="cb305-177">Para características categóricas: La codificación "One-hot" para características de baja cardinalidad y la codificación de hash "One-hot" para características categóricas de alta cardinalidad.</span><span class="sxs-lookup"><span data-stu-id="cb305-177">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="cb305-178">Transformaciones y codificaciones</span><span class="sxs-lookup"><span data-stu-id="cb305-178">Transformations and encodings</span></span>

    <span data-ttu-id="cb305-179">Características de texto con muy pocos valores únicos que se transforman en características categóricas.</span><span class="sxs-lookup"><span data-stu-id="cb305-179">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="cb305-180">En función de la cardinalidad de las características categóricas, realice una codificación "One-hot" o una codificación de hash "One-hot".</span><span class="sxs-lookup"><span data-stu-id="cb305-180">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="cb305-181">Criterios de salida</span><span class="sxs-lookup"><span data-stu-id="cb305-181">Exit criteria</span></span>

<span data-ttu-id="cb305-182">Defina los criterios para completar la tarea:</span><span class="sxs-lookup"><span data-stu-id="cb305-182">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="cb305-183">Salida después de un período de tiempo: mediante `MaxExperimentTimeInSeconds` en la configuración del experimento puede definir cuántos segundos se debe seguir ejecutando una tarea.</span><span class="sxs-lookup"><span data-stu-id="cb305-183">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="cb305-184">Salida con un token de cancelación: puede usar un token de cancelación que le permita cancelar la tarea antes de que se programe para finalizar.</span><span class="sxs-lookup"><span data-stu-id="cb305-184">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="cb305-185">Crear un experimento</span><span class="sxs-lookup"><span data-stu-id="cb305-185">Create an experiment</span></span>

<span data-ttu-id="cb305-186">Una vez que haya configurado las opciones del experimento, está listo para crearlo.</span><span class="sxs-lookup"><span data-stu-id="cb305-186">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="cb305-187">Ejecutar el experimento</span><span class="sxs-lookup"><span data-stu-id="cb305-187">Run the experiment</span></span>

<span data-ttu-id="cb305-188">La ejecución del experimento desencadena el procesamiento previo de los datos, la selección del algoritmo de aprendizaje y el ajuste de los hiperparámetros.</span><span class="sxs-lookup"><span data-stu-id="cb305-188">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="cb305-189">AutoML seguirá generando combinaciones de caracterización, algoritmos de aprendizaje e hiperparámetros hasta que se alcance `MaxExperimentTimeInSeconds` o se termine el experimento.</span><span class="sxs-lookup"><span data-stu-id="cb305-189">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="cb305-190">Explore otras sobrecargas para `Execute()` si desea pasar datos de validación, información de columna que indique el propósito de la columna o caracterizaciones previas.</span><span class="sxs-lookup"><span data-stu-id="cb305-190">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="cb305-191">Modelo de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="cb305-191">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="cb305-192">Conjunto de datos de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="cb305-192">Training dataset</span></span>

<span data-ttu-id="cb305-193">AutoML proporciona un método de ejecución de experimentos sobrecargados que permite proporcionar datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="cb305-193">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="cb305-194">Internamente, ML automatizado divide los datos en divisiones de validación de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="cb305-194">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);   
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="cb305-195">Conjunto de datos de validación personalizada</span><span class="sxs-lookup"><span data-stu-id="cb305-195">Custom validation dataset</span></span>

<span data-ttu-id="cb305-196">Use el conjunto de datos de validación personalizada si la división aleatoria no es aceptable, como suele ser el caso con los datos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="cb305-196">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="cb305-197">Puede especificar su propio conjunto de datos de validación.</span><span class="sxs-lookup"><span data-stu-id="cb305-197">You can specify your own validation dataset.</span></span> <span data-ttu-id="cb305-198">El modelo se evaluará en el conjunto de datos de validación especificado, en lugar de uno o varios conjuntos de datos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="cb305-198">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);   
```

## <a name="explore-model-metrics"></a><span data-ttu-id="cb305-199">Explorar métricas de modelo</span><span class="sxs-lookup"><span data-stu-id="cb305-199">Explore model metrics</span></span>

<span data-ttu-id="cb305-200">Después de cada iteración de un experimento de ML, se almacenan las métricas relacionadas con esa tarea.</span><span class="sxs-lookup"><span data-stu-id="cb305-200">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="cb305-201">Por ejemplo, podemos acceder a las métricas de validación de la mejor ejecución:</span><span class="sxs-lookup"><span data-stu-id="cb305-201">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="cb305-202">Las siguientes son todas las métricas disponibles por tarea de ML:</span><span class="sxs-lookup"><span data-stu-id="cb305-202">The following are all the available metrics per ML task:</span></span>
* [<span data-ttu-id="cb305-203">Métricas de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="cb305-203">Binary classification metrics</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.binaryclassificationmetric?view=automl-dotnet
)
* [<span data-ttu-id="cb305-204">Métricas de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="cb305-204">Multiclass classification metrics</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.multiclassclassificationmetric?view=automl-dotnet
)
* [<span data-ttu-id="cb305-205">Métricas de regresión</span><span class="sxs-lookup"><span data-stu-id="cb305-205">Regression metrics</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.automl.regressionmetric?view=automl-dotnet
)

## <a name="see-also"></a><span data-ttu-id="cb305-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb305-206">See also</span></span>

<span data-ttu-id="cb305-207">Para ver los ejemplos de código completos y mucho más, visite el repositorio de GitHub [machinelearning-dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="cb305-207">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
