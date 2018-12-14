---
title: 'Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET'
description: Descubra cómo usar ML.NET para usar un modelo de Machine Learning entrenado y evaluado en las aplicaciones
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ff3f0a8856382d020129693bcf722f572fd87606
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131649"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET

Si está satisfecho con las métricas del modelo, es hora de "operacionalizarlo". El objeto `model` que creó se puede usar, conservar y reutilizar en distintos entornos, aplicando los mismos pasos que "aprendió" durante el entrenamiento.

Para guardar el modelo en un archivo y recargarlo (posiblemente en otro contexto), use el ejemplo siguiente:

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
