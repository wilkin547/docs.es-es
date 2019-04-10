---
title: Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306929"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="d4ce7-102">Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="d4ce7-103">El método `FileGet` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-103">The `FileGet` method includes an argument of type `Object`.</span></span> `FileGetObject` <span data-ttu-id="d4ce7-104">en lugar de `FileGet` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-104">should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="d4ce7-105">Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4ce7-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d4ce7-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d4ce7-107">Reemplace `FileGet` por `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="d4ce7-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="d4ce7-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ce7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4ce7-109">See also</span></span>

- [<span data-ttu-id="d4ce7-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="d4ce7-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
