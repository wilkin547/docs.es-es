---
title: 'Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET'
description: Obtenga más información sobre cómo usar normalizadores para preprocesar los datos de aprendizaje con el fin de usarlos en la creación, el aprendizaje y la puntuación de modelos de Machine Learning con ML.NET.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c8b959904705e996c97bdcd8b3444e754d14d046
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148839"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="fb5a8-103">Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET</span><span class="sxs-lookup"><span data-stu-id="fb5a8-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

<span data-ttu-id="fb5a8-104">ML.NET expone un número de [algoritmos paramétricos y no paramétricos](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="fb5a8-104">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="fb5a8-105">El normalizador que se elija **no** es lo importante, sino el hecho de **usar** un normalizador al entrenar modelos lineales u otros modelos paramétricos.</span><span class="sxs-lookup"><span data-stu-id="fb5a8-105">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="fb5a8-106">Incluya siempre el normalizador directamente en la canalización de aprendizaje de ML.NET, para que:</span><span class="sxs-lookup"><span data-stu-id="fb5a8-106">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="fb5a8-107">solo se entrene en los datos de aprendizaje y no en los de prueba,</span><span class="sxs-lookup"><span data-stu-id="fb5a8-107">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="fb5a8-108">se aplique correctamente a todos los datos entrantes nuevos, sin necesidad de un procesamiento previo adicional en tiempo de predicción.</span><span class="sxs-lookup"><span data-stu-id="fb5a8-108">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="fb5a8-109">A continuación tiene un fragmento de código en el que se muestra la normalización en las canalizaciones de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="fb5a8-109">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="fb5a8-110">En él se adopta el conjunto de datos Iris:</span><span class="sxs-lookup"><span data-stu-id="fb5a8-110">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features", DataKind.R4, 0, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
