---
title: "Cómo: Comprobar si dos objetos son iguales (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="5e812-102">Cómo: Comprobar si dos objetos son iguales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e812-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="5e812-103">Si tiene dos variables que hacen referencia a objetos, puede utilizar cualquiera el `Is` o `IsNot` operador o ambos, para determinar si hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="5e812-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="5e812-104">Para probar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="5e812-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="5e812-105">Use la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.</span><span class="sxs-lookup"><span data-stu-id="5e812-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="5e812-106">Puede realizar una acción determinada, dependiendo de si los dos objetos hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="5e812-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="5e812-107">En el ejemplo anterior se compara el control `c` en el control activo en el formulario `f`.</span><span class="sxs-lookup"><span data-stu-id="5e812-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="5e812-108">Si no hay ningún control activo, o si no hay uno, pero no es la misma instancia de control como `c`, la `If` instrucción produce un error y el procedimiento devuelve un valor sin procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="5e812-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="5e812-109">Si utiliza `Is` o `IsNot` es cuestión de preferencias personales.</span><span class="sxs-lookup"><span data-stu-id="5e812-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="5e812-110">Uno podría ser más fácil de leer que el otro en una expresión determinada.</span><span class="sxs-lookup"><span data-stu-id="5e812-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e812-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e812-111">See Also</span></span>  
 [<span data-ttu-id="5e812-112">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e812-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
