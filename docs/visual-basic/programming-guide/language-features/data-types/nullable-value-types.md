---
title: Tipos de valores que aceptan valores NULL
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249687"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="0f731-102">Tipos que admiten valores null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f731-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="0f731-103">A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="0f731-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="0f731-104">Por ejemplo, un campo de una base de datos podría tener que distinguir entre tener un valor asignado que sea significativo y no tener un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="0f731-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="0f731-105">Los tipos de valor se pueden extender para tomar sus valores normales o un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="0f731-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="0f731-106">Dicha extensión se denomina tipo que *acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="0f731-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="0f731-107">Cada tipo de valor que acepta <xref:System.Nullable%601> valores NULL se construye a partir de la estructura genérica.</span><span class="sxs-lookup"><span data-stu-id="0f731-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="0f731-108">Considere una base de datos que realiza un seguimiento de las actividades relacionadas con el trabajo.</span><span class="sxs-lookup"><span data-stu-id="0f731-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="0f731-109">En el ejemplo siguiente `Boolean` se construye un tipo que acepta valores NULL y se declara una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0f731-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="0f731-110">Puede escribir la declaración de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="0f731-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="0f731-111">La `ridesBusToWork` variable puede contener `True`un valor `False`de , un valor de , o ningún valor en absoluto.</span><span class="sxs-lookup"><span data-stu-id="0f731-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="0f731-112">Su valor predeterminado inicial no es ningún valor en absoluto, lo que en este caso podría significar que la información aún no se ha obtenido para esta persona.</span><span class="sxs-lookup"><span data-stu-id="0f731-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="0f731-113">Por el `False` contrario, podría significar que la información se ha obtenido y la persona no viaja en el autobús al trabajo.</span><span class="sxs-lookup"><span data-stu-id="0f731-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="0f731-114">Puede declarar variables y propiedades con tipos de valor que aceptan valores NULL y puede declarar una matriz con elementos de un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="0f731-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="0f731-115">Puede declarar procedimientos con tipos de valor que aceptan valores NULL `Function` como parámetros y puede devolver un tipo de valor que acepta valores NULL de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0f731-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="0f731-116">No se puede construir un tipo que acepta valores `String`NULL en un tipo de referencia como una matriz, una o una clase.</span><span class="sxs-lookup"><span data-stu-id="0f731-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="0f731-117">El tipo subyacente debe ser un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0f731-117">The underlying type must be a value type.</span></span> <span data-ttu-id="0f731-118">Para obtener más información, vea [Tipos de valor y tipos](value-types-and-reference-types.md)de referencia .</span><span class="sxs-lookup"><span data-stu-id="0f731-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="0f731-119">Uso de una variable de tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="0f731-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="0f731-120">Los miembros más importantes de un <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> tipo de valor que acepta valores NULL son sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="0f731-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="0f731-121">Para una variable de un <xref:System.Nullable%601.HasValue%2A> tipo de valor que acepta valores NULL, le indica si la variable contiene un valor definido.</span><span class="sxs-lookup"><span data-stu-id="0f731-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="0f731-122">Si <xref:System.Nullable%601.HasValue%2A> `True`es , puede leer <xref:System.Nullable%601.Value%2A>el valor de .</span><span class="sxs-lookup"><span data-stu-id="0f731-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="0f731-123">Tenga en <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> cuenta `ReadOnly` que ambas y son propiedades.</span><span class="sxs-lookup"><span data-stu-id="0f731-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="0f731-124">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="0f731-124">Default Values</span></span>

<span data-ttu-id="0f731-125">Cuando se declara una variable con un <xref:System.Nullable%601.HasValue%2A> tipo de valor `False`que acepta valores NULL, su propiedad tiene un valor predeterminado de .</span><span class="sxs-lookup"><span data-stu-id="0f731-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="0f731-126">Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="0f731-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="0f731-127">En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún `Integer` valor definido, aunque el valor predeterminado del tipo es 0.</span><span class="sxs-lookup"><span data-stu-id="0f731-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="0f731-128">Un valor nulo es útil para indicar un valor indefinido o desconocido.</span><span class="sxs-lookup"><span data-stu-id="0f731-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="0f731-129">Si `numberOfChildren` se hubiera `Integer`declarado como , no habría ningún valor que pudiera indicar que la información no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="0f731-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="0f731-130">Almacenar valores</span><span class="sxs-lookup"><span data-stu-id="0f731-130">Storing Values</span></span>

<span data-ttu-id="0f731-131">Almacenar un valor en una variable o propiedad de un tipo de valor que acepta valores NULL de la manera típica.</span><span class="sxs-lookup"><span data-stu-id="0f731-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="0f731-132">En el ejemplo siguiente se `numberOfChildren` asigna un valor a la variable declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0f731-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="0f731-133">Si una variable o propiedad de un tipo de valor que acepta valores NULL contiene un valor definido, puede hacer que vuelva a su estado inicial de no tener un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="0f731-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="0f731-134">Para ello, establezca la variable `Nothing`o propiedad en , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0f731-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="0f731-135">Aunque puede `Nothing` asignar a una variable de un tipo de `Nothing` valor que acepta valores NULL, no puede probarlo mediante el signo igual.</span><span class="sxs-lookup"><span data-stu-id="0f731-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="0f731-136">La comparación que `someVar = Nothing`utiliza el signo `Nothing`igual, , siempre se evalúa como .</span><span class="sxs-lookup"><span data-stu-id="0f731-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="0f731-137">Puede probar la propiedad <xref:System.Nullable%601.HasValue%2A> de `False`la variable para `Is` `IsNot` , o probar mediante el operador or.</span><span class="sxs-lookup"><span data-stu-id="0f731-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="0f731-138">Recuperación de valores</span><span class="sxs-lookup"><span data-stu-id="0f731-138">Retrieving Values</span></span>

<span data-ttu-id="0f731-139">Para recuperar el valor de una variable de un tipo <xref:System.Nullable%601.HasValue%2A> de valor que acepta valores NULL, primero debe probar su propiedad para confirmar que tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="0f731-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="0f731-140">Si intenta leer el <xref:System.Nullable%601.HasValue%2A> valor `False`cuando es , <xref:System.InvalidOperationException> Visual Basic produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="0f731-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="0f731-141">En el ejemplo siguiente se muestra `numberOfChildren` la forma recomendada de leer la variable de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="0f731-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="0f731-142">Comparación de tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="0f731-142">Comparing Nullable Types</span></span>

<span data-ttu-id="0f731-143">Cuando se `Boolean` utilizan variables que aceptan valores `True`NULL `False`en `Nothing`expresiones booleanas, el resultado puede ser , , o .</span><span class="sxs-lookup"><span data-stu-id="0f731-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="0f731-144">La siguiente es la `And` `Or`tabla de la verdad para y .</span><span class="sxs-lookup"><span data-stu-id="0f731-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="0f731-145">Dado `b1` `b2` que y ahora tienen tres valores posibles, hay nueve combinaciones para evaluar.</span><span class="sxs-lookup"><span data-stu-id="0f731-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="0f731-146">b1</span><span class="sxs-lookup"><span data-stu-id="0f731-146">b1</span></span>|<span data-ttu-id="0f731-147">B2</span><span class="sxs-lookup"><span data-stu-id="0f731-147">b2</span></span>|<span data-ttu-id="0f731-148">b1 Y b2</span><span class="sxs-lookup"><span data-stu-id="0f731-148">b1 And b2</span></span>|<span data-ttu-id="0f731-149">b1 O b2</span><span class="sxs-lookup"><span data-stu-id="0f731-149">b1 Or b2</span></span>|
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

<span data-ttu-id="0f731-150">Cuando el valor de una `Nothing`variable o `true` expresión `false`booleana es , no es ni .</span><span class="sxs-lookup"><span data-stu-id="0f731-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="0f731-151">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0f731-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="0f731-152">En este `b1 And b2` ejemplo, `Nothing`se evalúa como .</span><span class="sxs-lookup"><span data-stu-id="0f731-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="0f731-153">Como resultado, `Else` la cláusula se `If` ejecuta en cada instrucción y la salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f731-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="0f731-154">`AndAlso`y `OrElse`, que utilizan la evaluación de cortocircuito, deben evaluar `Nothing`sus segundos operandos cuando el primero se evalúa como .</span><span class="sxs-lookup"><span data-stu-id="0f731-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="0f731-155">Propagación</span><span class="sxs-lookup"><span data-stu-id="0f731-155">Propagation</span></span>

<span data-ttu-id="0f731-156">Si uno o ambos de los operandos de una operación aritmética, de comparación, de desplazamiento o de tipo es un tipo de valor que acepta valores NULL, el resultado de la operación también es un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="0f731-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="0f731-157">Si ambos operandos tienen `Nothing`valores que no lo son, la operación se realiza en los valores subyacentes de los operandos, como si ninguno de los dos fuera un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="0f731-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="0f731-158">En el ejemplo siguiente, las variables `compare1` y `sum1` se escriben implícitamente.</span><span class="sxs-lookup"><span data-stu-id="0f731-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="0f731-159">Si descansa el puntero del mouse sobre ellos, verá que el compilador deduce tipos de valor que aceptan valores NULL para ambos.</span><span class="sxs-lookup"><span data-stu-id="0f731-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="0f731-160">Si uno o ambos operandos `Nothing`tienen un `Nothing`valor de , el resultado será .</span><span class="sxs-lookup"><span data-stu-id="0f731-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="0f731-161">Uso de tipos que aceptan valores NULL con datos</span><span class="sxs-lookup"><span data-stu-id="0f731-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="0f731-162">Una base de datos es uno de los lugares más importantes para usar tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="0f731-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="0f731-163">No todos los objetos de base de datos admiten actualmente tipos de valor que aceptan valores NULL, pero sí los adaptadores de tabla generados por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="0f731-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="0f731-164">Consulte [Compatibilidad con TableAdapter para tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="0f731-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f731-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f731-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="0f731-166">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0f731-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="0f731-167">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="0f731-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="0f731-168">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0f731-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="0f731-169">Rellenar conjuntos de datos mediante TableAdapters</span><span class="sxs-lookup"><span data-stu-id="0f731-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="0f731-170">Operador If</span><span class="sxs-lookup"><span data-stu-id="0f731-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="0f731-171">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="0f731-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="0f731-172">Operador Is</span><span class="sxs-lookup"><span data-stu-id="0f731-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="0f731-173">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="0f731-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="0f731-174">Tipos de valor que aceptan valores NULL (C-)</span><span class="sxs-lookup"><span data-stu-id="0f731-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
