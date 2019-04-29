---
title: Procedimiento Devolver un valor de un procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 8b53df1634d2b9971bc44c968a17db81cac3924f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665759"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="2feee-102">Procedimiento Devolver un valor de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2feee-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="2feee-103">Un `Function` procedimiento devuelve un valor al código de llamada ya sea mediante la ejecución de un `Return` instrucción o encontrando una `Exit Function` o `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2feee-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="2feee-104">Para devolver un valor mediante la instrucción Return</span><span class="sxs-lookup"><span data-stu-id="2feee-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="2feee-105">Coloque un `Return` instrucción en el punto donde se completa la tarea del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="2feee-106">Siga el `Return` palabra clave con una expresión que da como resultado el valor que desea volver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2feee-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="2feee-107">Puede tener más de una instrucción `Return` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="2feee-108">La siguiente `Function` procedimiento calcula el lado más largo o la hipotenusa de un triángulo rectángulo y lo devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2feee-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="2feee-109">El ejemplo siguiente muestra una llamada típica al `hypotenuse`, que almacena el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="2feee-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="2feee-110">Para devolver un valor mediante Exit Function o End Function</span><span class="sxs-lookup"><span data-stu-id="2feee-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="2feee-111">En lugar de al menos una de las `Function` procedimiento, asigne un valor para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="2feee-112">Cuando se ejecuta un `Exit Function` o `End Function` instrucción, Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="2feee-113">Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="2feee-114">Puede tener sólo uno `End Function` instrucción en un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2feee-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="2feee-115">Para obtener más información y un ejemplo, vea "Valor devuelto" en [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2feee-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2feee-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2feee-116">See also</span></span>

- [<span data-ttu-id="2feee-117">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2feee-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2feee-118">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="2feee-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="2feee-119">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="2feee-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="2feee-120">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="2feee-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="2feee-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="2feee-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2feee-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2feee-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="2feee-123">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2feee-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="2feee-124">Cómo: Crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="2feee-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="2feee-125">Cómo: Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="2feee-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
