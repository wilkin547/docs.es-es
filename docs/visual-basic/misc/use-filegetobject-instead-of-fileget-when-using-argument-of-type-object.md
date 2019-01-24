---
title: Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 60eaabc686070aced908116728f06d4e82b5cecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723399"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="1b459-102">Use 'FileGetObject' en lugar de 'FileGet' al usar el argumento de tipo 'Object'.</span><span class="sxs-lookup"><span data-stu-id="1b459-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="1b459-103">El método `FileGet` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="1b459-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="1b459-104">Debe usarse`FileGetObject` en lugar de `FileGet` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="1b459-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="1b459-105">Tenga en cuenta que la funcionalidad que proporciona `My.Computer.Filesystem` ofrece mayor facilidad de uso y rendimiento que `FileGet` o `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="1b459-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b459-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1b459-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="1b459-107">Reemplace `FileGet` por `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="1b459-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="1b459-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="1b459-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b459-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b459-109">See also</span></span>

- [<span data-ttu-id="1b459-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="1b459-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
