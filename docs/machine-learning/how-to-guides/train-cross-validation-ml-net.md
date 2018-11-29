---
title: 'Entrenamiento de un modelo de Machine Learning con validación cruzada: ML.NET'
description: Descubra cómo entrenar un modelo de Machine Learning mediante la validación cruzada con ML.NET para tener un mayor nivel de precisión de las predicciones del modelo.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 41b99415d736b6583a8d43434c031e677e6f3ac8
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297582"
---
# <a name="train-a-machine-learning-model-using-cross-validation---mlnet"></a>Entrenamiento de un modelo de Machine Learning con validación cruzada: ML.NET

La [validación cruzada](https://en.wikipedia.org/wiki/Cross-validation_(statistics)) es una técnica útil para las aplicaciones de ML. Ayuda a calcular la varianza de la calidad del modelo de una ejecución a otra y también elimina la necesidad de extraer un conjunto de pruebas independientes para la evaluación.

ML.NET aplica correctamente las características de forma automática (siempre y cuando todo el preprocesamiento resida en una canalización de aprendizaje) y, después, se usa el concepto de "columna de estratificación" para asegurarse de que los ejemplos relacionados no se separen.

A continuación tiene un ejemplo de entrenamiento en un conjunto de datos Iris mediante una división de pruebas de aprendizaje 90/10 aleatoria y una validación cruzada de cinco subconjuntos:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // We read the first 11 values as a single float vector.
        new TextLoader.Column("SepalLength", DataKind.R4, 0),
        new TextLoader.Column("SepalWidth", DataKind.R4, 1),
        new TextLoader.Column("PetalLength", DataKind.R4, 2),
        new TextLoader.Column("PetalWidth", DataKind.R4, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    Separator = ","
});

// Read the data.
var data = reader.Read(dataPath);

// Build the training pipeline.
var dynamicPipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Categorical.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent());

// Split the data 90:10 into train and test sets, train and evaluate.
var (trainData, testData) = mlContext.MulticlassClassification.TrainTestSplit(data, testFraction: 0.1);

// Train the model.
var model = dynamicPipeline.Fit(trainData);
// Compute quality metrics on the test set.
var metrics = mlContext.MulticlassClassification.Evaluate(model.Transform(testData));
Console.WriteLine(metrics.AccuracyMicro);

// Now run the 5-fold cross-validation experiment, using the same pipeline.
var cvResults = mlContext.MulticlassClassification.CrossValidate(data, dynamicPipeline, numFolds: 5);

// The results object is an array of 5 elements. For each of the 5 folds, we have metrics, model and scored test data.
// Let's compute the average micro-accuracy.
var microAccuracies = cvResults.Select(r => r.metrics.AccuracyMicro);
Console.WriteLine(microAccuracies.Average());
```
