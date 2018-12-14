---
title: Determinación de la importancia de características de modelos con importancia de característica de permutación en ML.NET
description: Descripción de la importancia de características de modelos con importancia de característica de permutación en ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 4b93e085dbb99e7f6f5a0a839b863aad1c69c7ba
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156573"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Determinación de la importancia de características de modelos con importancia de característica de permutación en ML.NET

Al crear modelos de Machine Learning, a menudo no es suficiente crear simplemente predicciones. Con frecuencia, los desarrolladores del aprendizaje automático, las personas que toman decisiones y aquellas que se ven afectadas por los modelos deben comprender cómo los modelos de Machine Learning toman decisiones y las características que contribuyen a su rendimiento. `Permutation Feature Importance` (PFI) es una herramienta de explicación de modelos que se usa internamente en Microsoft para ayudar a los desarrolladores de aprendizaje automático a comprender mejor la importancia de las características de los modelos.

PFI es una técnica para determinar la **importancia de las características globales** en un modelo de aprendizaje automático entrenado, motivado por Breiman en la [sección 10 del documento "Random Forests", sección 10 ](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). PFI mide la importancia de las características formulando la pregunta, "¿Cuál sería el efecto en el modelo si los valores de una característica estuvieran establecidos en un valor aleatorio*?". La ventaja del método PFI es que es independiente del modelo (funciona con cualquier modelo que se pueda evaluar) y puede usar cualquier conjunto de datos, no solo el conjunto de entrenamiento, para calcular la importancia de las características. Puede usar PFI como para producir importancias de característica como este gráfico:

![Gráfico de la importación de la característica de permutación](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model, data);
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Write out the feature names and their importance to the model's R-squared value
for (int i = 0; i < featureNames.Length; i++)
  Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].rSquared:G4}");
```

Para un ejemplo de uso de PFI para analizar la importancia de las características de un modelo, vea [el repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance.cs).

/ * Bien, no aleatorio exactamente, sino permutado en todo el conjunto de ejemplos.
