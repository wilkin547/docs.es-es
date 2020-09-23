---
title: Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059410"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="cfdbb-102">Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="cfdbb-103">El método `FileGet` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="cfdbb-104">Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="cfdbb-105">Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cfdbb-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cfdbb-106">To correct this error</span></span>  
  
1. <span data-ttu-id="cfdbb-107">Reemplace `FileGet` por `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="cfdbb-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="cfdbb-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdbb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfdbb-109">See also</span></span>

- [<span data-ttu-id="cfdbb-110">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="cfdbb-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
