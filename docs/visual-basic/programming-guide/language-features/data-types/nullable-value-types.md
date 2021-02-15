---
description: 'Más información sobre: tipos de valor que aceptan valores NULL (Visual Basic)'
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
ms.openlocfilehash: acc91d98a3ed288a9bf0bcf6abbd3d8a516bd699
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483890"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="5115d-103">Tipos que admiten valores null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5115d-103">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="5115d-104">A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="5115d-104">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="5115d-105">Por ejemplo, un campo de una base de datos podría tener que distinguir entre tener un valor asignado que sea significativo y que no tenga un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="5115d-105">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="5115d-106">Los tipos de valor se pueden extender para tomar sus valores normales o un valor null.</span><span class="sxs-lookup"><span data-stu-id="5115d-106">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="5115d-107">Dicha extensión se denomina un *tipo que acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="5115d-107">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="5115d-108">Cada tipo de valor que acepta valores NULL se construye a partir de la <xref:System.Nullable%601> estructura genérica.</span><span class="sxs-lookup"><span data-stu-id="5115d-108">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="5115d-109">Considere una base de datos que realice un seguimiento de las actividades relacionadas con el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5115d-109">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="5115d-110">En el ejemplo siguiente se crea un tipo que acepta valores NULL `Boolean` y se declara una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5115d-110">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="5115d-111">Puede escribir la declaración de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="5115d-111">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="5115d-112">La variable `ridesBusToWork` puede contener un valor de `True` , un valor de `False` o ningún valor.</span><span class="sxs-lookup"><span data-stu-id="5115d-112">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="5115d-113">Su valor predeterminado inicial es ningún valor, que en este caso podría significar que la información no se ha obtenido todavía para esta persona.</span><span class="sxs-lookup"><span data-stu-id="5115d-113">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="5115d-114">Por el contrario, `False` podría significar que se ha obtenido la información y que la persona no pasa el bus para que funcione.</span><span class="sxs-lookup"><span data-stu-id="5115d-114">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="5115d-115">Puede declarar variables y propiedades con tipos de valor que aceptan valores NULL y puede declarar una matriz con elementos de un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5115d-115">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="5115d-116">Puede declarar procedimientos con tipos de valor que aceptan valores NULL como parámetros, y puede devolver un tipo de valor que acepta valores NULL de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5115d-116">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="5115d-117">No se puede crear un tipo que acepta valores NULL en un tipo de referencia, como una matriz, una `String` o una clase.</span><span class="sxs-lookup"><span data-stu-id="5115d-117">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="5115d-118">El tipo subyacente debe ser un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="5115d-118">The underlying type must be a value type.</span></span> <span data-ttu-id="5115d-119">Para obtener más información, vea [tipos de valor y tipos de referencia](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="5115d-119">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="5115d-120">Usar una variable de tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="5115d-120">Using a Nullable Type Variable</span></span>

<span data-ttu-id="5115d-121">Los miembros más importantes de un tipo de valor que acepta valores NULL son sus <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> propiedades y.</span><span class="sxs-lookup"><span data-stu-id="5115d-121">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="5115d-122">En el caso de una variable de un tipo de valor que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido.</span><span class="sxs-lookup"><span data-stu-id="5115d-122">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="5115d-123">Si <xref:System.Nullable%601.HasValue%2A> es `True` , puede leer el valor de <xref:System.Nullable%601.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="5115d-123">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="5115d-124">Tenga en cuenta que <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son `ReadOnly` propiedades.</span><span class="sxs-lookup"><span data-stu-id="5115d-124">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="5115d-125">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="5115d-125">Default Values</span></span>

<span data-ttu-id="5115d-126">Cuando se declara una variable con un tipo de valor que acepta valores NULL, su <xref:System.Nullable%601.HasValue%2A> propiedad tiene un valor predeterminado de `False` .</span><span class="sxs-lookup"><span data-stu-id="5115d-126">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="5115d-127">Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="5115d-127">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="5115d-128">En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado del `Integer` tipo sea 0.</span><span class="sxs-lookup"><span data-stu-id="5115d-128">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="5115d-129">Un valor NULL es útil para indicar un valor no definido o desconocido.</span><span class="sxs-lookup"><span data-stu-id="5115d-129">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="5115d-130">Si se `numberOfChildren` hubiera declarado como `Integer` , no habría ningún valor que pudiera indicar que la información no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="5115d-130">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="5115d-131">Almacenar valores</span><span class="sxs-lookup"><span data-stu-id="5115d-131">Storing Values</span></span>

<span data-ttu-id="5115d-132">Puede almacenar un valor en una variable o propiedad de un tipo de valor que acepta valores NULL de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="5115d-132">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="5115d-133">En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5115d-133">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="5115d-134">Si una variable o propiedad de un tipo de valor que acepta valores NULL contiene un valor definido, puede hacer que revierta a su estado inicial de no tener asignado un valor.</span><span class="sxs-lookup"><span data-stu-id="5115d-134">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="5115d-135">Para ello, establezca la variable o la propiedad en `Nothing` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5115d-135">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="5115d-136">Aunque puede asignar `Nothing` a una variable de un tipo de valor que acepta valores NULL, no puede probarla con `Nothing` el signo igual.</span><span class="sxs-lookup"><span data-stu-id="5115d-136">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="5115d-137">La comparación que usa el signo igual, `someVar = Nothing` , siempre se evalúa como `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5115d-137">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="5115d-138">Puede probar la propiedad de la variable <xref:System.Nullable%601.HasValue%2A> para `False` o probar mediante el `Is` `IsNot` operador OR.</span><span class="sxs-lookup"><span data-stu-id="5115d-138">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="5115d-139">Recuperación de valores</span><span class="sxs-lookup"><span data-stu-id="5115d-139">Retrieving Values</span></span>

<span data-ttu-id="5115d-140">Para recuperar el valor de una variable de un tipo de valor que acepta valores NULL, primero debe probar su <xref:System.Nullable%601.HasValue%2A> propiedad para confirmar que tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="5115d-140">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="5115d-141">Si intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False` , Visual Basic produce una <xref:System.InvalidOperationException> excepción.</span><span class="sxs-lookup"><span data-stu-id="5115d-141">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="5115d-142">En el ejemplo siguiente se muestra la forma recomendada de leer la variable `numberOfChildren` de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5115d-142">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="5115d-143">Comparar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="5115d-143">Comparing Nullable Types</span></span>

<span data-ttu-id="5115d-144">Cuando `Boolean` se usan variables que aceptan valores NULL en Expresiones booleanas, el resultado puede ser `True` , `False` o `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5115d-144">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="5115d-145">A continuación se encuentra la tabla de verdad para `And` y `Or` .</span><span class="sxs-lookup"><span data-stu-id="5115d-145">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="5115d-146">Dado que `b1` y `b2` ahora tienen tres valores posibles, hay nueve combinaciones que evaluar.</span><span class="sxs-lookup"><span data-stu-id="5115d-146">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="5115d-147">B1</span><span class="sxs-lookup"><span data-stu-id="5115d-147">b1</span></span>|<span data-ttu-id="5115d-148">B2</span><span class="sxs-lookup"><span data-stu-id="5115d-148">b2</span></span>|<span data-ttu-id="5115d-149">B1 y B2</span><span class="sxs-lookup"><span data-stu-id="5115d-149">b1 And b2</span></span>|<span data-ttu-id="5115d-150">B1 o B2</span><span class="sxs-lookup"><span data-stu-id="5115d-150">b1 Or b2</span></span>|
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

<span data-ttu-id="5115d-151">Cuando el valor de una expresión o variable booleana es `Nothing` , no es `true` ni `false` .</span><span class="sxs-lookup"><span data-stu-id="5115d-151">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="5115d-152">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5115d-152">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="5115d-153">En este ejemplo, `b1 And b2` se evalúa como `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5115d-153">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="5115d-154">Como resultado, la `Else` cláusula se ejecuta en cada `If` instrucción y el resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5115d-154">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="5115d-155">`AndAlso` y `OrElse` , que usan la evaluación de cortocircuito, deben evaluar sus segundos operandos cuando el primero se evalúa como `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5115d-155">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="5115d-156">Propagación</span><span class="sxs-lookup"><span data-stu-id="5115d-156">Propagation</span></span>

<span data-ttu-id="5115d-157">Si uno o los dos operandos de una operación aritmética, de comparación, de desplazamiento o de tipo es un tipo de valor que acepta valores NULL, el resultado de la operación es también un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5115d-157">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="5115d-158">Si ambos operandos tienen valores que no son `Nothing` , la operación se realiza en los valores subyacentes de los operandos, como si ninguno fuese un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5115d-158">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="5115d-159">En el ejemplo siguiente, las variables `compare1` y `sum1` se escriben implícitamente.</span><span class="sxs-lookup"><span data-stu-id="5115d-159">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="5115d-160">Si coloca el puntero del mouse sobre ellos, verá que el compilador deduce los tipos de valor que aceptan valores NULL para ambos.</span><span class="sxs-lookup"><span data-stu-id="5115d-160">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="5115d-161">Si uno o ambos operandos tienen un valor de `Nothing` , el resultado será `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5115d-161">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="5115d-162">Usar tipos que aceptan valores NULL con datos</span><span class="sxs-lookup"><span data-stu-id="5115d-162">Using Nullable Types with Data</span></span>

<span data-ttu-id="5115d-163">Una base de datos es uno de los lugares más importantes para usar tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5115d-163">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="5115d-164">No todos los objetos de base de datos admiten actualmente tipos de valor que aceptan valores NULL, pero sí los adaptadores de tabla generados por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="5115d-164">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="5115d-165">Vea [compatibilidad de TableAdapter con tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="5115d-165">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="5115d-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5115d-166">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="5115d-167">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5115d-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="5115d-168">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="5115d-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="5115d-169">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5115d-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="5115d-170">Rellenar conjuntos de datos mediante TableAdapters</span><span class="sxs-lookup"><span data-stu-id="5115d-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="5115d-171">Operador If</span><span class="sxs-lookup"><span data-stu-id="5115d-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="5115d-172">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="5115d-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="5115d-173">Operador Is</span><span class="sxs-lookup"><span data-stu-id="5115d-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="5115d-174">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="5115d-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="5115d-175">Tipos de valor que aceptan valores NULL (C#)</span><span class="sxs-lookup"><span data-stu-id="5115d-175">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
