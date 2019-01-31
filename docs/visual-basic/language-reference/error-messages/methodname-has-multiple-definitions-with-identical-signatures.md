---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 97113227591c40f302d3d1a08a4248a8199817bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285433"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="3d534-102">'\<methodname >' tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="3d534-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="3d534-103">Un `Function` o `Sub` declaración de procedimiento utiliza el procedimiento idéntico nombre y lista de argumentos que una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="3d534-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="3d534-104">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="3d534-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="3d534-105">Los procedimientos sobrecargados deben tener distintas listas de argumentos.</span><span class="sxs-lookup"><span data-stu-id="3d534-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="3d534-106">**Identificador de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="3d534-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d534-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3d534-107">To correct this error</span></span>  
  
-   <span data-ttu-id="3d534-108">Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="3d534-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d534-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d534-109">See also</span></span>
- [<span data-ttu-id="3d534-110">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="3d534-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="3d534-111">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3d534-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
