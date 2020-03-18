---
title: Cálculo de métricas para evaluar la calidad del modelo de aprendizaje automático
description: Obtenga más información sobre cómo calcular las métricas para evaluar y comprobar la calidad del modelo de Machine Learning con ML.NET.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73975840"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="1ec2f-103">Cálculo de métricas para evaluar la calidad del modelo de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="1ec2f-103">Calculate metrics to evaluate machine learning model quality</span></span>

> [!NOTE]
> <span data-ttu-id="1ec2f-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="1ec2f-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1ec2f-105">Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1ec2f-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="1ec2f-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="1ec2f-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="1ec2f-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="1ec2f-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1ec2f-108">¿Cómo se evalúa la calidad después de entrenar el modelo?</span><span class="sxs-lookup"><span data-stu-id="1ec2f-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="1ec2f-109">Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.</span><span class="sxs-lookup"><span data-stu-id="1ec2f-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="1ec2f-110">Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ec2f-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
