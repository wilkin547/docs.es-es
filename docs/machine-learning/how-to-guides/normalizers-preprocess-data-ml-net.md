---
title: 'Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET'
description: Obtenga más información sobre cómo usar normalizadores para preprocesar los datos de aprendizaje con el fin de usarlos en la creación, el aprendizaje y la puntuación de modelos de Machine Learning con ML.NET.
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4311307f5410a96bb4a30fcedd88bc43afd25c12
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738583"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Preprocesamiento de datos de aprendizaje con normalizadores para su uso en el procesamiento de datos: ML.NET

ML.NET expone un número de [algoritmos paramétricos y no paramétricos](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

El normalizador que se elija **no** es lo importante, sino el hecho de **usar** un normalizador al entrenar modelos lineales u otros modelos paramétricos.

Incluya siempre el normalizador directamente en la canalización de aprendizaje de ML.NET, para que:

- solo se entrene en los datos de aprendizaje y no en los de prueba,
- se aplique correctamente a todos los datos entrantes nuevos, sin necesidad de un procesamiento previo adicional en tiempo de predicción.

A continuación tiene un fragmento de código en el que se muestra la normalización en las canalizaciones de aprendizaje. En él se adopta el conjunto de datos Iris:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
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
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
