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
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913169"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="33a6d-102">And (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33a6d-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="33a6d-103">Realiza una conjunción lógica de `Boolean` dos expresiones o una conjunción bit a bit de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="33a6d-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a6d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33a6d-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="33a6d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="33a6d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="33a6d-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="33a6d-106">Required.</span></span> <span data-ttu-id="33a6d-107">Cualquier `Boolean` expresión numérica o.</span><span class="sxs-lookup"><span data-stu-id="33a6d-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="33a6d-108">En la comparación booleana `result` , es la conjunción lógica `Boolean` de dos valores.</span><span class="sxs-lookup"><span data-stu-id="33a6d-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="33a6d-109">Para las operaciones bit `result` a bit, es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="33a6d-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="33a6d-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="33a6d-110">Required.</span></span> <span data-ttu-id="33a6d-111">Cualquier `Boolean` expresión numérica o.</span><span class="sxs-lookup"><span data-stu-id="33a6d-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="33a6d-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="33a6d-112">Required.</span></span> <span data-ttu-id="33a6d-113">Cualquier `Boolean` expresión numérica o.</span><span class="sxs-lookup"><span data-stu-id="33a6d-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33a6d-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33a6d-114">Remarks</span></span>  
 <span data-ttu-id="33a6d-115">En la comparación booleana `result` , `True` es `expression1` si y solo si y `expression2` se evalúan como `True`.</span><span class="sxs-lookup"><span data-stu-id="33a6d-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="33a6d-116">En la tabla siguiente se muestra `result` cómo se determina.</span><span class="sxs-lookup"><span data-stu-id="33a6d-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="33a6d-117">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="33a6d-117">If `expression1` is</span></span>|<span data-ttu-id="33a6d-118">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="33a6d-118">And `expression2` is</span></span>|<span data-ttu-id="33a6d-119">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="33a6d-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="33a6d-120">En una comparación booleana, el `And` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="33a6d-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="33a6d-121">El [operador AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `False`, `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="33a6d-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="33a6d-122">Cuando se aplica a valores numéricos `And` , el operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos `result` expresiones numéricas y establece el bit correspondiente en de acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="33a6d-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="33a6d-123">Si el bit `expression1` de es</span><span class="sxs-lookup"><span data-stu-id="33a6d-123">If bit in `expression1` is</span></span>|<span data-ttu-id="33a6d-124">Y el bit `expression2` en es</span><span class="sxs-lookup"><span data-stu-id="33a6d-124">And bit in `expression2` is</span></span>|<span data-ttu-id="33a6d-125">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="33a6d-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="33a6d-126">1</span><span class="sxs-lookup"><span data-stu-id="33a6d-126">1</span></span>|<span data-ttu-id="33a6d-127">1</span><span class="sxs-lookup"><span data-stu-id="33a6d-127">1</span></span>|<span data-ttu-id="33a6d-128">1</span><span class="sxs-lookup"><span data-stu-id="33a6d-128">1</span></span>|  
|<span data-ttu-id="33a6d-129">1</span><span class="sxs-lookup"><span data-stu-id="33a6d-129">1</span></span>|<span data-ttu-id="33a6d-130">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-130">0</span></span>|<span data-ttu-id="33a6d-131">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-131">0</span></span>|  
|<span data-ttu-id="33a6d-132">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-132">0</span></span>|<span data-ttu-id="33a6d-133">1</span><span class="sxs-lookup"><span data-stu-id="33a6d-133">1</span></span>|<span data-ttu-id="33a6d-134">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-134">0</span></span>|  
|<span data-ttu-id="33a6d-135">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-135">0</span></span>|<span data-ttu-id="33a6d-136">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-136">0</span></span>|<span data-ttu-id="33a6d-137">0</span><span class="sxs-lookup"><span data-stu-id="33a6d-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="33a6d-138">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar resultados precisos.</span><span class="sxs-lookup"><span data-stu-id="33a6d-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="33a6d-139">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="33a6d-139">Data Types</span></span>  
 <span data-ttu-id="33a6d-140">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="33a6d-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="33a6d-141">En el caso de una comparación booleana, el tipo de datos `Boolean`del resultado es.</span><span class="sxs-lookup"><span data-stu-id="33a6d-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="33a6d-142">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para `expression1` los `expression2`tipos de datos de y.</span><span class="sxs-lookup"><span data-stu-id="33a6d-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="33a6d-143">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="33a6d-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33a6d-144">El `And` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="33a6d-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="33a6d-145">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="33a6d-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="33a6d-146">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="33a6d-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33a6d-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33a6d-147">Example</span></span>  
 <span data-ttu-id="33a6d-148">En el ejemplo siguiente se `And` usa el operador para realizar una conjunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="33a6d-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="33a6d-149">El resultado es un `Boolean` valor que representa si ambas expresiones son. `True`</span><span class="sxs-lookup"><span data-stu-id="33a6d-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="33a6d-150">En el ejemplo anterior se generan `True` los `False`resultados de y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="33a6d-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33a6d-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33a6d-151">Example</span></span>  
 <span data-ttu-id="33a6d-152">En el ejemplo siguiente se `And` usa el operador para realizar una conjunción lógica de los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="33a6d-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="33a6d-153">El bit en el patrón del resultado se establece si los bits correspondientes de los operandos están establecidos en 1.</span><span class="sxs-lookup"><span data-stu-id="33a6d-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="33a6d-154">En el ejemplo anterior se generan los resultados de 8, 2 y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="33a6d-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a6d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="33a6d-155">See also</span></span>

- [<span data-ttu-id="33a6d-156">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33a6d-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="33a6d-157">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33a6d-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="33a6d-158">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="33a6d-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="33a6d-159">AndAlso (operador)</span><span class="sxs-lookup"><span data-stu-id="33a6d-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="33a6d-160">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33a6d-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
