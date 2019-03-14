---
title: 'Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET'
description: Obtenga más información sobre cómo usar normalizadores para preprocesar los datos de aprendizaje con el fin de usarlos en la creación, el aprendizaje y la puntuación de modelos de Machine Learning con ML.NET.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676608"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="ac3cf-103">Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET</span><span class="sxs-lookup"><span data-stu-id="ac3cf-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ac3cf-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="ac3cf-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ac3cf-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ac3cf-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ac3cf-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="ac3cf-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="ac3cf-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="ac3cf-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="ac3cf-108">ML.NET expone un número de [algoritmos paramétricos y no paramétricos](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="ac3cf-108">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="ac3cf-109">El normalizador que se elija **no** es lo importante, sino el hecho de **usar** un normalizador al entrenar modelos lineales u otros modelos paramétricos.</span><span class="sxs-lookup"><span data-stu-id="ac3cf-109">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="ac3cf-110">Incluya siempre el normalizador directamente en la canalización de aprendizaje de ML.NET, para que:</span><span class="sxs-lookup"><span data-stu-id="ac3cf-110">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="ac3cf-111">solo se entrene en los datos de aprendizaje y no en los de prueba,</span><span class="sxs-lookup"><span data-stu-id="ac3cf-111">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="ac3cf-112">se aplique correctamente a todos los datos entrantes nuevos, sin necesidad de un procesamiento previo adicional en tiempo de predicción.</span><span class="sxs-lookup"><span data-stu-id="ac3cf-112">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="ac3cf-113">A continuación tiene un fragmento de código en el que se muestra la normalización en las canalizaciones de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ac3cf-113">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="ac3cf-114">En él se adopta el conjunto de datos Iris:</span><span class="sxs-lookup"><span data-stu-id="ac3cf-114">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
