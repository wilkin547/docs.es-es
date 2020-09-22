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
# <a name="save-and-load-trained-models"></a>Guardar y cargar modelos entrenados

Obtenga información sobre cómo guardar y cargar modelos entrenados en la aplicación.

En todo el proceso de compilación de modelos, un modelo se encuentra en la memoria y es accesible a lo largo del ciclo de vida de la aplicación. Sin embargo, una vez que la aplicación deja de ejecutarse, si el modelo no se guarda en algún lugar local o remotamente, ya no es accesible. Normalmente, los modelos se utilizan en algún momento después de su entrenamiento en otras aplicaciones, ya sea por inferencia o al volver a entrenar. Por lo tanto, es importante almacenar el modelo. Guarde y cargue modelos mediante los pasos descritos en las secciones siguientes de este documento, cuando use la preparación de datos y las canalizaciones de aprendizaje del modelo, como la que se detalla a continuación. Aunque en este ejemplo se usa un modelo de regresión lineal, el mismo proceso se aplica a otros algoritmos de ML.NET.

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

Dado que la mayoría de los modelos y canalizaciones de preparación de datos se heredan del mismo conjunto de clases, las firmas del método de guardado y carga para estos componentes es el mismo. Según el caso de uso, puede combinar la canalización de preparación de datos y el modelo en un solo [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) que generaría un único [`ITransformer`](xref:Microsoft.ML.ITransformer) o los separaría creando así un [`ITransformer`](xref:Microsoft.ML.ITransformer) independiente para cada uno.

## <a name="save-a-model-locally"></a>Guardar un modelo de forma local

Al guardar un modelo, se necesitan dos cosas:

1. El [`ITransformer`](xref:Microsoft.ML.ITransformer) del modelo.
2. El [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) de la entrada esperada del [`ITransformer`](xref:Microsoft.ML.ITransformer).

Después de entrenar el modelo, use el método [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) para guardar el modelo entrenado en un archivo denominado `model.zip` con el `DataViewSchema` de los datos de entrada.

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a>Cargar un modelo almacenado localmente

Los modelos almacenados localmente se pueden usar en otros procesos o aplicaciones, como `ASP.NET Core` y `Serverless Web Applications`. Consulte los artículos de procedimientos [Uso de ML.NET en la API Web](./serve-model-web-api-ml-net.md) e [Implementación de la aplicación web sin servidor de ML.NET](./serve-model-serverless-azure-functions-ml-net.md) para obtener más información.

En una aplicación o proceso independiente, use el método [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) junto con la ruta de acceso al archivo para obtener el modelo entrenado en la aplicación.

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a>Cargar un modelo almacenado remotamente

Para cargar canalizaciones de preparación de datos y modelos almacenados en una ubicación remota de la aplicación, use [`Stream`](xref:System.IO.Stream) en lugar de una ruta de acceso al archivo en el método [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A).

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

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a>Trabajar con una preparación de datos independiente y canalizaciones de modelo

> [!NOTE]
> Trabajar con una preparación de datos independiente y canalizaciones de entrenamiento de modelos es opcional. La separación de canalizaciones facilita la inspección de parámetros de modelos aprendidos. Para las predicciones, es más fácil guardar y cargar una sola canalización que incluye la preparación de datos y las operaciones de entrenamiento del modelo.

Al trabajar con modelos y canalizaciones de preparación de datos independientes, se aplica el mismo proceso que con las canalizaciones únicas; excepto que ahora ambas canalizaciones deben guardarse y cargarse al mismo tiempo.

Dada la preparación de datos independiente y las canalizaciones de entrenamiento de modelos:

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

### <a name="save-data-preparation-pipeline-and-trained-model"></a>Guardar la canalización de preparación de datos y el modelo entrenado

Para guardar la canalización de preparación de datos y el modelo entrenado, use los siguientes comandos:

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a>Cargar la canalización de preparación de datos y el modelo entrenado

En una aplicación o proceso independiente, cargue la canalización de preparación de datos y el modelo entrenado simultáneamente de la siguiente manera:

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
