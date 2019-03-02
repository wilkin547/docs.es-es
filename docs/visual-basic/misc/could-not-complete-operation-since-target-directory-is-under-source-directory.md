---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 39373cd368282f3b109b450189561366b9e74484
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200577"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="4b418-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="4b418-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="4b418-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="4b418-103">A cyclic operation has failed.</span></span> <span data-ttu-id="4b418-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="4b418-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="4b418-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="4b418-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b418-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4b418-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4b418-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="4b418-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b418-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b418-108">See also</span></span>
- [<span data-ttu-id="4b418-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="4b418-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="4b418-110">Utilizar puntos de interrupción en el depurador de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b418-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
