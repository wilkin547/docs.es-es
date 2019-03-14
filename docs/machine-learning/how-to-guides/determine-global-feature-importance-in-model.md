---
title: Determinación de la importancia de características de modelos con importancia de característica de permutación en ML.NET
description: Descripción de la importancia de características de modelos con importancia de característica de permutación en ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675555"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="31668-103">Determinación de la importancia de características de modelos con importancia de característica de permutación en ML.NET</span><span class="sxs-lookup"><span data-stu-id="31668-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="31668-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="31668-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="31668-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="31668-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="31668-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="31668-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="31668-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="31668-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="31668-108">Al crear modelos de Machine Learning, a menudo no es suficiente crear simplemente predicciones.</span><span class="sxs-lookup"><span data-stu-id="31668-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="31668-109">Con frecuencia, los desarrolladores del aprendizaje automático, las personas que toman decisiones y aquellas que se ven afectadas por los modelos deben comprender cómo los modelos de Machine Learning toman decisiones y las características que contribuyen a su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="31668-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="31668-110">`Permutation Feature Importance` (PFI) es una herramienta de explicación de modelos que se usa internamente en Microsoft para ayudar a los desarrolladores de aprendizaje automático a comprender mejor la importancia de las características de los modelos.</span><span class="sxs-lookup"><span data-stu-id="31668-110">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="31668-111">PFI es una técnica para determinar la **importancia de las características globales** en un modelo de aprendizaje automático entrenado, motivado por Breiman en la [sección 10 del documento "Random Forests", sección 10 ](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span><span class="sxs-lookup"><span data-stu-id="31668-111">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="31668-112">PFI mide la importancia de las características formulando la pregunta, "¿Cuál sería el efecto en el modelo si los valores de una característica estuvieran establecidos en un valor aleatorio\*?".</span><span class="sxs-lookup"><span data-stu-id="31668-112">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="31668-113">La ventaja del método PFI es que es independiente del modelo (funciona con cualquier modelo que se pueda evaluar) y puede usar cualquier conjunto de datos, no solo el conjunto de entrenamiento, para calcular la importancia de las características.</span><span class="sxs-lookup"><span data-stu-id="31668-113">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="31668-114">Puede usar PFI como para producir importancias de característica como este gráfico:</span><span class="sxs-lookup"><span data-stu-id="31668-114">You can use PFI like so to produce feature importances like this graph:</span></span>

![Gráfico de la importación de la característica de permutación](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

<span data-ttu-id="31668-116">Para un ejemplo de uso de PFI para analizar la importancia de las características de un modelo, vea [el repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span><span class="sxs-lookup"><span data-stu-id="31668-116">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="31668-117">/ \* Bien, no aleatorio exactamente, sino permutado en todo el conjunto de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="31668-117">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
