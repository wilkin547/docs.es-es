---
title: Xor (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b14f11f2df2df9c29e88e9188390cfe245d2cb58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="f8595-102">Xor (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8595-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="f8595-103">Realiza una exclusión lógica en dos `Boolean` expresiones o una exclusión bit a bit en dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="f8595-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8595-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8595-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f8595-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f8595-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f8595-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8595-106">Required.</span></span> <span data-ttu-id="f8595-107">Cualquier `Boolean` o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="f8595-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="f8595-108">Para la comparación booleana, `result` será la exclusión lógica (disyunción lógica exclusiva) de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="f8595-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="f8595-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la exclusión bit a bit (disyunción exclusiva bit a bit) de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="f8595-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="f8595-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8595-110">Required.</span></span> <span data-ttu-id="f8595-111">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f8595-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f8595-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8595-112">Required.</span></span> <span data-ttu-id="f8595-113">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f8595-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8595-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8595-114">Remarks</span></span>  
 <span data-ttu-id="f8595-115">Para la comparación booleana, `result` es `True` si y solo si exactamente uno de `expression1` y `expression2` se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="f8595-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="f8595-116">Es decir, si y solo si `expression1` y `expression2` evaluar opuesto a `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="f8595-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="f8595-117">La tabla siguiente se muestra cómo `result` viene determinado.</span><span class="sxs-lookup"><span data-stu-id="f8595-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f8595-118">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="f8595-118">If `expression1` is</span></span>|<span data-ttu-id="f8595-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="f8595-119">And `expression2` is</span></span>|<span data-ttu-id="f8595-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="f8595-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="f8595-121">En una comparación booleana, el `Xor` operador evalúa siempre las dos expresiones, lo que pudieron incluir realizar llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f8595-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="f8595-122">No hay ningún homólogo de cortocircuito para `Xor`, ya que el resultado depende siempre de ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="f8595-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="f8595-123">Para *evaluación "cortocircuitada"* operadores lógicos, consulte [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md) y [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f8595-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="f8595-124">Para las operaciones bit a bit, el `Xor` operador realiza una comparación bit a bit de bits colocados idénticamente en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8595-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f8595-125">Si bit en `expression1` es</span><span class="sxs-lookup"><span data-stu-id="f8595-125">If bit in `expression1` is</span></span>|<span data-ttu-id="f8595-126">Y que el bit de `expression2` es</span><span class="sxs-lookup"><span data-stu-id="f8595-126">And bit in `expression2` is</span></span>|<span data-ttu-id="f8595-127">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="f8595-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="f8595-128">1</span><span class="sxs-lookup"><span data-stu-id="f8595-128">1</span></span>|<span data-ttu-id="f8595-129">1</span><span class="sxs-lookup"><span data-stu-id="f8595-129">1</span></span>|<span data-ttu-id="f8595-130">0</span><span class="sxs-lookup"><span data-stu-id="f8595-130">0</span></span>|  
|<span data-ttu-id="f8595-131">1</span><span class="sxs-lookup"><span data-stu-id="f8595-131">1</span></span>|<span data-ttu-id="f8595-132">0</span><span class="sxs-lookup"><span data-stu-id="f8595-132">0</span></span>|<span data-ttu-id="f8595-133">1</span><span class="sxs-lookup"><span data-stu-id="f8595-133">1</span></span>|  
|<span data-ttu-id="f8595-134">0</span><span class="sxs-lookup"><span data-stu-id="f8595-134">0</span></span>|<span data-ttu-id="f8595-135">1</span><span class="sxs-lookup"><span data-stu-id="f8595-135">1</span></span>|<span data-ttu-id="f8595-136">1</span><span class="sxs-lookup"><span data-stu-id="f8595-136">1</span></span>|  
|<span data-ttu-id="f8595-137">0</span><span class="sxs-lookup"><span data-stu-id="f8595-137">0</span></span>|<span data-ttu-id="f8595-138">0</span><span class="sxs-lookup"><span data-stu-id="f8595-138">0</span></span>|<span data-ttu-id="f8595-139">0</span><span class="sxs-lookup"><span data-stu-id="f8595-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f8595-140">Dado que los operadores lógicos y bit a bit tienen una prioridad inferior a otros operadores aritméticos y relacionales, las operaciones bit a bit deben incluirse entre paréntesis para garantizar una correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="f8595-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="f8595-141">Por ejemplo, 5 `Xor` 3 es 6.</span><span class="sxs-lookup"><span data-stu-id="f8595-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="f8595-142">Para ver por qué esto es por lo tanto, convierta 5 y 3 en sus representaciones binarias, 101 y 011.</span><span class="sxs-lookup"><span data-stu-id="f8595-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="f8595-143">A continuación, utilice la tabla anterior para determinar que 101 Xor 011 es 110, que es la representación binaria del número decimal 6.</span><span class="sxs-lookup"><span data-stu-id="f8595-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f8595-144">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f8595-144">Data Types</span></span>  
 <span data-ttu-id="f8595-145">Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte el `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="f8595-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="f8595-146">Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f8595-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f8595-147">Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.</span><span class="sxs-lookup"><span data-stu-id="f8595-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f8595-148">Vea la tabla "relacionales y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="f8595-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f8595-149">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f8595-149">Overloading</span></span>  
 <span data-ttu-id="f8595-150">El `Xor` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f8595-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f8595-151">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f8595-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="f8595-152">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f8595-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8595-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8595-153">Example</span></span>  
 <span data-ttu-id="f8595-154">En el ejemplo siguiente se usa el `Xor` operador que se va a realizar una exclusión lógica (disyunción lógica exclusiva) de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="f8595-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="f8595-155">El resultado es un `Boolean` valor que indica si exactamente una de las expresiones es `True`.</span><span class="sxs-lookup"><span data-stu-id="f8595-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="f8595-156">El ejemplo anterior genera unos resultados de `False`, `True`, y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f8595-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8595-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8595-157">Example</span></span>  
 <span data-ttu-id="f8595-158">En el ejemplo siguiente se usa el `Xor` operador que se va a realizar una exclusión lógica (disyunción lógica exclusiva) en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="f8595-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="f8595-159">El bit en el modelo resultante se establece si exactamente uno de los bits correspondientes de los operandos se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="f8595-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="f8595-160">En el ejemplo anterior se genera los resultados de 2, 12 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f8595-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8595-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8595-161">See Also</span></span>  
 [<span data-ttu-id="f8595-162">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8595-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="f8595-163">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8595-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="f8595-164">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f8595-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="f8595-165">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8595-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
