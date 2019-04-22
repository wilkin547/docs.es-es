---
title: Operadores de comparación (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821041"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="d8965-102">Operadores de comparación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8965-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="d8965-103">Estos son los operadores de comparación definidos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d8965-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="d8965-104">`<` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-104">`<` operator</span></span>  
  
 <span data-ttu-id="d8965-105">`<=` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-105">`<=` operator</span></span>  
  
 <span data-ttu-id="d8965-106">`>` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-106">`>` operator</span></span>  
  
 <span data-ttu-id="d8965-107">`>=` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-107">`>=` operator</span></span>  
  
 <span data-ttu-id="d8965-108">`=` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-108">`=` operator</span></span>  
  
 <span data-ttu-id="d8965-109">`<>` Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="d8965-110">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="d8965-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="d8965-111">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="d8965-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="d8965-112">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="d8965-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="d8965-113">Estos operadores comparan dos expresiones para determinar si son iguales y, si no, cómo se diferencian.</span><span class="sxs-lookup"><span data-stu-id="d8965-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="d8965-114">`Is`, `IsNot`, y `Like` se tratan detalladamente en las páginas de Ayuda independientes.</span><span class="sxs-lookup"><span data-stu-id="d8965-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="d8965-115">Los operadores de comparación relacional se tratan detalladamente en esta página.</span><span class="sxs-lookup"><span data-stu-id="d8965-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8965-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8965-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d8965-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="d8965-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="d8965-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-118">Required.</span></span> <span data-ttu-id="d8965-119">Un `Boolean` valor que representa el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="d8965-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="d8965-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-120">Required.</span></span> <span data-ttu-id="d8965-121">Cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="d8965-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="d8965-122">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-122">Required.</span></span> <span data-ttu-id="d8965-123">Cualquier operador de comparación relacional.</span><span class="sxs-lookup"><span data-stu-id="d8965-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="d8965-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="d8965-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="d8965-125">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-125">Required.</span></span> <span data-ttu-id="d8965-126">Los nombres de objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="d8965-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="d8965-127">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-127">Required.</span></span> <span data-ttu-id="d8965-128">Cualquier expresión `String` .</span><span class="sxs-lookup"><span data-stu-id="d8965-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d8965-129">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8965-129">Required.</span></span> <span data-ttu-id="d8965-130">Cualquier `String` expresión o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8965-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8965-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8965-131">Remarks</span></span>  
 <span data-ttu-id="d8965-132">En la tabla siguiente contiene una lista de los operadores de comparación relacional y las condiciones que determinan si `result` es `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="d8965-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="d8965-133">Operador</span><span class="sxs-lookup"><span data-stu-id="d8965-133">Operator</span></span>|<span data-ttu-id="d8965-134">`True` si</span><span class="sxs-lookup"><span data-stu-id="d8965-134">`True` if</span></span>|<span data-ttu-id="d8965-135">`False` si</span><span class="sxs-lookup"><span data-stu-id="d8965-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="d8965-136">`<` (Menor que)</span><span class="sxs-lookup"><span data-stu-id="d8965-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="d8965-137">`<=` (Menor o igual que)</span><span class="sxs-lookup"><span data-stu-id="d8965-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="d8965-138">`>` (Mayor que)</span><span class="sxs-lookup"><span data-stu-id="d8965-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="d8965-139">`>=` (Mayor o igual que)</span><span class="sxs-lookup"><span data-stu-id="d8965-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="d8965-140">`=` (Igual a)</span><span class="sxs-lookup"><span data-stu-id="d8965-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="d8965-141">`<>` (No es igual a)</span><span class="sxs-lookup"><span data-stu-id="d8965-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="d8965-142">El [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) también se utiliza como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="d8965-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="d8965-143">El `Is` operador, el `IsNot` operador y el `Like` operador tiene funcionalidades de comparación específica que difieren de los operadores en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="d8965-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="d8965-144">Comparación de números</span><span class="sxs-lookup"><span data-stu-id="d8965-144">Comparing Numbers</span></span>  
 <span data-ttu-id="d8965-145">Cuando se compara una expresión de tipo `Single` a uno de tipo `Double`, `Single` expresión se convierte en `Double`.</span><span class="sxs-lookup"><span data-stu-id="d8965-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="d8965-146">Este comportamiento es opuesto del comportamiento encontrado en Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="d8965-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="d8965-147">De forma similar, cuando se compara una expresión de tipo `Decimal` en una expresión de tipo `Single` o `Double`, `Decimal` expresión se convierte en `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="d8965-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="d8965-148">Para `Decimal` expresiones, cualquier valor fraccionario menor que 1E-28 podría perderse.</span><span class="sxs-lookup"><span data-stu-id="d8965-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="d8965-149">Dicha pérdida de valor fraccionario puede hacen que se consideran iguales cuando no estén dos valores.</span><span class="sxs-lookup"><span data-stu-id="d8965-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="d8965-150">Por este motivo, debe tener cuidado al usar la igualdad (`=`) para comparar dos variables de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="d8965-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="d8965-151">Es más seguro comprobar si el valor absoluto de la diferencia entre los dos números es menor que el mínimo aceptable.</span><span class="sxs-lookup"><span data-stu-id="d8965-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="d8965-152">Punto flotante imprecisión</span><span class="sxs-lookup"><span data-stu-id="d8965-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="d8965-153">Cuando se trabaja con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="d8965-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d8965-154">Esto podría provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el [Mod (operador)](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d8965-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="d8965-155">Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d8965-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="d8965-156">Comparar cadenas</span><span class="sxs-lookup"><span data-stu-id="d8965-156">Comparing Strings</span></span>  
 <span data-ttu-id="d8965-157">Cuando se comparan cadenas, las expresiones de cadena se evalúan según su criterio de ordenación alfabética, que depende el `Option Compare` configuración.</span><span class="sxs-lookup"><span data-stu-id="d8965-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="d8965-158">`Option Compare Binary` comparaciones en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres de cadenas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d8965-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="d8965-159">El criterio de ordenación viene determinada por la página de códigos.</span><span class="sxs-lookup"><span data-stu-id="d8965-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="d8965-160">El ejemplo siguiente muestra un criterio de ordenación binario típico.</span><span class="sxs-lookup"><span data-stu-id="d8965-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d8965-161">`Option Compare Text` bases de datos de cadena comparaciones en un criterio de ordenación textual entre mayúsculas y minúsculas determinado por la configuración regional de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8965-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="d8965-162">Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el criterio de ordenación de texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8965-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="d8965-163">Dependencia de la configuración regional</span><span class="sxs-lookup"><span data-stu-id="d8965-163">Locale Dependence</span></span>  
 <span data-ttu-id="d8965-164">Al establecer `Option Compare Text`, el resultado de una comparación de cadenas puede depender de la configuración regional en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8965-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="d8965-165">Pueden comparar dos caracteres como iguales en una configuración regional, pero no en otro.</span><span class="sxs-lookup"><span data-stu-id="d8965-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="d8965-166">Si está utilizando una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe aparecer la alerta para la sensibilidad de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="d8965-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="d8965-167">Considere la posibilidad de cualquier `Option Compare Binary` o que realiza la llamada la <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, que tiene la configuración regional en la cuenta.</span><span class="sxs-lookup"><span data-stu-id="d8965-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="d8965-168">Programación sin tipos con operadores de comparación relacional</span><span class="sxs-lookup"><span data-stu-id="d8965-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="d8965-169">El uso de operadores de comparación relacional con `Object` expresiones no se permite en `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="d8965-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="d8965-170">Cuando `Option Strict` es `Off`y `expression1` o `expression2` es un `Object` expresión, los tipos de tiempo de ejecución determinan cómo se comparan.</span><span class="sxs-lookup"><span data-stu-id="d8965-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="d8965-171">En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.</span><span class="sxs-lookup"><span data-stu-id="d8965-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="d8965-172">Si los operandos son</span><span class="sxs-lookup"><span data-stu-id="d8965-172">If operands are</span></span>|<span data-ttu-id="d8965-173">La comparación es</span><span class="sxs-lookup"><span data-stu-id="d8965-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="d8965-174">Ambos `String`</span><span class="sxs-lookup"><span data-stu-id="d8965-174">Both `String`</span></span>|<span data-ttu-id="d8965-175">Ordenar en función de las características de ordenación de cadenas de comparación.</span><span class="sxs-lookup"><span data-stu-id="d8965-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="d8965-176">Ambas numéricas</span><span class="sxs-lookup"><span data-stu-id="d8965-176">Both numeric</span></span>|<span data-ttu-id="d8965-177">Convierten objetos en `Double`, comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="d8965-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="d8965-178">Uno numérico y otro `String`</span><span class="sxs-lookup"><span data-stu-id="d8965-178">One numeric and one `String`</span></span>|<span data-ttu-id="d8965-179">El `String` se convierte en un `Double` y se realiza una comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="d8965-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="d8965-180">Si el `String` no se puede convertir a `Double`, un <xref:System.InvalidCastException> se produce.</span><span class="sxs-lookup"><span data-stu-id="d8965-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="d8965-181">Uno o ambos son tipos de referencia distinto `String`</span><span class="sxs-lookup"><span data-stu-id="d8965-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="d8965-182">Se inicia una <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="d8965-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="d8965-183">Tratan las comparaciones numéricas `Nothing` como 0.</span><span class="sxs-lookup"><span data-stu-id="d8965-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="d8965-184">Tratan las comparaciones de cadenas `Nothing` como `""` (una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="d8965-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d8965-185">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="d8965-185">Overloading</span></span>  
 <span data-ttu-id="d8965-186">Los operadores de comparación relacional (`<`.</span><span class="sxs-lookup"><span data-stu-id="d8965-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="d8965-187">`<=``>`, `>=`, `=`, `<>`) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d8965-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d8965-188">Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprender el comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="d8965-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="d8965-189">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d8965-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="d8965-190">Tenga en cuenta que el [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="d8965-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8965-191">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8965-191">Example</span></span>  
 <span data-ttu-id="d8965-192">El ejemplo siguiente muestra varios usos de los operadores de comparación relacional, que se utilizan para comparar expresiones.</span><span class="sxs-lookup"><span data-stu-id="d8965-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="d8965-193">Operadores de comparación relacional devuelven un `Boolean` resultado que representa si se evalúa como la expresión indicada `True`.</span><span class="sxs-lookup"><span data-stu-id="d8965-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="d8965-194">Al aplicar el `>` y `<` operadores en cadenas, la comparación se realiza mediante el criterio de ordenación alfabético normal de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="d8965-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="d8965-195">Este orden puede depender de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="d8965-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="d8965-196">Si el criterio de ordenación distingue mayúsculas de minúsculas o no depende de la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) configuración.</span><span class="sxs-lookup"><span data-stu-id="d8965-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 <span data-ttu-id="d8965-197">En el ejemplo anterior, se devuelve la primera comparación `False` y las comparaciones restantes devuelven `True`.</span><span class="sxs-lookup"><span data-stu-id="d8965-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8965-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8965-198">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="d8965-199">Operador =</span><span class="sxs-lookup"><span data-stu-id="d8965-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="d8965-200">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8965-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d8965-201">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d8965-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d8965-202">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d8965-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d8965-203">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8965-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
