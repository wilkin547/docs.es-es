---
title: 'Tipos de valor que aceptan valores NULL: Visual Basic'
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
ms.openlocfilehash: 072496a560775a8f79274f1d44dd389d6ed5b40d
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71351771"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="b613f-102">Tipos que admiten valores null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b613f-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="b613f-103">A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="b613f-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="b613f-104">Por ejemplo, un campo de una base de datos podría tener que distinguir entre tener un valor asignado que sea significativo y que no tenga un valor asignado.</span><span class="sxs-lookup"><span data-stu-id="b613f-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="b613f-105">Los tipos de valor se pueden extender para tomar sus valores normales o un valor null.</span><span class="sxs-lookup"><span data-stu-id="b613f-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="b613f-106">Dicha extensión se denomina un *tipo que acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="b613f-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="b613f-107">Cada tipo que acepta valores NULL se construye a partir de la estructura genérica <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="b613f-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="b613f-108">Considere una base de datos que realice un seguimiento de las actividades relacionadas con el trabajo.</span><span class="sxs-lookup"><span data-stu-id="b613f-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="b613f-109">En el ejemplo siguiente se crea un tipo `Boolean` que acepta valores NULL y se declara una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="b613f-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="b613f-110">Puede escribir la declaración de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="b613f-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="b613f-111">La variable `ridesBusToWork` puede contener un valor de `True`, un valor de `False` o ningún valor.</span><span class="sxs-lookup"><span data-stu-id="b613f-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="b613f-112">Su valor predeterminado inicial es ningún valor, que en este caso podría significar que la información no se ha obtenido todavía para esta persona.</span><span class="sxs-lookup"><span data-stu-id="b613f-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="b613f-113">Por el contrario, `False` podría significar que se ha obtenido la información y que la persona no ha puesto en marcha el bus.</span><span class="sxs-lookup"><span data-stu-id="b613f-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="b613f-114">Puede declarar variables y propiedades con tipos que aceptan valores NULL, y puede declarar una matriz con elementos de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="b613f-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="b613f-115">Puede declarar procedimientos con tipos que aceptan valores NULL como parámetros y puede devolver un tipo que acepta valores NULL desde un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="b613f-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="b613f-116">No se puede crear un tipo que acepta valores NULL en un tipo de referencia, como una matriz, una `String` o una clase.</span><span class="sxs-lookup"><span data-stu-id="b613f-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="b613f-117">El tipo subyacente debe ser un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="b613f-117">The underlying type must be a value type.</span></span> <span data-ttu-id="b613f-118">Para obtener más información, consulta [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="b613f-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="b613f-119">Usar una variable de tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="b613f-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="b613f-120">Los miembros más importantes de un tipo que acepta valores NULL son sus propiedades <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="b613f-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="b613f-121">En el caso de una variable de un tipo que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido.</span><span class="sxs-lookup"><span data-stu-id="b613f-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="b613f-122">Si <xref:System.Nullable%601.HasValue%2A> es `True`, puede leer el valor de <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="b613f-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="b613f-123">Tenga en cuenta que <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son propiedades @no__t 2.</span><span class="sxs-lookup"><span data-stu-id="b613f-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="b613f-124">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="b613f-124">Default Values</span></span>

<span data-ttu-id="b613f-125">Cuando se declara una variable con un tipo que acepta valores NULL, su propiedad <xref:System.Nullable%601.HasValue%2A> tiene un valor predeterminado de `False`.</span><span class="sxs-lookup"><span data-stu-id="b613f-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="b613f-126">Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="b613f-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="b613f-127">En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado del tipo `Integer` es 0.</span><span class="sxs-lookup"><span data-stu-id="b613f-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="b613f-128">Un valor NULL es útil para indicar un valor no definido o desconocido.</span><span class="sxs-lookup"><span data-stu-id="b613f-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="b613f-129">Si `numberOfChildren` se ha declarado como `Integer`, no habría ningún valor que pudiera indicar que la información no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="b613f-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="b613f-130">Almacenar valores</span><span class="sxs-lookup"><span data-stu-id="b613f-130">Storing Values</span></span>

<span data-ttu-id="b613f-131">Puede almacenar un valor en una variable o propiedad de un tipo que acepta valores NULL de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="b613f-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="b613f-132">En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b613f-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="b613f-133">Si una variable o propiedad de un tipo que acepta valores NULL contiene un valor definido, puede hacer que revierta a su estado inicial de no tener asignado un valor.</span><span class="sxs-lookup"><span data-stu-id="b613f-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="b613f-134">Para ello, establezca la variable o la propiedad en `Nothing`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b613f-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="b613f-135">Aunque puede asignar `Nothing` a una variable de un tipo que acepta valores NULL, no puede probarla para `Nothing` mediante el signo igual.</span><span class="sxs-lookup"><span data-stu-id="b613f-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="b613f-136">La comparación que usa el signo igual, `someVar = Nothing`, siempre se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b613f-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="b613f-137">Puede probar la propiedad <xref:System.Nullable%601.HasValue%2A> de la variable para `False`, o bien probar con el operador `Is` o `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="b613f-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="b613f-138">Recuperación de valores</span><span class="sxs-lookup"><span data-stu-id="b613f-138">Retrieving Values</span></span>

<span data-ttu-id="b613f-139">Para recuperar el valor de una variable de un tipo que acepta valores NULL, primero debe probar su propiedad <xref:System.Nullable%601.HasValue%2A> para confirmar que tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="b613f-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="b613f-140">Si intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False`, Visual Basic produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="b613f-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="b613f-141">En el ejemplo siguiente se muestra la forma recomendada de leer la variable `numberOfChildren` de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="b613f-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="b613f-142">Comparar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="b613f-142">Comparing Nullable Types</span></span>

<span data-ttu-id="b613f-143">Cuando se usan variables `Boolean` que aceptan valores NULL en Expresiones booleanas, el resultado puede ser `True`, `False` o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b613f-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="b613f-144">A continuación se encuentra la tabla de verdad para `And` y `Or`.</span><span class="sxs-lookup"><span data-stu-id="b613f-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="b613f-145">Dado que `b1` y `b2` ahora tienen tres valores posibles, hay nueve combinaciones que evaluar.</span><span class="sxs-lookup"><span data-stu-id="b613f-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="b613f-146">b1</span><span class="sxs-lookup"><span data-stu-id="b613f-146">b1</span></span>|<span data-ttu-id="b613f-147">b2</span><span class="sxs-lookup"><span data-stu-id="b613f-147">b2</span></span>|<span data-ttu-id="b613f-148">B1 y B2</span><span class="sxs-lookup"><span data-stu-id="b613f-148">b1 And b2</span></span>|<span data-ttu-id="b613f-149">B1 o B2</span><span class="sxs-lookup"><span data-stu-id="b613f-149">b1 Or b2</span></span>|
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

<span data-ttu-id="b613f-150">Cuando el valor de una expresión o variable booleana es `Nothing`, no es `true` ni `false`.</span><span class="sxs-lookup"><span data-stu-id="b613f-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="b613f-151">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b613f-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="b613f-152">En este ejemplo, `b1 And b2` se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b613f-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="b613f-153">Como resultado, se ejecuta la cláusula `Else` en cada instrucción `If` y el resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b613f-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="b613f-154">`AndAlso` y `OrElse`, que usan la evaluación de cortocircuito, deben evaluar sus segundos operandos cuando el primero se evalúa como @no__t 2.</span><span class="sxs-lookup"><span data-stu-id="b613f-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="b613f-155">Propagación</span><span class="sxs-lookup"><span data-stu-id="b613f-155">Propagation</span></span>

<span data-ttu-id="b613f-156">Si uno o los dos operandos de una operación aritmética, de comparación, de desplazamiento o de tipo aceptan valores NULL, el resultado de la operación también acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="b613f-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="b613f-157">Si ambos operandos tienen valores que no son `Nothing`, la operación se realiza en los valores subyacentes de los operandos, como si ninguno fuese un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="b613f-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="b613f-158">En el ejemplo siguiente, las variables `compare1` y `sum1` se escriben implícitamente.</span><span class="sxs-lookup"><span data-stu-id="b613f-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="b613f-159">Si coloca el puntero del mouse sobre ellos, verá que el compilador deduce los tipos que aceptan valores NULL para ambos.</span><span class="sxs-lookup"><span data-stu-id="b613f-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="b613f-160">Si uno o ambos operandos tienen un valor de `Nothing`, el resultado será `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b613f-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="b613f-161">Usar tipos que aceptan valores NULL con datos</span><span class="sxs-lookup"><span data-stu-id="b613f-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="b613f-162">Una base de datos es uno de los lugares más importantes para usar tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="b613f-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="b613f-163">No todos los objetos de base de datos admiten actualmente tipos que aceptan valores NULL, pero sí los adaptadores de tabla generados por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b613f-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="b613f-164">Vea [compatibilidad de TableAdapter con tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="b613f-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="b613f-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="b613f-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="b613f-166">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b613f-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="b613f-167">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="b613f-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="b613f-168">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b613f-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="b613f-169">Llenar conjuntos de datos mediante TableAdapters</span><span class="sxs-lookup"><span data-stu-id="b613f-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="b613f-170">If (operador)</span><span class="sxs-lookup"><span data-stu-id="b613f-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="b613f-171">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="b613f-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="b613f-172">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="b613f-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="b613f-173">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="b613f-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="b613f-174">Usar tipos de valor que aceptanC#valores NULL ()</span><span class="sxs-lookup"><span data-stu-id="b613f-174">Using Nullable Value Types (C#)</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
