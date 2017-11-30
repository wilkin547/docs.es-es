---
title: "Cómo: Devolver un valor de un procedimiento (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce7aa0942be413986cb010963753447ea18cdf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="8407a-102">Cómo: Devolver un valor de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8407a-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="8407a-103">A `Function` procedimiento devuelve un valor al código de llamada mediante la ejecución de un `Return` instrucción o encontrar una `Exit Function` o `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8407a-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="8407a-104">Para devolver un valor mediante la instrucción Return</span><span class="sxs-lookup"><span data-stu-id="8407a-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="8407a-105">Coloque un `Return` instrucción en el punto donde se completa la tarea del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="8407a-106">Siga el `Return` palabra clave con una expresión que da como resultado el valor que desea devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="8407a-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="8407a-107">Puede tener más de una instrucción `Return` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="8407a-108">El siguiente `Function` procedimiento calcula el lado o la hipotenusa de un triángulo rectángulo y lo devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="8407a-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="8407a-109">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`, que almacena el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="8407a-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="8407a-110">Para devolver un valor mediante Exit Function o End Function</span><span class="sxs-lookup"><span data-stu-id="8407a-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="8407a-111">En lugar de al menos una de las `Function` procedimiento, asigne un valor para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="8407a-112">Cuando se ejecuta un `Exit Function` o `End Function` instrucción, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] devuelve el valor asignado más recientemente al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-112">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="8407a-113">Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="8407a-114">Puede tener solo una `End Function` instrucción en un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8407a-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="8407a-115">Para obtener más información y un ejemplo, vea "Valor devuelto" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8407a-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8407a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8407a-116">See Also</span></span>  
 [<span data-ttu-id="8407a-117">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8407a-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8407a-118">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="8407a-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8407a-119">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="8407a-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8407a-120">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="8407a-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="8407a-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="8407a-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8407a-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8407a-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="8407a-123">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8407a-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="8407a-124">Crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="8407a-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="8407a-125">Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="8407a-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
