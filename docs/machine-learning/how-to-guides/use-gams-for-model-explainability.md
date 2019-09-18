---
title: Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo
description: Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo en ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c58cf823007196c35da093fab7423c1e40ba1158
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855604"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a>Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo en ML.NET

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Al crear modelos de Machine Learning, a menudo no es suficiente crear simplemente predicciones. Con frecuencia, los desarrolladores del aprendizaje automático, las personas que toman decisiones y aquellas que se ven afectadas por los modelos deben comprender cómo los modelos de Machine Learning toman decisiones y las características que contribuyen a su rendimiento. Los **modelos aditivos generalizados (GAM)** se usan internamente en Microsoft para la explicación del modelo con el fin de ayudar a los desarrolladores de aprendizaje automático a crear modelos de alta capacidad que puedan interpretar fácilmente otros usuarios.

Los GAM son una clase de **modelos interpretables** que son modelos lineales donde los términos son funciones no lineales, denominadas "funciones de forma" de una sola variable. Al igual que los modelos lineales, se interpretan con facilidad, pero dado que los modelos aprenden funciones de características en lugar de una sola ponderación, pueden modelar relaciones más complejas que un modelo lineal simple. El indicador de GAM resultante tiene un término de interceptación que representa la predicción promedia con respecto al conjunto de aprendizaje, y las funciones de forma que representan la desviación de la predicción promedia. Las funciones de forma se pueden inspeccionar a ojo para ver la respuesta del modelo a valores distintos de una característica, y se visualizan como el siguiente gráfico creado al final del código de ejemplo. El instructor de GAM en ML.NET se implementa mediante árboles impulsados por gradiente superficiales (por ejemplo, troncos) para aprender funciones de forma no paramétrica, y se basa en el método descrito en [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelos inteligibles para clasificación y regresión) de Lou, Caruana y Gehrke.

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![Gráfico de función de forma de modelos aditivos generalizados](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

Para ver un ejemplo de cómo entrenar un modelo de GAM e inspeccionar e interpretar los resultados, consulte el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).
