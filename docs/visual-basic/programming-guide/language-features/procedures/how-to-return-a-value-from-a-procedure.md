---
description: 'Más información acerca de cómo: devolver un valor de un procedimiento (Visual Basic)'
title: Procedimiento para devolver un valor de un procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: c158f15b1e6acb7334d78037d84145981822e177
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476181"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="29bbe-103">Cómo: Devolver un valor de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29bbe-103">How to: Return a Value from a Procedure (Visual Basic)</span></span>

<span data-ttu-id="29bbe-104">Un `Function` procedimiento devuelve un valor al código de llamada mediante la ejecución de una `Return` instrucción o al encontrar una `Exit Function` `End Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="29bbe-104">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="29bbe-105">Para devolver un valor mediante la instrucción return</span><span class="sxs-lookup"><span data-stu-id="29bbe-105">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="29bbe-106">Coloque una `Return` instrucción en el punto en el que se complete la tarea del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-106">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="29bbe-107">Siga la `Return` palabra clave con una expresión que produzca el valor que desea devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="29bbe-107">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="29bbe-108">Puede tener más de una instrucción `Return` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-108">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="29bbe-109">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo derecho y se devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="29bbe-109">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="29bbe-110">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` , que almacena el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="29bbe-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="29bbe-111">Para devolver un valor mediante la función EXIT o end</span><span class="sxs-lookup"><span data-stu-id="29bbe-111">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="29bbe-112">En al menos un lugar del `Function` procedimiento, asigne un valor al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-112">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="29bbe-113">Al ejecutar una `Exit Function` instrucción o `End Function` , Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-113">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="29bbe-114">Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-114">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="29bbe-115">Solo puede tener una `End Function` instrucción en un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29bbe-115">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="29bbe-116">Para obtener más información y un ejemplo, vea el tema sobre el valor devuelto en la [instrucción function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="29bbe-116">For more information and an example, see "Return Value" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bbe-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29bbe-117">See also</span></span>

- [<span data-ttu-id="29bbe-118">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="29bbe-118">Procedures</span></span>](./index.md)
- [<span data-ttu-id="29bbe-119">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="29bbe-119">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="29bbe-120">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="29bbe-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="29bbe-121">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="29bbe-121">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="29bbe-122">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="29bbe-122">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="29bbe-123">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="29bbe-123">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="29bbe-124">Instrucción Return</span><span class="sxs-lookup"><span data-stu-id="29bbe-124">Return Statement</span></span>](../../../language-reference/statements/return-statement.md)
- [<span data-ttu-id="29bbe-125">Procedimiento para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="29bbe-125">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="29bbe-126">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="29bbe-126">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
