---
title: Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725563"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="46416-102">Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.</span><span class="sxs-lookup"><span data-stu-id="46416-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="46416-103">El método `FilePut` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="46416-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="46416-104">Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="46416-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46416-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="46416-105">To correct this error</span></span>  
  
-   <span data-ttu-id="46416-106">Reemplace `FilePut` por `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="46416-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="46416-107">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="46416-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="46416-108">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="46416-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46416-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="46416-109">See also</span></span>

- [<span data-ttu-id="46416-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="46416-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="46416-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="46416-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
