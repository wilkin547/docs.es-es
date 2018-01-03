---
title: Usar &#39; FileGetObject &#39; en lugar de &#39; FileGet &#39; al usar el argumento de tipo &#39; objeto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="ca030-102">Usar &#39; FileGetObject &#39; en lugar de &#39; FileGet &#39; al usar el argumento de tipo &#39; objeto &#39;</span><span class="sxs-lookup"><span data-stu-id="ca030-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="ca030-103">El método `FileGet` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="ca030-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="ca030-104">Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="ca030-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="ca030-105">Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="ca030-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ca030-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ca030-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ca030-107">Reemplace `FileGet` por `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="ca030-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="ca030-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="ca030-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca030-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca030-109">See Also</span></span>  
   
 [<span data-ttu-id="ca030-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="ca030-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
