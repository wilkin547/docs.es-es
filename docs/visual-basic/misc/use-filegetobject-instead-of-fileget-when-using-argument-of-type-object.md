---
title: Use &#39;FileGetObject&#39; en lugar de &#39;FileGet&#39; al usar el argumento de tipo &#39;objeto&#39;
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 2edb80f6df95774e0ea5a7b51e57925845d7ba75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640422"
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="947a5-102">Use &#39;FileGetObject&#39; en lugar de &#39;FileGet&#39; al usar el argumento de tipo &#39;objeto&#39;</span><span class="sxs-lookup"><span data-stu-id="947a5-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="947a5-103">El método `FileGet` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="947a5-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="947a5-104">Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="947a5-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="947a5-105">Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="947a5-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="947a5-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="947a5-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="947a5-107">Reemplace `FileGet` por `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="947a5-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="947a5-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="947a5-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="947a5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="947a5-109">See Also</span></span>  
   
 [<span data-ttu-id="947a5-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="947a5-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
