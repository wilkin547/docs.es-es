---
title: Cálculo de métricas para evaluar la calidad del modelo de aprendizaje automático
description: Obtenga más información sobre cómo calcular las métricas para evaluar y comprobar la calidad del modelo de Machine Learning con ML.NET.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 529003913b166c966e131b006800f944096605b7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855564"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="190d5-103">Cálculo de métricas para evaluar la calidad del modelo de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="190d5-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="190d5-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="190d5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="190d5-105">Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="190d5-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="190d5-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="190d5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="190d5-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="190d5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="190d5-108">¿Cómo se evalúa la calidad después de entrenar el modelo?</span><span class="sxs-lookup"><span data-stu-id="190d5-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="190d5-109">Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.</span><span class="sxs-lookup"><span data-stu-id="190d5-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="190d5-110">Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="190d5-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
