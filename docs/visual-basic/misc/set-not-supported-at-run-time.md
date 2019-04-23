---
title: No se admite Set en tiempo de ejecución
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: 1b3f8aa3811baae240e6baa546082d0dcf2cf667
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325870"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="ce5d0-102">No se admite Set en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ce5d0-102">Set not supported at run time</span></span>
<span data-ttu-id="ce5d0-103">Se intentó establecer o cambiar una propiedad cuyo valor solo se puede establecer en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ce5d0-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce5d0-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ce5d0-104">To correct this error</span></span>  
  
1. <span data-ttu-id="ce5d0-105">Quite la referencia a la propiedad desde el código.</span><span class="sxs-lookup"><span data-stu-id="ce5d0-105">Remove the reference to the property from your code.</span></span>  
  
2. <span data-ttu-id="ce5d0-106">Cambie la referencia para que solo devuelva el valor de la propiedad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ce5d0-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce5d0-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce5d0-107">See also</span></span>

- [<span data-ttu-id="ce5d0-108">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="ce5d0-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
