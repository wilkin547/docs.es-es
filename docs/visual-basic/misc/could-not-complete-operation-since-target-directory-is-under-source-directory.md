---
description: 'Más información acerca de: no se pudo completar la operación porque el directorio de destino está en el directorio de origen'
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 5fb0bf1d761faf9d3d0c64e8815e28e14841b1fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463525"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="e92b5-103">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="e92b5-103">Could not complete operation since target directory is under source directory</span></span>

<span data-ttu-id="e92b5-104">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="e92b5-104">A cyclic operation has failed.</span></span> <span data-ttu-id="e92b5-105">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="e92b5-105">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="e92b5-106">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="e92b5-106">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e92b5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e92b5-107">To correct this error</span></span>  
  
- <span data-ttu-id="e92b5-108">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="e92b5-108">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92b5-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e92b5-109">See also</span></span>

- [<span data-ttu-id="e92b5-110">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="e92b5-110">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="e92b5-111">Uso de puntos de interrupción en el depurador de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e92b5-111">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
