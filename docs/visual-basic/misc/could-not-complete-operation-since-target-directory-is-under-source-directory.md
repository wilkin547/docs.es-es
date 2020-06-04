---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376747"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="e204d-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="e204d-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="e204d-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="e204d-103">A cyclic operation has failed.</span></span> <span data-ttu-id="e204d-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="e204d-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="e204d-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="e204d-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e204d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e204d-106">To correct this error</span></span>  
  
- <span data-ttu-id="e204d-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="e204d-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e204d-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e204d-108">See also</span></span>

- [<span data-ttu-id="e204d-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="e204d-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="e204d-110">Uso de puntos de interrupción en el depurador de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e204d-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
