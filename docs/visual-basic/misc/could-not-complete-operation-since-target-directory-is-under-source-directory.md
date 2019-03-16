---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039429"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="9c4c2-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="9c4c2-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="9c4c2-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="9c4c2-103">A cyclic operation has failed.</span></span> <span data-ttu-id="9c4c2-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="9c4c2-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="9c4c2-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="9c4c2-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c4c2-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9c4c2-106">To correct this error</span></span>  
  
-   <span data-ttu-id="9c4c2-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="9c4c2-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4c2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c4c2-108">See also</span></span>

- [<span data-ttu-id="9c4c2-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="9c4c2-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="9c4c2-110">Utilizar puntos de interrupción en el depurador de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9c4c2-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
