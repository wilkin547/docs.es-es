---
title: Guardar y cargar modelos entrenados
description: Obtenga información sobre cómo guardar y cargar modelos entrenados
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 681a35956a8959e2f1cbb5a7023e0ef29b67097e
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679539"
---
# <a name="save-and-load-trained-models"></a><span data-ttu-id="be55c-103">Guardar y cargar modelos entrenados</span><span class="sxs-lookup"><span data-stu-id="be55c-103">Save and load trained models</span></span>

<span data-ttu-id="be55c-104">Obtenga información sobre cómo guardar y cargar modelos entrenados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be55c-104">Learn how to save and load trained models in your application.</span></span>

<span data-ttu-id="be55c-105">En todo el proceso de compilación de modelos, un modelo se encuentra en la memoria y es accesible a lo largo del ciclo de vida de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be55c-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="be55c-106">Sin embargo, una vez que la aplicación deja de ejecutarse, si el modelo no se guarda en algún lugar local o remotamente, ya no es accesible.</span><span class="sxs-lookup"><span data-stu-id="be55c-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="be55c-107">Normalmente, los modelos se utilizan en algún momento después de su entrenamiento en otras aplicaciones, ya sea por inferencia o al volver a entrenar.</span><span class="sxs-lookup"><span data-stu-id="be55c-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="be55c-108">Por lo tanto, es importante almacenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="be55c-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="be55c-109">Guarde y cargue modelos mediante los pasos descritos en las secciones siguientes de este documento, cuando use la preparación de datos y las canalizaciones de aprendizaje del modelo, como la que se detalla a continuación.</span><span class="sxs-lookup"><span data-stu-id="be55c-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="be55c-110">Aunque en este ejemplo se usa un modelo de regresión lineal, el mismo proceso se aplica a otros algoritmos de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="be55c-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
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
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

<span data-ttu-id="be55c-111">Dado que la mayoría de los modelos y canalizaciones de preparación de datos se heredan del mismo conjunto de clases, las firmas del método de guardado y carga para estos componentes es el mismo.</span><span class="sxs-lookup"><span data-stu-id="be55c-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="be55c-112">Según el caso de uso, puede combinar la canalización de preparación de datos y el modelo en un solo [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) que generaría un único [`ITransformer`](xref:Microsoft.ML.ITransformer) o los separaría creando así un [`ITransformer`](xref:Microsoft.ML.ITransformer) independiente para cada uno.</span><span class="sxs-lookup"><span data-stu-id="be55c-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span>

## <a name="save-a-model-locally"></a><span data-ttu-id="be55c-113">Guardar un modelo de forma local</span><span class="sxs-lookup"><span data-stu-id="be55c-113">Save a model locally</span></span>

<span data-ttu-id="be55c-114">Al guardar un modelo, se necesitan dos cosas:</span><span class="sxs-lookup"><span data-stu-id="be55c-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="be55c-115">El [`ITransformer`](xref:Microsoft.ML.ITransformer) del modelo.</span><span class="sxs-lookup"><span data-stu-id="be55c-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="be55c-116">El [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) de la entrada esperada del [`ITransformer`](xref:Microsoft.ML.ITransformer).</span><span class="sxs-lookup"><span data-stu-id="be55c-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="be55c-117">Después de entrenar el modelo, use el método [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) para guardar el modelo entrenado en un archivo denominado `model.zip` con el `DataViewSchema` de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="be55c-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span>

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="be55c-118">Cargar un modelo almacenado localmente</span><span class="sxs-lookup"><span data-stu-id="be55c-118">Load a model stored locally</span></span>

<span data-ttu-id="be55c-119">Los modelos almacenados localmente se pueden usar en otros procesos o aplicaciones, como `ASP.NET Core` y `Serverless Web Applications`.</span><span class="sxs-lookup"><span data-stu-id="be55c-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="be55c-120">Consulte los artículos de procedimientos [Uso de ML.NET en la API Web](./serve-model-web-api-ml-net.md) e [Implementación de la aplicación web sin servidor de ML.NET](./serve-model-serverless-azure-functions-ml-net.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="be55c-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span>

<span data-ttu-id="be55c-121">En una aplicación o proceso independiente, use el método [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) junto con la ruta de acceso al archivo para obtener el modelo entrenado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be55c-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="be55c-122">Cargar un modelo almacenado remotamente</span><span class="sxs-lookup"><span data-stu-id="be55c-122">Load a model stored remotely</span></span>

<span data-ttu-id="be55c-123">Para cargar canalizaciones de preparación de datos y modelos almacenados en una ubicación remota de la aplicación, use [`Stream`](xref:System.IO.Stream) en lugar de una ruta de acceso al archivo en el método [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A).</span><span class="sxs-lookup"><span data-stu-id="be55c-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) method.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="be55c-124">Trabajar con una preparación de datos independiente y canalizaciones de modelo</span><span class="sxs-lookup"><span data-stu-id="be55c-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="be55c-125">Trabajar con una preparación de datos independiente y canalizaciones de entrenamiento de modelos es opcional.</span><span class="sxs-lookup"><span data-stu-id="be55c-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="be55c-126">La separación de canalizaciones facilita la inspección de parámetros de modelos aprendidos.</span><span class="sxs-lookup"><span data-stu-id="be55c-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="be55c-127">Para las predicciones, es más fácil guardar y cargar una sola canalización que incluye la preparación de datos y las operaciones de entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="be55c-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="be55c-128">Al trabajar con modelos y canalizaciones de preparación de datos independientes, se aplica el mismo proceso que con las canalizaciones únicas; excepto que ahora ambas canalizaciones deben guardarse y cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="be55c-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="be55c-129">Dada la preparación de datos independiente y las canalizaciones de entrenamiento de modelos:</span><span class="sxs-lookup"><span data-stu-id="be55c-129">Given separate data preparation and model training pipelines:</span></span>

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="be55c-130">Guardar la canalización de preparación de datos y el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="be55c-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="be55c-131">Para guardar la canalización de preparación de datos y el modelo entrenado, use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="be55c-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="be55c-132">Cargar la canalización de preparación de datos y el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="be55c-132">Load data preparation pipeline and trained model</span></span>

<span data-ttu-id="be55c-133">En una aplicación o proceso independiente, cargue la canalización de preparación de datos y el modelo entrenado simultáneamente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be55c-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
