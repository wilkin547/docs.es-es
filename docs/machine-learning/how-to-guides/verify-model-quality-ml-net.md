---
title: 'Cálculo de métricas para evaluar la calidad del modelo de Machine Learning: ML.NET'
description: Obtenga más información sobre cómo calcular las métricas para evaluar y comprobar la calidad del modelo de Machine Learning con ML.NET.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297572"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="3227d-103">Cálculo de métricas para evaluar la calidad del modelo de Machine Learning: ML.NET</span><span class="sxs-lookup"><span data-stu-id="3227d-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

<span data-ttu-id="3227d-104">¿Cómo se evalúa la calidad después de entrenar el modelo?</span><span class="sxs-lookup"><span data-stu-id="3227d-104">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="3227d-105">Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.</span><span class="sxs-lookup"><span data-stu-id="3227d-105">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="3227d-106">Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3227d-106">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```