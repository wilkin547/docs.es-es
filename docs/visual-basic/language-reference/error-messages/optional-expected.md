---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 0ad0d0890b73103a0678b13409a24190329d37d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266339"
---
# <a name="optional-expected"></a><span data-ttu-id="7eafe-102">Se esperaba 'Optional'</span><span class="sxs-lookup"><span data-stu-id="7eafe-102">'Optional' expected</span></span>
<span data-ttu-id="7eafe-103">Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario.</span><span class="sxs-lookup"><span data-stu-id="7eafe-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="7eafe-104">Cada argumento que sigue a un argumento opcional también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="7eafe-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="7eafe-105">**Identificador de error:** BC30202</span><span class="sxs-lookup"><span data-stu-id="7eafe-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7eafe-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7eafe-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7eafe-107">Si el argumento debe ser necesario, muévalo para que preceda al primer argumento opcional en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="7eafe-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="7eafe-108">Si el argumento está pensado para que sea opcional, use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7eafe-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eafe-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eafe-109">See also</span></span>
- [<span data-ttu-id="7eafe-110">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="7eafe-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
