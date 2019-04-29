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
ms.openlocfilehash: 3876fd9c32d486b8ebecc9ee2428486a687a1624
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608325"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="7d309-102">AndAlso (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d309-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="7d309-103">Realiza una conjunción lógica de dos expresiones de cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="7d309-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d309-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d309-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7d309-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="7d309-105">Parts</span></span>  
  
|<span data-ttu-id="7d309-106">Término</span><span class="sxs-lookup"><span data-stu-id="7d309-106">Term</span></span>|<span data-ttu-id="7d309-107">Definición</span><span class="sxs-lookup"><span data-stu-id="7d309-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="7d309-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d309-108">Required.</span></span> <span data-ttu-id="7d309-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7d309-109">Any `Boolean` expression.</span></span> <span data-ttu-id="7d309-110">El resultado es el `Boolean` resultado de comparación de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="7d309-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="7d309-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d309-111">Required.</span></span> <span data-ttu-id="7d309-112">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7d309-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="7d309-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d309-113">Required.</span></span> <span data-ttu-id="7d309-114">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7d309-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d309-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d309-115">Remarks</span></span>  
 <span data-ttu-id="7d309-116">Se dice que una operación lógica sea *cortocircuitar* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="7d309-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="7d309-117">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, porque no se puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="7d309-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="7d309-118">Evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja, o si se trata de las llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7d309-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="7d309-119">Si ambas expresiones se evalúan como `True`, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="7d309-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="7d309-120">La tabla siguiente se muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="7d309-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7d309-121">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="7d309-121">If `expression1` is</span></span>|<span data-ttu-id="7d309-122">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="7d309-122">And `expression2` is</span></span>|<span data-ttu-id="7d309-123">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="7d309-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="7d309-124">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="7d309-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="7d309-125">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7d309-125">Data Types</span></span>  
 <span data-ttu-id="7d309-126">El `AndAlso` operador está definido solo para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7d309-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="7d309-127">Visual Basic convierte cada operando según sea necesario para `Boolean` y realiza la operación totalmente en `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7d309-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="7d309-128">Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="7d309-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="7d309-129">Esto podría producir un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="7d309-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="7d309-130">Por ejemplo, `5 AndAlso 12` da como resultado `–1` cuando se convierte en `Integer`.</span><span class="sxs-lookup"><span data-stu-id="7d309-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7d309-131">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="7d309-131">Overloading</span></span>  
 <span data-ttu-id="7d309-132">El [y operador](../../../visual-basic/language-reference/operators/and-operator.md) y [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo del que clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7d309-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7d309-133">Sobrecargar el `And` y `IsFalse` operadores afecta al comportamiento de la `AndAlso` operador.</span><span class="sxs-lookup"><span data-stu-id="7d309-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="7d309-134">Si el código usa `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="7d309-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="7d309-135">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d309-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d309-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d309-136">Example</span></span>  
 <span data-ttu-id="7d309-137">En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="7d309-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="7d309-138">El resultado es un `Boolean` valor que indica si unidas de toda la expresión es true.</span><span class="sxs-lookup"><span data-stu-id="7d309-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="7d309-139">Si la primera expresión es `False`, no se evalúa el segundo.</span><span class="sxs-lookup"><span data-stu-id="7d309-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="7d309-140">El ejemplo anterior genera los resultados de `True`, `False`, y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7d309-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="7d309-141">En el cálculo de `secondCheck`, la segunda expresión no se evalúa porque ya se encuentra la primera `False`.</span><span class="sxs-lookup"><span data-stu-id="7d309-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="7d309-142">Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="7d309-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d309-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d309-143">Example</span></span>  
 <span data-ttu-id="7d309-144">El ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="7d309-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="7d309-145">Si la matriz está vacía, o si se superó la longitud de la matriz, el `While` instrucción no comprueba el elemento de matriz con el valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d309-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="7d309-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d309-146">See also</span></span>

- [<span data-ttu-id="7d309-147">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d309-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="7d309-148">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d309-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7d309-149">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="7d309-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7d309-150">And (operador)</span><span class="sxs-lookup"><span data-stu-id="7d309-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="7d309-151">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="7d309-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="7d309-152">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d309-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
