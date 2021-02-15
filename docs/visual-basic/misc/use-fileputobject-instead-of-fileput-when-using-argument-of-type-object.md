---
description: "Más información acerca de: Use ' FilePutObject ' en lugar de ' FilePut ' al usar el argumento de tipo ' Object '"
title: Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 5e5822999aa39bff4d43f83a2719341034cdcadc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460103"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="912e9-103">Use 'FilePutObject' en lugar de 'FilePut' al usar el argumento de tipo 'Object'.</span><span class="sxs-lookup"><span data-stu-id="912e9-103">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>

<span data-ttu-id="912e9-104">El método `FilePut` incluye un argumento de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="912e9-104">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="912e9-105">Debe usarse`FilePutObject` en lugar de `FilePut` para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="912e9-105">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="912e9-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="912e9-106">To correct this error</span></span>  
  
- <span data-ttu-id="912e9-107">Reemplace `FilePut` por `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="912e9-107">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="912e9-108">Convierta el argumento `Object` a un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="912e9-108">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="912e9-109">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="912e9-109">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912e9-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="912e9-110">See also</span></span>

- [<span data-ttu-id="912e9-111">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="912e9-111">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="912e9-112">My. Computer. FileSystem. WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="912e9-112">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
