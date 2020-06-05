---
title: Procedimiento para comprobar si dos objetos son iguales
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403426"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="c3a2f-102">Cómo: Comprobar si dos objetos son iguales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3a2f-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="c3a2f-103">Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` `IsNot` operador o, o ambos, para determinar si hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="c3a2f-104">Para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="c3a2f-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="c3a2f-105">Use el [operador is](../../../language-reference/operators/is-operator.md) o el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) con las dos variables como operandos.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="c3a2f-106">Es posible que desee realizar una acción determinada dependiendo de si dos objetos hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="c3a2f-107">En el ejemplo anterior se compara `c` el control con el control activo en el formulario `f` .</span><span class="sxs-lookup"><span data-stu-id="c3a2f-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="c3a2f-108">Si no hay ningún control activo, o si hay alguno pero no es la misma instancia de control que `c` , la `If` instrucción genera un error y el procedimiento vuelve sin más procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="c3a2f-109">Tanto si usa `Is` como si `IsNot` es una cuestión de comodidad personal.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="c3a2f-110">Una puede ser más fácil de leer que la otra en una expresión dada.</span><span class="sxs-lookup"><span data-stu-id="c3a2f-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a2f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3a2f-111">See also</span></span>

- [<span data-ttu-id="c3a2f-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3a2f-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
