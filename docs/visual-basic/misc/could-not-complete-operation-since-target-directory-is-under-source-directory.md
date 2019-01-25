---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 253e7ff1d457827a2e1cb9f64eae4bfa971a3798
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645878"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="56d6f-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="56d6f-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="56d6f-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="56d6f-103">A cyclic operation has failed.</span></span> <span data-ttu-id="56d6f-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="56d6f-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="56d6f-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="56d6f-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56d6f-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="56d6f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="56d6f-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="56d6f-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d6f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="56d6f-108">See also</span></span>
- [<span data-ttu-id="56d6f-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="56d6f-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="56d6f-110">Fundamentos de la depuración: Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="56d6f-110">Debugging Basics: Breakpoints</span></span>](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
