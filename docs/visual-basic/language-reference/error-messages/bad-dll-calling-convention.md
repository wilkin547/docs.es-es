---
title: Convención de llamada a archivo DLL no válida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 0481bd5e4dfe7a24dff454d0754b519509fa967f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875729"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="806be-102">Convención de llamada a archivo DLL no válida</span><span class="sxs-lookup"><span data-stu-id="806be-102">Bad DLL calling convention</span></span>

<span data-ttu-id="806be-103">Los argumentos pasados a una biblioteca de vínculos dinámicos (DLL) deben coincidir exactamente con los esperados por la rutina.</span><span class="sxs-lookup"><span data-stu-id="806be-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="806be-104">Las convenciones de llamada abordan el número, el tipo y el orden de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="806be-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="806be-105">Es posible que el programa esté llamando a una rutina de un archivo DLL al que se está pasando el tipo o el número de argumentos equivocado.</span><span class="sxs-lookup"><span data-stu-id="806be-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="806be-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="806be-106">To correct this error</span></span>  
  
1. <span data-ttu-id="806be-107">Asegúrese de que todos los tipos de argumento coinciden con los especificados en la declaración de la rutina a la que está llamando.</span><span class="sxs-lookup"><span data-stu-id="806be-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="806be-108">Asegúrese de que está pasando el mismo número de argumentos indicado en la declaración de la rutina a la que está llamando.</span><span class="sxs-lookup"><span data-stu-id="806be-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="806be-109">Si la rutina DLL espera argumentos por valor, asegúrese de que `ByVal` se especifica para esos argumentos en la declaración de la rutina.</span><span class="sxs-lookup"><span data-stu-id="806be-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806be-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="806be-110">See also</span></span>

- [<span data-ttu-id="806be-111">Tipos de errores</span><span class="sxs-lookup"><span data-stu-id="806be-111">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="806be-112">Instrucción Call</span><span class="sxs-lookup"><span data-stu-id="806be-112">Call Statement</span></span>](../statements/call-statement.md)
- [<span data-ttu-id="806be-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="806be-113">Declare Statement</span></span>](../statements/declare-statement.md)
