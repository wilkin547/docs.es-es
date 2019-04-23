---
title: Tipos de valor que acepta valores NULL - Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: d17d2ad3fd99c6d563c21ddd646396ccb1c1ca48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58921317"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="697d7-102">Tipos que admiten valores null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="697d7-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="697d7-103">A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="697d7-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="697d7-104">Por ejemplo, podría tener un campo en una base de datos distinguir entre tener un valor asignado que es significativo y no tener un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="697d7-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="697d7-105">Tipos de valor pueden ampliarse para aprovechar sus valores normales o un valor null.</span><span class="sxs-lookup"><span data-stu-id="697d7-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="697d7-106">Se llama a este tipo de extensión un *tipo que acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="697d7-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="697d7-107">Cada tipo que acepta valores NULL se construye a partir del genérico <xref:System.Nullable%601> estructura.</span><span class="sxs-lookup"><span data-stu-id="697d7-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="697d7-108">Considere la posibilidad de una base de datos que realiza el seguimiento de las actividades relacionadas con el trabajo.</span><span class="sxs-lookup"><span data-stu-id="697d7-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="697d7-109">En el ejemplo siguiente se crea un que acepta valores NULL `Boolean` escriba y declara una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="697d7-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="697d7-110">Puede escribir la declaración de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="697d7-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="697d7-111">La variable `ridesBusToWork` puede contener un valor de `True`, un valor de `False`, o ningún valor en absoluto.</span><span class="sxs-lookup"><span data-stu-id="697d7-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="697d7-112">Su valor predeterminado inicial no es ningún valor en absoluto, lo que en este caso podría significar que la información no se ha obtenido para esa persona.</span><span class="sxs-lookup"><span data-stu-id="697d7-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="697d7-113">En cambio, `False` puede significar que se ha obtenido la información y la persona que no utiliza el autobús funcione.</span><span class="sxs-lookup"><span data-stu-id="697d7-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="697d7-114">Puede declarar variables y propiedades con tipos que aceptan valores NULL y puede declarar una matriz con elementos de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="697d7-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="697d7-115">Puede declarar procedimientos con tipos que aceptan valores NULL como parámetros y devolver un tipo que acepta valores NULL de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="697d7-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="697d7-116">No se puede construir un tipo que acepta valores NULL en un tipo de referencia como una matriz, un `String`, o una clase.</span><span class="sxs-lookup"><span data-stu-id="697d7-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="697d7-117">El tipo subyacente debe ser un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="697d7-117">The underlying type must be a value type.</span></span> <span data-ttu-id="697d7-118">Para obtener más información, consulta [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="697d7-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="697d7-119">Uso de una Variable de tipo que acepta valores null</span><span class="sxs-lookup"><span data-stu-id="697d7-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="697d7-120">Los miembros más importantes de un tipo que acepta valores NULL son su <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="697d7-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="697d7-121">Para una variable de un tipo que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido.</span><span class="sxs-lookup"><span data-stu-id="697d7-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="697d7-122">Si <xref:System.Nullable%601.HasValue%2A> es `True`, puede leer el valor de <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="697d7-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="697d7-123">Tenga en cuenta que ambos <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son `ReadOnly` propiedades.</span><span class="sxs-lookup"><span data-stu-id="697d7-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="697d7-124">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="697d7-124">Default Values</span></span>

<span data-ttu-id="697d7-125">Cuando se declara una variable con un tipo que acepta valores NULL, su <xref:System.Nullable%601.HasValue%2A> propiedad tiene un valor predeterminado de `False`.</span><span class="sxs-lookup"><span data-stu-id="697d7-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="697d7-126">Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="697d7-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="697d7-127">En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado de la `Integer` tipo es 0.</span><span class="sxs-lookup"><span data-stu-id="697d7-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="697d7-128">Un valor null es útil para indicar un valor indefinido o desconocido.</span><span class="sxs-lookup"><span data-stu-id="697d7-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="697d7-129">Si `numberOfChildren` se ha declarado como `Integer`, no habría ningún valor que podría indicar que la información no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="697d7-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="697d7-130">Almacenamiento de valores</span><span class="sxs-lookup"><span data-stu-id="697d7-130">Storing Values</span></span>

<span data-ttu-id="697d7-131">Almacenar un valor en una variable o propiedad de un tipo que acepta valores NULL de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="697d7-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="697d7-132">En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="697d7-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="697d7-133">Si una variable o propiedad de un tipo que acepta valores NULL contiene un valor definido, puede provocar que vuelva a su estado inicial de no tener un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="697d7-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="697d7-134">Para ello, Establece la variable o propiedad a `Nothing`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="697d7-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="697d7-135">Aunque puede asignar `Nothing` a una variable de un tipo que acepta valores NULL, no se puede probar para `Nothing` mediante el uso del signo igual.</span><span class="sxs-lookup"><span data-stu-id="697d7-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="697d7-136">Comparación que utiliza el signo igual, `someVar = Nothing`, siempre se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="697d7-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="697d7-137">Puede probar la variable <xref:System.Nullable%601.HasValue%2A> propiedad `False`, o probar mediante el `Is` o `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="697d7-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="697d7-138">Recuperación de valores</span><span class="sxs-lookup"><span data-stu-id="697d7-138">Retrieving Values</span></span>

<span data-ttu-id="697d7-139">Para recuperar el valor de una variable de un tipo que acepta valores NULL, debe probar su <xref:System.Nullable%601.HasValue%2A> propiedad para confirmar que tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="697d7-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="697d7-140">Si se intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False`, Visual Basic produce una <xref:System.InvalidOperationException> excepción.</span><span class="sxs-lookup"><span data-stu-id="697d7-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="697d7-141">El ejemplo siguiente muestra la manera recomendada para leer la variable `numberOfChildren` de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="697d7-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="697d7-142">Comparación de tipos que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="697d7-142">Comparing Nullable Types</span></span>

<span data-ttu-id="697d7-143">Cuando acepta valores NULL `Boolean` variables se usan en expresiones booleanas, el resultado puede ser `True`, `False`, o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="697d7-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="697d7-144">El siguiente es la tabla de verdad para `And` y `Or`.</span><span class="sxs-lookup"><span data-stu-id="697d7-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="697d7-145">Dado que `b1` y `b2` ahora tiene tres valores posibles, hay nueve combinaciones para evaluar.</span><span class="sxs-lookup"><span data-stu-id="697d7-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="697d7-146">b1</span><span class="sxs-lookup"><span data-stu-id="697d7-146">b1</span></span>|<span data-ttu-id="697d7-147">b2</span><span class="sxs-lookup"><span data-stu-id="697d7-147">b2</span></span>|<span data-ttu-id="697d7-148">B1 y b2</span><span class="sxs-lookup"><span data-stu-id="697d7-148">b1 And b2</span></span>|<span data-ttu-id="697d7-149">B1 o b2</span><span class="sxs-lookup"><span data-stu-id="697d7-149">b1 Or b2</span></span>|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

<span data-ttu-id="697d7-150">Cuando el valor de una variable o expresión booleana es `Nothing`, ninguna de ellas es `true` ni `false`.</span><span class="sxs-lookup"><span data-stu-id="697d7-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="697d7-151">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="697d7-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="697d7-152">En este ejemplo, `b1 And b2` se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="697d7-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="697d7-153">Como resultado, el `Else` cláusula se ejecuta en cada `If` instrucción y el resultado es como sigue:</span><span class="sxs-lookup"><span data-stu-id="697d7-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="697d7-154">`AndAlso` y `OrElse`, que usan cortocircuitar la evaluación, debe evaluar los operandos segundo cuando se evalúa como el primer `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="697d7-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="697d7-155">Propagación</span><span class="sxs-lookup"><span data-stu-id="697d7-155">Propagation</span></span>

<span data-ttu-id="697d7-156">Si uno o ambos operandos de una aritmética, comparación, MAYÚS o de operación de tipo acepta valores NULL, el resultado de la operación también es que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="697d7-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="697d7-157">Si ambos operandos tienen valores que no son `Nothing`, la operación se realiza en los valores subyacentes de los operandos, como si no fuera un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="697d7-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="697d7-158">En el ejemplo siguiente, las variables `compare1` y `sum1` tipos se declaran implícitamente.</span><span class="sxs-lookup"><span data-stu-id="697d7-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="697d7-159">Si sitúa el puntero del mouse sobre ellos, verá que el compilador infiere los tipos que aceptan valores NULL para ambas.</span><span class="sxs-lookup"><span data-stu-id="697d7-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="697d7-160">Si uno o ambos operandos tienen un valor de `Nothing`, el resultado será `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="697d7-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="697d7-161">Utilizar tipos que aceptan valores NULL con datos</span><span class="sxs-lookup"><span data-stu-id="697d7-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="697d7-162">Una base de datos es uno de los lugares más importantes para utilizar tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="697d7-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="697d7-163">Actualmente, no todos los objetos de base de datos admiten tipos que aceptan valores NULL, pero hace de los adaptadores de tabla generado por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="697d7-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="697d7-164">Consulte [TableAdapter compatibilidad con tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="697d7-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="697d7-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="697d7-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="697d7-166">Utilizar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="697d7-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="697d7-167">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="697d7-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="697d7-168">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="697d7-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="697d7-169">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="697d7-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="697d7-170">Llenar conjuntos de datos mediante TableAdapters</span><span class="sxs-lookup"><span data-stu-id="697d7-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="697d7-171">If (operador)</span><span class="sxs-lookup"><span data-stu-id="697d7-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="697d7-172">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="697d7-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="697d7-173">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="697d7-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="697d7-174">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="697d7-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)