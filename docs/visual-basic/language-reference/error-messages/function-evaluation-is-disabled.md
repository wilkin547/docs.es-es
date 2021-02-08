---
description: 'Más información acerca de: BC30957: la evaluación de la función está deshabilitada porque se agotó el tiempo de espera de una evaluación de función anterior'
title: Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 32e4b460a0334a542d59091bfc0b9a2337fdd089
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796189"
---
# <a name="bc30957-function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="973b2-103">BC30957: la evaluación de la función está deshabilitada porque se agotó el tiempo de espera de una evaluación de función anterior</span><span class="sxs-lookup"><span data-stu-id="973b2-103">BC30957: Function evaluation is disabled because a previous function evaluation timed out</span></span>

<span data-ttu-id="973b2-104">La evaluación de la función está deshabilitada porque se agotó el tiempo de espera de evaluación de la función anterior. Para volver a habilitar la evaluación de funciones, vuelva a ejecutar el paso o reinicie la depuración.</span><span class="sxs-lookup"><span data-stu-id="973b2-104">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>

 <span data-ttu-id="973b2-105">En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="973b2-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>

 <span data-ttu-id="973b2-106">Las posibles causas de que se agote el tiempo de espera de una llamada a un procedimiento incluyen un bucle infinito o un *bucle sin fin*.</span><span class="sxs-lookup"><span data-stu-id="973b2-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="973b2-107">Para obtener más información, vea [para... Instrucción siguiente](../statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="973b2-107">For more information, see [For...Next Statement](../statements/for-next-statement.md).</span></span>

 <span data-ttu-id="973b2-108">Un caso especial de un bucle infinito es la *recursividad*.</span><span class="sxs-lookup"><span data-stu-id="973b2-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="973b2-109">Para obtener más información, vea [procedimientos recursivos](../../programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="973b2-109">For more information, see [Recursive Procedures](../../programming-guide/language-features/procedures/recursive-procedures.md).</span></span>

 <span data-ttu-id="973b2-110">**Identificador de error:** BC30957</span><span class="sxs-lookup"><span data-stu-id="973b2-110">**Error ID:** BC30957</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="973b2-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="973b2-111">To correct this error</span></span>

1. <span data-ttu-id="973b2-112">Si es posible, Determine cuál era la evaluación de la función anterior y qué hizo que se agotara el tiempo de espera. De lo contrario, es posible que se produzca este error de nuevo.</span><span class="sxs-lookup"><span data-stu-id="973b2-112">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>

2. <span data-ttu-id="973b2-113">O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.</span><span class="sxs-lookup"><span data-stu-id="973b2-113">Either step the debugger again, or terminate and restart debugging.</span></span>

## <a name="see-also"></a><span data-ttu-id="973b2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="973b2-114">See also</span></span>

- [<span data-ttu-id="973b2-115">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="973b2-115">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="973b2-116">Desplazarse por el código con el depurador</span><span class="sxs-lookup"><span data-stu-id="973b2-116">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
