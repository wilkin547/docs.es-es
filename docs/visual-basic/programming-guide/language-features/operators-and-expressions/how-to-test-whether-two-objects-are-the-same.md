---
title: Procedimiento Comprobar si dos objetos son el mismo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 6301228d786fe55e8851b6207dd84819671656f4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649678"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="b566c-102">Procedimiento Comprobar si dos objetos son el mismo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b566c-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="b566c-103">Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` o `IsNot` operador o ambos, para determinar si hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="b566c-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="b566c-104">Para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="b566c-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="b566c-105">Use la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.</span><span class="sxs-lookup"><span data-stu-id="b566c-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="b566c-106">Es posible que desee realizar una acción determinada, dependiendo de si los dos objetos hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="b566c-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="b566c-107">El ejemplo anterior comparan control `c` con el control activo en el formulario `f`.</span><span class="sxs-lookup"><span data-stu-id="b566c-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="b566c-108">Si no hay ningún control activo, o si hay uno, pero no es la misma instancia de control como `c`, el `If` instrucción produce un error y el procedimiento devuelve sin más procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b566c-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="b566c-109">Si usa `Is` o `IsNot` es una cuestión de preferencias personales.</span><span class="sxs-lookup"><span data-stu-id="b566c-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="b566c-110">Uno puede ser más fácil de leer que el otro en una expresión dada.</span><span class="sxs-lookup"><span data-stu-id="b566c-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b566c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b566c-111">See also</span></span>

- [<span data-ttu-id="b566c-112">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b566c-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
