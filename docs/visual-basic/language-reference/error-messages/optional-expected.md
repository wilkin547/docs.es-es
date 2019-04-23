---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 71a25784f357a7e596093b314ed5b3d721d6f92c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341886"
---
# <a name="optional-expected"></a><span data-ttu-id="5682d-102">Se esperaba 'Optional'</span><span class="sxs-lookup"><span data-stu-id="5682d-102">'Optional' expected</span></span>
<span data-ttu-id="5682d-103">Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario.</span><span class="sxs-lookup"><span data-stu-id="5682d-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="5682d-104">Cada argumento que sigue a un argumento opcional también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="5682d-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="5682d-105">**Identificador de error:** BC30202</span><span class="sxs-lookup"><span data-stu-id="5682d-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5682d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5682d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="5682d-107">Si el argumento debe ser necesario, muévalo para que preceda al primer argumento opcional en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="5682d-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="5682d-108">Si el argumento está pensado para que sea opcional, use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="5682d-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5682d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5682d-109">See also</span></span>

- [<span data-ttu-id="5682d-110">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="5682d-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
