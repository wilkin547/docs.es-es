---
title: 'Cómo: Devolver un valor de un procedimiento'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346028"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="5b11f-102">Cómo: Devolver un valor de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b11f-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="5b11f-103">Un procedimiento `Function` devuelve un valor al código de llamada mediante la ejecución de una instrucción de `Return` o una instrucción `Exit Function` o `End Function`.</span><span class="sxs-lookup"><span data-stu-id="5b11f-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="5b11f-104">Para devolver un valor mediante la instrucción return</span><span class="sxs-lookup"><span data-stu-id="5b11f-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="5b11f-105">Coloque una instrucción `Return` en el punto en el que se complete la tarea del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5b11f-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="5b11f-106">Siga la palabra clave `Return` con una expresión que produzca el valor que desea devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5b11f-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="5b11f-107">Puede tener más de una instrucción `Return` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5b11f-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="5b11f-108">En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo derecho y se devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5b11f-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="5b11f-109">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`, que almacena el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5b11f-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="5b11f-110">Para devolver un valor mediante la función EXIT o end</span><span class="sxs-lookup"><span data-stu-id="5b11f-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="5b11f-111">En al menos un lugar del procedimiento `Function`, asigne un valor al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5b11f-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="5b11f-112">Al ejecutar una instrucción `Exit Function` o `End Function`, Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5b11f-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="5b11f-113">Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5b11f-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="5b11f-114">Solo puede tener una instrucción `End Function` en un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="5b11f-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="5b11f-115">Para obtener más información y un ejemplo, vea el tema sobre el valor devuelto en la [instrucción function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b11f-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b11f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b11f-116">See also</span></span>

- [<span data-ttu-id="5b11f-117">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="5b11f-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5b11f-118">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="5b11f-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="5b11f-119">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="5b11f-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="5b11f-120">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="5b11f-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="5b11f-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="5b11f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5b11f-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5b11f-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5b11f-123">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5b11f-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="5b11f-124">Crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="5b11f-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="5b11f-125">Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="5b11f-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
