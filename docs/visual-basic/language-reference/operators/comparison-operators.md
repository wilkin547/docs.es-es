---
title: "Operadores de comparación (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="dc27a-102">Operadores de comparación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc27a-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="dc27a-103">Éstos son los operadores de comparación definidos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dc27a-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="dc27a-104">`<`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-104">`<` operator</span></span>  
  
 <span data-ttu-id="dc27a-105">`<=`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-105">`<=` operator</span></span>  
  
 <span data-ttu-id="dc27a-106">`>`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-106">`>` operator</span></span>  
  
 <span data-ttu-id="dc27a-107">`>=`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-107">`>=` operator</span></span>  
  
 <span data-ttu-id="dc27a-108">`=`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-108">`=` operator</span></span>  
  
 <span data-ttu-id="dc27a-109">`<>`operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="dc27a-110">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="dc27a-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="dc27a-111">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="dc27a-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="dc27a-112">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="dc27a-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="dc27a-113">Estos operadores comparan dos expresiones para determinar si no son iguales y, si no es así, cómo se diferencian.</span><span class="sxs-lookup"><span data-stu-id="dc27a-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="dc27a-114">`Is`, `IsNot`, y `Like` se describen en detalle en las páginas de Ayuda independientes.</span><span class="sxs-lookup"><span data-stu-id="dc27a-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="dc27a-115">Los operadores de comparación relacionales se explican detalladamente en esta página.</span><span class="sxs-lookup"><span data-stu-id="dc27a-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc27a-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc27a-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="dc27a-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="dc27a-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="dc27a-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc27a-118">Required.</span></span> <span data-ttu-id="dc27a-119">Un `Boolean` valor que representa el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="dc27a-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="dc27a-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc27a-120">Required.</span></span> <span data-ttu-id="dc27a-121">Cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="dc27a-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="dc27a-122">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc27a-122">Required.</span></span> <span data-ttu-id="dc27a-123">Cualquier operador de comparación relacional.</span><span class="sxs-lookup"><span data-stu-id="dc27a-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="dc27a-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="dc27a-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="dc27a-125">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dc27a-125">Required.</span></span> <span data-ttu-id="dc27a-126">Los nombres de objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="dc27a-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="dc27a-127">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc27a-127">Required.</span></span> <span data-ttu-id="dc27a-128">Cualquier expresión `String`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="dc27a-129">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc27a-129">Required.</span></span> <span data-ttu-id="dc27a-130">Cualquier `String` expresión o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="dc27a-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc27a-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc27a-131">Remarks</span></span>  
 <span data-ttu-id="dc27a-132">En la tabla siguiente contiene una lista de los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="dc27a-133">Operador</span><span class="sxs-lookup"><span data-stu-id="dc27a-133">Operator</span></span>|<span data-ttu-id="dc27a-134">`True`If</span><span class="sxs-lookup"><span data-stu-id="dc27a-134">`True` if</span></span>|<span data-ttu-id="dc27a-135">`False`If</span><span class="sxs-lookup"><span data-stu-id="dc27a-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="dc27a-136">`<`(Menor que)</span><span class="sxs-lookup"><span data-stu-id="dc27a-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="dc27a-137">`<=`(Menor o igual que)</span><span class="sxs-lookup"><span data-stu-id="dc27a-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="dc27a-138">`>`(Mayor que)</span><span class="sxs-lookup"><span data-stu-id="dc27a-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="dc27a-139">`>=`(Mayor o igual que)</span><span class="sxs-lookup"><span data-stu-id="dc27a-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="dc27a-140">`=`(Igual a)</span><span class="sxs-lookup"><span data-stu-id="dc27a-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="dc27a-141">`<>`(No es igual a)</span><span class="sxs-lookup"><span data-stu-id="dc27a-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="dc27a-142">El [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) también se utiliza como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="dc27a-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="dc27a-143">El `Is` (operador), el `IsNot` (operador) y el `Like` operador tienen funcionalidades de comparación específicas que difieren de los operadores en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="dc27a-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="dc27a-144">Comparación de números</span><span class="sxs-lookup"><span data-stu-id="dc27a-144">Comparing Numbers</span></span>  
 <span data-ttu-id="dc27a-145">Cuando se compara una expresión de tipo `Single` en uno de tipo `Double`, `Single` expresión se convierte en `Double`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="dc27a-146">Este comportamiento es opuesto del comportamiento encontrado en Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="dc27a-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="dc27a-147">De forma similar, cuando se compara una expresión de tipo `Decimal` en una expresión de tipo `Single` o `Double`, `Decimal` expresión se convierte a `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="dc27a-148">Para `Decimal` expresiones, cualquier valor fraccionario inferior a 1E-28 podría perderse.</span><span class="sxs-lookup"><span data-stu-id="dc27a-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="dc27a-149">Dicha pérdida de valor fraccionario puede provocar dos valores que se consideran iguales cuando no lo están.</span><span class="sxs-lookup"><span data-stu-id="dc27a-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="dc27a-150">Por este motivo, debe tener cuidado de cuando se usa la igualdad (`=`) para comparar dos variables de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="dc27a-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="dc27a-151">Es más seguro comprobar si el valor absoluto de la diferencia entre los dos números es menor que el mínimo aceptable.</span><span class="sxs-lookup"><span data-stu-id="dc27a-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="dc27a-152">Punto flotante imprecisión</span><span class="sxs-lookup"><span data-stu-id="dc27a-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="dc27a-153">Cuando trabaje con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="dc27a-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="dc27a-154">Esto podría provocar resultados inesperados en ciertas operaciones, como comparación de valores y la [Mod (operador)](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dc27a-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="dc27a-155">Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="dc27a-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="dc27a-156">Comparar cadenas</span><span class="sxs-lookup"><span data-stu-id="dc27a-156">Comparing Strings</span></span>  
 <span data-ttu-id="dc27a-157">Cuando se comparan cadenas, las expresiones de cadena se evalúan según su criterio de ordenación alfabética, que depende de la `Option Compare` configuración.</span><span class="sxs-lookup"><span data-stu-id="dc27a-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="dc27a-158">`Option Compare Binary`comparaciones en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres de cadenas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="dc27a-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="dc27a-159">El criterio de ordenación viene determinado por la página de código.</span><span class="sxs-lookup"><span data-stu-id="dc27a-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="dc27a-160">En el ejemplo siguiente se muestra un criterio de ordenación binario típico.</span><span class="sxs-lookup"><span data-stu-id="dc27a-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="dc27a-161">`Option Compare Text`bases de datos de cadena comparaciones en un criterio de ordenación entre mayúsculas y minúsculas, textual determinado por la configuración regional de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc27a-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="dc27a-162">Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el criterio de ordenación de texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc27a-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="dc27a-163">Dependen de la configuración regional</span><span class="sxs-lookup"><span data-stu-id="dc27a-163">Locale Dependence</span></span>  
 <span data-ttu-id="dc27a-164">Al establecer `Option Compare Text`, el resultado de una comparación de cadenas puede depender de la configuración regional en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc27a-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="dc27a-165">Dos caracteres podrían compararse como iguales en varias configuraciones regionales, pero no en otro.</span><span class="sxs-lookup"><span data-stu-id="dc27a-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="dc27a-166">Si está usando una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe aparecer la alerta para la sensibilidad de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="dc27a-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="dc27a-167">Tenga en cuenta cualquier configuración `Option Compare Binary` o que realiza la llamada la <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, la configuración regional que tiene en cuenta.</span><span class="sxs-lookup"><span data-stu-id="dc27a-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="dc27a-168">Programación sin tipos con operadores de comparación relacionales</span><span class="sxs-lookup"><span data-stu-id="dc27a-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="dc27a-169">El uso de operadores de comparación relacionales con `Object` expresiones no se permite en `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="dc27a-170">Cuando `Option Strict` es `Off`y `expression1` o `expression2` es un `Object` expresión, los tipos de tiempo de ejecución determinan cómo se comparan.</span><span class="sxs-lookup"><span data-stu-id="dc27a-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="dc27a-171">En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.</span><span class="sxs-lookup"><span data-stu-id="dc27a-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="dc27a-172">Si los operandos son</span><span class="sxs-lookup"><span data-stu-id="dc27a-172">If operands are</span></span>|<span data-ttu-id="dc27a-173">La comparación es</span><span class="sxs-lookup"><span data-stu-id="dc27a-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="dc27a-174">Ambos`String`</span><span class="sxs-lookup"><span data-stu-id="dc27a-174">Both `String`</span></span>|<span data-ttu-id="dc27a-175">Ordenar la comparación según las características de ordenación de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="dc27a-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="dc27a-176">Ambas numéricas</span><span class="sxs-lookup"><span data-stu-id="dc27a-176">Both numeric</span></span>|<span data-ttu-id="dc27a-177">Los objetos se convierten a `Double`, comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="dc27a-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="dc27a-178">Uno numérico y otro`String`</span><span class="sxs-lookup"><span data-stu-id="dc27a-178">One numeric and one `String`</span></span>|<span data-ttu-id="dc27a-179">El `String` se convierte en un `Double` y se realiza una comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="dc27a-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="dc27a-180">Si el `String` no se puede convertir a `Double`, un <xref:System.InvalidCastException> se produce.</span><span class="sxs-lookup"><span data-stu-id="dc27a-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="dc27a-181">Uno o ambos son tipos de referencia distintos de`String`</span><span class="sxs-lookup"><span data-stu-id="dc27a-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="dc27a-182">Se inicia una <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="dc27a-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="dc27a-183">Las comparaciones numéricas tratan `Nothing` como 0.</span><span class="sxs-lookup"><span data-stu-id="dc27a-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="dc27a-184">Las comparaciones de cadena tratan `Nothing` como `""` (una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="dc27a-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="dc27a-185">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="dc27a-185">Overloading</span></span>  
 <span data-ttu-id="dc27a-186">Los operadores de comparación relacionales (`<`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="dc27a-187">`<=``>`, `>=`, `=`, `<>`) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="dc27a-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="dc27a-188">Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprende el comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="dc27a-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="dc27a-189">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="dc27a-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="dc27a-190">Tenga en cuenta que la [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="dc27a-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc27a-191">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc27a-191">Example</span></span>  
 <span data-ttu-id="dc27a-192">En el ejemplo siguiente se muestra varios usos de los operadores de comparación relacionales, que se utilizan para comparar expresiones.</span><span class="sxs-lookup"><span data-stu-id="dc27a-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="dc27a-193">Operadores de comparación relacionales devuelven un `Boolean` resultado que representa si o no se evalúa como la expresión indicada `True`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="dc27a-194">Al aplicar el `>` y `<` operadores para las cadenas, la comparación se realiza utilizando el orden alfabético normal de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="dc27a-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="dc27a-195">Este orden puede ser dependiente de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="dc27a-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="dc27a-196">Si el criterio de ordenación distingue mayúsculas de minúsculas o no depende de la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) configuración.</span><span class="sxs-lookup"><span data-stu-id="dc27a-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="dc27a-197">En el ejemplo anterior, se devuelve la primera comparación `False` y las comparaciones restantes devuelven `True`.</span><span class="sxs-lookup"><span data-stu-id="dc27a-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc27a-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc27a-198">See Also</span></span>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="dc27a-199">Operador =</span><span class="sxs-lookup"><span data-stu-id="dc27a-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="dc27a-200">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc27a-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="dc27a-201">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="dc27a-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="dc27a-202">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dc27a-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="dc27a-203">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc27a-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
