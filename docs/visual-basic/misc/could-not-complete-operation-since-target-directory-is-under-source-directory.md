---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970123"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="bb7aa-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="bb7aa-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="bb7aa-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="bb7aa-103">A cyclic operation has failed.</span></span> <span data-ttu-id="bb7aa-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="bb7aa-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="bb7aa-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="bb7aa-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb7aa-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bb7aa-106">To correct this error</span></span>  
  
- <span data-ttu-id="bb7aa-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="bb7aa-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7aa-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb7aa-108">See also</span></span>

- [<span data-ttu-id="bb7aa-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="bb7aa-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="bb7aa-110">Utilizar puntos de interrupción en el depurador de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bb7aa-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
