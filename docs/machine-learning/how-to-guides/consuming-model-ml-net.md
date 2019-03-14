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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="16b77-103">Operacionalización de un modelo de aprendizaje automático entrenado en aplicaciones: ML.NET</span><span class="sxs-lookup"><span data-stu-id="16b77-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="16b77-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="16b77-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="16b77-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="16b77-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="16b77-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="16b77-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="16b77-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="16b77-107">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="16b77-108">Si está satisfecho con las métricas del modelo, es hora de "operacionalizarlo".</span><span class="sxs-lookup"><span data-stu-id="16b77-108">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="16b77-109">El objeto `model` que creó se puede usar, conservar y reutilizar en distintos entornos, aplicando los mismos pasos que "aprendió" durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="16b77-109">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="16b77-110">Para guardar el modelo en un archivo y recargarlo (posiblemente en otro contexto), use el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16b77-110">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
