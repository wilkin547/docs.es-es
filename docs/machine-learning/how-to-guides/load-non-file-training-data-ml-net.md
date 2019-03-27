---
title: 'Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET'
description: Descubra cómo usar ML.NET para cargar datos de entrenamiento que no sean archivos para el entrenamiento de modelos de Machine Learning como parte de la canalización de predicción.
ms.date: 03/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 32de37e45b9e19669ea06d74c7f252ec885fe004
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186096"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="2b809-103">Entrenamiento de un modelo de Machine Learning con datos que no están en un archivo de texto: ML.NET</span><span class="sxs-lookup"><span data-stu-id="2b809-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="2b809-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="2b809-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2b809-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2b809-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2b809-106">En este tutorial y en el ejemplo relacionado se usa actualmente **ML.NET en su versión 0.11**.</span><span class="sxs-lookup"><span data-stu-id="2b809-106">This how-to and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="2b809-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="2b809-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="2b809-108">El caso de uso usado normalmente como ejemplo para ML.NET es el uso de `TextLoader` para leer los datos de entrenamiento de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2b809-108">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="2b809-109">Pero en escenarios de entrenamiento en tiempo real, los datos pueden estar en otros lugares, como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b809-109">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="2b809-110">tablas SQL.</span><span class="sxs-lookup"><span data-stu-id="2b809-110">in SQL tables</span></span>
* <span data-ttu-id="2b809-111">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="2b809-111">JSON/XML</span></span>
* <span data-ttu-id="2b809-112">extraídos de archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="2b809-112">extracted from log files</span></span>
* <span data-ttu-id="2b809-113">generados sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="2b809-113">generated on the fly</span></span>

<span data-ttu-id="2b809-114">Use la [comprensión de esquema](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) para llevar una función `IEnumerable` de C# existente a ML.NET como `DataView`.</span><span class="sxs-lookup"><span data-stu-id="2b809-114">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="2b809-115">En este ejemplo, creará un modelo de predicción de cancelación de clientes y extraerá las siguientes características de su sistema de producción:</span><span class="sxs-lookup"><span data-stu-id="2b809-115">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="2b809-116">Id. de cliente (ignorado por el modelo).</span><span class="sxs-lookup"><span data-stu-id="2b809-116">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="2b809-117">Si el cliente ha cancelado (la "etiqueta" de destino).</span><span class="sxs-lookup"><span data-stu-id="2b809-117">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="2b809-118">"Categoría demográfica" (una cadena, como "joven adulto" o similares).</span><span class="sxs-lookup"><span data-stu-id="2b809-118">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="2b809-119">Número de visitas de los últimos 5 días.</span><span class="sxs-lookup"><span data-stu-id="2b809-119">The number of visits from the last 5 days.</span></span>

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

<span data-ttu-id="2b809-120">Cargue estos datos en `DataView` y entrene el modelo con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2b809-120">Load this data into the `DataView` and train the model, using the following code:</span></span>

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
var trainData = mlContext.Data.LoadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
