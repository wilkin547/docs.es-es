---
description: 'Más información acerca de: operador XOR (Visual Basic)'
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
ms.openlocfilehash: 313ff30ace91b1832c0d35df13294e570a8e410d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795227"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="4e7d3-103">Xor (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e7d3-103">Xor Operator (Visual Basic)</span></span>

<span data-ttu-id="4e7d3-104">Realiza una exclusión lógica en dos `Boolean` expresiones o una exclusión bit a bit en dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-104">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e7d3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e7d3-105">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4e7d3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="4e7d3-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="4e7d3-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-107">Required.</span></span> <span data-ttu-id="4e7d3-108">Any `Boolean` o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-108">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="4e7d3-109">En la comparación booleana, `result` es la exclusión lógica (disyunción lógica exclusiva) de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-109">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="4e7d3-110">Para las operaciones bit a bit, `result` es un valor numérico que representa la exclusión bit a bit (disyunción bit a bit exclusiva) de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-110">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4e7d3-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-111">Required.</span></span> <span data-ttu-id="4e7d3-112">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-112">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4e7d3-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-113">Required.</span></span> <span data-ttu-id="4e7d3-114">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-114">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e7d3-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e7d3-115">Remarks</span></span>  

 <span data-ttu-id="4e7d3-116">En la comparación booleana, `result` es `True` si y solo si exactamente uno de `expression1` y `expression2` se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="4e7d3-116">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="4e7d3-117">Es decir, si y solo si `expression1` y `expression2` se evalúan como valores opuestos `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="4e7d3-117">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="4e7d3-118">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-118">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4e7d3-119">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="4e7d3-119">If `expression1` is</span></span>|<span data-ttu-id="4e7d3-120">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="4e7d3-120">And `expression2` is</span></span>|<span data-ttu-id="4e7d3-121">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="4e7d3-121">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="4e7d3-122">En una comparación booleana, el `Xor` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-122">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="4e7d3-123">No hay ningún homólogo de cortocircuito en `Xor` , porque el resultado siempre depende de ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-123">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="4e7d3-124">Para los operadores lógicos de *cortocircuito* , vea [operador AndAlso](andalso-operator.md) y [operador OrElse](orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4e7d3-124">For *short-circuiting* logical operators, see [AndAlso Operator](andalso-operator.md) and [OrElse Operator](orelse-operator.md).</span></span>  
  
 <span data-ttu-id="4e7d3-125">Para las operaciones bit a bit, el `Xor` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-125">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="4e7d3-126">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="4e7d3-126">If bit in `expression1` is</span></span>|<span data-ttu-id="4e7d3-127">Y el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="4e7d3-127">And bit in `expression2` is</span></span>|<span data-ttu-id="4e7d3-128">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="4e7d3-128">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="4e7d3-129">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-129">1</span></span>|<span data-ttu-id="4e7d3-130">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-130">1</span></span>|<span data-ttu-id="4e7d3-131">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-131">0</span></span>|  
|<span data-ttu-id="4e7d3-132">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-132">1</span></span>|<span data-ttu-id="4e7d3-133">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-133">0</span></span>|<span data-ttu-id="4e7d3-134">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-134">1</span></span>|  
|<span data-ttu-id="4e7d3-135">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-135">0</span></span>|<span data-ttu-id="4e7d3-136">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-136">1</span></span>|<span data-ttu-id="4e7d3-137">1</span><span class="sxs-lookup"><span data-stu-id="4e7d3-137">1</span></span>|  
|<span data-ttu-id="4e7d3-138">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-138">0</span></span>|<span data-ttu-id="4e7d3-139">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-139">0</span></span>|<span data-ttu-id="4e7d3-140">0</span><span class="sxs-lookup"><span data-stu-id="4e7d3-140">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="4e7d3-141">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-141">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="4e7d3-142">Por ejemplo, 5 `Xor` 3 es 6.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-142">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="4e7d3-143">Para ver por qué es así, convierta 5 y 3 en sus representaciones binarias, 101 y 011.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-143">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="4e7d3-144">A continuación, use la tabla anterior para determinar que 101 XOR 011 es 110, que es la representación binaria del número decimal 6.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-144">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4e7d3-145">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4e7d3-145">Data Types</span></span>  

 <span data-ttu-id="4e7d3-146">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False` ) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-146">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="4e7d3-147">Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="4e7d3-147">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="4e7d3-148">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="4e7d3-148">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4e7d3-149">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4e7d3-149">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4e7d3-150">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="4e7d3-150">Overloading</span></span>  

 <span data-ttu-id="4e7d3-151">El `Xor` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-151">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4e7d3-152">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-152">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="4e7d3-153">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4e7d3-153">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e7d3-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e7d3-154">Example</span></span>  

 <span data-ttu-id="4e7d3-155">En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-155">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="4e7d3-156">El resultado es un `Boolean` valor que indica si exactamente una de las expresiones es `True` .</span><span class="sxs-lookup"><span data-stu-id="4e7d3-156">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="4e7d3-157">En el ejemplo anterior se generan los resultados de `False` , `True` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-157">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e7d3-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e7d3-158">Example</span></span>  

 <span data-ttu-id="4e7d3-159">En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-159">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="4e7d3-160">El bit en el patrón del resultado se establece si exactamente uno de los bits correspondientes de los operandos está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-160">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="4e7d3-161">En el ejemplo anterior se generan los resultados de 2, 12 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d3-161">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e7d3-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e7d3-162">See also</span></span>

- [<span data-ttu-id="4e7d3-163">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e7d3-163">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="4e7d3-164">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e7d3-164">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="4e7d3-165">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="4e7d3-165">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="4e7d3-166">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e7d3-166">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
