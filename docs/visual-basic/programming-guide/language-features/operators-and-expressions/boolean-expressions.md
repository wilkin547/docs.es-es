---
description: 'Más información acerca de: Expresiones booleanas (Visual Basic)'
title: Expresiones booleanas
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 3b752e2146755e1272b261f32931e3022e8ef354
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465319"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="fec7d-103">Expresiones booleanas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fec7d-103">Boolean Expressions (Visual Basic)</span></span>

<span data-ttu-id="fec7d-104">Una *expresión booleana* es una expresión que se evalúa como un valor del [tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md): `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-104">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="fec7d-105">`Boolean` las expresiones pueden tomar varias formas.</span><span class="sxs-lookup"><span data-stu-id="fec7d-105">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="fec7d-106">La más simple es la comparación directa del valor de una `Boolean` variable con un `Boolean` literal, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fec7d-106">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="fec7d-107">Dos significados del operador =</span><span class="sxs-lookup"><span data-stu-id="fec7d-107">Two Meanings of the = Operator</span></span>  

 <span data-ttu-id="fec7d-108">Observe que la instrucción `newCustomer = True` de asignación tiene el mismo aspecto que la expresión del ejemplo anterior, pero realiza una función diferente y se usa de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="fec7d-108">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="fec7d-109">En el ejemplo anterior, la expresión `newCustomer = True` representa un valor booleano y el `=` signo se interpreta como un operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="fec7d-109">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="fec7d-110">En una instrucción independiente, el `=` signo se interpreta como un operador de asignación y asigna el valor de la derecha a la variable de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="fec7d-110">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="fec7d-111">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fec7d-111">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="fec7d-112">Para obtener más información, vea [comparaciones de valores](value-comparisons.md) e [instrucciones](../../../language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="fec7d-112">For further information, see [Value Comparisons](value-comparisons.md) and [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="fec7d-113">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="fec7d-113">Comparison Operators</span></span>  

 <span data-ttu-id="fec7d-114">Los operadores de comparación, como `=` ,, `<` `>` , `<>` , `<=` y `>=` generan Expresiones booleanas comparando la expresión del lado izquierdo del operador con la expresión del lado derecho del operador y evaluando el resultado como `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-114">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="fec7d-115">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fec7d-115">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="fec7d-116">Dado que 42 es menor que 81, la expresión booleana en el ejemplo anterior se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-116">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="fec7d-117">Para obtener más información sobre este tipo de expresión, vea [comparaciones de valores](value-comparisons.md).</span><span class="sxs-lookup"><span data-stu-id="fec7d-117">For more information on this kind of expression, see [Value Comparisons](value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="fec7d-118">Operadores de comparación combinados con operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="fec7d-118">Comparison Operators Combined with Logical Operators</span></span>  

 <span data-ttu-id="fec7d-119">Las expresiones de comparación se pueden combinar mediante operadores lógicos para generar Expresiones booleanas más complejas.</span><span class="sxs-lookup"><span data-stu-id="fec7d-119">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="fec7d-120">En el ejemplo siguiente se muestra el uso de operadores de comparación junto con un operador lógico.</span><span class="sxs-lookup"><span data-stu-id="fec7d-120">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="fec7d-121">En el ejemplo anterior, el valor de la expresión general depende de los valores de las expresiones de cada lado del `And` operador.</span><span class="sxs-lookup"><span data-stu-id="fec7d-121">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="fec7d-122">Si ambas expresiones son `True` , la expresión general se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-122">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="fec7d-123">Si alguna `False` de las expresiones es, toda la expresión se evalúa como `False` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-123">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="fec7d-124">Operadores de Short-Circuiting</span><span class="sxs-lookup"><span data-stu-id="fec7d-124">Short-Circuiting Operators</span></span>  

 <span data-ttu-id="fec7d-125">Los operadores lógicos y el comportamiento de los `AndAlso` `OrElse` exhibes se conocen como cortocircuitos. </span><span class="sxs-lookup"><span data-stu-id="fec7d-125">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="fec7d-126">Un operador de cortocircuito evalúa primero el operando izquierdo.</span><span class="sxs-lookup"><span data-stu-id="fec7d-126">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="fec7d-127">Si el operando izquierdo determina el valor de toda la expresión, la ejecución del programa continúa sin evaluar la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="fec7d-127">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="fec7d-128">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fec7d-128">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="fec7d-129">En el ejemplo anterior, el operador evalúa la expresión de la izquierda, `45 < 12` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-129">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="fec7d-130">Dado que la expresión de la izquierda se evalúa como `False` , toda la expresión lógica debe evaluarse como `False` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-130">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="fec7d-131">Así, la ejecución del programa omite la ejecución del código dentro del `If` bloque sin evaluar la expresión de la derecha, `testFunction(3)` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-131">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="fec7d-132">En este ejemplo no se llama a `testFunction()` porque la expresión de la izquierda falsea toda la expresión.</span><span class="sxs-lookup"><span data-stu-id="fec7d-132">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="fec7d-133">Del mismo modo, si la expresión de la izquierda en una expresión lógica con `OrElse` se evalúa como `True` , la ejecución continúa en la siguiente línea de código sin evaluar la expresión de la derecha, ya que la expresión de la izquierda ya ha validado toda la expresión.</span><span class="sxs-lookup"><span data-stu-id="fec7d-133">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="fec7d-134">Comparación con operadores que no son de cortocircuito</span><span class="sxs-lookup"><span data-stu-id="fec7d-134">Comparison with Non-Short-Circuiting Operators</span></span>  

 <span data-ttu-id="fec7d-135">Por el contrario, los dos lados del operador lógico se evalúan cuando se usan los operadores lógicos `And` y `Or` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-135">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="fec7d-136">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fec7d-136">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="fec7d-137">En el ejemplo anterior `testFunction()` se llama a, aunque la expresión de la izquierda se evalúe como `False` .</span><span class="sxs-lookup"><span data-stu-id="fec7d-137">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="fec7d-138">Expresiones entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="fec7d-138">Parenthetical Expressions</span></span>  

 <span data-ttu-id="fec7d-139">Puede usar paréntesis para controlar el orden de evaluación de las Expresiones booleanas.</span><span class="sxs-lookup"><span data-stu-id="fec7d-139">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="fec7d-140">Las expresiones entre paréntesis se evalúan primero.</span><span class="sxs-lookup"><span data-stu-id="fec7d-140">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="fec7d-141">En el caso de varios niveles de anidamiento, la prioridad se concede a las expresiones más anidadas.</span><span class="sxs-lookup"><span data-stu-id="fec7d-141">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="fec7d-142">Entre paréntesis, la evaluación continúa según las reglas de prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="fec7d-142">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="fec7d-143">Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="fec7d-143">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec7d-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fec7d-144">See also</span></span>

- [<span data-ttu-id="fec7d-145">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fec7d-145">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="fec7d-146">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="fec7d-146">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="fec7d-147">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="fec7d-147">Statements</span></span>](../statements.md)
- [<span data-ttu-id="fec7d-148">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="fec7d-148">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="fec7d-149">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="fec7d-149">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
- [<span data-ttu-id="fec7d-150">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fec7d-150">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fec7d-151">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="fec7d-151">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)
