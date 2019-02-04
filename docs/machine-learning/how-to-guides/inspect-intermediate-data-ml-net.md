---
title: Inspección de los valores de datos intermedios durante el procesamiento de canalizaciones de ML.NET
description: Obtenga más información sobre cómo inspeccionar los valores reales de los datos intermedios durante el procesamiento de canalizaciones de aprendizaje de automático de ML.NET.
ms.date: 01/30/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b3a554bf7cd88219a66f91a18b9d983bb91c0f0e
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675017"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="d98a0-103">Inspección de los valores de datos intermedios durante el procesamiento de canalizaciones de ML.NET</span><span class="sxs-lookup"><span data-stu-id="d98a0-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

<span data-ttu-id="d98a0-104">Durante el experimento, le interesará observar y validar los resultados del procesamiento de datos en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="d98a0-104">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="d98a0-105">No se trata de una tarea fácil, ya que las operaciones de ML.NET son diferidas y se construyen objetos que son "promesas" de datos.</span><span class="sxs-lookup"><span data-stu-id="d98a0-105">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="d98a0-106">El método de extensión `GetColumn<T>` permite inspeccionar los datos intermedios.</span><span class="sxs-lookup"><span data-stu-id="d98a0-106">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="d98a0-107">Devuelve el contenido de una columna de datos como un elemento `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="d98a0-107">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="d98a0-108">En el ejemplo siguiente se muestra cómo usar el método de extensión `GetColumn<T>`:</span><span class="sxs-lookup"><span data-stu-id="d98a0-108">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="d98a0-109">[Archivo de ejemplo](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="d98a0-109">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

<span data-ttu-id="d98a0-110">La clase se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d98a0-110">Our class is defined as follows:</span></span>

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
