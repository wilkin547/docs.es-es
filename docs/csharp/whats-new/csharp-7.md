---
title: Novedades de C# 7.0 | Guía de C#
description: Obtenga información general de las nuevas características de la versión 7.0 del lenguaje C#.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 897729022e45e96d0f54057ef4dad1a4fc0d6799
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480847"
---
# <a name="whats-new-in-c-70-through-c-73"></a><span data-ttu-id="5057b-103">Novedades de C# 7.0 hasta C# 7.3</span><span class="sxs-lookup"><span data-stu-id="5057b-103">What's new in C# 7.0 through C# 7.3</span></span>

<span data-ttu-id="5057b-104">Entre C# 7.0 y C# 7.3 se han incorporado varias características y mejoras incrementales en la experiencia de desarrollo con C#.</span><span class="sxs-lookup"><span data-stu-id="5057b-104">C# 7.0 through C# 7.3 brought a number of features and incremental improvements to your development experience with C#.</span></span> <span data-ttu-id="5057b-105">En este artículo se proporciona información general sobre las nuevas características y opciones del compilador del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5057b-105">This article provides an overview of the new language features and compiler options.</span></span> <span data-ttu-id="5057b-106">Se describe el comportamiento para C# 7.3, que es la versión más reciente compatible con las aplicaciones basadas en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5057b-106">The descriptions describe the behavior for C# 7.3, which is the most recent version supported for .NET Framework-based applications.</span></span>

<span data-ttu-id="5057b-107">El elemento de configuración de [selección de versión del lenguaje](../language-reference/configure-language-version.md) se agregó con C# 7.1, lo que permite especificar la versión de lenguaje del compilador en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5057b-107">The [language version selection](../language-reference/configure-language-version.md) configuration element was added with C# 7.1, which enables you to specify the compiler language version in your project file.</span></span>

<span data-ttu-id="5057b-108">En C# 7.0-7.3 se agregan estas características y temas al lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="5057b-108">C# 7.0-7.3 adds these features and themes to the C# language:</span></span>

- [<span data-ttu-id="5057b-109">Tuplas y descartes</span><span class="sxs-lookup"><span data-stu-id="5057b-109">Tuples and discards</span></span>](#tuples-and-discards)
  - <span data-ttu-id="5057b-110">Puede crear tipos ligeros sin nombre que contengan varios campos públicos.</span><span class="sxs-lookup"><span data-stu-id="5057b-110">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="5057b-111">Los compiladores y las herramientas IDE comprenden la semántica de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="5057b-111">Compilers and IDE tools understand the semantics of these types.</span></span>
  - <span data-ttu-id="5057b-112">Los descartes son variables temporales y de solo escritura que se usan en argumentos cuando el valor asignado es indiferente.</span><span class="sxs-lookup"><span data-stu-id="5057b-112">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="5057b-113">Son especialmente útiles al deconstruir tuplas y tipos definidos por el usuario, así como al realizar llamadas a métodos con parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="5057b-113">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
- [<span data-ttu-id="5057b-114">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="5057b-114">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="5057b-115">Puede crear la lógica de bifurcación en función de tipos y valores arbitrarios de los miembros de esos tipos.</span><span class="sxs-lookup"><span data-stu-id="5057b-115">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
- [<span data-ttu-id="5057b-116">Método `async` `Main`</span><span class="sxs-lookup"><span data-stu-id="5057b-116">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="5057b-117">El punto de entrada de una aplicación puede tener el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="5057b-117">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="5057b-118">Funciones locales</span><span class="sxs-lookup"><span data-stu-id="5057b-118">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="5057b-119">Puede anidar funciones en otras funciones para limitar su ámbito y visibilidad.</span><span class="sxs-lookup"><span data-stu-id="5057b-119">You can nest functions inside other functions to limit their scope and visibility.</span></span>
- [<span data-ttu-id="5057b-120">Más miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="5057b-120">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="5057b-121">La lista de miembros que se pueden crear con expresiones ha crecido.</span><span class="sxs-lookup"><span data-stu-id="5057b-121">The list of members that can be authored using expressions has grown.</span></span>
- [<span data-ttu-id="5057b-122">Expresiones `throw`</span><span class="sxs-lookup"><span data-stu-id="5057b-122">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="5057b-123">Puede iniciar excepciones en construcciones de código que antes no se permitían porque `throw` era una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5057b-123">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
- [<span data-ttu-id="5057b-124">Expresiones literales `default`</span><span class="sxs-lookup"><span data-stu-id="5057b-124">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="5057b-125">Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.</span><span class="sxs-lookup"><span data-stu-id="5057b-125">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="5057b-126">Mejoras en la sintaxis de literales numéricos</span><span class="sxs-lookup"><span data-stu-id="5057b-126">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="5057b-127">Nuevos tokens mejoran la legibilidad de las constantes numéricas.</span><span class="sxs-lookup"><span data-stu-id="5057b-127">New tokens improve readability for numeric constants.</span></span>
- [<span data-ttu-id="5057b-128">Variables de `out`</span><span class="sxs-lookup"><span data-stu-id="5057b-128">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="5057b-129">Puede declarar valores `out` insertados como argumentos en el método cuando se usen.</span><span class="sxs-lookup"><span data-stu-id="5057b-129">You can declare `out` values inline as arguments to the method where they're used.</span></span>
- [<span data-ttu-id="5057b-130">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="5057b-130">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="5057b-131">Los argumentos con nombre pueden ir seguidos de argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="5057b-131">Named arguments can be followed by positional arguments.</span></span>
- [<span data-ttu-id="5057b-132">Modificador de acceso `private protected`</span><span class="sxs-lookup"><span data-stu-id="5057b-132">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="5057b-133">El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5057b-133">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
- [<span data-ttu-id="5057b-134">Mejoras en la resolución de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5057b-134">Improved overload resolution</span></span>](#improved-overload-candidates)
  - <span data-ttu-id="5057b-135">Nuevas reglas para resolver la ambigüedad de la resolución de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="5057b-135">New rules to resolve overload resolution ambiguity.</span></span>
- [<span data-ttu-id="5057b-136">Técnicas para escribir código eficiente seguro</span><span class="sxs-lookup"><span data-stu-id="5057b-136">Techniques for writing safe efficient code</span></span>](#enabling-more-efficient-safe-code)
  - <span data-ttu-id="5057b-137">Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="5057b-137">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>

<span data-ttu-id="5057b-138">Por último, el compilador tiene nuevas opciones:</span><span class="sxs-lookup"><span data-stu-id="5057b-138">Finally, the compiler has new options:</span></span>

- <span data-ttu-id="5057b-139">`-refout` y `-refonly` para controlar la [generación de ensamblados de referencia](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="5057b-139">`-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>
- <span data-ttu-id="5057b-140">`-publicsign` para habilitar la firma de ensamblados de software de código abierto (OSS).</span><span class="sxs-lookup"><span data-stu-id="5057b-140">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="5057b-141">`-pathmap` para proporcionar una asignación para los directorios de origen.</span><span class="sxs-lookup"><span data-stu-id="5057b-141">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="5057b-142">En el resto de este artículo se proporciona información general sobre cada característica.</span><span class="sxs-lookup"><span data-stu-id="5057b-142">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="5057b-143">Para cada característica, obtendrá información sobre el razonamiento subyacente y la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="5057b-143">For each feature, you'll learn the reasoning behind it and the syntax.</span></span> <span data-ttu-id="5057b-144">Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="5057b-144">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="5057b-145">Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="5057b-145">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="5057b-146">Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="5057b-146">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="5057b-147">Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="5057b-147">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="5057b-148">Ejecute `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="5057b-148">Run `dotnet try`.</span></span>

## <a name="tuples-and-discards"></a><span data-ttu-id="5057b-149">Tuplas y descartes</span><span class="sxs-lookup"><span data-stu-id="5057b-149">Tuples and discards</span></span>

<span data-ttu-id="5057b-150">C# ofrece una sintaxis enriquecida para clases y estructuras que se usa para explicar la intención del diseño.</span><span class="sxs-lookup"><span data-stu-id="5057b-150">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="5057b-151">Pero a veces esa sintaxis enriquecida requiere trabajo adicional con apenas beneficio.</span><span class="sxs-lookup"><span data-stu-id="5057b-151">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="5057b-152">Puede que a menudo escriba métodos que requieren una estructura simple que contenga más de un elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="5057b-152">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="5057b-153">Para admitir estos escenarios, se han agregado *tuplas* a C#.</span><span class="sxs-lookup"><span data-stu-id="5057b-153">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="5057b-154">Las tuplas son estructuras de datos ligeros que contienen varios campos para representar los miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="5057b-154">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span> <span data-ttu-id="5057b-155">Los campos no se validan y no se pueden definir métodos propios.</span><span class="sxs-lookup"><span data-stu-id="5057b-155">The fields aren't validated, and you can't define your own methods.</span></span> <span data-ttu-id="5057b-156">Los tipos de tupla de C# admiten `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="5057b-156">C# tuple types support `==` and `!=`.</span></span> <span data-ttu-id="5057b-157">Para obtener más información,</span><span class="sxs-lookup"><span data-stu-id="5057b-157">For more information.</span></span>

> [!NOTE]
> <span data-ttu-id="5057b-158">Las tuplas estaban disponibles antes de C# 7.0, pero no eran eficientes ni compatibles con ningún lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5057b-158">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span> <span data-ttu-id="5057b-159">Esto significaba que solo se podía hacer referencia a los elementos tupla como `Item1`, `Item2`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5057b-159">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="5057b-160">C# 7.0 presenta la compatibilidad de lenguaje con las tuplas, que permite usar nombres semánticos en los campos de una tupla mediante tipos de tupla nuevos y más eficientes.</span><span class="sxs-lookup"><span data-stu-id="5057b-160">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="5057b-161">Puede crear una tupla asignando un valor a cada miembro, y, opcionalmente, proporcionando nombres semánticos a cada uno de los miembros de la tupla:</span><span class="sxs-lookup"><span data-stu-id="5057b-161">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="5057b-162">La tupla `namedLetters` contiene campos denominados `Alpha` y `Beta`.</span><span class="sxs-lookup"><span data-stu-id="5057b-162">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="5057b-163">Esos nombres solo existen en tiempo de compilación y no se conservan, por ejemplo, al inspeccionar la tupla mediante la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5057b-163">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at run time.</span></span>

<span data-ttu-id="5057b-164">En la asignación de una tupla, también pueden especificarse los nombres de los campos a la derecha de la asignación:</span><span class="sxs-lookup"><span data-stu-id="5057b-164">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="5057b-165">Puede que a veces quiera desempaquetar los miembros de una tupla devueltos de un método.</span><span class="sxs-lookup"><span data-stu-id="5057b-165">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="5057b-166">Para ello, declare distintas variables para cada uno de los valores de la tupla.</span><span class="sxs-lookup"><span data-stu-id="5057b-166">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="5057b-167">Este desempaquetado se denomina *deconstrucción* de la tupla:</span><span class="sxs-lookup"><span data-stu-id="5057b-167">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="5057b-168">También puede proporcionar una deconstrucción similar para cualquier tipo de .NET.</span><span class="sxs-lookup"><span data-stu-id="5057b-168">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="5057b-169">Un método `Deconstruct` se escribe como un miembro de la clase.</span><span class="sxs-lookup"><span data-stu-id="5057b-169">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="5057b-170">Ese método `Deconstruct` proporciona un conjunto de argumentos `out` para cada una de las propiedades que quiere extraer.</span><span class="sxs-lookup"><span data-stu-id="5057b-170">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="5057b-171">Tenga en cuenta que esta clase `Point` proporciona un método deconstructor que extrae las coordenadas `X` e `Y`:</span><span class="sxs-lookup"><span data-stu-id="5057b-171">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="5057b-172">Puede extraer los campos individuales asignando un `Point` a una tupla:</span><span class="sxs-lookup"><span data-stu-id="5057b-172">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="5057b-173">Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla: Los nombres de los elementos de tupla se pueden deducir de las variables usadas para inicializar la tupla:</span><span class="sxs-lookup"><span data-stu-id="5057b-173">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements: The names of tuple elements can be inferred from the variables used to initialize the tuple:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="5057b-174">Encontrará más información sobre esta característica en el artículo sobre [tipos de tuplas](../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-174">You can learn more about this feature in the [Tuple types](../language-reference/builtin-types/value-tuples.md) article.</span></span>

<span data-ttu-id="5057b-175">Habitualmente, al deconstruir una tupla o realizar una llamada a un método mediante parámetros `out`, debe definir una variable con un valor indiferente y que no vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="5057b-175">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="5057b-176">C# agrega la compatibilidad con *descartes* para gestionar este tipo de escenarios.</span><span class="sxs-lookup"><span data-stu-id="5057b-176">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="5057b-177">Un descarte es una variable de solo escritura con el nombre `_` (el carácter de guion bajo). Puede asignar todos los valores que quiera descartar a una única variable.</span><span class="sxs-lookup"><span data-stu-id="5057b-177">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="5057b-178">Un descarte se parece a una variable no asignada, aunque no puede usarse en el código (excepto la instrucción de asignación).</span><span class="sxs-lookup"><span data-stu-id="5057b-178">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="5057b-179">Los descartes se admiten en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="5057b-179">Discards are supported in the following scenarios:</span></span>

- <span data-ttu-id="5057b-180">Al deconstruir tuplas o tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5057b-180">When deconstructing tuples or user-defined types.</span></span>
- <span data-ttu-id="5057b-181">Al realizar llamadas a métodos mediante parámetros [out](../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-181">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="5057b-182">En una operación de coincidencia de patrones con las instrucciones [is](../language-reference/keywords/is.md) y [switch](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-182">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
- <span data-ttu-id="5057b-183">Como un identificador independiente cuando quiera identificar explícitamente el valor de una asignación como descarte.</span><span class="sxs-lookup"><span data-stu-id="5057b-183">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="5057b-184">En el ejemplo siguiente se define un método `QueryCityDataForYears` que devuelve una tupla de tipo 6 con datos de una ciudad correspondientes a dos años diferentes.</span><span class="sxs-lookup"><span data-stu-id="5057b-184">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="5057b-185">La llamada de método del ejemplo se refiere únicamente a los dos valores de rellenado que devuelve el método, por lo que trata los valores restantes de la tupla como descartes al deconstruirla.</span><span class="sxs-lookup"><span data-stu-id="5057b-185">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="5057b-186">Para obtener más información, vea [Descartes](../discards.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-186">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="5057b-187">Detección de patrones</span><span class="sxs-lookup"><span data-stu-id="5057b-187">Pattern matching</span></span>

<span data-ttu-id="5057b-188">La *coincidencia de patrones* es un conjunto de características que permiten nuevas formas de expresar el flujo de control en el código.</span><span class="sxs-lookup"><span data-stu-id="5057b-188">*Pattern matching* is a set of features that enable new ways to express control flow in your code.</span></span> <span data-ttu-id="5057b-189">En las variables, puede probar su tipo, sus valores o los valores de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="5057b-189">You can test variables for their type, values or the values of their properties.</span></span> <span data-ttu-id="5057b-190">Estas técnicas crean un flujo de código más legible.</span><span class="sxs-lookup"><span data-stu-id="5057b-190">These techniques create more readable code flow.</span></span>

<span data-ttu-id="5057b-191">La coincidencia de patrones admite expresiones `is` y `switch`.</span><span class="sxs-lookup"><span data-stu-id="5057b-191">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="5057b-192">Cada una de ellas habilita la inspección de un objeto y sus propiedades para determinar si el objeto cumple el patrón buscado.</span><span class="sxs-lookup"><span data-stu-id="5057b-192">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="5057b-193">Use la palabra clave `when` para especificar reglas adicionales para el patrón.</span><span class="sxs-lookup"><span data-stu-id="5057b-193">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="5057b-194">La expresión de patrón `is` extiende el conocido [operador `is`](../language-reference/keywords/is.md#pattern-matching-with-is) para consultar el tipo de un objeto y asignar el resultado en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5057b-194">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="5057b-195">En el código siguiente se comprueba si una variable es de tipo `int` y, si lo es, se agrega a la suma actual:</span><span class="sxs-lookup"><span data-stu-id="5057b-195">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="5057b-196">En el pequeño ejemplo anterior se muestran las mejoras en la expresión `is`.</span><span class="sxs-lookup"><span data-stu-id="5057b-196">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="5057b-197">Puede probar con tipos de valor y tipos de referencia, y asignar el resultado correcto a una nueva variable del tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="5057b-197">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="5057b-198">La expresión de coincidencia switch tiene una sintaxis conocida, basada en la instrucción `switch` que ya forma parte del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="5057b-198">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="5057b-199">La instrucción switch actualizada tiene varias construcciones nuevas:</span><span class="sxs-lookup"><span data-stu-id="5057b-199">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="5057b-200">El tipo de control de una expresión `switch` ya no se limita a tipos enteros, tipos `Enum`, `string` o a un tipo que acepta valores NULL correspondiente a uno de esos tipos.</span><span class="sxs-lookup"><span data-stu-id="5057b-200">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="5057b-201">Se puede usar cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="5057b-201">Any type may be used.</span></span>
- <span data-ttu-id="5057b-202">Puede probar el tipo de la expresión `switch` en todas las etiquetas `case`.</span><span class="sxs-lookup"><span data-stu-id="5057b-202">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="5057b-203">Como sucede con la expresión `is`, puede asignar una variable nueva a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5057b-203">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="5057b-204">Puede agregar una cláusula `when` para probar más condiciones en esa variable.</span><span class="sxs-lookup"><span data-stu-id="5057b-204">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="5057b-205">Ahora el orden de las etiquetas `case` es importante.</span><span class="sxs-lookup"><span data-stu-id="5057b-205">The order of `case` labels is now important.</span></span> <span data-ttu-id="5057b-206">Se ejecuta la primera rama de la que se quiere obtener la coincidencia, mientras que el resto se omite.</span><span class="sxs-lookup"><span data-stu-id="5057b-206">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="5057b-207">En el código siguiente se muestran estas características:</span><span class="sxs-lookup"><span data-stu-id="5057b-207">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="5057b-208">`case 0:` es el patrón de constante conocido.</span><span class="sxs-lookup"><span data-stu-id="5057b-208">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="5057b-209">`case IEnumerable<int> childSequence:` es un patrón de tipo.</span><span class="sxs-lookup"><span data-stu-id="5057b-209">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="5057b-210">`case int n when n > 0:` es un patrón de tipo con una condición `when` adicional.</span><span class="sxs-lookup"><span data-stu-id="5057b-210">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="5057b-211">`case null:` es el patrón NULL.</span><span class="sxs-lookup"><span data-stu-id="5057b-211">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="5057b-212">`default:` es el caso predeterminado conocido.</span><span class="sxs-lookup"><span data-stu-id="5057b-212">`default:` is the familiar default case.</span></span>

<span data-ttu-id="5057b-213">A partir de C# 7.1, la expresión de patrón para `is` y el patrón de tipo `switch` pueden tener el tipo de un parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5057b-213">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="5057b-214">Esto puede ser especialmente útil al comprobar los tipos que pueden ser tipos `struct` o `class` y si quiere evitar la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="5057b-214">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

<span data-ttu-id="5057b-215">Puede obtener más información sobre la coincidencia de patrones en [Coincidencia de patrones en C#](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-215">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="async-main"></a><span data-ttu-id="5057b-216">Async main</span><span class="sxs-lookup"><span data-stu-id="5057b-216">Async main</span></span>

<span data-ttu-id="5057b-217">Un método *async main* permite usar `await` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="5057b-217">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="5057b-218">Anteriormente, hubiera sido necesario escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5057b-218">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="5057b-219">Ahora se puede escribir esto:</span><span class="sxs-lookup"><span data-stu-id="5057b-219">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="5057b-220">Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="5057b-220">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="5057b-221">En el artículo sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.</span><span class="sxs-lookup"><span data-stu-id="5057b-221">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="local-functions"></a><span data-ttu-id="5057b-222">Funciones locales</span><span class="sxs-lookup"><span data-stu-id="5057b-222">Local functions</span></span>

<span data-ttu-id="5057b-223">Muchos diseños de clases incluyen métodos que se llaman desde una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="5057b-223">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="5057b-224">Estos métodos privados adicionales mantienen cada método pequeño y centrado.</span><span class="sxs-lookup"><span data-stu-id="5057b-224">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="5057b-225">Las *funciones locales* permiten declarar métodos en el contexto de otro método.</span><span class="sxs-lookup"><span data-stu-id="5057b-225">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="5057b-226">Las funciones locales facilitan que los lectores de la clase vean que el método local solo se llama desde el contexto en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="5057b-226">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="5057b-227">Hay dos casos de uso comunes para las funciones locales: métodos de iterador públicos y métodos asincrónicos públicos.</span><span class="sxs-lookup"><span data-stu-id="5057b-227">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="5057b-228">Ambos tipos de métodos generan código que informa de errores más tarde de lo que los programadores podrían esperar.</span><span class="sxs-lookup"><span data-stu-id="5057b-228">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="5057b-229">En los métodos de iterador, las excepciones solo se observan al llamar a código que enumera la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="5057b-229">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="5057b-230">En los métodos asincrónicos, las excepciones solo se observan cuando se espera al elemento `Task` devuelto.</span><span class="sxs-lookup"><span data-stu-id="5057b-230">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="5057b-231">En el ejemplo siguiente se muestra la separación de la validación de parámetros de la implementación de iteradores mediante una función local:</span><span class="sxs-lookup"><span data-stu-id="5057b-231">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="5057b-232">La misma técnica se puede emplear con métodos `async` para asegurarse de que las excepciones derivadas de la validación de argumentos se inician antes de comenzar el trabajo asincrónico:</span><span class="sxs-lookup"><span data-stu-id="5057b-232">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="5057b-233">Esta sintaxis ahora se admite:</span><span class="sxs-lookup"><span data-stu-id="5057b-233">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="5057b-234">El atributo `SomeThingAboutFieldAttribute` se aplica al campo de respaldo generado por el compilador para `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="5057b-234">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="5057b-235">Para obtener más información, vea [atributos](../programming-guide/concepts/attributes/index.md) en la guía de programación de C#.</span><span class="sxs-lookup"><span data-stu-id="5057b-235">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

> [!NOTE]
> <span data-ttu-id="5057b-236">Algunos de los diseños que se admiten con funciones locales también se pueden realizar con *expresiones lambda*.</span><span class="sxs-lookup"><span data-stu-id="5057b-236">Some of the designs that are supported by local functions can also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="5057b-237">Para más información, consulte [Funciones locales frente a expresiones lambda](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span><span class="sxs-lookup"><span data-stu-id="5057b-237">For more information, see [Local functions vs. lambda expressions](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="5057b-238">Más miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="5057b-238">More expression-bodied members</span></span>

<span data-ttu-id="5057b-239">En C# 6 se presentaron los miembros con forma de expresión para funciones de miembros y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5057b-239">C# 6 introduced expression-bodied members for member functions and read-only properties.</span></span> <span data-ttu-id="5057b-240">C# 7.0 amplía los miembros permitidos que pueden implementarse como expresiones.</span><span class="sxs-lookup"><span data-stu-id="5057b-240">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="5057b-241">En C# 7.0, se pueden implementar *constructores*, *finalizadores* y descriptores de acceso `get` y `set` en *propiedades* e *indizadores*.</span><span class="sxs-lookup"><span data-stu-id="5057b-241">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="5057b-242">En el código siguiente se muestran ejemplos de cada uno:</span><span class="sxs-lookup"><span data-stu-id="5057b-242">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="5057b-243">En este ejemplo no se requiere un finalizador, pero se muestra para demostrar la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="5057b-243">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="5057b-244">No debe implementar un finalizador en la clase salvo que sea necesario para liberar recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="5057b-244">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="5057b-245">También debe plantearse el uso de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de administrar directamente los recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="5057b-245">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="5057b-246">Estas nuevas ubicaciones para los miembros con forma de expresión representan un hito importante para el lenguaje C#: miembros de la comunidad que trabajan en el proyecto [Roslyn](https://github.com/dotnet/Roslyn) de código abierto implementaron estas características.</span><span class="sxs-lookup"><span data-stu-id="5057b-246">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="5057b-247">Cambiar un método a un miembro con cuerpo de expresión es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-247">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="5057b-248">Expresiones throw</span><span class="sxs-lookup"><span data-stu-id="5057b-248">Throw expressions</span></span>

<span data-ttu-id="5057b-249">En C#, `throw` siempre ha sido una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5057b-249">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="5057b-250">Como `throw` es una instrucción, no una expresión, había construcciones de C# en las que no se podía usar.</span><span class="sxs-lookup"><span data-stu-id="5057b-250">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="5057b-251">Incluyen expresiones condicionales, expresiones de fusión nulas y algunas expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="5057b-251">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="5057b-252">La incorporación de miembros con forma de expresión agrega más ubicaciones donde las expresiones `throw` resultarían útiles.</span><span class="sxs-lookup"><span data-stu-id="5057b-252">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="5057b-253">Para que pueda escribir cualquiera de estas construcciones, C# 7.0 presenta las [*expresiones throw*](../language-reference/keywords/throw.md#the-throw-expression).</span><span class="sxs-lookup"><span data-stu-id="5057b-253">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="5057b-254">Esta adición facilita la escritura de código más basado en expresiones.</span><span class="sxs-lookup"><span data-stu-id="5057b-254">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="5057b-255">No se necesitan instrucciones adicionales para la comprobación de errores.</span><span class="sxs-lookup"><span data-stu-id="5057b-255">You don't need additional statements for error checking.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="5057b-256">Expresiones literales predeterminadas</span><span class="sxs-lookup"><span data-stu-id="5057b-256">Default literal expressions</span></span>

<span data-ttu-id="5057b-257">Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="5057b-257">Default literal expressions are an enhancement to default value expressions.</span></span> <span data-ttu-id="5057b-258">Estas expresiones inicializan una variable en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5057b-258">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="5057b-259">Donde anteriormente habría que escribir:</span><span class="sxs-lookup"><span data-stu-id="5057b-259">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="5057b-260">Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:</span><span class="sxs-lookup"><span data-stu-id="5057b-260">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="5057b-261">Para más información, consulte la sección [Literal default](../language-reference/operators/default.md#default-literal) del artículo [Operador default](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-261">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="5057b-262">Mejoras en la sintaxis de literales numéricos</span><span class="sxs-lookup"><span data-stu-id="5057b-262">Numeric literal syntax improvements</span></span>

<span data-ttu-id="5057b-263">La lectura incorrecta de constantes numéricas puede complicar la comprensión del código cuando se lee por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5057b-263">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="5057b-264">Las máscaras de bits u otros valores simbólicos son propensos a malentendidos.</span><span class="sxs-lookup"><span data-stu-id="5057b-264">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="5057b-265">En C# 7.0 se incluyen dos nuevas características para escribir números de la manera más legible para el uso previsto: *literales binarios* y *separadores de dígitos*.</span><span class="sxs-lookup"><span data-stu-id="5057b-265">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="5057b-266">En aquellos casos en que cree máscaras de bits, o siempre que una representación binaria de un número aumente la legibilidad del código, escriba el número en formato binario:</span><span class="sxs-lookup"><span data-stu-id="5057b-266">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="5057b-267">El `0b` al principio de la constante indica que el número está escrito como número binario.</span><span class="sxs-lookup"><span data-stu-id="5057b-267">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="5057b-268">Los números binarios pueden ser muy largos, por lo que a menudo resulta más fácil ver los patrones de bits si se introduce `_` como separador de dígitos, como se ha mostrado en la constante binaria del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5057b-268">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown in the binary constant in the preceding example.</span></span> <span data-ttu-id="5057b-269">El separador de dígitos puede aparecer en cualquier parte de la constante.</span><span class="sxs-lookup"><span data-stu-id="5057b-269">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="5057b-270">En números de base 10, es habitual usarlo como separador de miles.</span><span class="sxs-lookup"><span data-stu-id="5057b-270">For base 10 numbers, it is common to use it as a thousands separator.</span></span> <span data-ttu-id="5057b-271">Los literales numéricos hexadecimales y binarios pueden empezar con `_`:</span><span class="sxs-lookup"><span data-stu-id="5057b-271">Hex and binary numeric literals may begin with an `_`:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="5057b-272">El separador de dígitos también se puede usar con tipos `decimal`, `float` y `double`:</span><span class="sxs-lookup"><span data-stu-id="5057b-272">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="5057b-273">En conjunto, se pueden declarar constantes numéricas con mucha más legibilidad.</span><span class="sxs-lookup"><span data-stu-id="5057b-273">Taken together, you can declare numeric constants with much more readability.</span></span>

## <a name="out-variables"></a><span data-ttu-id="5057b-274">Variables `out`</span><span class="sxs-lookup"><span data-stu-id="5057b-274">`out` variables</span></span>

<span data-ttu-id="5057b-275">La sintaxis existente que admite parámetros `out` se ha mejorado en C# 7.</span><span class="sxs-lookup"><span data-stu-id="5057b-275">The existing syntax that supports `out` parameters has been improved in C# 7.</span></span> <span data-ttu-id="5057b-276">Ahora puede declarar variables `out` en la lista de argumentos de una llamada a método, en lugar de escribir una instrucción de declaración distinta:</span><span class="sxs-lookup"><span data-stu-id="5057b-276">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="5057b-277">Para mayor claridad, es posible que quiera especificar el tipo de la variable `out`, como se ha mostrado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5057b-277">You may want to specify the type of the `out` variable for clarity, as shown in the preceding example.</span></span> <span data-ttu-id="5057b-278">Pero el lenguaje admite el uso de una variable local con tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="5057b-278">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- <span data-ttu-id="5057b-279">El código es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="5057b-279">The code is easier to read.</span></span>
  - <span data-ttu-id="5057b-280">Declare la variable out donde la use, no en una línea de código anterior.</span><span class="sxs-lookup"><span data-stu-id="5057b-280">You declare the out variable where you use it, not on a preceding line of code.</span></span>
- <span data-ttu-id="5057b-281">No es preciso asignar ningún valor inicial.</span><span class="sxs-lookup"><span data-stu-id="5057b-281">No need to assign an initial value.</span></span>
  - <span data-ttu-id="5057b-282">Al declarar la variable `out` cuando se usa en una llamada de método, no podrá usarla accidentalmente antes de que se asigne.</span><span class="sxs-lookup"><span data-stu-id="5057b-282">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="5057b-283">La sintaxis que se agregó en C# 7.0 para permitir declaraciones de variable `out` se ha ampliado para incluir inicializadores de campo, inicializadores de propiedad, inicializadores de constructor y cláusulas de consulta.</span><span class="sxs-lookup"><span data-stu-id="5057b-283">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="5057b-284">Permite código como el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5057b-284">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="5057b-285">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="5057b-285">Non-trailing named arguments</span></span>

<span data-ttu-id="5057b-286">Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada.</span><span class="sxs-lookup"><span data-stu-id="5057b-286">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="5057b-287">Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-287">For more information, see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="private-protected-access-modifier"></a><span data-ttu-id="5057b-288">Modificador de acceso *private protected*</span><span class="sxs-lookup"><span data-stu-id="5057b-288">*private protected* access modifier</span></span>

<span data-ttu-id="5057b-289">Presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5057b-289">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="5057b-290">Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5057b-290">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="5057b-291">Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5057b-291">For more information, see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="improved-overload-candidates"></a><span data-ttu-id="5057b-292">Mejoras en los candidatos de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5057b-292">Improved overload candidates</span></span>

<span data-ttu-id="5057b-293">En cada versión, las reglas de resolución de sobrecarga se actualizan para abordar situaciones en las que las invocaciones de métodos ambiguos tienen una opción "obvia".</span><span class="sxs-lookup"><span data-stu-id="5057b-293">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="5057b-294">Esta versión agrega tres nuevas reglas para ayudar a que el compilador elija la opción obvia:</span><span class="sxs-lookup"><span data-stu-id="5057b-294">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="5057b-295">Cuando un grupo de métodos contiene tanto miembros de instancia como estáticos, el compilador descarta los miembros de la instancia si el método fue invocado sin un receptor o contexto de instancia.</span><span class="sxs-lookup"><span data-stu-id="5057b-295">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="5057b-296">El compilador descarta los miembros estáticos si el método se invocó con un receptor de instancia.</span><span class="sxs-lookup"><span data-stu-id="5057b-296">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="5057b-297">Cuando no hay ningún receptor, el compilador incluye solo miembros estáticos en un contexto estático; de lo contrario, miembros estáticos y de instancia.</span><span class="sxs-lookup"><span data-stu-id="5057b-297">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="5057b-298">Cuando el receptor es ambiguamente una instancia o un tipo, el compilador incluye ambos.</span><span class="sxs-lookup"><span data-stu-id="5057b-298">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="5057b-299">Un contexto estático, donde no se puede usar un receptor de instancia `this` implícito, incluye el cuerpo de miembros donde no se define `this`, como miembros estáticos, así como lugares donde `this` no se puede usar, como inicializadores de campo e inicializadores-constructores.</span><span class="sxs-lookup"><span data-stu-id="5057b-299">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="5057b-300">Cuando un grupo de métodos contiene algunos métodos genéricos cuyos argumentos de tipo no cumplen con sus restricciones, estos miembros se eliminan del conjunto de candidatos.</span><span class="sxs-lookup"><span data-stu-id="5057b-300">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="5057b-301">En el caso de una conversión de grupo de métodos, los métodos candidatos cuyo tipo de valor devuelto no coincide con el tipo de valor devuelto del delegado se eliminan del conjunto.</span><span class="sxs-lookup"><span data-stu-id="5057b-301">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="5057b-302">Solo notará este cambio porque encontrará menos errores de compilación para sobrecargas ambiguas de métodos cuando esté seguro de qué método es mejor.</span><span class="sxs-lookup"><span data-stu-id="5057b-302">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="5057b-303">Habilitación de código seguro más eficaz</span><span class="sxs-lookup"><span data-stu-id="5057b-303">Enabling more efficient safe code</span></span>

<span data-ttu-id="5057b-304">Debería poder escribir código de C# de forma segura que tenga el mismo rendimiento que el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="5057b-304">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="5057b-305">El código seguro evita clases de errores, como desbordamientos de búfer, punteros perdidos y otros errores de acceso a la memoria.</span><span class="sxs-lookup"><span data-stu-id="5057b-305">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="5057b-306">Estas nuevas características amplían las capacidades de código seguro comprobable.</span><span class="sxs-lookup"><span data-stu-id="5057b-306">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="5057b-307">Procure escribir más código utilizando construcciones seguras.</span><span class="sxs-lookup"><span data-stu-id="5057b-307">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="5057b-308">Estas características lo facilitan en gran medida.</span><span class="sxs-lookup"><span data-stu-id="5057b-308">These features make that easier.</span></span>

<span data-ttu-id="5057b-309">Las siguientes características nuevas admiten el tema del mejor rendimiento para código seguro:</span><span class="sxs-lookup"><span data-stu-id="5057b-309">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="5057b-310">Puede tener acceso a campos fijos sin anclar.</span><span class="sxs-lookup"><span data-stu-id="5057b-310">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="5057b-311">Puede volver a asignar variables locales `ref`.</span><span class="sxs-lookup"><span data-stu-id="5057b-311">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="5057b-312">Puede usar inicializadores en matrices `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="5057b-312">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="5057b-313">Puede usar instrucciones `fixed` con cualquier tipo que admita un patrón.</span><span class="sxs-lookup"><span data-stu-id="5057b-313">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="5057b-314">Puede usar restricciones genéricas adicionales.</span><span class="sxs-lookup"><span data-stu-id="5057b-314">You can use additional generic constraints.</span></span>
- <span data-ttu-id="5057b-315">El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique.</span><span class="sxs-lookup"><span data-stu-id="5057b-315">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="5057b-316">Agregar el modificador `in` a un argumento es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-316">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="5057b-317">El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto.</span><span class="sxs-lookup"><span data-stu-id="5057b-317">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="5057b-318">Agregar el modificador `ref readonly` es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes), si el resultado devuelto se asigna a un valor.</span><span class="sxs-lookup"><span data-stu-id="5057b-318">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="5057b-319">Agregar el modificador `readonly` a una instrucción return `ref` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-319">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="5057b-320">Requiere que los autores de las llamadas actualicen la declaración de las variables locales `ref` para incluir el modificador `readonly`.</span><span class="sxs-lookup"><span data-stu-id="5057b-320">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="5057b-321">La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro.</span><span class="sxs-lookup"><span data-stu-id="5057b-321">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="5057b-322">Agregar el modificador `readonly` a una declaración struct existente es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-322">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="5057b-323">La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila.</span><span class="sxs-lookup"><span data-stu-id="5057b-323">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="5057b-324">Agregar el modificador `ref` a una declaración `struct` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-324">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="5057b-325">Un elemento `ref struct` no puede ser un miembro de una clase o usarse en otras ubicaciones donde puede asignarse en el montón.</span><span class="sxs-lookup"><span data-stu-id="5057b-325">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="5057b-326">Puede leer más información sobre todos estos cambios en [Write safe efficient code](../write-safe-efficient-code.md) (Escribir código eficiente seguro).</span><span class="sxs-lookup"><span data-stu-id="5057b-326">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

### <a name="ref-locals-and-returns"></a><span data-ttu-id="5057b-327">Devoluciones y variables locales ref</span><span class="sxs-lookup"><span data-stu-id="5057b-327">Ref locals and returns</span></span>

<span data-ttu-id="5057b-328">Esta característica habilita algoritmos que usan y devuelven referencias a variables definidas en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="5057b-328">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="5057b-329">Por ejemplo, trabajar con matrices de gran tamaño y buscar una sola ubicación con determinadas características.</span><span class="sxs-lookup"><span data-stu-id="5057b-329">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="5057b-330">El método siguiente devuelve una **referencia** a ese almacenamiento en la matriz:</span><span class="sxs-lookup"><span data-stu-id="5057b-330">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="5057b-331">Puede declarar el valor devuelto como un elemento `ref` y modificar ese valor en la matriz, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5057b-331">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="5057b-332">El lenguaje C# tiene varias reglas que impiden el uso incorrecto de las variables locales y devoluciones de `ref`:</span><span class="sxs-lookup"><span data-stu-id="5057b-332">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

- <span data-ttu-id="5057b-333">Tendrá que agregar la palabra clave `ref` a la firma del método y a todas las instrucciones `return` de un método.</span><span class="sxs-lookup"><span data-stu-id="5057b-333">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="5057b-334">Esto evidencia que el método se devuelve por referencia a lo largo del método.</span><span class="sxs-lookup"><span data-stu-id="5057b-334">That makes it clear the method returns by reference throughout the method.</span></span>
- <span data-ttu-id="5057b-335">Se puede asignar `ref return` a una variable de valor, o bien a una variable `ref`.</span><span class="sxs-lookup"><span data-stu-id="5057b-335">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="5057b-336">El autor de la llamada controla si se copia el valor devuelto o no.</span><span class="sxs-lookup"><span data-stu-id="5057b-336">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="5057b-337">La omisión del modificador `ref` al asignar el valor devuelto indica que el autor de la llamada quiere una copia del valor, no una referencia al almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5057b-337">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
- <span data-ttu-id="5057b-338">No se puede asignar un valor devuelto de método estándar a una variable local `ref`.</span><span class="sxs-lookup"><span data-stu-id="5057b-338">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="5057b-339">No permite instrucciones como `ref int i = sequence.Count();`</span><span class="sxs-lookup"><span data-stu-id="5057b-339">That disallows statements like `ref int i = sequence.Count();`</span></span>
- <span data-ttu-id="5057b-340">No se puede devolver un elemento `ref` a una variable cuya duración se extiende más allá de la ejecución del método.</span><span class="sxs-lookup"><span data-stu-id="5057b-340">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="5057b-341">Esto significa que no se puede devolver una referencia a una variable local o a una variable con un ámbito similar.</span><span class="sxs-lookup"><span data-stu-id="5057b-341">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
- <span data-ttu-id="5057b-342">Las `ref` locales y las devoluciones no se pueden usar con métodos asíncronos.</span><span class="sxs-lookup"><span data-stu-id="5057b-342">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="5057b-343">El compilador no puede identificar si una variable a la que se hace referencia se ha establecido en su valor final en la devolución del método asíncrono.</span><span class="sxs-lookup"><span data-stu-id="5057b-343">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="5057b-344">La incorporación de variables locales ref y devoluciones de ref permite usar algoritmos que resultan más eficientes si se evita copiar los valores o se realizan operaciones de desreferencia varias veces.</span><span class="sxs-lookup"><span data-stu-id="5057b-344">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="5057b-345">Agregar `ref` al valor devuelto es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-345">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="5057b-346">El código existente se compila, pero el valor devuelto de referencia se copia cuando se asigna.</span><span class="sxs-lookup"><span data-stu-id="5057b-346">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="5057b-347">Los autores de las llamadas deben actualizar el almacenamiento para el valor devuelto en una variable local `ref` para almacenar el valor devuelto como referencia.</span><span class="sxs-lookup"><span data-stu-id="5057b-347">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="5057b-348">Ahora, las variables locales de `ref` pueden reasignarse para hacer referencia a instancias diferentes después de haberse inicializado.</span><span class="sxs-lookup"><span data-stu-id="5057b-348">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="5057b-349">El código siguiente ahora compila:</span><span class="sxs-lookup"><span data-stu-id="5057b-349">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="5057b-350">Para obtener más información, vea el artículo sobre valores devueltos de [`ref` y `ref`locales](../programming-guide/classes-and-structs/ref-returns.md), así como el artículo sobre [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-350">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

<span data-ttu-id="5057b-351">Para más información, consulte el artículo sobre la [palabra clave ref](../language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-351">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

### <a name="conditional-ref-expressions"></a><span data-ttu-id="5057b-352">Expresiones `ref` condicionales</span><span class="sxs-lookup"><span data-stu-id="5057b-352">Conditional `ref` expressions</span></span>

<span data-ttu-id="5057b-353">Por último, la expresión condicional puede producir un resultado de referencia en lugar de un resultado de valor.</span><span class="sxs-lookup"><span data-stu-id="5057b-353">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="5057b-354">Por ejemplo, podría escribir lo siguiente para recuperar una referencia al primer elemento en una de dos matrices:</span><span class="sxs-lookup"><span data-stu-id="5057b-354">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="5057b-355">La variable `r` es una referencia al primer valor de `arr` o `otherArr`.</span><span class="sxs-lookup"><span data-stu-id="5057b-355">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="5057b-356">Para más información, vea el [operador condicional (?:)](../language-reference/operators/conditional-operator.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5057b-356">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>

### <a name="in-parameter-modifier"></a><span data-ttu-id="5057b-357">`in` (modificador de parámetro)</span><span class="sxs-lookup"><span data-stu-id="5057b-357">`in` parameter modifier</span></span>

<span data-ttu-id="5057b-358">La palabra clave `in` complementa las palabras clave ref y out existentes para pasar argumentos por referencia.</span><span class="sxs-lookup"><span data-stu-id="5057b-358">The `in` keyword complements the existing ref and out keywords to pass arguments by reference.</span></span> <span data-ttu-id="5057b-359">La palabra clave `in` especifica que se pasa el argumento por referencia, pero el método llamado no modifica el valor.</span><span class="sxs-lookup"><span data-stu-id="5057b-359">The `in` keyword specifies passing the argument by reference, but the called method doesn't modify the value.</span></span>

<span data-ttu-id="5057b-360">Puede declarar sobrecargas que se pasen por valor o por referencia de solo lectura, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5057b-360">You may declare overloads that pass by value or by readonly reference, as shown in the following code:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="5057b-361">La sobrecarga por valor (la primera del ejemplo anterior) es mejor que la de la versión de referencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5057b-361">The by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="5057b-362">Para llamar a la versión con el argumento de referencia de solo lectura, debe incluir el modificador `in` cuando llame al método.</span><span class="sxs-lookup"><span data-stu-id="5057b-362">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

<span data-ttu-id="5057b-363">Para obtener más información, consulte el artículo sobre el [modificador de parámetros`in`](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-363">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="5057b-364">Hay más tipos compatibles con la instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="5057b-364">More types support the `fixed` statement</span></span>

<span data-ttu-id="5057b-365">La instrucción `fixed` admite un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="5057b-365">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="5057b-366">A partir de C# 7.3, cualquier tipo que contenga un método `GetPinnableReference()` que devuelve un `ref T` o `ref readonly T` puede ser `fixed`.</span><span class="sxs-lookup"><span data-stu-id="5057b-366">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="5057b-367">La adición de esta característica significa que `fixed` puede utilizarse con <xref:System.Span%601?displayProperty=nameWithType> y tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="5057b-367">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="5057b-368">Para más información, vea el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5057b-368">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="5057b-369">Indexación de campos `fixed` sin requerir anclaje</span><span class="sxs-lookup"><span data-stu-id="5057b-369">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="5057b-370">Considere esta estructura:</span><span class="sxs-lookup"><span data-stu-id="5057b-370">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="5057b-371">En versiones anteriores de C#, era necesario anclar una variable para acceder a uno de los enteros que forman parte de `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="5057b-371">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="5057b-372">Ahora, el código siguiente se compila sin anclar la variable `p` dentro de una instrucción `fixed` independiente:</span><span class="sxs-lookup"><span data-stu-id="5057b-372">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="5057b-373">La variable `p` tiene acceso a un elemento en `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="5057b-373">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="5057b-374">No es necesario declarar otra variable `int*` independiente.</span><span class="sxs-lookup"><span data-stu-id="5057b-374">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="5057b-375">Todavía necesita un contexto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="5057b-375">You still need an `unsafe` context.</span></span> <span data-ttu-id="5057b-376">En versiones anteriores de C#, es necesario declarar un segundo puntero fijo:</span><span class="sxs-lookup"><span data-stu-id="5057b-376">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="5057b-377">Para más información, consulte el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-377">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="5057b-378">Las matrices `stackalloc` admiten inicializadores</span><span class="sxs-lookup"><span data-stu-id="5057b-378">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="5057b-379">Ha podido especificar los valores para los elementos en una matriz cuando la inicializa:</span><span class="sxs-lookup"><span data-stu-id="5057b-379">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="5057b-380">Ahora, esa misma sintaxis se puede aplicar a las matrices que se declaran con `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="5057b-380">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="5057b-381">Para obtener más información, vea el artículo [Operador `stackalloc`](../language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-381">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="5057b-382">Restricciones genéricas mejoradas</span><span class="sxs-lookup"><span data-stu-id="5057b-382">Enhanced generic constraints</span></span>

<span data-ttu-id="5057b-383">Ahora puede especificar el tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> como restricciones de clase base para un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="5057b-383">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="5057b-384">También puede usar la nueva restricción `unmanaged` para especificar que el parámetro de tipo debe ser un [tipo no administrado](../language-reference/builtin-types/unmanaged-types.md) que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5057b-384">You can also use the new `unmanaged` constraint, to specify that a type parameter must be a non-nullable [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span>

<span data-ttu-id="5057b-385">Para obtener más información, vea los artículos sobre [restricciones genéricas de `where`](../language-reference/keywords/where-generic-type-constraint.md) y [restricciones sobre parámetros de tipo](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5057b-385">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="5057b-386">Agregar estas restricciones a tipos existentes es un [cambio incompatible](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="5057b-386">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="5057b-387">Los tipos genéricos cerrados puede que ya no cumplan estas nuevas restricciones.</span><span class="sxs-lookup"><span data-stu-id="5057b-387">Closed generic types may no longer meet these new constraints.</span></span>

### <a name="generalized-async-return-types"></a><span data-ttu-id="5057b-388">Tipos de valor devueltos de async generalizados</span><span class="sxs-lookup"><span data-stu-id="5057b-388">Generalized async return types</span></span>

<span data-ttu-id="5057b-389">La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="5057b-389">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="5057b-390">`Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5057b-390">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="5057b-391">En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="5057b-391">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="5057b-392">Esas asignaciones pueden resultar costosas si se producen en bucles ajustados.</span><span class="sxs-lookup"><span data-stu-id="5057b-392">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="5057b-393">La nueva característica de lenguaje implica que los tipos de valor devuelto de métodos asincrónicos no están limitados a `Task`, `Task<T>` y `void`.</span><span class="sxs-lookup"><span data-stu-id="5057b-393">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="5057b-394">El tipo devuelto debe seguir cumpliendo con el patrón asincrónico, lo que significa que debe haber un método `GetAwaiter` accesible.</span><span class="sxs-lookup"><span data-stu-id="5057b-394">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="5057b-395">Como ejemplo concreto, se ha agregado el tipo `ValueTask` a .NET para sacar partido de esta nueva característica del lenguaje:</span><span class="sxs-lookup"><span data-stu-id="5057b-395">As one concrete example, the `ValueTask` type has been added to .NET to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="5057b-396">Para poder usar el tipo <xref:System.Threading.Tasks.ValueTask%601> tiene que agregar el paquete NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/).</span><span class="sxs-lookup"><span data-stu-id="5057b-396">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) > in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="5057b-397">Esta mejora es especialmente útil para que los creadores de bibliotecas eviten la asignación de un elemento `Task` en código de rendimiento crítico.</span><span class="sxs-lookup"><span data-stu-id="5057b-397">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="5057b-398">Nuevas opciones del compilador</span><span class="sxs-lookup"><span data-stu-id="5057b-398">New compiler options</span></span>

<span data-ttu-id="5057b-399">Las nuevas opciones del compilador admiten nuevos escenarios de DevOps y compilación de programas de C#.</span><span class="sxs-lookup"><span data-stu-id="5057b-399">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="reference-assembly-generation"></a><span data-ttu-id="5057b-400">Generación de ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="5057b-400">Reference assembly generation</span></span>

<span data-ttu-id="5057b-401">Hay dos opciones del compilador nuevas que generan *ensamblados de solo referencia*: [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) y [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly).</span><span class="sxs-lookup"><span data-stu-id="5057b-401">There are two new compiler options that generate *reference-only assemblies*: [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) and [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly).</span></span>
<span data-ttu-id="5057b-402">En los artículos de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.</span><span class="sxs-lookup"><span data-stu-id="5057b-402">The linked articles explain these options and reference assemblies in more detail.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="5057b-403">Firma pública o de código abierto</span><span class="sxs-lookup"><span data-stu-id="5057b-403">Public or Open Source signing</span></span>

<span data-ttu-id="5057b-404">La opción del compilador **PublicSign** indica al compilador que firme el ensamblado con una clave pública.</span><span class="sxs-lookup"><span data-stu-id="5057b-404">The **PublicSign** compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="5057b-405">El ensamblado se marca como firmado, pero la firma se toma de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="5057b-405">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="5057b-406">Esta opción le permite crear ensamblados firmados a partir de proyectos de código abierto utilizando una clave pública.</span><span class="sxs-lookup"><span data-stu-id="5057b-406">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="5057b-407">Para obtener más información, vea el artículo [Opción del compilador **PublicSign**](../language-reference/compiler-options/security.md#publicsign).</span><span class="sxs-lookup"><span data-stu-id="5057b-407">For more information, see the [**PublicSign** compiler option](../language-reference/compiler-options/security.md#publicsign) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="5057b-408">pathmap</span><span class="sxs-lookup"><span data-stu-id="5057b-408">pathmap</span></span>

<span data-ttu-id="5057b-409">La opción del compilador **PathMap** indica al compilador que reemplace las rutas de acceso de origen del entorno de compilación por rutas de acceso de origen asignadas.</span><span class="sxs-lookup"><span data-stu-id="5057b-409">The **PathMap** compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="5057b-410">La opción **PathMap** controla la ruta de acceso de origen que el compilador escribe en los archivos PDB o para <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5057b-410">The **PathMap** option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="5057b-411">Para obtener más información, vea el artículo [Opción del compilador **PathMap**](../language-reference/compiler-options/advanced.md#pathmap).</span><span class="sxs-lookup"><span data-stu-id="5057b-411">For more information, see the [**PathMap** compiler option](../language-reference/compiler-options/advanced.md#pathmap) article.</span></span>
