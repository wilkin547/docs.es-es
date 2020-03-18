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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a>Cálculo de métricas para evaluar la calidad del modelo de aprendizaje automático

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

¿Cómo se evalúa la calidad después de entrenar el modelo? Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.

Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
