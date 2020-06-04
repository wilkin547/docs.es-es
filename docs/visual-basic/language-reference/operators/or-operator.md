---
title: Operador Or
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
ms.openlocfilehash: 657b2a473b23789a8ba25fbd11c6b83538fa7803
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401425"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="85b6a-102">Or (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85b6a-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="85b6a-103">Realiza una disyunción lógica entre dos `Boolean` expresiones o una disyunción bit a bit entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="85b6a-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85b6a-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="85b6a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="85b6a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="85b6a-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="85b6a-106">Required.</span></span> <span data-ttu-id="85b6a-107">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="85b6a-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="85b6a-108">Para `Boolean` la comparación, `result` es la disyunción lógica inclusiva de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="85b6a-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="85b6a-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción bit a bit inclusiva de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="85b6a-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="85b6a-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="85b6a-110">Required.</span></span> <span data-ttu-id="85b6a-111">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="85b6a-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="85b6a-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="85b6a-112">Required.</span></span> <span data-ttu-id="85b6a-113">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="85b6a-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85b6a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="85b6a-114">Remarks</span></span>  
 <span data-ttu-id="85b6a-115">Para la `Boolean` comparación, `result` es `False` si y solo si `expression1` y `expression2` se evalúan como `False` .</span><span class="sxs-lookup"><span data-stu-id="85b6a-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="85b6a-116">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="85b6a-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="85b6a-117">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="85b6a-117">If `expression1` is</span></span>|<span data-ttu-id="85b6a-118">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="85b6a-118">And `expression2` is</span></span>|<span data-ttu-id="85b6a-119">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="85b6a-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="85b6a-120">En una `Boolean` comparación, el `Or` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="85b6a-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="85b6a-121">El [operador OrElse](orelse-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `True` , `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="85b6a-121">The [OrElse Operator](orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="85b6a-122">Para las operaciones bit a bit, el `Or` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="85b6a-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="85b6a-123">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="85b6a-123">If bit in `expression1` is</span></span>|<span data-ttu-id="85b6a-124">Y el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="85b6a-124">And bit in `expression2` is</span></span>|<span data-ttu-id="85b6a-125">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="85b6a-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="85b6a-126">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-126">1</span></span>|<span data-ttu-id="85b6a-127">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-127">1</span></span>|<span data-ttu-id="85b6a-128">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-128">1</span></span>|  
|<span data-ttu-id="85b6a-129">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-129">1</span></span>|<span data-ttu-id="85b6a-130">0</span><span class="sxs-lookup"><span data-stu-id="85b6a-130">0</span></span>|<span data-ttu-id="85b6a-131">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-131">1</span></span>|  
|<span data-ttu-id="85b6a-132">0</span><span class="sxs-lookup"><span data-stu-id="85b6a-132">0</span></span>|<span data-ttu-id="85b6a-133">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-133">1</span></span>|<span data-ttu-id="85b6a-134">1</span><span class="sxs-lookup"><span data-stu-id="85b6a-134">1</span></span>|  
|<span data-ttu-id="85b6a-135">0</span><span class="sxs-lookup"><span data-stu-id="85b6a-135">0</span></span>|<span data-ttu-id="85b6a-136">0</span><span class="sxs-lookup"><span data-stu-id="85b6a-136">0</span></span>|<span data-ttu-id="85b6a-137">0</span><span class="sxs-lookup"><span data-stu-id="85b6a-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="85b6a-138">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="85b6a-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="85b6a-139">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="85b6a-139">Data Types</span></span>  
 <span data-ttu-id="85b6a-140">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False` ) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="85b6a-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="85b6a-141">Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="85b6a-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="85b6a-142">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="85b6a-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="85b6a-143">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="85b6a-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="85b6a-144">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="85b6a-144">Overloading</span></span>  
 <span data-ttu-id="85b6a-145">El `Or` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="85b6a-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="85b6a-146">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="85b6a-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="85b6a-147">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="85b6a-147">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85b6a-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85b6a-148">Example</span></span>  
 <span data-ttu-id="85b6a-149">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="85b6a-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="85b6a-150">El resultado es un `Boolean` valor que indica si cualquiera de las dos expresiones es `True` .</span><span class="sxs-lookup"><span data-stu-id="85b6a-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="85b6a-151">En el ejemplo anterior se generan los resultados de `True` , `True` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="85b6a-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85b6a-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85b6a-152">Example</span></span>  
 <span data-ttu-id="85b6a-153">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="85b6a-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="85b6a-154">El bit del modelo de resultado se establece si alguno de los bits correspondientes de los operandos se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="85b6a-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="85b6a-155">En el ejemplo anterior se generan resultados de 10, 14 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="85b6a-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b6a-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85b6a-156">See also</span></span>

- [<span data-ttu-id="85b6a-157">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85b6a-157">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="85b6a-158">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85b6a-158">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="85b6a-159">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="85b6a-159">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="85b6a-160">Operador OrElse</span><span class="sxs-lookup"><span data-stu-id="85b6a-160">OrElse Operator</span></span>](orelse-operator.md)
- [<span data-ttu-id="85b6a-161">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85b6a-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
