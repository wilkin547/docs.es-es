---
title: No se admite Set en tiempo de ejecución
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: c5ab1fe0dc6f588f710cb2879aad7896d13be800
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537782"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="b80d2-102">No se admite Set en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b80d2-102">Set not supported at run time</span></span>
<span data-ttu-id="b80d2-103">Se intentó establecer o cambiar una propiedad cuyo valor solo se puede establecer en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="b80d2-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b80d2-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b80d2-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="b80d2-105">Quite la referencia a la propiedad desde el código.</span><span class="sxs-lookup"><span data-stu-id="b80d2-105">Remove the reference to the property from your code.</span></span>  
  
2.  <span data-ttu-id="b80d2-106">Cambie la referencia para que solo devuelva el valor de la propiedad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b80d2-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80d2-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b80d2-107">See also</span></span>
- [<span data-ttu-id="b80d2-108">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="b80d2-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
