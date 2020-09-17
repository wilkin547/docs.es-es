---
title: Tuplas
description: 'Obtenga información sobre la tupla de F #, una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f4adf7e10e22d8b7a8cf697baee15962adf3630
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720366"
---
# <a name="tuples"></a><span data-ttu-id="d538f-103">Tuplas</span><span class="sxs-lookup"><span data-stu-id="d538f-103">Tuples</span></span>

<span data-ttu-id="d538f-104">Una *tupla* es una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d538f-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="d538f-105">Las tuplas pueden ser tipos de referencia o Structs.</span><span class="sxs-lookup"><span data-stu-id="d538f-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="d538f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d538f-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="d538f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d538f-107">Remarks</span></span>

<span data-ttu-id="d538f-108">Cada *elemento* de la sintaxis anterior puede ser cualquier expresión de F # válida.</span><span class="sxs-lookup"><span data-stu-id="d538f-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="d538f-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d538f-109">Examples</span></span>

<span data-ttu-id="d538f-110">Entre los ejemplos de tuplas se incluyen pares, tripas, etc., del mismo tipo o de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d538f-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="d538f-111">En el código siguiente se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d538f-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="d538f-112">Obtener valores individuales</span><span class="sxs-lookup"><span data-stu-id="d538f-112">Obtaining Individual Values</span></span>

<span data-ttu-id="d538f-113">Puede usar la coincidencia de patrones para obtener acceso y asignar nombres para los elementos de tupla, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d538f-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="d538f-114">También puede deconstruir una tupla a través de la coincidencia de patrones fuera de una `match` expresión a través del  `let` enlace:</span><span class="sxs-lookup"><span data-stu-id="d538f-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="d538f-115">O bien, puede buscar coincidencias en tuplas como entradas en funciones:</span><span class="sxs-lookup"><span data-stu-id="d538f-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="d538f-116">Si solo necesita un elemento de la tupla, se puede usar el carácter comodín (el carácter de subrayado) para evitar la creación de un nuevo nombre para un valor que no necesite.</span><span class="sxs-lookup"><span data-stu-id="d538f-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="d538f-117">Copiar elementos de una tupla de referencia en una tupla de struct también es simple:</span><span class="sxs-lookup"><span data-stu-id="d538f-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="d538f-118">Las funciones `fst` y `snd` (solo tuplas de referencia) devuelven el primer y el segundo elemento de una tupla, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d538f-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="d538f-119">No hay ninguna función integrada que devuelva el tercer elemento de un triple, pero se puede escribir fácilmente como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="d538f-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="d538f-120">Por lo general, es mejor usar la coincidencia de patrones para tener acceso a elementos de tupla individuales.</span><span class="sxs-lookup"><span data-stu-id="d538f-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="d538f-121">Usar tuplas</span><span class="sxs-lookup"><span data-stu-id="d538f-121">Using Tuples</span></span>

<span data-ttu-id="d538f-122">Las tuplas proporcionan una manera cómoda de devolver varios valores de una función, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d538f-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="d538f-123">Este ejemplo realiza una división de enteros y devuelve el resultado redondeado de la operación como un primer miembro de un par de tupla y el resto como un segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="d538f-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="d538f-124">Las tuplas también se pueden usar como argumentos de función cuando se desea evitar el currificación implícito de los argumentos de función que está implícito en la sintaxis de función habitual.</span><span class="sxs-lookup"><span data-stu-id="d538f-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="d538f-125">La sintaxis habitual para definir la función `let sum a b = a + b` permite definir una función que es la aplicación parcial del primer argumento de la función, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d538f-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="d538f-126">El uso de una tupla como parámetro deshabilita currificación.</span><span class="sxs-lookup"><span data-stu-id="d538f-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="d538f-127">Para obtener más información, vea "aplicación parcial de argumentos" en [funciones](./functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="d538f-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="d538f-128">Nombres de tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="d538f-128">Names of Tuple Types</span></span>

<span data-ttu-id="d538f-129">Cuando se escribe el nombre de un tipo que es una tupla, se usa el `*` símbolo para separar los elementos.</span><span class="sxs-lookup"><span data-stu-id="d538f-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="d538f-130">Para una tupla que consta de un, `int` un `float` y un `string` , como `(10, 10.0, "ten")` , el tipo se escribiría como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="d538f-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="d538f-131">Interoperación con tuplas de C#</span><span class="sxs-lookup"><span data-stu-id="d538f-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="d538f-132">C# 7,0 presentó tuplas en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d538f-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="d538f-133">Las tuplas en C# son estructuras y son equivalentes a las tuplas de struct en F #.</span><span class="sxs-lookup"><span data-stu-id="d538f-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="d538f-134">Si necesita interoperar con C#, debe utilizar tuplas de struct.</span><span class="sxs-lookup"><span data-stu-id="d538f-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="d538f-135">Esto es fácil de hacer.</span><span class="sxs-lookup"><span data-stu-id="d538f-135">This is easy to do.</span></span>  <span data-ttu-id="d538f-136">Por ejemplo, Imagine que tiene que pasar una tupla a una clase de C# y luego consumir su resultado, que también es una tupla:</span><span class="sxs-lookup"><span data-stu-id="d538f-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="d538f-137">En el código de F #, puede pasar una tupla de struct como parámetro y consumir el resultado como una tupla de estructura.</span><span class="sxs-lookup"><span data-stu-id="d538f-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="d538f-138">Convertir entre tuplas de referencia y tuplas de struct</span><span class="sxs-lookup"><span data-stu-id="d538f-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="d538f-139">Dado que las tuplas de referencia y las tuplas de struct tienen una representación subyacente completamente diferente, no se pueden convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="d538f-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="d538f-140">Es decir, el código como el siguiente no se compilará:</span><span class="sxs-lookup"><span data-stu-id="d538f-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="d538f-141">Debe crear patrones de coincidencia en una tupla y construir la otra con las partes constituyentes.</span><span class="sxs-lookup"><span data-stu-id="d538f-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="d538f-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d538f-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="d538f-143">Forma compilada de tuplas de referencia</span><span class="sxs-lookup"><span data-stu-id="d538f-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="d538f-144">En esta sección se explica la forma de las tuplas cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="d538f-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="d538f-145">Esta información no es necesaria para leer a menos que tenga como destino .NET Framework 3,5 o inferior.</span><span class="sxs-lookup"><span data-stu-id="d538f-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="d538f-146">Las tuplas se compilan en objetos de uno de varios tipos genéricos, todos los nombres `System.Tuple` , que están sobrecargados en la aridad o el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d538f-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="d538f-147">Los tipos de tupla aparecen en este formulario cuando se ven desde otro lenguaje, como C# o Visual Basic, o cuando se usa una herramienta que no es consciente de las construcciones de F #.</span><span class="sxs-lookup"><span data-stu-id="d538f-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="d538f-148">Los `Tuple` tipos se introdujeron en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d538f-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="d538f-149">Si el destino es una versión anterior de .NET Framework, el compilador usa versiones de de `System.Tuple` la versión 2,0 de la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="d538f-149">If you are targeting an earlier version of .NET Framework, the compiler uses versions of `System.Tuple` from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="d538f-150">Los tipos de esta biblioteca solo se usan para las aplicaciones destinadas a las versiones 2,0, 3,0 y 3,5 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d538f-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of .NET Framework.</span></span> <span data-ttu-id="d538f-151">El reenvío de tipos se usa para garantizar la compatibilidad binaria entre .NET Framework 2,0 y .NET Framework 4 componentes de F #.</span><span class="sxs-lookup"><span data-stu-id="d538f-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="d538f-152">Forma compilada de tuplas de struct</span><span class="sxs-lookup"><span data-stu-id="d538f-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="d538f-153">Las tuplas de estructura (por ejemplo, `struct (x, y)` ), son fundamentalmente distintas de las tuplas de referencia.</span><span class="sxs-lookup"><span data-stu-id="d538f-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="d538f-154">Se compilan en el <xref:System.ValueTuple> tipo, sobrecargado por aridad o el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d538f-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="d538f-155">Son equivalentes a las tuplas de [C# 7,0](../../csharp/language-reference/builtin-types/value-tuples.md) y [Visual Basic las tuplas 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md), e interoperan bidireccionalmente.</span><span class="sxs-lookup"><span data-stu-id="d538f-155">They are equivalent to [C# 7.0 Tuples](../../csharp/language-reference/builtin-types/value-tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="d538f-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="d538f-156">See also</span></span>

- [<span data-ttu-id="d538f-157">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="d538f-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d538f-158">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="d538f-158">F# Types</span></span>](fsharp-types.md)
