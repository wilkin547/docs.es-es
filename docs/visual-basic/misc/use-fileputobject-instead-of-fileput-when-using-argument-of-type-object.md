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
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="07312-102">Usar &#39; FilePutObject &#39; en lugar de &#39; FilePut &#39; al usar el argumento de tipo &#39; objeto &#39;</span><span class="sxs-lookup"><span data-stu-id="07312-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="07312-103">El `FilePut` método incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="07312-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="07312-104">Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="07312-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07312-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="07312-105">To correct this error</span></span>  
  
-   <span data-ttu-id="07312-106">Reemplace `FilePut` por `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="07312-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="07312-107">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="07312-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="07312-108">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="07312-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07312-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="07312-109">See Also</span></span>  
 [<span data-ttu-id="07312-110">NO está en la compilación: FilePutObject (función)</span><span class="sxs-lookup"><span data-stu-id="07312-110">NOT IN BUILD: FilePutObject Function</span></span>](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [<span data-ttu-id="07312-111">My.Computer.FileSystem (objeto)</span><span class="sxs-lookup"><span data-stu-id="07312-111">My.Computer.FileSystem Object</span></span>](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [<span data-ttu-id="07312-112">Método My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="07312-112">My.Computer.FileSystem.WriteAllBytes Method</span></span>](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
