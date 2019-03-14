---
title: 'Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET'
description: Descubra cómo usar ML.NET para usar un modelo de Machine Learning entrenado y evaluado en las aplicaciones
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675139"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

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
