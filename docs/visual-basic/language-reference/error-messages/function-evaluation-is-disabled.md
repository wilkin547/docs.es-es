---
title: Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315782"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="a3366-102">Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior</span><span class="sxs-lookup"><span data-stu-id="a3366-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="a3366-103">Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior Para volver a habilitar la evaluación de funciones, vuelva a intentarlo o reinicie la depuración.</span><span class="sxs-lookup"><span data-stu-id="a3366-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="a3366-104">En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a3366-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="a3366-105">Las posibles causas de una llamada a procedimiento en tiempo de espera incluyen un bucle infinito o *bucle sin fin*.</span><span class="sxs-lookup"><span data-stu-id="a3366-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="a3366-106">Para obtener más información, consulte [para... Instrucción Next](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a3366-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="a3366-107">Es un caso especial de un bucle infinito *recursividad*.</span><span class="sxs-lookup"><span data-stu-id="a3366-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="a3366-108">Para obtener más información, consulte [procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a3366-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="a3366-109">**Identificador de error:** BC30957</span><span class="sxs-lookup"><span data-stu-id="a3366-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a3366-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a3366-110">To correct this error</span></span>  
  
1. <span data-ttu-id="a3366-111">Si es posible, determine cuál era la evaluación de función anterior y lo que lo produjo que se superara el tiempo de espera. De lo contrario, podría encontrar de nuevo este error.</span><span class="sxs-lookup"><span data-stu-id="a3366-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="a3366-112">O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.</span><span class="sxs-lookup"><span data-stu-id="a3366-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3366-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3366-113">See also</span></span>

- [<span data-ttu-id="a3366-114">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3366-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="a3366-115">Desplazarse por el código con el depurador</span><span class="sxs-lookup"><span data-stu-id="a3366-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
