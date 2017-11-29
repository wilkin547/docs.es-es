---
title: Tuplas (F#)
description: "Obtenga información acerca de la tupla de F #, una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 35069073-9a82-410f-8dea-912e2a152e6d
ms.openlocfilehash: c6a0565ac7022928f5c2bdad5387d896c6c3d387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="tuples"></a><span data-ttu-id="3df8c-104">Tuplas</span><span class="sxs-lookup"><span data-stu-id="3df8c-104">Tuples</span></span>

<span data-ttu-id="3df8c-105">A *tupla* es una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3df8c-105">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="3df8c-106">Tuplas pueden ser tipos de referencia o structs.</span><span class="sxs-lookup"><span data-stu-id="3df8c-106">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="3df8c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3df8c-107">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="3df8c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3df8c-108">Remarks</span></span>
<span data-ttu-id="3df8c-109">Cada *elemento* en la sintaxis anterior puede ser cualquier expresión válida de F #.</span><span class="sxs-lookup"><span data-stu-id="3df8c-109">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="3df8c-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3df8c-110">Examples</span></span>
<span data-ttu-id="3df8c-111">Algunos ejemplos de tuplas son pares, los triples etc., de los tipos iguales o distintos.</span><span class="sxs-lookup"><span data-stu-id="3df8c-111">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="3df8c-112">Algunos ejemplos se ilustran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-112">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="3df8c-113">Obtener valores individuales</span><span class="sxs-lookup"><span data-stu-id="3df8c-113">Obtaining Individual Values</span></span>
<span data-ttu-id="3df8c-114">Puede usar una coincidencia de patrones para acceder y asignar nombres a elementos de tupla, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-114">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="3df8c-115">También puede anular una tupla a través de coincidencia de patrones fuera de un `match` expresión mediante `let` enlace:</span><span class="sxs-lookup"><span data-stu-id="3df8c-115">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="3df8c-116">O puede definir como patrón coinciden en tuplas como entradas para funciones:</span><span class="sxs-lookup"><span data-stu-id="3df8c-116">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="3df8c-117">Si necesita un único elemento de la tupla, el carácter comodín (el carácter de subrayado) puede utilizarse para evitar la creación de un nuevo nombre para un valor que no es necesario.</span><span class="sxs-lookup"><span data-stu-id="3df8c-117">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="3df8c-118">Copiar elementos de una tupla de referencia en una tupla de struct también es simple:</span><span class="sxs-lookup"><span data-stu-id="3df8c-118">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="3df8c-119">Las funciones `fst` y `snd` (hacer referencia solo tuplas) devuelve el primer y segundo elementos de una tupla, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-119">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="3df8c-120">No hay ninguna función integrada que devuelva el tercer elemento de un triple, pero se puede escribir fácilmente uno como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="3df8c-120">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="3df8c-121">Por lo general, es mejor usar la coincidencia de patrón para tener acceso a elementos de tupla individuales.</span><span class="sxs-lookup"><span data-stu-id="3df8c-121">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="3df8c-122">Uso de tuplas</span><span class="sxs-lookup"><span data-stu-id="3df8c-122">Using Tuples</span></span>
<span data-ttu-id="3df8c-123">Tuplas proporcionan una manera cómoda para devolver varios valores de una función, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-123">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="3df8c-124">En este ejemplo se realiza la división de enteros y devuelve el resultado redondeado de la operación como primer miembro de una tupla de dos elementos y el resto como segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="3df8c-124">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="3df8c-125">Si desea evitar la currificación implícita de los argumentos de función que está implícito en la sintaxis de función habitual tuplas también pueden utilizarse como argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="3df8c-125">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="3df8c-126">La sintaxis habitual para definir la función `let sum a b = a + b` le permite definir una función que es la aplicación parcial del primer argumento de la función, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-126">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="3df8c-127">El uso de una tupla como parámetro deshabilita la currificación.</span><span class="sxs-lookup"><span data-stu-id="3df8c-127">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="3df8c-128">Para obtener más información, vea "Aplicación parcial de argumentos" en [funciones](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="3df8c-128">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="3df8c-129">Nombres de tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="3df8c-129">Names of Tuple Types</span></span>
<span data-ttu-id="3df8c-130">Cuando se escribe el nombre de un tipo que es una tupla, use la `*` símbolos para separar los elementos.</span><span class="sxs-lookup"><span data-stu-id="3df8c-130">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="3df8c-131">Para una tupla que consta de un `int`, `float`y un `string`, como `(10, 10.0, "ten")`, el tipo se escribiría como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="3df8c-131">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="3df8c-132">Interoperación con tuplas de C#</span><span class="sxs-lookup"><span data-stu-id="3df8c-132">Interoperation with C# Tuples</span></span>

<span data-ttu-id="3df8c-133">C# 7 introdujo tuplas del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="3df8c-133">C# 7 introduced tuples to the language.</span></span>  <span data-ttu-id="3df8c-134">Tuplas en estructuras de C# y se y son equivalentes a las tuplas de struct en F #.</span><span class="sxs-lookup"><span data-stu-id="3df8c-134">Tuples in C# and are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="3df8c-135">Si tiene que interoperar con C# usa tuplas, debe utilizar tuplas de struct.</span><span class="sxs-lookup"><span data-stu-id="3df8c-135">If you need to interoperate with C# uses tuples, you must use struct tuples.</span></span>

<span data-ttu-id="3df8c-136">Esto es muy fácil de hacer.</span><span class="sxs-lookup"><span data-stu-id="3df8c-136">This is easy to do.</span></span>  <span data-ttu-id="3df8c-137">Por ejemplo, imagine que tiene que pasar una tupla a una clase de C# y, a continuación, utilizar su resultado, que también es una tupla:</span><span class="sxs-lookup"><span data-stu-id="3df8c-137">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="3df8c-138">En el código de F #, a continuación, puede pasar una tupla de struct como parámetro y consumir el resultado como una tupla de struct.</span><span class="sxs-lookup"><span data-stu-id="3df8c-138">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="3df8c-139">Convertir entre tuplas de referencia y las tuplas de Struct</span><span class="sxs-lookup"><span data-stu-id="3df8c-139">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="3df8c-140">Dado que tuplas de referencia y Struct Tuples tienen una representación subyacente completamente diferente, no son convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="3df8c-140">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="3df8c-141">Es decir, no se compilará código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3df8c-141">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="3df8c-142">Debe patrón coinciden en una tupla y crear otro con las partes constituyentes.</span><span class="sxs-lookup"><span data-stu-id="3df8c-142">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="3df8c-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3df8c-143">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="3df8c-144">Formato compilado de tuplas de referencia</span><span class="sxs-lookup"><span data-stu-id="3df8c-144">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="3df8c-145">Esta sección explica la forma de tuplas cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="3df8c-145">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="3df8c-146">La información aquí no es necesario leer a menos que se dirige a .NET Framework 3.5 o inferior.</span><span class="sxs-lookup"><span data-stu-id="3df8c-146">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="3df8c-147">Tuplas se compilan en objetos de uno de varios tipos genéricos, con todos los nombre `System.Tuple`, que están sobrecargados en la aridad o el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="3df8c-147">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="3df8c-148">Tipos de tupla aparecen en este formulario cuando se visualizan desde otro lenguaje, como C# o Visual Basic, o cuando se usa una herramienta que no es compatible con construcciones de F #.</span><span class="sxs-lookup"><span data-stu-id="3df8c-148">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="3df8c-149">El `Tuple` tipos se incorporaron en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3df8c-149">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="3df8c-150">Si se establece como destino una versión anterior de .NET Framework, el compilador utiliza las versiones de [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) desde la versión 2.0 de la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="3df8c-150">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="3df8c-151">Los tipos de esta biblioteca se utilizan únicamente para aplicaciones que tienen como destino la versión 2.0, 3.0 y 3.5 versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3df8c-151">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="3df8c-152">El reenvío de tipos se utiliza para garantizar la compatibilidad binaria entre los componentes de .NET Framework 2.0 y F # de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3df8c-152">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="3df8c-153">Formato compilado de tuplas de Struct</span><span class="sxs-lookup"><span data-stu-id="3df8c-153">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="3df8c-154">Tuplas de struct (por ejemplo, `struct (x, y)`), son fundamentalmente diferentes de tuplas de referencia.</span><span class="sxs-lookup"><span data-stu-id="3df8c-154">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="3df8c-155">Se compilan en el <xref:System.ValueTuple> tipo, sobrecargada por aridad o el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="3df8c-155">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="3df8c-156">Equivalen a [C# 7 tuplas](../../csharp/tuples.md) y [Visual Basic 2017 tuplas](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interoperen bidireccional.</span><span class="sxs-lookup"><span data-stu-id="3df8c-156">They are equivalent to [C# 7 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="3df8c-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="3df8c-157">See Also</span></span>
[<span data-ttu-id="3df8c-158">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="3df8c-158">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="3df8c-159">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="3df8c-159">F# Types</span></span>](fsharp-types.md)
