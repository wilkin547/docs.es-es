---
title: Estructuras de bucles
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
ms.openlocfilehash: 0a75205a7d52c332094d624d082e5db3e89447f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353913"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="cbc64-102">Estructuras de bucles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc64-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="cbc64-103">Visual Basic estructuras de bucle permiten ejecutar una o varias líneas de código repetidamente.</span><span class="sxs-lookup"><span data-stu-id="cbc64-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="cbc64-104">Puede repetir las instrucciones en una estructura de bucle hasta que se `True`una condición, hasta que se `False`una condición, un número especificado de veces o una vez por cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="cbc64-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="cbc64-105">En la ilustración siguiente se muestra una estructura de bucle que ejecuta un conjunto de instrucciones hasta que una condición se vuelve verdadera:</span><span class="sxs-lookup"><span data-stu-id="cbc64-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagrama de flujo que muestra una... Bucle Until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="cbc64-107">Bucles while</span><span class="sxs-lookup"><span data-stu-id="cbc64-107">While Loops</span></span>  
 <span data-ttu-id="cbc64-108">La construcción `While`...`End While` ejecuta un conjunto de instrucciones siempre que se `True`la condición especificada en la instrucción `While`.</span><span class="sxs-lookup"><span data-stu-id="cbc64-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="cbc64-109">Para obtener más información, vea [while... End while (instrucción](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="cbc64-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="cbc64-110">Bucles do</span><span class="sxs-lookup"><span data-stu-id="cbc64-110">Do Loops</span></span>  
 <span data-ttu-id="cbc64-111">La construcción `Do`...`Loop` permite probar una condición al principio o al final de una estructura de bucle.</span><span class="sxs-lookup"><span data-stu-id="cbc64-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="cbc64-112">También puede especificar si se va a repetir el bucle mientras la condición permanece `True` o hasta que se `True`.</span><span class="sxs-lookup"><span data-stu-id="cbc64-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="cbc64-113">Para obtener más información, vea.. [. Instrucción Loop](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="cbc64-114">Bucles for</span><span class="sxs-lookup"><span data-stu-id="cbc64-114">For Loops</span></span>  
 <span data-ttu-id="cbc64-115">La construcción `For`...`Next` realiza un bucle un número de veces.</span><span class="sxs-lookup"><span data-stu-id="cbc64-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="cbc64-116">Usa una variable de control de bucle, también denominada *contador*, para realizar un seguimiento de las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="cbc64-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="cbc64-117">Especifique los valores inicial y final de este contador y, opcionalmente, puede especificar la cantidad por la que aumenta de una repetición a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="cbc64-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="cbc64-118">Para obtener más información, vea [para... Instrucción siguiente](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="cbc64-119">Bucles for each</span><span class="sxs-lookup"><span data-stu-id="cbc64-119">For Each Loops</span></span>  
 <span data-ttu-id="cbc64-120">La construcción `For Each`...`Next` ejecuta un conjunto de instrucciones una vez para cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="cbc64-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="cbc64-121">Especifique la variable de control de bucle, pero no tiene que determinar los valores iniciales o finales de la misma.</span><span class="sxs-lookup"><span data-stu-id="cbc64-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="cbc64-122">Para obtener más información, vea [para cada uno... Instrucción siguiente](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cbc64-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc64-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbc64-123">See also</span></span>

- [<span data-ttu-id="cbc64-124">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="cbc64-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="cbc64-125">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="cbc64-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="cbc64-126">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="cbc64-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="cbc64-127">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="cbc64-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
