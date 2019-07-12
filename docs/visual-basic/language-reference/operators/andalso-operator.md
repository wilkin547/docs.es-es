---
title: AndAlso (Operador, Visual Basic)
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
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859882"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="5d095-102">AndAlso (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d095-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="5d095-103">Realiza una conjunción lógica de dos expresiones de cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="5d095-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d095-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d095-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="5d095-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5d095-105">Parts</span></span>  
  
|<span data-ttu-id="5d095-106">Término</span><span class="sxs-lookup"><span data-stu-id="5d095-106">Term</span></span>|<span data-ttu-id="5d095-107">Definición</span><span class="sxs-lookup"><span data-stu-id="5d095-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="5d095-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5d095-108">Required.</span></span> <span data-ttu-id="5d095-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5d095-109">Any `Boolean` expression.</span></span> <span data-ttu-id="5d095-110">El resultado es el `Boolean` resultado de comparación de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="5d095-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="5d095-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5d095-111">Required.</span></span> <span data-ttu-id="5d095-112">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5d095-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="5d095-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5d095-113">Required.</span></span> <span data-ttu-id="5d095-114">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5d095-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d095-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d095-115">Remarks</span></span>  
 <span data-ttu-id="5d095-116">Se dice que una operación lógica sea *cortocircuitar* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="5d095-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="5d095-117">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, porque no se puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="5d095-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="5d095-118">Evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja, o si se trata de las llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5d095-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="5d095-119">Si ambas expresiones se evalúan como `True`, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="5d095-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="5d095-120">La tabla siguiente se muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="5d095-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="5d095-121">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="5d095-121">If `expression1` is</span></span>|<span data-ttu-id="5d095-122">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="5d095-122">And `expression2` is</span></span>|<span data-ttu-id="5d095-123">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="5d095-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="5d095-124">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="5d095-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="5d095-125">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5d095-125">Data Types</span></span>  
 <span data-ttu-id="5d095-126">El `AndAlso` operador está definido solo para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="5d095-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="5d095-127">Visual Basic convierte cada operando según sea necesario para `Boolean` antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="5d095-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="5d095-128">Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo de modo que `False` se convierte en `0` y `True` se convierte en `-1`.</span><span class="sxs-lookup"><span data-stu-id="5d095-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="5d095-129">Para obtener más información, consulte [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="5d095-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="5d095-130">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5d095-130">Overloading</span></span>  
 <span data-ttu-id="5d095-131">El [y operador](../../../visual-basic/language-reference/operators/and-operator.md) y [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo del que clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5d095-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5d095-132">Sobrecargar el `And` y `IsFalse` operadores afecta al comportamiento de la `AndAlso` operador.</span><span class="sxs-lookup"><span data-stu-id="5d095-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="5d095-133">Si el código usa `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="5d095-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="5d095-134">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5d095-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d095-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d095-135">Example</span></span>  
 <span data-ttu-id="5d095-136">En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="5d095-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="5d095-137">El resultado es un `Boolean` valor que indica si unidas de toda la expresión es true.</span><span class="sxs-lookup"><span data-stu-id="5d095-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="5d095-138">Si la primera expresión es `False`, no se evalúa el segundo.</span><span class="sxs-lookup"><span data-stu-id="5d095-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="5d095-139">El ejemplo anterior genera los resultados de `True`, `False`, y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5d095-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="5d095-140">En el cálculo de `secondCheck`, la segunda expresión no se evalúa porque ya se encuentra la primera `False`.</span><span class="sxs-lookup"><span data-stu-id="5d095-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="5d095-141">Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="5d095-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d095-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d095-142">Example</span></span>  
 <span data-ttu-id="5d095-143">El ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="5d095-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="5d095-144">Si la matriz está vacía, o si se superó la longitud de la matriz, el `While` instrucción no comprueba el elemento de matriz con el valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5d095-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="5d095-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d095-145">See also</span></span>

- [<span data-ttu-id="5d095-146">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d095-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="5d095-147">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d095-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5d095-148">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5d095-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5d095-149">And (operador)</span><span class="sxs-lookup"><span data-stu-id="5d095-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="5d095-150">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="5d095-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="5d095-151">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d095-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
