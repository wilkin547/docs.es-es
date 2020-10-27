---
title: Tipos de tupla - Referencia de C#
description: 'Obtenga información sobre las tuplas de C#: estructuras de datos ligeras que puede usar para agrupar elementos de datos relacionados de forma flexible'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471777"
---
# <a name="tuple-types-c-reference"></a><span data-ttu-id="62d4c-103">Tipos de tupla (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="62d4c-103">Tuple types (C# reference)</span></span>

<span data-ttu-id="62d4c-104">Disponible en C# 7.0 y versiones posteriores, la característica *tuplas* proporciona una sintaxis concisa para agrupar varios elementos de datos en una estructura de datos ligera.</span><span class="sxs-lookup"><span data-stu-id="62d4c-104">Available in C# 7.0 and later, the *tuples* feature provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="62d4c-105">En el siguiente ejemplo se muestra cómo se puede declarar una variable de tupla, inicializarla y acceder a sus miembros de datos:</span><span class="sxs-lookup"><span data-stu-id="62d4c-105">The following example shows how you can declare a tuple variable, initialize it, and access its data members:</span></span>

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

<span data-ttu-id="62d4c-106">Como se muestra en el ejemplo anterior, para definir un tipo de tupla, se especifican los tipos de todos sus miembros de datos y, opcionalmente, los [nombres de campos](#tuple-field-names).</span><span class="sxs-lookup"><span data-stu-id="62d4c-106">As the preceding example shows, to define a tuple type, you specify types of all its data members and, optionally, the [field names](#tuple-field-names).</span></span> <span data-ttu-id="62d4c-107">No se pueden definir métodos en un tipo de tupla, pero se pueden usar los métodos proporcionados por .NET, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-107">You cannot define methods in a tuple type, but you can use the methods provided by .NET, as the following example shows:</span></span>

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

<span data-ttu-id="62d4c-108">A partir de C# 7.3, los tipos de tupla admiten [operadores de igualdad](../operators/equality-operators.md) `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="62d4c-108">Beginning with C# 7.3, tuple types support [equality operators](../operators/equality-operators.md) `==` and `!=`.</span></span> <span data-ttu-id="62d4c-109">Para obtener más información, consulte la sección [Igualdad de tupla](#tuple-equality).</span><span class="sxs-lookup"><span data-stu-id="62d4c-109">For more information, see the [Tuple equality](#tuple-equality) section.</span></span>

<span data-ttu-id="62d4c-110">Los tipos de tupla son [tipos de valores](value-types.md); los elementos de tupla son campos públicos.</span><span class="sxs-lookup"><span data-stu-id="62d4c-110">Tuple types are [value types](value-types.md); tuple elements are public fields.</span></span> <span data-ttu-id="62d4c-111">Esto hace que las tuplas sean tipos de valor *mutables* .</span><span class="sxs-lookup"><span data-stu-id="62d4c-111">That makes tuples *mutable* value types.</span></span>

> [!NOTE]
> <span data-ttu-id="62d4c-112">La característica de las tuplas requiere el tipo <xref:System.ValueTuple?displayProperty=nameWithType> y los tipos genéricos relacionados (por ejemplo, <xref:System.ValueTuple%602?displayProperty=nameWithType>), que están disponibles en .NET Core y .NET Framework 4.7 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="62d4c-112">The tuples feature requires the <xref:System.ValueTuple?displayProperty=nameWithType> type and related generic types (for example, <xref:System.ValueTuple%602?displayProperty=nameWithType>), which are available in .NET Core and .NET Framework 4.7 and later.</span></span> <span data-ttu-id="62d4c-113">Para usar tuplas en un proyecto que tenga como destino .NET Framework 4.6.2 o versiones anteriores, agregue el paquete NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="62d4c-113">To use tuples in a project that targets .NET Framework 4.6.2 or earlier, add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) to the project.</span></span>

<span data-ttu-id="62d4c-114">Puede definir tuplas con un gran número arbitrario de elementos:</span><span class="sxs-lookup"><span data-stu-id="62d4c-114">You can define tuples with an arbitrary large number of elements:</span></span>

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a><span data-ttu-id="62d4c-115">Casos de uso de tuplas</span><span class="sxs-lookup"><span data-stu-id="62d4c-115">Use cases of tuples</span></span>

<span data-ttu-id="62d4c-116">Uno de los casos de uso más comunes de tuplas es como un tipo devuelto del método.</span><span class="sxs-lookup"><span data-stu-id="62d4c-116">One of the most common use cases of tuples is as a method return type.</span></span> <span data-ttu-id="62d4c-117">Es decir, en lugar de definir [`out`los parámetros del método](../keywords/out-parameter-modifier.md), puede agrupar los resultados del método en un tipo devuelto de tupla, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="62d4c-117">That is, instead of defining [`out` method parameters](../keywords/out-parameter-modifier.md), you can group method results in a tuple return type, as the following example shows:</span></span>

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

<span data-ttu-id="62d4c-118">Como se muestra en el ejemplo anterior, puede trabajar directamente con la instancia de la tupla devuelta o [deconstruirla](#tuple-assignment-and-deconstruction) en variables independientes.</span><span class="sxs-lookup"><span data-stu-id="62d4c-118">As the preceding example shows, you can work with the returned tuple instance directly or [deconstruct](#tuple-assignment-and-deconstruction) it in separate variables.</span></span>

<span data-ttu-id="62d4c-119">También puede utilizar tipos de tupla en lugar de [tipos anónimos](../../programming-guide/classes-and-structs/anonymous-types.md); por ejemplo, en las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="62d4c-119">You can also use tuple types instead of [anonymous types](../../programming-guide/classes-and-structs/anonymous-types.md); for example, in LINQ queries.</span></span> <span data-ttu-id="62d4c-120">Para obtener más información, vea [Elección entre tipos de tupla y anónimos](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span><span class="sxs-lookup"><span data-stu-id="62d4c-120">For more information, see [Choosing between anonymous and tuple types](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span></span>

<span data-ttu-id="62d4c-121">Normalmente, se usan tuplas para agrupar elementos de datos relacionados de forma flexible.</span><span class="sxs-lookup"><span data-stu-id="62d4c-121">Typically, you use tuples to group loosely related data elements.</span></span> <span data-ttu-id="62d4c-122">Esto suele ser útil en métodos de utilidad privados e internos.</span><span class="sxs-lookup"><span data-stu-id="62d4c-122">That is usually useful within private and internal utility methods.</span></span> <span data-ttu-id="62d4c-123">En el caso de la API pública, considere la posibilidad de definir un tipo de [clase](../keywords/class.md) o de [estructura](struct.md).</span><span class="sxs-lookup"><span data-stu-id="62d4c-123">In the case of public API, consider defining a [class](../keywords/class.md) or a [structure](struct.md) type.</span></span>

## <a name="tuple-field-names"></a><span data-ttu-id="62d4c-124">Nombres de campo de tupla</span><span class="sxs-lookup"><span data-stu-id="62d4c-124">Tuple field names</span></span>

<span data-ttu-id="62d4c-125">Puede especificar explícitamente los nombres de campo de tupla en una expresión de inicialización de tuplas o en la definición de un tipo de tupla, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-125">You can explicitly specify the names of tuple fields either in a tuple initialization expression or in the definition of a tuple type, as the following example shows:</span></span>

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

<span data-ttu-id="62d4c-126">A partir de C# 7.1, si no se especifica ningún nombre de campo, se puede deducir del nombre de la variable correspondiente en una expresión de inicialización de tupla, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-126">Beginning with C# 7.1, if you don't specify a field name, it may be inferred from the name of the corresponding variable in a tuple initialization expression, as the following example shows:</span></span>

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

<span data-ttu-id="62d4c-127">Esto se conoce como "inicializadores de proyección de tupla".</span><span class="sxs-lookup"><span data-stu-id="62d4c-127">That's known as tuple projection initializers.</span></span> <span data-ttu-id="62d4c-128">El nombre de una variable no se proyecta en un nombre de campo de tupla en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="62d4c-128">The name of a variable isn't projected onto a tuple field name in the following cases:</span></span>

- <span data-ttu-id="62d4c-129">El nombre del candidato es un nombre de miembro de un tipo de tupla, por ejemplo, `Item3`, `ToString` o `Rest`.</span><span class="sxs-lookup"><span data-stu-id="62d4c-129">The candidate name is a member name of a tuple type, for example, `Item3`, `ToString`, or `Rest`.</span></span>
- <span data-ttu-id="62d4c-130">El nombre del candidato es un duplicado de otro nombre de campo de tupla, ya sea explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="62d4c-130">The candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="62d4c-131">En estos casos, se especifica el nombre de un campo o se accede a un campo por su nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="62d4c-131">In those cases you either explicitly specify the name of a field or access a field by its default name.</span></span>

<span data-ttu-id="62d4c-132">Los nombres predeterminados de los campos de tupla son `Item1`, `Item2`, `Item3`, etc.</span><span class="sxs-lookup"><span data-stu-id="62d4c-132">The default names of tuple fields are `Item1`, `Item2`, `Item3` and so on.</span></span> <span data-ttu-id="62d4c-133">Siempre puede usar el nombre predeterminado de un campo, incluso cuando se especifica un nombre de campo de forma explícita o inferida, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-133">You can always use the default name of a field, even when a field name is specified explicitly or inferred, as the following example shows:</span></span>

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

<span data-ttu-id="62d4c-134">En la [asignación de tuplas](#tuple-assignment-and-deconstruction) y las [comparaciones de igualdad de tuplas](#tuple-equality) no se tienen en cuenta los nombres de campo.</span><span class="sxs-lookup"><span data-stu-id="62d4c-134">[Tuple assignment](#tuple-assignment-and-deconstruction) and [tuple equality comparisons](#tuple-equality) don't take field names into account.</span></span>

<span data-ttu-id="62d4c-135">En el tiempo de compilación, el compilador sustituye los nombres de campo no predeterminados por los nombres predeterminados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="62d4c-135">At compile time, the compiler replaces non-default field names with the corresponding default names.</span></span> <span data-ttu-id="62d4c-136">Como resultado, los nombres de campo especificados o inferidos no están disponibles en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="62d4c-136">As a result, explicitly specified or inferred field names aren't available at run time.</span></span>

## <a name="tuple-assignment-and-deconstruction"></a><span data-ttu-id="62d4c-137">Asignación y deconstrucción de tuplas</span><span class="sxs-lookup"><span data-stu-id="62d4c-137">Tuple assignment and deconstruction</span></span>

<span data-ttu-id="62d4c-138">C# admite la asignación entre tipos de tupla que satisfacen estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="62d4c-138">C# supports assignment between tuple types that satisfy both of the following conditions:</span></span>

- <span data-ttu-id="62d4c-139">ambos tipos de tupla tienen el mismo número de elementos;</span><span class="sxs-lookup"><span data-stu-id="62d4c-139">both tuple types have the same number of elements</span></span>
- <span data-ttu-id="62d4c-140">para cada posición de tupla, el tipo de elemento de tupla de la derecha es el mismo que el tipo de elemento de tupla de la izquierda correspondiente, o bien puede convertirse a este.</span><span class="sxs-lookup"><span data-stu-id="62d4c-140">for each tuple position, the type of the right-hand tuple element is the same as or implicitly convertible to the type of the corresponding left-hand tuple element</span></span>

<span data-ttu-id="62d4c-141">Los valores de elementos de tupla se asignan siguiendo el orden de los elementos de tupla.</span><span class="sxs-lookup"><span data-stu-id="62d4c-141">Tuple element values are assigned following the order of tuple elements.</span></span> <span data-ttu-id="62d4c-142">Los nombres de los campos de tupla se omiten y no se asignan, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-142">The names of tuple fields are ignored and not assigned, as the following example shows:</span></span>

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

<span data-ttu-id="62d4c-143">También puede usar el operador de asignación `=` para *deconstruir* una instancia de tupla en variables independientes.</span><span class="sxs-lookup"><span data-stu-id="62d4c-143">You can also use the assignment operator `=` to *deconstruct* a tuple instance in separate variables.</span></span> <span data-ttu-id="62d4c-144">Para ello, siga uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="62d4c-144">You can do that in one of the following ways:</span></span>

- <span data-ttu-id="62d4c-145">Declarar explícitamente el tipo de cada variable entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="62d4c-145">Explicitly declare the type of each variable inside parentheses:</span></span>

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- <span data-ttu-id="62d4c-146">Usar la palabra clave `var` fuera de los paréntesis para declarar las variables con tipo implícito y permitir que el compilador deduzca sus tipos:</span><span class="sxs-lookup"><span data-stu-id="62d4c-146">Use the `var` keyword outside the parentheses to declare implicitly typed variables and let the compiler infer their types:</span></span>

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- <span data-ttu-id="62d4c-147">Usar variables existentes:</span><span class="sxs-lookup"><span data-stu-id="62d4c-147">Use existing variables:</span></span>

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

<span data-ttu-id="62d4c-148">Para obtener más información sobre la deconstrucción de tuplas y otros tipos, consulte [Deconstrucción de tuplas y otros tipos](../../deconstruct.md).</span><span class="sxs-lookup"><span data-stu-id="62d4c-148">For more information about deconstruction of tuples and other types, see [Deconstructing tuples and other types](../../deconstruct.md).</span></span>

## <a name="tuple-equality"></a><span data-ttu-id="62d4c-149">Igualdad de tupla</span><span class="sxs-lookup"><span data-stu-id="62d4c-149">Tuple equality</span></span>

<span data-ttu-id="62d4c-150">Comenzando con C# 7.3, los tipos de tupla admiten los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="62d4c-150">Beginning with C# 7.3, tuple types support the `==` and `!=` operators.</span></span> <span data-ttu-id="62d4c-151">Estos operadores comparan los miembros del operando izquierdo con los miembros correspondientes del operando derecho, siguiendo el orden de los elementos de la tupla.</span><span class="sxs-lookup"><span data-stu-id="62d4c-151">These operators compare members of the left-hand operand with the corresponding members of the right-hand operand following the order of tuple elements.</span></span>

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

<span data-ttu-id="62d4c-152">Como se muestra en el ejemplo anterior, las operaciones `==` y `!=` no tienen en cuenta los nombres de campo de tupla.</span><span class="sxs-lookup"><span data-stu-id="62d4c-152">As the preceding example shows, the `==` and `!=` operations don't take into account tuple field names.</span></span>

<span data-ttu-id="62d4c-153">Dos tuplas son comparables cuando se cumplen estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="62d4c-153">Two tuples are comparable when both of the following conditions are satisfied:</span></span>

- <span data-ttu-id="62d4c-154">Ambas tuplas tienen el mismo número de elementos.</span><span class="sxs-lookup"><span data-stu-id="62d4c-154">Both tuples have the same number of elements.</span></span> <span data-ttu-id="62d4c-155">Por ejemplo, `t1 != t2` no se compila si `t1` y `t2` tienen números diferentes de elementos.</span><span class="sxs-lookup"><span data-stu-id="62d4c-155">For example, `t1 != t2` doesn't compile if `t1` and `t2` have different numbers of elements.</span></span>
- <span data-ttu-id="62d4c-156">Para cada posición de tupla, los elementos correspondientes de los operandos de la tupla de la izquierda y de la derecha son comparables con los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="62d4c-156">For each tuple position, the corresponding elements from the left-hand and right-hand tuple operands are comparable with the `==` and `!=` operators.</span></span> <span data-ttu-id="62d4c-157">Por ejemplo, `(1, (2, 3)) == ((1, 2), 3)` no se compila porque `1` no es comparable con `(1, 2)`.</span><span class="sxs-lookup"><span data-stu-id="62d4c-157">For example, `(1, (2, 3)) == ((1, 2), 3)` doesn't compile because `1` is not comparable with `(1, 2)`.</span></span>

<span data-ttu-id="62d4c-158">Los operadores `==` y `!=` comparan las tuplas en modo de cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="62d4c-158">The `==` and `!=` operators compare tuples in short-circuiting way.</span></span> <span data-ttu-id="62d4c-159">Es decir, una operación se detiene en cuanto da con un par de elementos que no son iguales o alcanza los extremos de las tuplas.</span><span class="sxs-lookup"><span data-stu-id="62d4c-159">That is, an operation stops as soon as it meets a pair of non equal elements or reaches the ends of tuples.</span></span> <span data-ttu-id="62d4c-160">Sin embargo, antes de cualquier comparación, se evalúan *todos* los elementos de tupla, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62d4c-160">However, before any comparison, *all* tuple elements are evaluated, as the following example shows:</span></span>

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a><span data-ttu-id="62d4c-161">Tuplas como parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="62d4c-161">Tuples as out parameters</span></span>

<span data-ttu-id="62d4c-162">Normalmente, se refactoriza un método que tiene parámetros de [`out`](../keywords/out-parameter-modifier.md) en un método que devuelve una tupla.</span><span class="sxs-lookup"><span data-stu-id="62d4c-162">Typically, you refactor a method that has [`out` parameters](../keywords/out-parameter-modifier.md) into a method that returns a tuple.</span></span> <span data-ttu-id="62d4c-163">Sin embargo, hay casos en los que un parámetro de `out` puede ser de un tipo de tupla.</span><span class="sxs-lookup"><span data-stu-id="62d4c-163">However, there are cases in which an `out` parameter can be of a tuple type.</span></span> <span data-ttu-id="62d4c-164">En el siguiente ejemplo básico se indica cómo trabajar con tuplas como parámetros de `out`:</span><span class="sxs-lookup"><span data-stu-id="62d4c-164">The following example shows how to work with tuples as `out` parameters:</span></span>

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a><span data-ttu-id="62d4c-165">Tuplas frente a `System.Tuple`</span><span class="sxs-lookup"><span data-stu-id="62d4c-165">Tuples vs `System.Tuple`</span></span>

<span data-ttu-id="62d4c-166">Las tuplas de C#, que están respaldadas por tipos de <xref:System.ValueTuple?displayProperty=nameWithType>, son diferentes de las tuplas representadas por tipos de <xref:System.Tuple?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="62d4c-166">C# tuples, which are backed by <xref:System.ValueTuple?displayProperty=nameWithType> types, are different from tuples that are represented by <xref:System.Tuple?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="62d4c-167">Las diferencias principales son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="62d4c-167">The main differences are as follows:</span></span>

- <span data-ttu-id="62d4c-168">Los tipos de `ValueTuple` son [tipos de valores](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="62d4c-168">`ValueTuple` types are [value types](value-types.md).</span></span> <span data-ttu-id="62d4c-169">Los tipos de `Tuple` son [tipos de referencia](../keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="62d4c-169">`Tuple` types are [reference types](../keywords/reference-types.md).</span></span>
- <span data-ttu-id="62d4c-170">Los tipos de `ValueTuple` son mutables.</span><span class="sxs-lookup"><span data-stu-id="62d4c-170">`ValueTuple` types are mutable.</span></span> <span data-ttu-id="62d4c-171">Los tipos de `Tuple` son inmutables.</span><span class="sxs-lookup"><span data-stu-id="62d4c-171">`Tuple` types are immutable.</span></span>
- <span data-ttu-id="62d4c-172">Los miembros de datos de tipos de `ValueTuple` son campos.</span><span class="sxs-lookup"><span data-stu-id="62d4c-172">Data members of `ValueTuple` types are fields.</span></span> <span data-ttu-id="62d4c-173">Los miembros de datos de tipos de `Tuple` son propiedades.</span><span class="sxs-lookup"><span data-stu-id="62d4c-173">Data members of `Tuple` types are properties.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="62d4c-174">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="62d4c-174">C# language specification</span></span>

<span data-ttu-id="62d4c-175">Para obtener más información, consulte las siguientes notas de propuestas de características:</span><span class="sxs-lookup"><span data-stu-id="62d4c-175">For more information, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="62d4c-176">Deducción de nombres de tupla (también conocidos como "inicializadores de proyección de tupla")</span><span class="sxs-lookup"><span data-stu-id="62d4c-176">Infer tuple names (aka. tuple projection initializers)</span></span>](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [<span data-ttu-id="62d4c-177">Compatibilidad con `==` y `!=` en tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="62d4c-177">Support for `==` and `!=` on tuple types</span></span>](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a><span data-ttu-id="62d4c-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="62d4c-178">See also</span></span>

- [<span data-ttu-id="62d4c-179">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="62d4c-179">C# reference</span></span>](../index.md)
- [<span data-ttu-id="62d4c-180">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="62d4c-180">Value types</span></span>](value-types.md)
- [<span data-ttu-id="62d4c-181">Elección entre tipos de tupla y anónimos</span><span class="sxs-lookup"><span data-stu-id="62d4c-181">Choosing between anonymous and tuple types</span></span>](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
