---
description: 'Más información acerca de: operador OR (Visual Basic)'
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
ms.openlocfilehash: dfc50af2298c162707976e4b2eda9e9536aa64bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730335"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="47895-103">Or (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47895-103">Or Operator (Visual Basic)</span></span>

<span data-ttu-id="47895-104">Realiza una disyunción lógica entre dos `Boolean` expresiones o una disyunción bit a bit entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="47895-104">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47895-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47895-105">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="47895-106">Partes</span><span class="sxs-lookup"><span data-stu-id="47895-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="47895-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="47895-107">Required.</span></span> <span data-ttu-id="47895-108">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="47895-108">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="47895-109">Para `Boolean` la comparación, `result` es la disyunción lógica inclusiva de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="47895-109">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="47895-110">Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción bit a bit inclusiva de dos modelos de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="47895-110">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="47895-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="47895-111">Required.</span></span> <span data-ttu-id="47895-112">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="47895-112">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="47895-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="47895-113">Required.</span></span> <span data-ttu-id="47895-114">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="47895-114">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47895-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47895-115">Remarks</span></span>  

 <span data-ttu-id="47895-116">Para la `Boolean` comparación, `result` es `False` si y solo si `expression1` y `expression2` se evalúan como `False` .</span><span class="sxs-lookup"><span data-stu-id="47895-116">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="47895-117">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="47895-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="47895-118">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="47895-118">If `expression1` is</span></span>|<span data-ttu-id="47895-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="47895-119">And `expression2` is</span></span>|<span data-ttu-id="47895-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="47895-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="47895-121">En una `Boolean` comparación, el `Or` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="47895-121">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="47895-122">El [operador OrElse](orelse-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `True` , `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="47895-122">The [OrElse Operator](orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="47895-123">Para las operaciones bit a bit, el `Or` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47895-123">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="47895-124">Si el bit de `expression1` es</span><span class="sxs-lookup"><span data-stu-id="47895-124">If bit in `expression1` is</span></span>|<span data-ttu-id="47895-125">Y el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="47895-125">And bit in `expression2` is</span></span>|<span data-ttu-id="47895-126">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="47895-126">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="47895-127">1</span><span class="sxs-lookup"><span data-stu-id="47895-127">1</span></span>|<span data-ttu-id="47895-128">1</span><span class="sxs-lookup"><span data-stu-id="47895-128">1</span></span>|<span data-ttu-id="47895-129">1</span><span class="sxs-lookup"><span data-stu-id="47895-129">1</span></span>|  
|<span data-ttu-id="47895-130">1</span><span class="sxs-lookup"><span data-stu-id="47895-130">1</span></span>|<span data-ttu-id="47895-131">0</span><span class="sxs-lookup"><span data-stu-id="47895-131">0</span></span>|<span data-ttu-id="47895-132">1</span><span class="sxs-lookup"><span data-stu-id="47895-132">1</span></span>|  
|<span data-ttu-id="47895-133">0</span><span class="sxs-lookup"><span data-stu-id="47895-133">0</span></span>|<span data-ttu-id="47895-134">1</span><span class="sxs-lookup"><span data-stu-id="47895-134">1</span></span>|<span data-ttu-id="47895-135">1</span><span class="sxs-lookup"><span data-stu-id="47895-135">1</span></span>|  
|<span data-ttu-id="47895-136">0</span><span class="sxs-lookup"><span data-stu-id="47895-136">0</span></span>|<span data-ttu-id="47895-137">0</span><span class="sxs-lookup"><span data-stu-id="47895-137">0</span></span>|<span data-ttu-id="47895-138">0</span><span class="sxs-lookup"><span data-stu-id="47895-138">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="47895-139">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="47895-139">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="47895-140">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="47895-140">Data Types</span></span>  

 <span data-ttu-id="47895-141">Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False` ) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="47895-141">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="47895-142">Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="47895-142">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="47895-143">En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="47895-143">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="47895-144">Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="47895-144">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="47895-145">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="47895-145">Overloading</span></span>  

 <span data-ttu-id="47895-146">El `Or` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="47895-146">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="47895-147">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="47895-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="47895-148">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="47895-148">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="47895-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47895-149">Example</span></span>  

 <span data-ttu-id="47895-150">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="47895-150">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="47895-151">El resultado es un `Boolean` valor que indica si cualquiera de las dos expresiones es `True` .</span><span class="sxs-lookup"><span data-stu-id="47895-151">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="47895-152">En el ejemplo anterior se generan los resultados de `True` , `True` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="47895-152">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47895-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47895-153">Example</span></span>  

 <span data-ttu-id="47895-154">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva en los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="47895-154">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="47895-155">El bit del modelo de resultado se establece si alguno de los bits correspondientes de los operandos se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="47895-155">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="47895-156">En el ejemplo anterior se generan resultados de 10, 14 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="47895-156">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47895-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="47895-157">See also</span></span>

- [<span data-ttu-id="47895-158">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47895-158">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="47895-159">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47895-159">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="47895-160">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="47895-160">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="47895-161">Operador OrElse</span><span class="sxs-lookup"><span data-stu-id="47895-161">OrElse Operator</span></span>](orelse-operator.md)
- [<span data-ttu-id="47895-162">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47895-162">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
