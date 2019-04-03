---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831883"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="3696c-102">'\<methodname >' tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="3696c-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="3696c-103">Un `Function` o `Sub` declaración de procedimiento utiliza el procedimiento idéntico nombre y lista de argumentos que una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="3696c-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="3696c-104">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="3696c-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="3696c-105">Los procedimientos sobrecargados deben tener distintas listas de argumentos.</span><span class="sxs-lookup"><span data-stu-id="3696c-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="3696c-106">**Identificador de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="3696c-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3696c-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3696c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="3696c-108">Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="3696c-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3696c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3696c-109">See also</span></span>

- [<span data-ttu-id="3696c-110">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="3696c-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="3696c-111">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3696c-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
