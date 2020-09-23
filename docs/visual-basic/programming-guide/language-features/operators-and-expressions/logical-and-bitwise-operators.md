---
title: Operadores lógicos y bit a bit
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: c15b9337f262563941699c0ff8fe5219ca6a5c93
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086002"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="fa474-102">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa474-102">Logical and Bitwise Operators in Visual Basic</span></span>

<span data-ttu-id="fa474-103">Los operadores lógicos comparan `Boolean` expresiones y devuelven un `Boolean` resultado.</span><span class="sxs-lookup"><span data-stu-id="fa474-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="fa474-104">Los `And` `Or` operadores,, `AndAlso` , `OrElse` y `Xor` son *binarios* porque toman dos operandos, mientras que el `Not` operador es *unario* porque toma un solo operando.</span><span class="sxs-lookup"><span data-stu-id="fa474-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="fa474-105">Algunos de estos operadores también pueden realizar operaciones lógicas bit a bit en valores enteros.</span><span class="sxs-lookup"><span data-stu-id="fa474-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="fa474-106">Operador lógico unario</span><span class="sxs-lookup"><span data-stu-id="fa474-106">Unary Logical Operator</span></span>  

 <span data-ttu-id="fa474-107">El [operador not](../../../language-reference/operators/not-operator.md) realiza una *negación* lógica en una `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="fa474-107">The [Not Operator](../../../language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="fa474-108">Produce el contrario lógico de su operando.</span><span class="sxs-lookup"><span data-stu-id="fa474-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="fa474-109">Si la expresión se evalúa como `True` , `Not` devuelve `False` ; si la expresión se evalúa como `False` , entonces `Not` devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="fa474-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="fa474-110">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa474-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="fa474-111">Operadores lógicos binarios</span><span class="sxs-lookup"><span data-stu-id="fa474-111">Binary Logical Operators</span></span>  

 <span data-ttu-id="fa474-112">El [operador and](../../../language-reference/operators/and-operator.md) realiza una *conjunción* lógica entre dos `Boolean` expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa474-112">The [And Operator](../../../language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="fa474-113">Si ambas expresiones se evalúan como `True` , `And` devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="fa474-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="fa474-114">Si al menos una de las expresiones se evalúa como `False` , entonces `And` devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="fa474-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="fa474-115">El [operador OR](../../../language-reference/operators/or-operator.md) realiza una *disyunción* lógica o una *inclusión* en dos `Boolean` expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa474-115">The [Or Operator](../../../language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="fa474-116">Si una de las expresiones se evalúa como `True` , o ambos se evalúan como `True` , entonces `Or` devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="fa474-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="fa474-117">Si ninguna de las expresiones se evalúa como `True` , `Or` devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="fa474-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="fa474-118">El [operador XOR](../../../language-reference/operators/xor-operator.md) realiza una *exclusión* lógica en dos `Boolean` expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa474-118">The [Xor Operator](../../../language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="fa474-119">Si exactamente una expresión se evalúa como `True` , pero no ambos, `Xor` devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="fa474-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="fa474-120">Si ambas expresiones se evalúan como `True` o se evalúan como `False` , `Xor` devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="fa474-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="fa474-121">En el ejemplo siguiente se muestran `And` los `Or` operadores, y `Xor` .</span><span class="sxs-lookup"><span data-stu-id="fa474-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="fa474-122">Operaciones lógicas de cortocircuito</span><span class="sxs-lookup"><span data-stu-id="fa474-122">Short-Circuiting Logical Operations</span></span>  

 <span data-ttu-id="fa474-123">El [operador AndAlso](../../../language-reference/operators/andalso-operator.md) es muy similar al `And` operador, ya que también realiza una conjunción lógica de dos `Boolean` expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa474-123">The [AndAlso Operator](../../../language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="fa474-124">La diferencia clave entre ambos es que `AndAlso` exhibe *un comportamiento de cortocircuito* .</span><span class="sxs-lookup"><span data-stu-id="fa474-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="fa474-125">Si la primera expresión de una `AndAlso` expresión se evalúa como `False` , la segunda expresión no se evalúa porque no puede modificar el resultado final y `AndAlso` devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="fa474-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="fa474-126">Del mismo modo, el [operador OrElse](../../../language-reference/operators/orelse-operator.md) realiza una disyunción lógica de cortocircuito en dos `Boolean` expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa474-126">Similarly, the [OrElse Operator](../../../language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="fa474-127">Si la primera expresión de una `OrElse` expresión se evalúa como `True` , la segunda expresión no se evalúa porque no puede modificar el resultado final y `OrElse` devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="fa474-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="fa474-128">Equilibrio de cortocircuito</span><span class="sxs-lookup"><span data-stu-id="fa474-128">Short-Circuiting Trade-Offs</span></span>  

 <span data-ttu-id="fa474-129">El cortocircuito puede mejorar el rendimiento al no evaluar una expresión que no pueda modificar el resultado de la operación lógica.</span><span class="sxs-lookup"><span data-stu-id="fa474-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="fa474-130">Sin embargo, si esa expresión realiza acciones adicionales, el cortocircuito omite esas acciones.</span><span class="sxs-lookup"><span data-stu-id="fa474-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="fa474-131">Por ejemplo, si la expresión incluye una llamada a un `Function` procedimiento, no se llama a ese procedimiento si la expresión se cortocircuita y no se ejecuta ningún código adicional incluido en `Function` .</span><span class="sxs-lookup"><span data-stu-id="fa474-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="fa474-132">Por lo tanto, la función puede ejecutarse solo ocasionalmente y no se puede probar correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa474-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="fa474-133">O la lógica del programa podría depender del código del `Function` .</span><span class="sxs-lookup"><span data-stu-id="fa474-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="fa474-134">En el ejemplo siguiente se muestra la diferencia entre `And` , `Or` y sus homólogos de cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="fa474-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="fa474-135">En el ejemplo anterior, tenga en cuenta que algunos códigos importantes `checkIfValid()` de no se ejecutan cuando la llamada está en cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="fa474-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="fa474-136">La primera `If` instrucción llama a `checkIfValid()` aunque `12 > 45` devuelve `False` , porque `And` no cortocircuita.</span><span class="sxs-lookup"><span data-stu-id="fa474-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="fa474-137">La segunda `If` instrucción no llama a `checkIfValid()` porque, cuando `12 > 45` devuelve `False` , `AndAlso` cortocircuita la segunda expresión.</span><span class="sxs-lookup"><span data-stu-id="fa474-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="fa474-138">La tercera `If` instrucción llama a `checkIfValid()` aunque `12 < 45` devuelve `True` , porque `Or` no cortocircuita.</span><span class="sxs-lookup"><span data-stu-id="fa474-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="fa474-139">La cuarta `If` instrucción no llama a `checkIfValid()` porque, cuando `12 < 45` devuelve `True` , `OrElse` cortocircuita la segunda expresión.</span><span class="sxs-lookup"><span data-stu-id="fa474-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="fa474-140">Operaciones bit a bit</span><span class="sxs-lookup"><span data-stu-id="fa474-140">Bitwise Operations</span></span>  

 <span data-ttu-id="fa474-141">Las operaciones bit a bit evalúan dos valores enteros en formato binario (base 2).</span><span class="sxs-lookup"><span data-stu-id="fa474-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="fa474-142">Comparan los bits en las posiciones correspondientes y, a continuación, asignan valores basados en la comparación.</span><span class="sxs-lookup"><span data-stu-id="fa474-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="fa474-143">En el siguiente ejemplo se muestra el `And` operador.</span><span class="sxs-lookup"><span data-stu-id="fa474-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="fa474-144">En el ejemplo anterior se establece el valor de `x` en 1.</span><span class="sxs-lookup"><span data-stu-id="fa474-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="fa474-145">Esto sucede por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="fa474-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="fa474-146">Los valores se tratan como binarios:</span><span class="sxs-lookup"><span data-stu-id="fa474-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="fa474-147">3 en formato binario = 011</span><span class="sxs-lookup"><span data-stu-id="fa474-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="fa474-148">5 en formato binario = 101</span><span class="sxs-lookup"><span data-stu-id="fa474-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="fa474-149">El `And` operador compara las representaciones binarias, una posición binaria (bit) a la vez.</span><span class="sxs-lookup"><span data-stu-id="fa474-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="fa474-150">Si los dos bits de una posición determinada son 1, se coloca un 1 en esa posición en el resultado.</span><span class="sxs-lookup"><span data-stu-id="fa474-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="fa474-151">Si alguno de los bits es 0, se coloca un 0 en esa posición en el resultado.</span><span class="sxs-lookup"><span data-stu-id="fa474-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="fa474-152">En el ejemplo anterior, esto funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fa474-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="fa474-153">011 (3 en formato binario)</span><span class="sxs-lookup"><span data-stu-id="fa474-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="fa474-154">101 (5 en formato binario)</span><span class="sxs-lookup"><span data-stu-id="fa474-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="fa474-155">001 (el resultado, en formato binario)</span><span class="sxs-lookup"><span data-stu-id="fa474-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="fa474-156">El resultado se trata como decimal.</span><span class="sxs-lookup"><span data-stu-id="fa474-156">The result is treated as decimal.</span></span> <span data-ttu-id="fa474-157">El valor 001 es la representación binaria de 1, por lo que `x` = 1.</span><span class="sxs-lookup"><span data-stu-id="fa474-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="fa474-158">La `Or` operación bit a bit es similar, salvo que se asigna 1 al bit de resultado si uno de los bits comparados es 1 o ambos.</span><span class="sxs-lookup"><span data-stu-id="fa474-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="fa474-159">`Xor` asigna un 1 al bit de resultado si exactamente uno de los bits comparados (no ambos) es 1.</span><span class="sxs-lookup"><span data-stu-id="fa474-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="fa474-160">`Not` toma un solo operando e invierte todos los bits, incluido el bit de signo, y asigna ese valor al resultado.</span><span class="sxs-lookup"><span data-stu-id="fa474-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="fa474-161">Esto significa que para los números positivos con signo, `Not` siempre devolverá un valor negativo y, en el caso de números negativos, `Not` siempre devolverá un valor positivo o cero.</span><span class="sxs-lookup"><span data-stu-id="fa474-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="fa474-162">Los `AndAlso` `OrElse` operadores y no admiten las operaciones bit a bit.</span><span class="sxs-lookup"><span data-stu-id="fa474-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa474-163">Las operaciones bit a bit solo se pueden realizar en tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="fa474-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="fa474-164">Los valores de punto flotante se deben convertir en tipos enteros antes de que pueda continuar la operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="fa474-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa474-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa474-165">See also</span></span>

- [<span data-ttu-id="fa474-166">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa474-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="fa474-167">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="fa474-167">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="fa474-168">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa474-168">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="fa474-169">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa474-169">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="fa474-170">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa474-170">Concatenation Operators in Visual Basic</span></span>](concatenation-operators.md)
- [<span data-ttu-id="fa474-171">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="fa474-171">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
