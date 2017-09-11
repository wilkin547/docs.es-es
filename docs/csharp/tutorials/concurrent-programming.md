---
title: "Programación simultánea: guía de C#"
description: "Aprenda técnicas para la ejecución de tareas (probablemente enlazadas a la CPU) en paralelo."
keywords: "C#, asincrónica, enlazado a CPU, enlazado a la red"
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0f8b42de-858a-44a3-87d9-998211f26377
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00cf3b04178ca48c9f8f35eb16bc216389e6b272
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="-concurrent-programming"></a><span data-ttu-id="1f467-104">🔧 Programación simultánea</span><span class="sxs-lookup"><span data-stu-id="1f467-104">🔧 Concurrent Programming</span></span>

> <span data-ttu-id="1f467-105">**Nota:**</span><span class="sxs-lookup"><span data-stu-id="1f467-105">**Note**</span></span>
> 
> <span data-ttu-id="1f467-106">¡Este tema no se ha escrito todavía!</span><span class="sxs-lookup"><span data-stu-id="1f467-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="1f467-107">Le agradecemos sus comentarios para facilitar el ámbito y el enfoque.</span><span class="sxs-lookup"><span data-stu-id="1f467-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="1f467-108">Puede hacer un seguimiento del estado de este [asunto](https://github.com/dotnet/docs/issues/953) y brindar comentarios al respecto en GitHub.</span><span class="sxs-lookup"><span data-stu-id="1f467-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/953) at GitHub.</span></span>
> 
> <span data-ttu-id="1f467-109">Si desea revisar esquemas y borradores iniciales de este tema, deje una nota con su información de contacto en el asunto.</span><span class="sxs-lookup"><span data-stu-id="1f467-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="1f467-110">Más información sobre cómo puede contribuir en [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="1f467-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

