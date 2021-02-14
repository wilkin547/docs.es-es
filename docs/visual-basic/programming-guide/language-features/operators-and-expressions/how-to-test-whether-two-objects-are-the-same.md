---
description: 'Más información acerca de cómo: comprobar si dos objetos son iguales (Visual Basic)'
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
ms.openlocfilehash: a0136d9db487ad0ce70b9d55ff8ee014ec30b05a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435543"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="c24b0-103">Cómo: Comprobar si dos objetos son iguales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c24b0-103">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>

<span data-ttu-id="c24b0-104">Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` `IsNot` operador o, o ambos, para determinar si hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="c24b0-104">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="c24b0-105">Para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="c24b0-105">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="c24b0-106">Use el [operador is](../../../language-reference/operators/is-operator.md) o el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) con las dos variables como operandos.</span><span class="sxs-lookup"><span data-stu-id="c24b0-106">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="c24b0-107">Es posible que desee realizar una acción determinada dependiendo de si dos objetos hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="c24b0-107">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="c24b0-108">En el ejemplo anterior se compara `c` el control con el control activo en el formulario `f` .</span><span class="sxs-lookup"><span data-stu-id="c24b0-108">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="c24b0-109">Si no hay ningún control activo, o si hay alguno pero no es la misma instancia de control que `c` , la `If` instrucción genera un error y el procedimiento vuelve sin más procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c24b0-109">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="c24b0-110">Tanto si usa `Is` como si `IsNot` es una cuestión de comodidad personal.</span><span class="sxs-lookup"><span data-stu-id="c24b0-110">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="c24b0-111">Una puede ser más fácil de leer que la otra en una expresión dada.</span><span class="sxs-lookup"><span data-stu-id="c24b0-111">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24b0-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c24b0-112">See also</span></span>

- [<span data-ttu-id="c24b0-113">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c24b0-113">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
