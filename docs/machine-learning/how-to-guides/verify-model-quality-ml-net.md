---
title: 'Cálculo de métricas para evaluar la calidad del modelo de Machine Learning: ML.NET'
description: Obtenga más información sobre cómo calcular las métricas para evaluar y comprobar la calidad del modelo de Machine Learning con ML.NET.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ad71f7da6981ac370e60725f88d3c70b1d5c5237
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679221"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="41ac5-103">Cálculo de métricas para evaluar la calidad del modelo de Machine Learning: ML.NET</span><span class="sxs-lookup"><span data-stu-id="41ac5-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="41ac5-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="41ac5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="41ac5-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="41ac5-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="41ac5-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="41ac5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="41ac5-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="41ac5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="41ac5-108">¿Cómo se evalúa la calidad después de entrenar el modelo?</span><span class="sxs-lookup"><span data-stu-id="41ac5-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="41ac5-109">Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.</span><span class="sxs-lookup"><span data-stu-id="41ac5-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="41ac5-110">Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41ac5-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```