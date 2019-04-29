---
title: Convención de llamada a archivo DLL no válida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935283"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="01414-102">Convención de llamada a archivo DLL no válida</span><span class="sxs-lookup"><span data-stu-id="01414-102">Bad DLL calling convention</span></span>
<span data-ttu-id="01414-103">Los argumentos pasados a una biblioteca de vínculos dinámicos (DLL) deben coincidir exactamente con los esperados por la rutina.</span><span class="sxs-lookup"><span data-stu-id="01414-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="01414-104">Convenciones de llamada ocupan de número, tipo y orden de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="01414-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="01414-105">El programa puede estar llamando a una rutina en un archivo DLL que se pasa el tipo incorrecto o el número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="01414-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01414-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="01414-106">To correct this error</span></span>  
  
1. <span data-ttu-id="01414-107">Asegúrese de que todos los tipos de argumento coinciden con los especificados en la declaración de la rutina que está llamando.</span><span class="sxs-lookup"><span data-stu-id="01414-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="01414-108">Asegúrese de que está pasando el mismo número de argumentos indicada en la declaración de la rutina que está llamando.</span><span class="sxs-lookup"><span data-stu-id="01414-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="01414-109">Si la rutina de la DLL espera argumentos por valor, asegúrese de que `ByVal` se especifica para esos argumentos en la declaración de la rutina.</span><span class="sxs-lookup"><span data-stu-id="01414-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01414-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="01414-110">See also</span></span>

- [<span data-ttu-id="01414-111">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="01414-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="01414-112">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01414-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="01414-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01414-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
