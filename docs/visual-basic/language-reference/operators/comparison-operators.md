---
description: 'Más información acerca de: operadores de comparación (Visual Basic)'
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
ms.openlocfilehash: 28eded0cfae54ec83ad9546b801243e4de0e45fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774114"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="916ef-103">Operadores de comparación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916ef-103">Comparison Operators (Visual Basic)</span></span>

<span data-ttu-id="916ef-104">A continuación se muestran los operadores de comparación definidos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="916ef-104">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="916ef-105">`<` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-105">`<` operator</span></span>

 <span data-ttu-id="916ef-106">`<=` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-106">`<=` operator</span></span>

 <span data-ttu-id="916ef-107">`>` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-107">`>` operator</span></span>

 <span data-ttu-id="916ef-108">`>=` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-108">`>=` operator</span></span>

 <span data-ttu-id="916ef-109">`=` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-109">`=` operator</span></span>

 <span data-ttu-id="916ef-110">`<>` Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-110">`<>` operator</span></span>

 [<span data-ttu-id="916ef-111">Operador Is</span><span class="sxs-lookup"><span data-stu-id="916ef-111">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="916ef-112">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="916ef-112">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="916ef-113">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="916ef-113">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="916ef-114">Estos operadores comparan dos expresiones para determinar si son iguales o no, y si no, cómo se diferencian.</span><span class="sxs-lookup"><span data-stu-id="916ef-114">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="916ef-115">`Is`, `IsNot` y `Like` se describen en detalle en páginas de ayuda independientes.</span><span class="sxs-lookup"><span data-stu-id="916ef-115">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="916ef-116">Los operadores de comparación relacional se describen en detalle en esta página.</span><span class="sxs-lookup"><span data-stu-id="916ef-116">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="916ef-117">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="916ef-117">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="916ef-118">Partes</span><span class="sxs-lookup"><span data-stu-id="916ef-118">Parts</span></span>

 `result`  
 <span data-ttu-id="916ef-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="916ef-119">Required.</span></span> <span data-ttu-id="916ef-120">`Boolean`Valor que representa el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="916ef-120">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="916ef-121">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="916ef-121">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="916ef-122">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="916ef-122">Required.</span></span> <span data-ttu-id="916ef-123">Cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="916ef-123">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="916ef-124">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="916ef-124">Required.</span></span> <span data-ttu-id="916ef-125">Cualquier operador de comparación relacional.</span><span class="sxs-lookup"><span data-stu-id="916ef-125">Any relational comparison operator.</span></span>

 <span data-ttu-id="916ef-126">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="916ef-126">`object1`, `object2`</span></span>  
 <span data-ttu-id="916ef-127">Necesario.</span><span class="sxs-lookup"><span data-stu-id="916ef-127">Required.</span></span> <span data-ttu-id="916ef-128">Cualquier nombre de objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="916ef-128">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="916ef-129">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="916ef-129">Required.</span></span> <span data-ttu-id="916ef-130">Cualquier expresión `String` .</span><span class="sxs-lookup"><span data-stu-id="916ef-130">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="916ef-131">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="916ef-131">Required.</span></span> <span data-ttu-id="916ef-132">Cualquier `String` expresión o intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="916ef-132">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="916ef-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="916ef-133">Remarks</span></span>

 <span data-ttu-id="916ef-134">La tabla siguiente contiene una lista de los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="916ef-134">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="916ef-135">Operator</span><span class="sxs-lookup"><span data-stu-id="916ef-135">Operator</span></span>|<span data-ttu-id="916ef-136">`True` si</span><span class="sxs-lookup"><span data-stu-id="916ef-136">`True` if</span></span>|<span data-ttu-id="916ef-137">`False` si</span><span class="sxs-lookup"><span data-stu-id="916ef-137">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="916ef-138">`<` (Menor que)</span><span class="sxs-lookup"><span data-stu-id="916ef-138">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="916ef-139">`<=` (Menor o igual que)</span><span class="sxs-lookup"><span data-stu-id="916ef-139">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="916ef-140">`>` (Mayor que)</span><span class="sxs-lookup"><span data-stu-id="916ef-140">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="916ef-141">`>=` (Mayor o igual que)</span><span class="sxs-lookup"><span data-stu-id="916ef-141">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="916ef-142">`=` (Igual a)</span><span class="sxs-lookup"><span data-stu-id="916ef-142">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="916ef-143">`<>` (No es igual a)</span><span class="sxs-lookup"><span data-stu-id="916ef-143">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="916ef-144">El [operador =](assignment-operator.md) también se usa como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="916ef-144">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="916ef-145">El `Is` operador, el `IsNot` operador y el `Like` operador tienen funcionalidades de comparación específicas que difieren de los operadores de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="916ef-145">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="916ef-146">Comparar números</span><span class="sxs-lookup"><span data-stu-id="916ef-146">Comparing Numbers</span></span>

 <span data-ttu-id="916ef-147">Al comparar una expresión de tipo `Single` con una de tipo `Double` , la `Single` expresión se convierte en `Double` .</span><span class="sxs-lookup"><span data-stu-id="916ef-147">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="916ef-148">Este comportamiento es opuesto al comportamiento que se encuentra en Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="916ef-148">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="916ef-149">Del mismo modo, al comparar una expresión de tipo `Decimal` con una expresión de tipo `Single` o `Double` , la `Decimal` expresión se convierte en `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="916ef-149">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="916ef-150">En el caso de `Decimal` las expresiones, se puede perder cualquier valor fraccionario inferior a 1E-28.</span><span class="sxs-lookup"><span data-stu-id="916ef-150">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="916ef-151">Esta pérdida de valor fraccionario puede hacer que dos valores se comparen como iguales cuando no lo son.</span><span class="sxs-lookup"><span data-stu-id="916ef-151">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="916ef-152">Por este motivo, debe tener cuidado al usar la igualdad ( `=` ) para comparar dos variables de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="916ef-152">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="916ef-153">Es más seguro probar si el valor absoluto de la diferencia entre los dos números es menor que una pequeña tolerancia aceptable.</span><span class="sxs-lookup"><span data-stu-id="916ef-153">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="916ef-154">Imprecisión de punto flotante</span><span class="sxs-lookup"><span data-stu-id="916ef-154">Floating-point Imprecision</span></span>

 <span data-ttu-id="916ef-155">Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="916ef-155">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="916ef-156">Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el [operador mod](mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="916ef-156">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="916ef-157">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="916ef-157">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="916ef-158">Comparar cadenas</span><span class="sxs-lookup"><span data-stu-id="916ef-158">Comparing Strings</span></span>

 <span data-ttu-id="916ef-159">Cuando se comparan cadenas, las expresiones de cadena se evalúan en función de su criterio de ordenación alfabético, que depende de la `Option Compare` configuración.</span><span class="sxs-lookup"><span data-stu-id="916ef-159">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="916ef-160">`Option Compare Binary` basa las comparaciones de cadenas en un criterio de ordenación derivado de las representaciones binarias internas de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="916ef-160">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="916ef-161">La página de códigos determina el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="916ef-161">The sort order is determined by the code page.</span></span> <span data-ttu-id="916ef-162">En el ejemplo siguiente se muestra un criterio de ordenación binario típico.</span><span class="sxs-lookup"><span data-stu-id="916ef-162">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="916ef-163">`Option Compare Text` basa las comparaciones de cadenas en un criterio de ordenación textual que no distingue entre mayúsculas y minúsculas, determinado por la configuración regional de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="916ef-163">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="916ef-164">Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el siguiente criterio de ordenación de texto:</span><span class="sxs-lookup"><span data-stu-id="916ef-164">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="916ef-165">Dependencia de la configuración regional</span><span class="sxs-lookup"><span data-stu-id="916ef-165">Locale Dependence</span></span>

 <span data-ttu-id="916ef-166">Al establecer `Option Compare Text` , el resultado de una comparación de cadenas puede depender de la configuración regional en la que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="916ef-166">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="916ef-167">Dos caracteres podrían compararse como iguales en una configuración regional, pero no en otra.</span><span class="sxs-lookup"><span data-stu-id="916ef-167">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="916ef-168">Si utiliza una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe alertar a la confidencialidad de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="916ef-168">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="916ef-169">Considere la posibilidad de establecer `Option Compare Binary` o llamar a <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , que tiene en cuenta la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="916ef-169">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="916ef-170">Programación sin tipos con operadores de comparación relacionales</span><span class="sxs-lookup"><span data-stu-id="916ef-170">Typeless Programming with Relational Comparison Operators</span></span>

 <span data-ttu-id="916ef-171">No se permite el uso de operadores de comparación relacionales con `Object` expresiones en `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="916ef-171">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="916ef-172">Cuando `Option Strict` es `Off` , y `expression1` o `expression2` es una `Object` expresión, los tipos en tiempo de ejecución determinan cómo se comparan.</span><span class="sxs-lookup"><span data-stu-id="916ef-172">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="916ef-173">En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.</span><span class="sxs-lookup"><span data-stu-id="916ef-173">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="916ef-174">Si los operandos son</span><span class="sxs-lookup"><span data-stu-id="916ef-174">If operands are</span></span>|<span data-ttu-id="916ef-175">La comparación es</span><span class="sxs-lookup"><span data-stu-id="916ef-175">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="916ef-176">Ambos `String`</span><span class="sxs-lookup"><span data-stu-id="916ef-176">Both `String`</span></span>|<span data-ttu-id="916ef-177">Ordenar la comparación en función de las características de ordenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="916ef-177">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="916ef-178">Ambos numéricos</span><span class="sxs-lookup"><span data-stu-id="916ef-178">Both numeric</span></span>|<span data-ttu-id="916ef-179">Objetos convertidos en `Double` , comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="916ef-179">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="916ef-180">Un valor numérico y uno `String`</span><span class="sxs-lookup"><span data-stu-id="916ef-180">One numeric and one `String`</span></span>|<span data-ttu-id="916ef-181">`String`Se convierte en `Double` y se realiza una comparación numérica.</span><span class="sxs-lookup"><span data-stu-id="916ef-181">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="916ef-182">Si `String` no se puede convertir en `Double` , <xref:System.InvalidCastException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="916ef-182">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="916ef-183">Uno o ambos son tipos de referencia distintos de `String`</span><span class="sxs-lookup"><span data-stu-id="916ef-183">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="916ef-184">Se inicia una <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="916ef-184">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="916ef-185">Las comparaciones numéricas se tratan `Nothing` como 0.</span><span class="sxs-lookup"><span data-stu-id="916ef-185">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="916ef-186">Las comparaciones `Nothing` de cadenas tratan como `""` (una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="916ef-186">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="916ef-187">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="916ef-187">Overloading</span></span>

 <span data-ttu-id="916ef-188">Operadores de comparación relacionales ( `<` .</span><span class="sxs-lookup"><span data-stu-id="916ef-188">The relational comparison operators (`<`.</span></span> <span data-ttu-id="916ef-189">`<=`, `>` , `>=` , `=` , `<>` ) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="916ef-189">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="916ef-190">Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprende el comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="916ef-190">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="916ef-191">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="916ef-191">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="916ef-192">Observe que el [operador =](assignment-operator.md) solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="916ef-192">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="916ef-193">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="916ef-193">Example</span></span>

 <span data-ttu-id="916ef-194">En el ejemplo siguiente se muestran varios usos de operadores de comparación relacionales, que se usan para comparar expresiones.</span><span class="sxs-lookup"><span data-stu-id="916ef-194">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="916ef-195">Los operadores de comparación relacional devuelven un `Boolean` resultado que indica si la expresión indicada se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="916ef-195">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="916ef-196">Cuando se aplican `>` los `<` operadores y a las cadenas, la comparación se realiza utilizando el criterio de ordenación alfabético normal de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="916ef-196">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="916ef-197">Este orden puede depender de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="916ef-197">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="916ef-198">La ordenación distingue entre mayúsculas y minúsculas o no depende del valor [Option Compare](../statements/option-compare-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="916ef-198">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="916ef-199">En el ejemplo anterior, la primera comparación devuelve `False` y las comparaciones restantes devuelven `True` .</span><span class="sxs-lookup"><span data-stu-id="916ef-199">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="916ef-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="916ef-200">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="916ef-201">= (Operador)</span><span class="sxs-lookup"><span data-stu-id="916ef-201">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="916ef-202">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="916ef-202">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="916ef-203">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="916ef-203">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="916ef-204">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="916ef-204">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="916ef-205">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="916ef-205">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
