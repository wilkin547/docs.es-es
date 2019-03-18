---
title: Inspección de los valores de datos intermedios durante el procesamiento de canalizaciones de ML.NET
description: Obtenga más información sobre cómo inspeccionar los valores reales de los datos intermedios durante el procesamiento de canalizaciones de aprendizaje de automático de ML.NET.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 362cb9351c3cb77b6aa67d59154854e882869ad9
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "57843421"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="85a8e-103">Inspección de los valores de datos intermedios durante el procesamiento de canalizaciones de ML.NET</span><span class="sxs-lookup"><span data-stu-id="85a8e-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

> [!NOTE]
> <span data-ttu-id="85a8e-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="85a8e-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="85a8e-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="85a8e-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="85a8e-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="85a8e-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="85a8e-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="85a8e-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="85a8e-108">Durante el experimento, le interesará observar y validar los resultados del procesamiento de datos en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="85a8e-108">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="85a8e-109">No se trata de una tarea fácil, ya que las operaciones de ML.NET son diferidas y se construyen objetos que son "promesas" de datos.</span><span class="sxs-lookup"><span data-stu-id="85a8e-109">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="85a8e-110">El método de extensión `GetColumn<T>` permite inspeccionar los datos intermedios.</span><span class="sxs-lookup"><span data-stu-id="85a8e-110">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="85a8e-111">Devuelve el contenido de una columna de datos como un elemento `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="85a8e-111">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="85a8e-112">En el ejemplo siguiente se muestra cómo usar el método de extensión `GetColumn<T>`:</span><span class="sxs-lookup"><span data-stu-id="85a8e-112">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="85a8e-113">[Archivo de ejemplo](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="85a8e-113">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>

<!-- markdownlint-disable MD010 -->
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="85a8e-114">La clase se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="85a8e-114">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
