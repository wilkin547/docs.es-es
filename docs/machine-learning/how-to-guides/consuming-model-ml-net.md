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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="b3420-103">Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET</span><span class="sxs-lookup"><span data-stu-id="b3420-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

<span data-ttu-id="b3420-104">Si está satisfecho con las métricas del modelo, es hora de "operacionalizarlo".</span><span class="sxs-lookup"><span data-stu-id="b3420-104">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="b3420-105">El objeto `model` que creó se puede usar, conservar y reutilizar en distintos entornos, aplicando los mismos pasos que "aprendió" durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="b3420-105">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="b3420-106">Para guardar el modelo en un archivo y recargarlo (posiblemente en otro contexto), use el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3420-106">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
