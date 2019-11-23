---
title: AndAlso (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: b3801c7e05142e1bc793e3c9d49a6f6991756f9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350234"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="fdffb-102">AndAlso (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdffb-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="fdffb-103">Performs short-circuiting logical conjunction on two expressions.</span><span class="sxs-lookup"><span data-stu-id="fdffb-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdffb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdffb-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="fdffb-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fdffb-105">Parts</span></span>  
  
|<span data-ttu-id="fdffb-106">Término</span><span class="sxs-lookup"><span data-stu-id="fdffb-106">Term</span></span>|<span data-ttu-id="fdffb-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="fdffb-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="fdffb-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fdffb-108">Required.</span></span> <span data-ttu-id="fdffb-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="fdffb-109">Any `Boolean` expression.</span></span> <span data-ttu-id="fdffb-110">The result is the `Boolean` result of comparison of the two expressions.</span><span class="sxs-lookup"><span data-stu-id="fdffb-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="fdffb-111">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fdffb-111">Required.</span></span> <span data-ttu-id="fdffb-112">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="fdffb-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="fdffb-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fdffb-113">Required.</span></span> <span data-ttu-id="fdffb-114">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="fdffb-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdffb-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdffb-115">Remarks</span></span>  
 <span data-ttu-id="fdffb-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span><span class="sxs-lookup"><span data-stu-id="fdffb-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="fdffb-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span><span class="sxs-lookup"><span data-stu-id="fdffb-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="fdffb-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span><span class="sxs-lookup"><span data-stu-id="fdffb-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="fdffb-119">If both expressions evaluate to `True`, `result` is `True`.</span><span class="sxs-lookup"><span data-stu-id="fdffb-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="fdffb-120">The following table illustrates how `result` is determined.</span><span class="sxs-lookup"><span data-stu-id="fdffb-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="fdffb-121">If `expression1` is</span><span class="sxs-lookup"><span data-stu-id="fdffb-121">If `expression1` is</span></span>|<span data-ttu-id="fdffb-122">And `expression2` is</span><span class="sxs-lookup"><span data-stu-id="fdffb-122">And `expression2` is</span></span>|<span data-ttu-id="fdffb-123">The value of `result` is</span><span class="sxs-lookup"><span data-stu-id="fdffb-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="fdffb-124">(not evaluated)</span><span class="sxs-lookup"><span data-stu-id="fdffb-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="fdffb-125">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fdffb-125">Data Types</span></span>  
 <span data-ttu-id="fdffb-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="fdffb-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="fdffb-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span><span class="sxs-lookup"><span data-stu-id="fdffb-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="fdffb-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span><span class="sxs-lookup"><span data-stu-id="fdffb-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="fdffb-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="fdffb-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="fdffb-130">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="fdffb-130">Overloading</span></span>  
 <span data-ttu-id="fdffb-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="fdffb-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fdffb-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span><span class="sxs-lookup"><span data-stu-id="fdffb-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="fdffb-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="fdffb-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="fdffb-134">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fdffb-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdffb-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdffb-135">Example</span></span>  
 <span data-ttu-id="fdffb-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span><span class="sxs-lookup"><span data-stu-id="fdffb-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="fdffb-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span><span class="sxs-lookup"><span data-stu-id="fdffb-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="fdffb-138">If the first expression is `False`, the second is not evaluated.</span><span class="sxs-lookup"><span data-stu-id="fdffb-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="fdffb-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span><span class="sxs-lookup"><span data-stu-id="fdffb-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="fdffb-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span><span class="sxs-lookup"><span data-stu-id="fdffb-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="fdffb-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="fdffb-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdffb-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdffb-142">Example</span></span>  
 <span data-ttu-id="fdffb-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span><span class="sxs-lookup"><span data-stu-id="fdffb-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="fdffb-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span><span class="sxs-lookup"><span data-stu-id="fdffb-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="fdffb-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdffb-145">See also</span></span>

- [<span data-ttu-id="fdffb-146">Logical/Bitwise Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdffb-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="fdffb-147">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdffb-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fdffb-148">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="fdffb-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fdffb-149">And (operador)</span><span class="sxs-lookup"><span data-stu-id="fdffb-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="fdffb-150">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="fdffb-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="fdffb-151">Logical and Bitwise Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdffb-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
