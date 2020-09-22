---
title: Operadores de comparación
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
ms.openlocfilehash: fcbb9052a79fa4b20b5a0f8fdc15de73d55a4281
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873449"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="54f94-102">Operadores de comparación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54f94-102">Comparison Operators (Visual Basic)</span></span>

<span data-ttu-id="54f94-103">A continuación se muestran los operadores de comparación definidos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="54f94-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="54f94-104">`<` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-104">`<` operator</span></span>

 <span data-ttu-id="54f94-105">`<=` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-105">`<=` operator</span></span>

 <span data-ttu-id="54f94-106">`>` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-106">`>` operator</span></span>

 <span data-ttu-id="54f94-107">`>=` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-107">`>=` operator</span></span>

 <span data-ttu-id="54f94-108">`=` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-108">`=` operator</span></span>

 <span data-ttu-id="54f94-109">`<>` Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-109">`<>` operator</span></span>

 [<span data-ttu-id="54f94-110">Operador Is</span><span class="sxs-lookup"><span data-stu-id="54f94-110">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="54f94-111">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="54f94-111">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="54f94-112">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="54f94-112">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="54f94-113">Estos operadores comparan dos expresiones para determinar si son iguales o no, y si no, cómo se diferencian.</span><span class="sxs-lookup"><span data-stu-id="54f94-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="54f94-114">`Is`, `IsNot` y `Like` se describen en detalle en páginas de ayuda independientes.</span><span class="sxs-lookup"><span data-stu-id="54f94-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="54f94-115">Los operadores de comparación relacional se describen en detalle en esta página.</span><span class="sxs-lookup"><span data-stu-id="54f94-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="54f94-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54f94-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="54f94-117">Partes</span><span class="sxs-lookup"><span data-stu-id="54f94-117">Parts</span></span>

 `result`  
 <span data-ttu-id="54f94-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-118">Required.</span></span> <span data-ttu-id="54f94-119">`Boolean`Valor que representa el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="54f94-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="54f94-120">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="54f94-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="54f94-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-121">Required.</span></span> <span data-ttu-id="54f94-122">Cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="54f94-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="54f94-123">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-123">Required.</span></span> <span data-ttu-id="54f94-124">Cualquier operador de comparación relacional.</span><span class="sxs-lookup"><span data-stu-id="54f94-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="54f94-125">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="54f94-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="54f94-126">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-126">Required.</span></span> <span data-ttu-id="54f94-127">Cualquier nombre de objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="54f94-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="54f94-128">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-128">Required.</span></span> <span data-ttu-id="54f94-129">Cualquier expresión `String` .</span><span class="sxs-lookup"><span data-stu-id="54f94-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="54f94-130">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="54f94-130">Required.</span></span> <span data-ttu-id="54f94-131">Cualquier `String` expresión o intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="54f94-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="54f94-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54f94-132">Remarks</span></span>

 <span data-ttu-id="54f94-133">La tabla siguiente contiene una lista de los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="54f94-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="54f94-134">Operator</span><span class="sxs-lookup"><span data-stu-id="54f94-134">Operator</span></span>|<span data-ttu-id="54f94-135">`True` si</span><span class="sxs-lookup"><span data-stu-id="54f94-135">`True` if</span></span>|<span data-ttu-id="54f94-136">`False` si</span><span class="sxs-lookup"><span data-stu-id="54f94-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="54f94-137">`<` (Menor que)</span><span class="sxs-lookup"><span data-stu-id="54f94-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="54f94-138">`<=` (Menor o igual que)</span><span class="sxs-lookup"><span data-stu-id="54f94-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="54f94-139">`>` (Mayor que)</span><span class="sxs-lookup"><span data-stu-id="54f94-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="54f94-140">`>=` (Mayor o igual que)</span><span class="sxs-lookup"><span data-stu-id="54f94-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="54f94-141">`=` (Igual a)</span><span class="sxs-lookup"><span data-stu-id="54f94-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="54f94-142">`<>` (No es igual a)</span><span class="sxs-lookup"><span data-stu-id="54f94-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="54f94-143">El [operador =](assignment-operator.md) también se usa como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="54f94-143">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="54f94-144">El `Is` operador, el `IsNot` operador y el `Like` operador tienen funcionalidades de comparación específicas que difieren de los operadores de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="54f94-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="54f94-145">Comparar números</span><span class="sxs-lookup"><span data-stu-id="54f94-145">Comparing Numbers</span></span>

 <span data-ttu-id="54f94-146">Al comparar una expresión de tipo `Single` con una de tipo `Double` , la `Single` expresión se convierte en `Double` .</span><span class="sxs-lookup"><span data-stu-id="54f94-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="54f94-147">Este comportamiento es opuesto al comportamiento que se encuentra en Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="54f94-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="54f94-148">Del mismo modo, al comparar una expresión de tipo `Decimal` con una expresión de tipo `Single` o `Double` , la `Decimal` expresión se convierte en `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="54f94-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="54f94-149">En el caso de `Decimal` las expresiones, se puede perder cualquier valor fraccionario inferior a 1E-28.</span><span class="sxs-lookup"><span data-stu-id="54f94-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="54f94-150">Esta pérdida de valor fraccionario puede hacer que dos valores se comparen como iguales cuando no lo son.</span><span class="sxs-lookup"><span data-stu-id="54f94-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="54f94-151">Por este motivo, debe tener cuidado al usar la igualdad ( `=` ) para comparar dos variables de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="54f94-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="54f94-152">Es más seguro probar si el valor absoluto de la diferencia entre los dos números es menor que una pequeña tolerancia aceptable.</span><span class="sxs-lookup"><span data-stu-id="54f94-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="54f94-153">Imprecisión de punto flotante</span><span class="sxs-lookup"><span data-stu-id="54f94-153">Floating-point Imprecision</span></span>

 <span data-ttu-id="54f94-154">Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="54f94-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="54f94-155">Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el [operador mod](mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="54f94-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="54f94-156">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="54f94-156">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="54f94-157">Comparar cadenas</span><span class="sxs-lookup"><span data-stu-id="54f94-157">Comparing Strings</span></span>

 <span data-ttu-id="54f94-158">Cuando se comparan cadenas, las expresiones de cadena se evalúan en función de su criterio de ordenación alfabético, que depende de la `Option Compare` configuración.</span><span class="sxs-lookup"><span data-stu-id="54f94-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="54f94-159">`Option Compare Binary` basa las comparaciones de cadenas en un criterio de ordenación derivado de las representaciones binarias internas de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="54f94-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="54f94-160">La página de códigos determina el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="54f94-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="54f94-161">En el ejemplo siguiente se muestra un criterio de ordenación binario típico.</span><span class="sxs-lookup"><span data-stu-id="54f94-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="54f94-162">`Option Compare Text` basa las comparaciones de cadenas en un criterio de ordenación textual que no distingue entre mayúsculas y minúsculas, determinado por la configuración regional de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54f94-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="54f94-163">Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el siguiente criterio de ordenación de texto:</span><span class="sxs-lookup"><span data-stu-id="54f94-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="54f94-164">Dependencia de la configuración regional</span><span class="sxs-lookup"><span data-stu-id="54f94-164">Locale Dependence</span></span>

 <span data-ttu-id="54f94-165">Al establecer `Option Compare Text` , el resultado de una comparación de cadenas puede depender de la configuración regional en la que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54f94-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="54f94-166">Dos caracteres podrían compararse como iguales en una configuración regional, pero no en otra.</span><span class="sxs-lookup"><span data-stu-id="54f94-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="54f94-167">Si utiliza una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe alertar a la confidencialidad de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="54f94-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="54f94-168">Considere la posibilidad de establecer `Option Compare Binary` o llamar a <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , que tiene en cuenta la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="54f94-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="54f94-169">Programación sin tipos con operadores de comparación relacionales</span><span class="sxs-lookup"><span data-stu-id="54f94-169">Typeless Programming with Relational Comparison Operators</span></span>

 <span data-ttu-id="54f94-170">No se permite el uso de operadores de comparación relacionales con `Object` expresiones en `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="54f94-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="54f94-171">Cuando `Option Strict` es `Off` , y `expression1` o `expression2` es una `Object` expresión, los tipos en tiempo de ejecución determinan cómo se comparan.</span><span class="sxs-lookup"><span data-stu-id="54f94-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="54f94-172">En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.</span><span class="sxs-lookup"><span data-stu-id="54f94-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="54f94-173">Si los operandos son</span><span class="sxs-lookup"><span data-stu-id="54f94-173">If operands are</span></span>|<span data-ttu-id="54f94-174">La comparación es</span><span class="sxs-lookup"><span data-stu-id="54f94-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="54f94-175">Ambos `String`</span><span class="sxs-lookup"><span data-stu-id="54f94-175">Both `String`</span></span>|<span data-ttu-id="54f94-176">Ordenar la comparación en función de las características de ordenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="54f94-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="54f94-177">Ambos numéricos</span><span class="sxs-lookup"><span data-stu-id="54f94-177">Both numeric</span></span>|<span data-ttu-id="54f94-178">Objetos convertidos en `Double` , comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="54f94-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="54f94-179">Un valor numérico y uno `String`</span><span class="sxs-lookup"><span data-stu-id="54f94-179">One numeric and one `String`</span></span>|<span data-ttu-id="54f94-180">`String`Se convierte en `Double` y se realiza una comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="54f94-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="54f94-181">Si `String` no se puede convertir en `Double` , <xref:System.InvalidCastException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="54f94-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="54f94-182">Uno o ambos son tipos de referencia distintos de `String`</span><span class="sxs-lookup"><span data-stu-id="54f94-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="54f94-183">Se inicia una <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="54f94-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="54f94-184">Las comparaciones numéricas se tratan `Nothing` como 0.</span><span class="sxs-lookup"><span data-stu-id="54f94-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="54f94-185">Las comparaciones `Nothing` de cadenas tratan como `""` (una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="54f94-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="54f94-186">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="54f94-186">Overloading</span></span>

 <span data-ttu-id="54f94-187">Operadores de comparación relacionales ( `<` .</span><span class="sxs-lookup"><span data-stu-id="54f94-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="54f94-188">`<=`, `>` , `>=` , `=` , `<>` ) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="54f94-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="54f94-189">Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprende el comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="54f94-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="54f94-190">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="54f94-190">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="54f94-191">Observe que el [operador =](assignment-operator.md) solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="54f94-191">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="54f94-192">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54f94-192">Example</span></span>

 <span data-ttu-id="54f94-193">En el ejemplo siguiente se muestran varios usos de operadores de comparación relacionales, que se usan para comparar expresiones.</span><span class="sxs-lookup"><span data-stu-id="54f94-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="54f94-194">Los operadores de comparación relacional devuelven un `Boolean` resultado que indica si la expresión indicada se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="54f94-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="54f94-195">Cuando se aplican `>` los `<` operadores y a las cadenas, la comparación se realiza utilizando el criterio de ordenación alfabético normal de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="54f94-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="54f94-196">Este orden puede depender de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="54f94-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="54f94-197">La ordenación distingue entre mayúsculas y minúsculas o no depende del valor [Option Compare](../statements/option-compare-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="54f94-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="54f94-198">En el ejemplo anterior, la primera comparación devuelve `False` y las comparaciones restantes devuelven `True` .</span><span class="sxs-lookup"><span data-stu-id="54f94-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="54f94-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54f94-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="54f94-200">= (Operador)</span><span class="sxs-lookup"><span data-stu-id="54f94-200">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="54f94-201">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54f94-201">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="54f94-202">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="54f94-202">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="54f94-203">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="54f94-203">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="54f94-204">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54f94-204">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
