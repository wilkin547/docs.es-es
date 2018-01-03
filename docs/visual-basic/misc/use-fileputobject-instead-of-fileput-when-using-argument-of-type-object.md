---
title: Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="8765a-102">Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;</span><span class="sxs-lookup"><span data-stu-id="8765a-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="8765a-103">El `FilePut` método incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="8765a-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="8765a-104">Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="8765a-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8765a-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8765a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="8765a-106">Reemplace `FilePut` por `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="8765a-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="8765a-107">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="8765a-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="8765a-108">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="8765a-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8765a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8765a-109">See Also</span></span>  
   
 [<span data-ttu-id="8765a-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="8765a-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="8765a-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="8765a-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
