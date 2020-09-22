---
title: Operador Xor
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
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
ms.openlocfilehash: ce7592c73f387d6ddbfd328abce8555cb7dcd303
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875298"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="452d6-102">Xor (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="452d6-102">Xor Operator (Visual Basic)</span></span>

<span data-ttu-id="452d6-103">Realiza una exclusión lógica en dos `Boolean` expresiones o una exclusión bit a bit en dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="452d6-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="452d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="452d6-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="452d6-105">Partes</span><span class="sxs-lookup"><span data-stu-id="452d6-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="452d6-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="452d6-106">Required.</span></span> <span data-ttu-id="452d6-107">Any `Boolean` o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="452d6-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="452d6-108">En la comparación booleana, `result` es la exclusión lógica (disyunción lógica exclusiva) de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="452d6-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="452d6-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la exclusión bit a bit (disyunción bit a bit exclusiva) de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="452d6-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="452d6-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="452d6-110">Required.</span></span> <span data-ttu-id="452d6-111">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="452d6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="452d6-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="452d6-112">Required.</span></span> <span data-ttu-id="452d6-113">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="452d6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="452d6-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="452d6-114">Remarks</span></span>  

 <span data-ttu-id="452d6-115">En la comparación booleana, `result` es `True` si y solo si exactamente uno de `expression1` y `expression2` se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="452d6-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="452d6-116">Es decir, si y solo si `expression1` y `expression2` se evalúan como valores opuestos `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="452d6-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="452d6-117">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="452d6-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="452d6-118">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="452d6-118">If `expression1` is</span></span>|<span data-ttu-id="452d6-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="452d6-119">And `expression2` is</span></span>|<span data-ttu-id="452d6-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="452d6-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="452d6-121">En una comparación booleana, el `Xor` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="452d6-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="452d6-122">No hay ningún homólogo de cortocircuito en `Xor` , porque el resultado siempre depende de ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="452d6-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="452d6-123">Para los operadores lógicos de *cortocircuito* , vea [operador AndAlso](andalso-operator.md) y [operador OrElse](orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="452d6-123">For *short-circuiting* logical operators, see [AndAlso Operator](andalso-operator.md) and [OrElse Operator](orelse-operator.md).</span></span>  
  
 <span data-ttu-id="452d6-124">Para las operaciones bit a bit, el `Xor` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="452d6-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="452d6-125">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="452d6-125">If bit in `expression1` is</span></span>|<span data-ttu-id="452d6-126">Y el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="452d6-126">And bit in `expression2` is</span></span>|<span data-ttu-id="452d6-127">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="452d6-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="452d6-128">1</span><span class="sxs-lookup"><span data-stu-id="452d6-128">1</span></span>|<span data-ttu-id="452d6-129">1</span><span class="sxs-lookup"><span data-stu-id="452d6-129">1</span></span>|<span data-ttu-id="452d6-130">0</span><span class="sxs-lookup"><span data-stu-id="452d6-130">0</span></span>|  
|<span data-ttu-id="452d6-131">1</span><span class="sxs-lookup"><span data-stu-id="452d6-131">1</span></span>|<span data-ttu-id="452d6-132">0</span><span class="sxs-lookup"><span data-stu-id="452d6-132">0</span></span>|<span data-ttu-id="452d6-133">1</span><span class="sxs-lookup"><span data-stu-id="452d6-133">1</span></span>|  
|<span data-ttu-id="452d6-134">0</span><span class="sxs-lookup"><span data-stu-id="452d6-134">0</span></span>|<span data-ttu-id="452d6-135">1</span><span class="sxs-lookup"><span data-stu-id="452d6-135">1</span></span>|<span data-ttu-id="452d6-136">1</span><span class="sxs-lookup"><span data-stu-id="452d6-136">1</span></span>|  
|<span data-ttu-id="452d6-137">0</span><span class="sxs-lookup"><span data-stu-id="452d6-137">0</span></span>|<span data-ttu-id="452d6-138">0</span><span class="sxs-lookup"><span data-stu-id="452d6-138">0</span></span>|<span data-ttu-id="452d6-139">0</span><span class="sxs-lookup"><span data-stu-id="452d6-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="452d6-140">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="452d6-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="452d6-141">Por ejemplo, 5 `Xor` 3 es 6.</span><span class="sxs-lookup"><span data-stu-id="452d6-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="452d6-142">Para ver por qué es así, convierta 5 y 3 en sus representaciones binarias, 101 y 011.</span><span class="sxs-lookup"><span data-stu-id="452d6-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="452d6-143">A continuación, use la tabla anterior para determinar que 101 XOR 011 es 110, que es la representación binaria del número decimal 6.</span><span class="sxs-lookup"><span data-stu-id="452d6-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="452d6-144">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="452d6-144">Data Types</span></span>  

 <span data-ttu-id="452d6-145">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False` ) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="452d6-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="452d6-146">Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="452d6-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="452d6-147">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="452d6-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="452d6-148">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="452d6-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="452d6-149">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="452d6-149">Overloading</span></span>  

 <span data-ttu-id="452d6-150">El `Xor` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="452d6-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="452d6-151">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="452d6-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="452d6-152">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="452d6-152">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="452d6-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="452d6-153">Example</span></span>  

 <span data-ttu-id="452d6-154">En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="452d6-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="452d6-155">El resultado es un `Boolean` valor que indica si exactamente una de las expresiones es `True` .</span><span class="sxs-lookup"><span data-stu-id="452d6-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="452d6-156">En el ejemplo anterior se generan los resultados de `False` , `True` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="452d6-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="452d6-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="452d6-157">Example</span></span>  

 <span data-ttu-id="452d6-158">En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="452d6-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="452d6-159">El bit en el patrón del resultado se establece si exactamente uno de los bits correspondientes de los operandos está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="452d6-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="452d6-160">En el ejemplo anterior se generan los resultados de 2, 12 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="452d6-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452d6-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="452d6-161">See also</span></span>

- [<span data-ttu-id="452d6-162">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="452d6-162">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="452d6-163">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="452d6-163">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="452d6-164">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="452d6-164">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="452d6-165">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="452d6-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
