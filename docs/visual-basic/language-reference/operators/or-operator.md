---
title: Or (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348249"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="4cf12-102">Or (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cf12-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="4cf12-103">Realiza una disyunción lógica entre dos expresiones `Boolean`, o una disyunción bit a bit entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="4cf12-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cf12-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4cf12-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4cf12-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4cf12-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4cf12-106">Required.</span></span> <span data-ttu-id="4cf12-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="4cf12-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="4cf12-108">En `Boolean` comparación, `result` es la disyunción lógica inclusiva de dos valores `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4cf12-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="4cf12-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción bit a bit inclusiva de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="4cf12-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4cf12-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4cf12-110">Required.</span></span> <span data-ttu-id="4cf12-111">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="4cf12-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4cf12-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4cf12-112">Required.</span></span> <span data-ttu-id="4cf12-113">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="4cf12-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf12-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4cf12-114">Remarks</span></span>  
 <span data-ttu-id="4cf12-115">Para la comparación de `Boolean`, `result` se `False` si y solo si `expression1` y `expression2` se evalúan como `False`.</span><span class="sxs-lookup"><span data-stu-id="4cf12-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="4cf12-116">En la tabla siguiente se muestra cómo se determina `result`.</span><span class="sxs-lookup"><span data-stu-id="4cf12-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4cf12-117">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-117">If `expression1` is</span></span>|<span data-ttu-id="4cf12-118">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-118">And `expression2` is</span></span>|<span data-ttu-id="4cf12-119">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="4cf12-120">En una comparación de `Boolean`, el operador `Or` siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4cf12-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="4cf12-121">El [operador OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `True`, `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="4cf12-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="4cf12-122">Para las operaciones bit a bit, el operador `Or` realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4cf12-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="4cf12-123">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-123">If bit in `expression1` is</span></span>|<span data-ttu-id="4cf12-124">Y el bit de `expression2` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-124">And bit in `expression2` is</span></span>|<span data-ttu-id="4cf12-125">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="4cf12-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="4cf12-126">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-126">1</span></span>|<span data-ttu-id="4cf12-127">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-127">1</span></span>|<span data-ttu-id="4cf12-128">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-128">1</span></span>|  
|<span data-ttu-id="4cf12-129">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-129">1</span></span>|<span data-ttu-id="4cf12-130">0</span><span class="sxs-lookup"><span data-stu-id="4cf12-130">0</span></span>|<span data-ttu-id="4cf12-131">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-131">1</span></span>|  
|<span data-ttu-id="4cf12-132">0</span><span class="sxs-lookup"><span data-stu-id="4cf12-132">0</span></span>|<span data-ttu-id="4cf12-133">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-133">1</span></span>|<span data-ttu-id="4cf12-134">1</span><span class="sxs-lookup"><span data-stu-id="4cf12-134">1</span></span>|  
|<span data-ttu-id="4cf12-135">0</span><span class="sxs-lookup"><span data-stu-id="4cf12-135">0</span></span>|<span data-ttu-id="4cf12-136">0</span><span class="sxs-lookup"><span data-stu-id="4cf12-136">0</span></span>|<span data-ttu-id="4cf12-137">0</span><span class="sxs-lookup"><span data-stu-id="4cf12-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="4cf12-138">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="4cf12-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4cf12-139">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4cf12-139">Data Types</span></span>  
 <span data-ttu-id="4cf12-140">Si los operandos constan de una expresión de `Boolean` y una expresión numérica, Visual Basic convierte la expresión de `Boolean` en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="4cf12-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="4cf12-141">Para una comparación de `Boolean`, se `Boolean`el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="4cf12-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="4cf12-142">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.</span><span class="sxs-lookup"><span data-stu-id="4cf12-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4cf12-143">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4cf12-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4cf12-144">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="4cf12-144">Overloading</span></span>  
 <span data-ttu-id="4cf12-145">El operador de `Or` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4cf12-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4cf12-146">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="4cf12-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4cf12-147">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4cf12-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf12-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cf12-148">Example</span></span>  
 <span data-ttu-id="4cf12-149">En el ejemplo siguiente se usa el operador `Or` para realizar una disyunción lógica inclusiva entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="4cf12-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="4cf12-150">El resultado es un valor `Boolean` que representa si una de las dos expresiones es `True`.</span><span class="sxs-lookup"><span data-stu-id="4cf12-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="4cf12-151">En el ejemplo anterior se generan los resultados de `True`, `True`y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4cf12-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf12-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cf12-152">Example</span></span>  
 <span data-ttu-id="4cf12-153">En el ejemplo siguiente se usa el operador `Or` para realizar una disyunción lógica inclusiva en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="4cf12-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="4cf12-154">El bit del modelo de resultado se establece si alguno de los bits correspondientes de los operandos se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="4cf12-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="4cf12-155">En el ejemplo anterior se generan resultados de 10, 14 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4cf12-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf12-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cf12-156">See also</span></span>

- [<span data-ttu-id="4cf12-157">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cf12-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="4cf12-158">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4cf12-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4cf12-159">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="4cf12-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4cf12-160">OrElse (operador)</span><span class="sxs-lookup"><span data-stu-id="4cf12-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="4cf12-161">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4cf12-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
