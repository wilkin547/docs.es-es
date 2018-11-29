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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Cálculo de métricas para evaluar la calidad del modelo de Machine Learning: ML.NET

¿Cómo se evalúa la calidad después de entrenar el modelo? Cada tarea de aprendizaje automático expone las métricas para evaluar la calidad.

Puede usar el "contexto" correspondiente de la tarea para evaluar el modelo, como en el ejemplo siguiente:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```