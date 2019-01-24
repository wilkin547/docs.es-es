---
title: Convención de llamada a archivo DLL no válida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 70200b38ea3d1497daa091fa407accabaf3c4eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715782"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="e8c1c-102">Convención de llamada a archivo DLL no válida</span><span class="sxs-lookup"><span data-stu-id="e8c1c-102">Bad DLL calling convention</span></span>
<span data-ttu-id="e8c1c-103">Los argumentos pasados a una biblioteca de vínculos dinámicos (DLL) deben coincidir exactamente con los esperados por la rutina.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="e8c1c-104">Convenciones de llamada ocupan de número, tipo y orden de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="e8c1c-105">El programa puede estar llamando a una rutina en un archivo DLL que se pasa el tipo incorrecto o el número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8c1c-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e8c1c-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="e8c1c-107">Asegúrese de que todos los tipos de argumento coinciden con los especificados en la declaración de la rutina que está llamando.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="e8c1c-108">Asegúrese de que está pasando el mismo número de argumentos indicada en la declaración de la rutina que está llamando.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="e8c1c-109">Si la rutina de la DLL espera argumentos por valor, asegúrese de que `ByVal` se especifica para esos argumentos en la declaración de la rutina.</span><span class="sxs-lookup"><span data-stu-id="e8c1c-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c1c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8c1c-110">See also</span></span>
- [<span data-ttu-id="e8c1c-111">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="e8c1c-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="e8c1c-112">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8c1c-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="e8c1c-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8c1c-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
