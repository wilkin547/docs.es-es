---
title: Estructuras de bucles (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f813a555677e3828297c9c360b7a47217c39524
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="40732-102">Estructuras de bucles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40732-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="40732-103">estructuras de bucle permiten ejecutar una o más líneas de código repetidamente.</span><span class="sxs-lookup"><span data-stu-id="40732-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="40732-104">Puede repetir las instrucciones en una estructura de bucle hasta que una condición es `True`, hasta que una condición es `False`, un número de veces o una vez por cada elemento especificado en una colección.</span><span class="sxs-lookup"><span data-stu-id="40732-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="40732-105">En la siguiente ilustración muestra una estructura de bucle que ejecuta un conjunto de instrucciones hasta que una condición sea true.</span><span class="sxs-lookup"><span data-stu-id="40732-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="40732-106">![Diagrama de flujo de un bucle Do... Hasta que el bucle](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="40732-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="40732-107">Ejecuta un conjunto de instrucciones hasta que una condición sea true</span><span class="sxs-lookup"><span data-stu-id="40732-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="40732-108">Bucles while</span><span class="sxs-lookup"><span data-stu-id="40732-108">While Loops</span></span>  
 <span data-ttu-id="40732-109">El `While`... `End While` construcción ejecuta un conjunto de instrucciones mientras la condición especificada en el `While` instrucción es `True`.</span><span class="sxs-lookup"><span data-stu-id="40732-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="40732-110">Para obtener más información, vea [mientras... End While (instrucción)](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="40732-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="40732-111">Bucles Do</span><span class="sxs-lookup"><span data-stu-id="40732-111">Do Loops</span></span>  
 <span data-ttu-id="40732-112">El `Do`... `Loop` construcción le permite probar una condición al principio o final de una estructura de bucle.</span><span class="sxs-lookup"><span data-stu-id="40732-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="40732-113">También puede especificar si se repite el bucle mientras la condición siga siendo `True` o hasta que se convierte en `True`.</span><span class="sxs-lookup"><span data-stu-id="40732-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="40732-114">Para obtener más información, vea [hacer... Instrucción de bucle](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="40732-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="40732-115">For (bucles)</span><span class="sxs-lookup"><span data-stu-id="40732-115">For Loops</span></span>  
 <span data-ttu-id="40732-116">El `For`... `Next` construcción realiza el bucle un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="40732-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="40732-117">Utiliza una variable de control de bucle, también se denomina un *contador*, realizar un seguimiento de las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="40732-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="40732-118">Especifique las iniciales y finales de los valores de este contador y, opcionalmente, puede especificar la cantidad por la que incrementa de una repetición a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="40732-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="40732-119">Para obtener más información, vea [para... Next (instrucción)](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="40732-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="40732-120">Bucles For Each</span><span class="sxs-lookup"><span data-stu-id="40732-120">For Each Loops</span></span>  
 <span data-ttu-id="40732-121">El `For Each`... `Next` construcción ejecuta un conjunto de instrucciones una vez por cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="40732-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="40732-122">Especifique la variable de control de bucle, pero no es necesario determinar inicial o final valores para él.</span><span class="sxs-lookup"><span data-stu-id="40732-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="40732-123">Para obtener más información, vea [For Each... Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="40732-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40732-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="40732-124">See Also</span></span>  
 [<span data-ttu-id="40732-125">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="40732-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="40732-126">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="40732-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="40732-127">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="40732-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="40732-128">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="40732-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
