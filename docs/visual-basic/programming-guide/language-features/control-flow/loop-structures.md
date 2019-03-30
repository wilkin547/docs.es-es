---
title: Estructuras de bucles (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: c09c0bdee0e8740abb7cc085f0796048a5db150c
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654372"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="1a85e-102">Estructuras de bucles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a85e-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="1a85e-103">Estructuras de bucle de Visual Basic permiten ejecutar repetidamente una o varias líneas de código.</span><span class="sxs-lookup"><span data-stu-id="1a85e-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="1a85e-104">Puede repetir las instrucciones en una estructura de bucle hasta que una condición es `True`, hasta que una condición es `False`, un número de veces o una vez por cada elemento especificado en una colección.</span><span class="sxs-lookup"><span data-stu-id="1a85e-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="1a85e-105">La siguiente ilustración muestra una estructura de bucle que se ejecuta un conjunto de instrucciones hasta que una condición sea true:</span><span class="sxs-lookup"><span data-stu-id="1a85e-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagrama de flujo que muestra una... Hasta el bucle.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="1a85e-107">Bucles while</span><span class="sxs-lookup"><span data-stu-id="1a85e-107">While Loops</span></span>  
 <span data-ttu-id="1a85e-108">El `While`... `End While` construcción ejecuta un conjunto de instrucciones mientras la condición especificada en el `While` instrucción es `True`.</span><span class="sxs-lookup"><span data-stu-id="1a85e-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="1a85e-109">Para obtener más información, consulte [mientras... End While (instrucción)](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1a85e-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="1a85e-110">"DO loops"</span><span class="sxs-lookup"><span data-stu-id="1a85e-110">Do Loops</span></span>  
 <span data-ttu-id="1a85e-111">El `Do`... `Loop` construcción permite probar una condición al principio o final de una estructura de bucle.</span><span class="sxs-lookup"><span data-stu-id="1a85e-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="1a85e-112">También puede especificar si se repite un bucle mientras la condición permanezca `True` o hasta que se `True`.</span><span class="sxs-lookup"><span data-stu-id="1a85e-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="1a85e-113">Para obtener más información, consulte [hacer... Instrucción de bucle](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1a85e-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="1a85e-114">Bucles for</span><span class="sxs-lookup"><span data-stu-id="1a85e-114">For Loops</span></span>  
 <span data-ttu-id="1a85e-115">El `For`... `Next` construcción realiza el bucle un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="1a85e-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="1a85e-116">Usa una variable de control del bucle, también se denomina un *contador*, realizar un seguimiento de las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="1a85e-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="1a85e-117">Especifique los valores iniciales y finales de este contador y, opcionalmente, puede especificar la cantidad por el que incrementa de una repetición a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="1a85e-118">Para obtener más información, consulte [para... Instrucción Next](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1a85e-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="1a85e-119">Bucles For Each</span><span class="sxs-lookup"><span data-stu-id="1a85e-119">For Each Loops</span></span>  
 <span data-ttu-id="1a85e-120">El `For Each`... `Next` construcción ejecuta un conjunto de instrucciones una vez por cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="1a85e-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="1a85e-121">Especifica la variable de control de bucle, pero no es necesario determinar inicial o final de los valores para él.</span><span class="sxs-lookup"><span data-stu-id="1a85e-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="1a85e-122">Para obtener más información, consulte [For Each... Instrucción Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1a85e-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a85e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a85e-123">See also</span></span>
- [<span data-ttu-id="1a85e-124">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="1a85e-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="1a85e-125">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="1a85e-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="1a85e-126">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="1a85e-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="1a85e-127">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="1a85e-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
