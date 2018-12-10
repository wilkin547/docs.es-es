---
title: 'Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET'
description: Descubra cómo usar ML.NET para cargar datos de entrenamiento que no sean archivos para el entrenamiento de modelos de Machine Learning como parte de la canalización de predicción.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 971c5c62acc9dd7bf29aa11ce898c2b76822c3d7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125407"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="5f898-103">Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET</span><span class="sxs-lookup"><span data-stu-id="5f898-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

<span data-ttu-id="5f898-104">El caso de uso usado normalmente como ejemplo para ML.NET es el uso de `TextLoader` para leer los datos de entrenamiento de un archivo.</span><span class="sxs-lookup"><span data-stu-id="5f898-104">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="5f898-105">Pero en escenarios de entrenamiento en tiempo real, los datos pueden estar en otros lugares, como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f898-105">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="5f898-106">tablas SQL.</span><span class="sxs-lookup"><span data-stu-id="5f898-106">in SQL tables</span></span>
* <span data-ttu-id="5f898-107">extraídos de archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="5f898-107">extracted from log files</span></span>
* <span data-ttu-id="5f898-108">generados sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="5f898-108">generated on the fly</span></span>

<span data-ttu-id="5f898-109">Use la [comprensión de esquema](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) para llevar una función `IEnumerable` de C# existente a ML.NET como `DataView`.</span><span class="sxs-lookup"><span data-stu-id="5f898-109">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="5f898-110">En este ejemplo, creará un modelo de predicción de cancelación de clientes y extraerá las siguientes características de su sistema de producción:</span><span class="sxs-lookup"><span data-stu-id="5f898-110">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="5f898-111">Id. de cliente (ignorado por el modelo).</span><span class="sxs-lookup"><span data-stu-id="5f898-111">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="5f898-112">Si el cliente ha cancelado (la "etiqueta" de destino).</span><span class="sxs-lookup"><span data-stu-id="5f898-112">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="5f898-113">"Categoría demográfica" (una cadena, como "joven adulto" o similares).</span><span class="sxs-lookup"><span data-stu-id="5f898-113">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="5f898-114">Número de visitas de los últimos 5 días.</span><span class="sxs-lookup"><span data-stu-id="5f898-114">The number of visits from the last 5 days.</span></span>

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

<span data-ttu-id="5f898-115">Cargue estos datos en `DataView` y entrene el modelo con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5f898-115">Load this data into the `DataView` and train the model, using the following code:</span></span>

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
var trainData = mlContext.CreateStreamingDataView(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
