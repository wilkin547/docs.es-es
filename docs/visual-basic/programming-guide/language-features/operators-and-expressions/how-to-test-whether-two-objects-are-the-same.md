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
ms.openlocfilehash: 4130dfbe70682e28b6bb15db633ede2790e20aa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595557"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="80036-102">Procedimiento Comprobar si dos objetos son el mismo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80036-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="80036-103">Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` o `IsNot` operador o ambos, para determinar si hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="80036-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="80036-104">Para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="80036-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="80036-105">Use la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.</span><span class="sxs-lookup"><span data-stu-id="80036-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="80036-106">Es posible que desee realizar una acción determinada, dependiendo de si los dos objetos hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="80036-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="80036-107">El ejemplo anterior comparan control `c` con el control activo en el formulario `f`.</span><span class="sxs-lookup"><span data-stu-id="80036-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="80036-108">Si no hay ningún control activo, o si hay uno, pero no es la misma instancia de control como `c`, el `If` instrucción produce un error y el procedimiento devuelve sin más procesamiento.</span><span class="sxs-lookup"><span data-stu-id="80036-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="80036-109">Si usa `Is` o `IsNot` es una cuestión de preferencias personales.</span><span class="sxs-lookup"><span data-stu-id="80036-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="80036-110">Uno puede ser más fácil de leer que el otro en una expresión dada.</span><span class="sxs-lookup"><span data-stu-id="80036-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80036-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="80036-111">See also</span></span>
- [<span data-ttu-id="80036-112">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80036-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
