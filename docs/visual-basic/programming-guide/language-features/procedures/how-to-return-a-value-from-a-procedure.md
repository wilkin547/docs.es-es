---
title: Procedimiento para devolver un valor de un procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 917e52b711645fbf94a132216a3fa90b0dfc15b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414329"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="53557-102">Cómo: Devolver un valor de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53557-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="53557-103">Un `Function` procedimiento devuelve un valor al código de llamada mediante la ejecución de una `Return` instrucción o al encontrar una `Exit Function` `End Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="53557-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="53557-104">Para devolver un valor mediante la instrucción return</span><span class="sxs-lookup"><span data-stu-id="53557-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="53557-105">Coloque una `Return` instrucción en el punto en el que se complete la tarea del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="53557-106">Siga la `Return` palabra clave con una expresión que produzca el valor que desea devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="53557-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="53557-107">Puede tener más de una instrucción `Return` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="53557-108">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo derecho y se devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="53557-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="53557-109">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` , que almacena el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="53557-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="53557-110">Para devolver un valor mediante la función EXIT o end</span><span class="sxs-lookup"><span data-stu-id="53557-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="53557-111">En al menos un lugar del `Function` procedimiento, asigne un valor al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="53557-112">Al ejecutar una `Exit Function` instrucción o `End Function` , Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="53557-113">Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="53557-114">Solo puede tener una `End Function` instrucción en un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="53557-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="53557-115">Para obtener más información y un ejemplo, vea el tema sobre el valor devuelto en la [instrucción function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="53557-115">For more information and an example, see "Return Value" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53557-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53557-116">See also</span></span>

- [<span data-ttu-id="53557-117">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="53557-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="53557-118">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="53557-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="53557-119">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="53557-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="53557-120">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="53557-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="53557-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="53557-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="53557-122">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="53557-122">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="53557-123">Instrucción return</span><span class="sxs-lookup"><span data-stu-id="53557-123">Return Statement</span></span>](../../../language-reference/statements/return-statement.md)
- [<span data-ttu-id="53557-124">Procedimiento para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="53557-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="53557-125">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="53557-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
