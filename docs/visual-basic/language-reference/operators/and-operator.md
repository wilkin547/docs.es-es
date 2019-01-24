---
title: And (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 2cdc272c07f3b30f61716f0c5ae72f0655c3f46b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597325"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="9f807-102">And (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f807-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="9f807-103">Realiza una conjunción lógica de dos `Boolean` expresiones o una conjunción bit a bit de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="9f807-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f807-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f807-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9f807-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="9f807-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9f807-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9f807-106">Required.</span></span> <span data-ttu-id="9f807-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="9f807-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="9f807-108">Para la comparación booleana, `result` es la conjunción lógica de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="9f807-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="9f807-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="9f807-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9f807-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9f807-110">Required.</span></span> <span data-ttu-id="9f807-111">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="9f807-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9f807-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9f807-112">Required.</span></span> <span data-ttu-id="9f807-113">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="9f807-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f807-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f807-114">Remarks</span></span>  
 <span data-ttu-id="9f807-115">Para la comparación booleana, `result` es `True` si y solo si ambos `expression1` y `expression2` se evalúan como `True`.</span><span class="sxs-lookup"><span data-stu-id="9f807-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="9f807-116">La tabla siguiente se muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="9f807-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="9f807-117">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="9f807-117">If `expression1` is</span></span>|<span data-ttu-id="9f807-118">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="9f807-118">And `expression2` is</span></span>|<span data-ttu-id="9f807-119">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="9f807-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="9f807-120">En una comparación booleana, el `And` operador siempre evalúa ambas expresiones, lo que podrían incluir la realización de llamadas de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9f807-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="9f807-121">El [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) realiza *cortocircuitar*, lo que significa que si `expression1` es `False`, a continuación, `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="9f807-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="9f807-122">Cuando se aplica a valores numéricos, el `And` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f807-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="9f807-123">Si bit en `expression1` es</span><span class="sxs-lookup"><span data-stu-id="9f807-123">If bit in `expression1` is</span></span>|<span data-ttu-id="9f807-124">Y que el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="9f807-124">And bit in `expression2` is</span></span>|<span data-ttu-id="9f807-125">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="9f807-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="9f807-126">1</span><span class="sxs-lookup"><span data-stu-id="9f807-126">1</span></span>|<span data-ttu-id="9f807-127">1</span><span class="sxs-lookup"><span data-stu-id="9f807-127">1</span></span>|<span data-ttu-id="9f807-128">1</span><span class="sxs-lookup"><span data-stu-id="9f807-128">1</span></span>|  
|<span data-ttu-id="9f807-129">1</span><span class="sxs-lookup"><span data-stu-id="9f807-129">1</span></span>|<span data-ttu-id="9f807-130">0</span><span class="sxs-lookup"><span data-stu-id="9f807-130">0</span></span>|<span data-ttu-id="9f807-131">0</span><span class="sxs-lookup"><span data-stu-id="9f807-131">0</span></span>|  
|<span data-ttu-id="9f807-132">0</span><span class="sxs-lookup"><span data-stu-id="9f807-132">0</span></span>|<span data-ttu-id="9f807-133">1</span><span class="sxs-lookup"><span data-stu-id="9f807-133">1</span></span>|<span data-ttu-id="9f807-134">0</span><span class="sxs-lookup"><span data-stu-id="9f807-134">0</span></span>|  
|<span data-ttu-id="9f807-135">0</span><span class="sxs-lookup"><span data-stu-id="9f807-135">0</span></span>|<span data-ttu-id="9f807-136">0</span><span class="sxs-lookup"><span data-stu-id="9f807-136">0</span></span>|<span data-ttu-id="9f807-137">0</span><span class="sxs-lookup"><span data-stu-id="9f807-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9f807-138">Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar resultados precisos.</span><span class="sxs-lookup"><span data-stu-id="9f807-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="9f807-139">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9f807-139">Data Types</span></span>  
 <span data-ttu-id="9f807-140">Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="9f807-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="9f807-141">Para obtener una comparación booleana, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9f807-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="9f807-142">Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.</span><span class="sxs-lookup"><span data-stu-id="9f807-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="9f807-143">Vea la tabla "relacional y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="9f807-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f807-144">El `And` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9f807-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9f807-145">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="9f807-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9f807-146">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9f807-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f807-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f807-147">Example</span></span>  
 <span data-ttu-id="9f807-148">En el ejemplo siguiente se usa el `And` operador para realizar una conjunción lógica de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="9f807-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="9f807-149">El resultado es un `Boolean` valor que indica si las dos expresiones son `True`.</span><span class="sxs-lookup"><span data-stu-id="9f807-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 <span data-ttu-id="9f807-150">El ejemplo anterior genera los resultados de `True` y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9f807-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f807-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f807-151">Example</span></span>  
 <span data-ttu-id="9f807-152">En el ejemplo siguiente se usa el `And` operador para realizar la conjunción lógica de los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="9f807-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="9f807-153">El bit en el modelo resultante se establece si los bits correspondientes de los operandos se establecen en 1.</span><span class="sxs-lookup"><span data-stu-id="9f807-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 <span data-ttu-id="9f807-154">El ejemplo anterior genera los resultados de 8, 2 y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9f807-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f807-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f807-155">See also</span></span>
- [<span data-ttu-id="9f807-156">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f807-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="9f807-157">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f807-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9f807-158">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="9f807-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9f807-159">AndAlso (operador)</span><span class="sxs-lookup"><span data-stu-id="9f807-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="9f807-160">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f807-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
