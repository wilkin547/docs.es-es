---
description: 'Más información acerca de: operador and (Visual Basic)'
title: Operador And
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
ms.openlocfilehash: 238ef0b2f14f2014da6e65684bfac183e03d963e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774283"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="5477e-103">And (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5477e-103">And Operator (Visual Basic)</span></span>

<span data-ttu-id="5477e-104">Realiza una conjunción lógica de dos `Boolean` expresiones o una conjunción bit a bit de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="5477e-104">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5477e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5477e-105">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="5477e-106">Partes</span><span class="sxs-lookup"><span data-stu-id="5477e-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="5477e-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5477e-107">Required.</span></span> <span data-ttu-id="5477e-108">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5477e-108">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="5477e-109">En la comparación booleana, `result` es la conjunción lógica de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="5477e-109">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="5477e-110">Para las operaciones bit a bit, `result` es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="5477e-110">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="5477e-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5477e-111">Required.</span></span> <span data-ttu-id="5477e-112">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5477e-112">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="5477e-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5477e-113">Required.</span></span> <span data-ttu-id="5477e-114">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5477e-114">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5477e-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5477e-115">Remarks</span></span>  

 <span data-ttu-id="5477e-116">En la comparación booleana, `result` es `True` si y solo si `expression1` y `expression2` se evalúan como `True` .</span><span class="sxs-lookup"><span data-stu-id="5477e-116">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="5477e-117">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="5477e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="5477e-118">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="5477e-118">If `expression1` is</span></span>|<span data-ttu-id="5477e-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="5477e-119">And `expression2` is</span></span>|<span data-ttu-id="5477e-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="5477e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="5477e-121">En una comparación booleana, el `And` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="5477e-121">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="5477e-122">El [operador AndAlso](andalso-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `False` , `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="5477e-122">The [AndAlso Operator](andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="5477e-123">Cuando se aplica a valores numéricos, el `And` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5477e-123">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="5477e-124">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="5477e-124">If bit in `expression1` is</span></span>|<span data-ttu-id="5477e-125">Y el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="5477e-125">And bit in `expression2` is</span></span>|<span data-ttu-id="5477e-126">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="5477e-126">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="5477e-127">1</span><span class="sxs-lookup"><span data-stu-id="5477e-127">1</span></span>|<span data-ttu-id="5477e-128">1</span><span class="sxs-lookup"><span data-stu-id="5477e-128">1</span></span>|<span data-ttu-id="5477e-129">1</span><span class="sxs-lookup"><span data-stu-id="5477e-129">1</span></span>|  
|<span data-ttu-id="5477e-130">1</span><span class="sxs-lookup"><span data-stu-id="5477e-130">1</span></span>|<span data-ttu-id="5477e-131">0</span><span class="sxs-lookup"><span data-stu-id="5477e-131">0</span></span>|<span data-ttu-id="5477e-132">0</span><span class="sxs-lookup"><span data-stu-id="5477e-132">0</span></span>|  
|<span data-ttu-id="5477e-133">0</span><span class="sxs-lookup"><span data-stu-id="5477e-133">0</span></span>|<span data-ttu-id="5477e-134">1</span><span class="sxs-lookup"><span data-stu-id="5477e-134">1</span></span>|<span data-ttu-id="5477e-135">0</span><span class="sxs-lookup"><span data-stu-id="5477e-135">0</span></span>|  
|<span data-ttu-id="5477e-136">0</span><span class="sxs-lookup"><span data-stu-id="5477e-136">0</span></span>|<span data-ttu-id="5477e-137">0</span><span class="sxs-lookup"><span data-stu-id="5477e-137">0</span></span>|<span data-ttu-id="5477e-138">0</span><span class="sxs-lookup"><span data-stu-id="5477e-138">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="5477e-139">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar resultados precisos.</span><span class="sxs-lookup"><span data-stu-id="5477e-139">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="5477e-140">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5477e-140">Data Types</span></span>  

 <span data-ttu-id="5477e-141">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False` ) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="5477e-141">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="5477e-142">En el caso de una comparación booleana, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5477e-142">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="5477e-143">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="5477e-143">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="5477e-144">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="5477e-144">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5477e-145">El `And` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5477e-145">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5477e-146">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="5477e-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5477e-147">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5477e-147">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5477e-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5477e-148">Example</span></span>  

 <span data-ttu-id="5477e-149">En el ejemplo siguiente se usa el `And` operador para realizar una conjunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="5477e-149">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="5477e-150">El resultado es un `Boolean` valor que representa si ambas expresiones son `True` .</span><span class="sxs-lookup"><span data-stu-id="5477e-150">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="5477e-151">En el ejemplo anterior se generan los resultados de `True` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5477e-151">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5477e-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5477e-152">Example</span></span>  

 <span data-ttu-id="5477e-153">En el ejemplo siguiente se usa el `And` operador para realizar una conjunción lógica de los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="5477e-153">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="5477e-154">El bit en el patrón del resultado se establece si los bits correspondientes de los operandos están establecidos en 1.</span><span class="sxs-lookup"><span data-stu-id="5477e-154">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="5477e-155">En el ejemplo anterior se generan los resultados de 8, 2 y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5477e-155">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5477e-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="5477e-156">See also</span></span>

- [<span data-ttu-id="5477e-157">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5477e-157">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="5477e-158">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5477e-158">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5477e-159">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5477e-159">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="5477e-160">Operador AndAlso</span><span class="sxs-lookup"><span data-stu-id="5477e-160">AndAlso Operator</span></span>](andalso-operator.md)
- [<span data-ttu-id="5477e-161">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5477e-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
