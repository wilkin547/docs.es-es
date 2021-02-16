---
description: 'Más información sobre: estructuras de bucle (Visual Basic)'
title: Estructuras de bucle
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
ms.openlocfilehash: 82ff36d8f5c05501fcff0f1d564e2613c9b78953
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480653"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="b072d-103">Estructuras de bucles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b072d-103">Loop Structures (Visual Basic)</span></span>

<span data-ttu-id="b072d-104">Visual Basic estructuras de bucle permiten ejecutar una o varias líneas de código repetidamente.</span><span class="sxs-lookup"><span data-stu-id="b072d-104">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="b072d-105">Puede repetir las instrucciones en una estructura de bucle hasta que una condición sea `True` , hasta que una condición sea `False` , un número especificado de veces o una vez por cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="b072d-105">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="b072d-106">En la ilustración siguiente se muestra una estructura de bucle que ejecuta un conjunto de instrucciones hasta que una condición se vuelve verdadera:</span><span class="sxs-lookup"><span data-stu-id="b072d-106">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagrama de flujo que muestra una... Bucle Until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="b072d-108">Bucles while</span><span class="sxs-lookup"><span data-stu-id="b072d-108">While Loops</span></span>  

 <span data-ttu-id="b072d-109">La `While` construcción... `End While` ejecuta un conjunto de instrucciones siempre y cuando la condición especificada en la `While` instrucción sea `True` .</span><span class="sxs-lookup"><span data-stu-id="b072d-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="b072d-110">Para obtener más información, vea [while... End while (instrucción](../../../language-reference/statements/while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="b072d-110">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="b072d-111">Bucles do</span><span class="sxs-lookup"><span data-stu-id="b072d-111">Do Loops</span></span>  

 <span data-ttu-id="b072d-112">La `Do` construcción... `Loop` permite probar una condición al principio o al final de una estructura de bucle.</span><span class="sxs-lookup"><span data-stu-id="b072d-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="b072d-113">También puede especificar si se va a repetir el bucle mientras la condición permanece `True` o hasta que se convierte en `True` .</span><span class="sxs-lookup"><span data-stu-id="b072d-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="b072d-114">Para obtener más información, vea.. [. Instrucción Loop](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b072d-114">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="b072d-115">Bucles for</span><span class="sxs-lookup"><span data-stu-id="b072d-115">For Loops</span></span>  

 <span data-ttu-id="b072d-116">La `For` construcción... `Next` realiza el bucle un número de veces.</span><span class="sxs-lookup"><span data-stu-id="b072d-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="b072d-117">Usa una variable de control de bucle, también denominada *contador*, para realizar un seguimiento de las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="b072d-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="b072d-118">Especifique los valores inicial y final de este contador y, opcionalmente, puede especificar la cantidad por la que aumenta de una repetición a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="b072d-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="b072d-119">Para obtener más información, vea [para... Instrucción siguiente](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b072d-119">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="b072d-120">Bucles for each</span><span class="sxs-lookup"><span data-stu-id="b072d-120">For Each Loops</span></span>  

 <span data-ttu-id="b072d-121">La `For Each` construcción... `Next` ejecuta un conjunto de instrucciones una vez para cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="b072d-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="b072d-122">Especifique la variable de control de bucle, pero no tiene que determinar los valores iniciales o finales de la misma.</span><span class="sxs-lookup"><span data-stu-id="b072d-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="b072d-123">Para obtener más información, vea [para cada uno... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b072d-123">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b072d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b072d-124">See also</span></span>

- [<span data-ttu-id="b072d-125">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="b072d-125">Control Flow</span></span>](index.md)
- [<span data-ttu-id="b072d-126">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="b072d-126">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="b072d-127">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="b072d-127">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="b072d-128">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="b072d-128">Nested Control Structures</span></span>](nested-control-structures.md)
