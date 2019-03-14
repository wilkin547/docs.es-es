---
title: 'Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET'
description: Descubra cómo usar ML.NET para cargar datos de entrenamiento que no sean archivos para el entrenamiento de modelos de Machine Learning como parte de la canalización de predicción.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678632"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

El caso de uso usado normalmente como ejemplo para ML.NET es el uso de `TextLoader` para leer los datos de entrenamiento de un archivo.
Pero en escenarios de entrenamiento en tiempo real, los datos pueden estar en otros lugares, como, por ejemplo:

* tablas SQL.
* extraídos de archivos de registro.
* generados sobre la marcha.

Use la [comprensión de esquema](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) para llevar una función `IEnumerable` de C# existente a ML.NET como `DataView`.

En este ejemplo, creará un modelo de predicción de cancelación de clientes y extraerá las siguientes características de su sistema de producción:

* Id. de cliente (ignorado por el modelo).
* Si el cliente ha cancelado (la "etiqueta" de destino).
* "Categoría demográfica" (una cadena, como "joven adulto" o similares).
* Número de visitas de los últimos 5 días.

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

Cargue estos datos en `DataView` y entrene el modelo con el siguiente código:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
