---
title: 'Novedades de F # 5,0-Guía de F #'
description: 'Obtenga información general sobre las nuevas características disponibles en F # 5,0.'
ms.date: 11/06/2020
ms.openlocfilehash: 29b5b110379dec476d7c0aa51540984acb25f26e
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098702"
---
# <a name="whats-new-in-f-50"></a><span data-ttu-id="c1413-103">Novedades de F# 5.0</span><span class="sxs-lookup"><span data-stu-id="c1413-103">What's new in F# 5.0</span></span>

<span data-ttu-id="c1413-104">F # 5,0 agrega varias mejoras en el lenguaje F # y F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="c1413-104">F# 5.0 adds several improvements to the F# language and F# Interactive.</span></span> <span data-ttu-id="c1413-105">Se publica con **.net 5**.</span><span class="sxs-lookup"><span data-stu-id="c1413-105">It is released with **.NET 5**.</span></span>

<span data-ttu-id="c1413-106">Puede descargar el SDK de .NET más reciente de la [página de descargas de .NET](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="c1413-106">You can download the latest .NET SDK from the [.NET downloads page](https://dotnet.microsoft.com/download).</span></span>

## <a name="get-started"></a><span data-ttu-id="c1413-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="c1413-107">Get started</span></span>

<span data-ttu-id="c1413-108">F # 5,0 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c1413-108">F# 5.0 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="c1413-109">Para obtener más información, consulte Introducción a [F #](../get-started/index.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c1413-109">For more information, see [Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="package-references-in-f-scripts"></a><span data-ttu-id="c1413-110">Referencias de paquetes en scripts de F #</span><span class="sxs-lookup"><span data-stu-id="c1413-110">Package references in F# scripts</span></span>

<span data-ttu-id="c1413-111">F # 5 proporciona compatibilidad con las referencias de paquete en scripts de F # con `#r "nuget:..."` Sintaxis.</span><span class="sxs-lookup"><span data-stu-id="c1413-111">F# 5 brings support for package references in F# scripts with `#r "nuget:..."` syntax.</span></span> <span data-ttu-id="c1413-112">Por ejemplo, considere la siguiente referencia de paquete:</span><span class="sxs-lookup"><span data-stu-id="c1413-112">For example, consider the following package reference:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn "%s" (JsonConvert.SerializeObject o)
```

<span data-ttu-id="c1413-113">También puede proporcionar una versión explícita después del nombre del paquete como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c1413-113">You can also supply an explicit version after the name of the package like this:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

<span data-ttu-id="c1413-114">Las referencias de paquete admiten paquetes con dependencias nativas, como ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c1413-114">Package references support packages with native dependencies, such as ML.NET.</span></span>

<span data-ttu-id="c1413-115">Las referencias de paquete también admiten paquetes con requisitos especiales para hacer referencia a s dependientes `.dll` .</span><span class="sxs-lookup"><span data-stu-id="c1413-115">Package references also support packages with special requirements about referencing dependent `.dll`s.</span></span> <span data-ttu-id="c1413-116">Por ejemplo, el paquete [FParsec](https://www.nuget.org/packages/FParsec/) que se usa para requerir que los usuarios se aseguren de forma manual antes de que se haga referencia a su dependiente `FParsecCS.dll` en primer lugar antes `FParsec.dll` de que se haga referencia a él en F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="c1413-116">For example, the [FParsec](https://www.nuget.org/packages/FParsec/) package used to require that users manually ensure that its dependent `FParsecCS.dll` was referenced first before `FParsec.dll` was referenced in F# Interactive.</span></span> <span data-ttu-id="c1413-117">Esto ya no es necesario y puede hacer referencia al paquete como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c1413-117">This is no longer needed, and you can reference the package as follows:</span></span>

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn "Success: %A" result
    | Failure(errorMsg, _, _) -> printfn "Failure: %s" errorMsg

test pfloat "1.234"
```

<span data-ttu-id="c1413-118">Esta característica implementa las [herramientas de F # RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-118">This feature implements [F# Tooling RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md).</span></span> <span data-ttu-id="c1413-119">Para obtener más información sobre las referencias de paquetes, vea el tutorial de [F# interactivo](../tutorials/fsharp-interactive/index.md) .</span><span class="sxs-lookup"><span data-stu-id="c1413-119">For more information on package references, see the [F# Interactive](../tutorials/fsharp-interactive/index.md) tutorial.</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="c1413-120">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="c1413-120">String interpolation</span></span>

<span data-ttu-id="c1413-121">Las cadenas interpoladas de F # son bastante similares a las cadenas interpoladas de C# o JavaScript, ya que permiten escribir código en "huecos" dentro de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="c1413-121">F# interpolated strings are fairly similar to C# or JavaScript interpolated strings, in that they let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="c1413-122">Este es un ejemplo básico:</span><span class="sxs-lookup"><span data-stu-id="c1413-122">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="c1413-123">Sin embargo, las cadenas interpoladas de F # también permiten las interpolaciones con tipo, al igual que la `sprintf` función, para exigir que una expresión dentro de un contexto interpolado se ajuste a un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="c1413-123">However, F# interpolated strings also allow for typed interpolations, just like the `sprintf` function, to enforce that an expression inside of an interpolated context conforms to a particular type.</span></span> <span data-ttu-id="c1413-124">Usa los mismos especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="c1413-124">It uses the same format specifiers.</span></span>

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="c1413-125">En el ejemplo de interpolación con tipo anterior, `%s` requiere que la interpolación sea de tipo `string` , mientras que `%d` requiere que la interpolación sea `integer` .</span><span class="sxs-lookup"><span data-stu-id="c1413-125">In the preceding typed interpolation example, the `%s` requires the interpolation to be of type `string`, whereas the `%d` requires the interpolation to be an `integer`.</span></span>

<span data-ttu-id="c1413-126">Además, cualquier expresión (o expresiones) arbitraria de F # se puede colocar en el lado de un contexto de interpolación.</span><span class="sxs-lookup"><span data-stu-id="c1413-126">Additionally, any arbitrary F# expression (or expressions) can be placed in side of an interpolation context.</span></span> <span data-ttu-id="c1413-127">Incluso es posible escribir una expresión más complicada, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1413-127">It is even possible to write a more complicated expression, like so:</span></span>

```fsharp
let str =
    $"""The result of squaring each odd item in {[1..10]} is:
{
    let square x = x * x
    let isOdd x = x % 2 <> 0
    let oddSquares xs =
        xs
        |> List.filter isOdd
        |> List.map square
    oddSquares [1..10]
}
"""
```

<span data-ttu-id="c1413-128">Aunque no se recomienda hacerlo demasiado en la práctica.</span><span class="sxs-lookup"><span data-stu-id="c1413-128">Although we don't recommend doing this too much in practice.</span></span>

<span data-ttu-id="c1413-129">Esta característica implementa [F # RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-129">This feature implements [F# RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).</span></span>

## <a name="support-for-nameof"></a><span data-ttu-id="c1413-130">Compatibilidad con el nombre de</span><span class="sxs-lookup"><span data-stu-id="c1413-130">Support for nameof</span></span>

<span data-ttu-id="c1413-131">F # 5 admite el `nameof` operador, que resuelve el símbolo que se usa para y genera su nombre en el origen de F #.</span><span class="sxs-lookup"><span data-stu-id="c1413-131">F# 5 supports the `nameof` operator, which resolves the symbol it's being used for and produces its name in F# source.</span></span> <span data-ttu-id="c1413-132">Esto resulta útil en varios escenarios, como el registro, y protege el registro de los cambios en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="c1413-132">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) (sprintf "Value passed in was %d." month)

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="c1413-133">La última línea producirá una excepción y "Month" se mostrará en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c1413-133">The last line will throw an exception and "month" will be shown in the error message.</span></span>

<span data-ttu-id="c1413-134">Puede tomar un nombre de casi todas las construcciones de F #:</span><span class="sxs-lookup"><span data-stu-id="c1413-134">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn "%s" (M.f 12)
printfn "%s" (nameof M)
printfn "%s" (nameof M.f)
```

<span data-ttu-id="c1413-135">Tres adiciones finales son cambios en el funcionamiento de los operadores: la adición del `nameof<'type-parameter>` formulario para los parámetros de tipo genérico y la capacidad de usar `nameof` como patrón en una expresión de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="c1413-135">Three final additions are changes to how operators work: the addition of the `nameof<'type-parameter>` form for generic type parameters, and the ability to use `nameof` as a pattern in a pattern match expression.</span></span>

<span data-ttu-id="c1413-136">Si se toma el nombre de un operador, se obtiene su cadena de origen.</span><span class="sxs-lookup"><span data-stu-id="c1413-136">Taking a name of an operator gives its source string.</span></span> <span data-ttu-id="c1413-137">Si necesita el formulario compilado, use el nombre compilado de un operador:</span><span class="sxs-lookup"><span data-stu-id="c1413-137">If you need the compiled form, use the compiled name of an operator:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

<span data-ttu-id="c1413-138">Tomar el nombre de un parámetro de tipo requiere una sintaxis ligeramente diferente:</span><span class="sxs-lookup"><span data-stu-id="c1413-138">Taking the name of a type parameter requires a slightly different syntax:</span></span>

```fsharp
type C<'TType> =
    member _.TypeName = nameof<'TType>
```

<span data-ttu-id="c1413-139">Esto es similar a los `typeof<'T>` `typedefof<'T>` operadores y.</span><span class="sxs-lookup"><span data-stu-id="c1413-139">This is similar to the `typeof<'T>` and `typedefof<'T>` operators.</span></span>

<span data-ttu-id="c1413-140">F # 5 también agrega compatibilidad con un `nameof` patrón que se puede usar en `match` expresiones:</span><span class="sxs-lookup"><span data-stu-id="c1413-140">F# 5 also adds support for a `nameof` pattern that can be used in `match` expressions:</span></span>

```fsharp
[<Struct; IsByRefLike>]
type RecordedEvent = { EventType: string; Data: ReadOnlySpan<byte> }

type MyEvent =
    | AData of int
    | BData of string

let deserialize (e: RecordedEvent) : MyEvent =
    match e.EventType with
    | nameof AData -> AData (JsonSerializer.Deserialize<int> e.Data)
    | nameof BData -> BData (JsonSerializer.Deserialize<string> e.Data)
    | t -> failwithf "Invalid EventType: %s" t
```

<span data-ttu-id="c1413-141">En el código anterior se usa ' name ' en lugar del literal de cadena en la expresión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c1413-141">The preceding code uses 'nameof' instead of the string literal in the match expression.</span></span>

<span data-ttu-id="c1413-142">Esta característica implementa [F # RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-142">This feature implements [F# RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).</span></span>

## <a name="open-type-declarations"></a><span data-ttu-id="c1413-143">Declaraciones de tipo abierto</span><span class="sxs-lookup"><span data-stu-id="c1413-143">Open type declarations</span></span>

<span data-ttu-id="c1413-144">F # 5 también agrega compatibilidad con las declaraciones de tipos abiertos.</span><span class="sxs-lookup"><span data-stu-id="c1413-144">F# 5 also adds support for open type declarations.</span></span> <span data-ttu-id="c1413-145">Una declaración de tipo abierto es como abrir una clase estática en C#, excepto con una sintaxis diferente y un comportamiento ligeramente diferente para ajustar la semántica de F #.</span><span class="sxs-lookup"><span data-stu-id="c1413-145">An open type declaration is like opening a static class in C#, except with some different syntax and some slightly different behavior to fit F# semantics.</span></span>

<span data-ttu-id="c1413-146">Con las declaraciones de tipos abiertos, puede `open` Mostrar cualquier tipo para exponer el contenido estático dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="c1413-146">With open type declarations, you can `open` any type to expose static contents inside of it.</span></span> <span data-ttu-id="c1413-147">Además, puede `open` definir uniones y registros definidos en F # para exponer su contenido.</span><span class="sxs-lookup"><span data-stu-id="c1413-147">Additionally, you can `open` F#-defined unions and records to expose their contents.</span></span> <span data-ttu-id="c1413-148">Por ejemplo, esto puede ser útil si tiene una Unión definida en un módulo y desea tener acceso a sus casos, pero no desea abrir todo el módulo.</span><span class="sxs-lookup"><span data-stu-id="c1413-148">For example, this can be useful if you have a union defined in a module and want to access its cases, but don't want to open the entire module.</span></span>

```fsharp
open type System.Math

let x = Min(1.0, 2.0)

module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

<span data-ttu-id="c1413-149">A diferencia de C#, cuando se trabaja `open type` con dos tipos que exponen un miembro con el mismo nombre, el miembro del último tipo que se va a `open` cambiar de nombre prevalece sobre el otro.</span><span class="sxs-lookup"><span data-stu-id="c1413-149">Unlike C#, when you `open type` on two types that expose a member with the same name, the member from the last type being `open`ed shadows the other name.</span></span> <span data-ttu-id="c1413-150">Esto es coherente con la semántica de F # en torno a la sombra que ya existe.</span><span class="sxs-lookup"><span data-stu-id="c1413-150">This is consistent with F# semantics around shadowing that exist already.</span></span>

<span data-ttu-id="c1413-151">Esta característica implementa [F # RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-151">This feature implements [F# RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).</span></span>

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a><span data-ttu-id="c1413-152">Comportamiento de división coherente para tipos de datos integrados</span><span class="sxs-lookup"><span data-stu-id="c1413-152">Consistent slicing behavior for built-in data types</span></span>

<span data-ttu-id="c1413-153">Comportamiento para segmentar los `FSharp.Core` tipos de datos integrados (matriz, lista, cadena, matriz 2D, matriz 3D, matriz 4D) que se usa para no ser coherente antes de F # 5.</span><span class="sxs-lookup"><span data-stu-id="c1413-153">Behavior for slicing the built-in `FSharp.Core` data types (array, list, string, 2D array, 3D array, 4D array) used to not be consistent prior to F# 5.</span></span> <span data-ttu-id="c1413-154">Algunos comportamientos de casos de borde han producido una excepción y otros no.</span><span class="sxs-lookup"><span data-stu-id="c1413-154">Some edge-case behavior threw an exception and some wouldn't.</span></span> <span data-ttu-id="c1413-155">En F # 5, todos los tipos integrados ahora devuelven segmentos vacíos para los segmentos que son imposibles de generar:</span><span class="sxs-lookup"><span data-stu-id="c1413-155">In F# 5, all built-in types now return empty slices for slices that are impossible to generate:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

// Before: would return empty list
// F# 5: same
let emptyList = l.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty array
let emptyArray = a.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty string
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="c1413-156">Esta característica implementa [F # RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-156">This feature implements [F# RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a><span data-ttu-id="c1413-157">Segmentos de índice fijo para matrices 3D y 4D en FSharp. Core</span><span class="sxs-lookup"><span data-stu-id="c1413-157">Fixed-index slices for 3D and 4D arrays in FSharp.Core</span></span>

<span data-ttu-id="c1413-158">F # 5,0 ofrece compatibilidad para segmentar con un índice fijo en los tipos de matriz 3D y 4D integrados.</span><span class="sxs-lookup"><span data-stu-id="c1413-158">F# 5.0 brings support for slicing with a fixed index in the built-in 3D and 4D array types.</span></span>

<span data-ttu-id="c1413-159">Para ilustrar esto, considere la siguiente matriz 3D:</span><span class="sxs-lookup"><span data-stu-id="c1413-159">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="c1413-160">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="c1413-160">*z = 0*</span></span>
| <span data-ttu-id="c1413-161">x\y</span><span class="sxs-lookup"><span data-stu-id="c1413-161">x\y</span></span>   | <span data-ttu-id="c1413-162">0</span><span class="sxs-lookup"><span data-stu-id="c1413-162">0</span></span> | <span data-ttu-id="c1413-163">1</span><span class="sxs-lookup"><span data-stu-id="c1413-163">1</span></span> |
|-------|---|---|
| <span data-ttu-id="c1413-164">**0**</span><span class="sxs-lookup"><span data-stu-id="c1413-164">**0**</span></span> | <span data-ttu-id="c1413-165">0</span><span class="sxs-lookup"><span data-stu-id="c1413-165">0</span></span> | <span data-ttu-id="c1413-166">1</span><span class="sxs-lookup"><span data-stu-id="c1413-166">1</span></span> |
| <span data-ttu-id="c1413-167">**1**</span><span class="sxs-lookup"><span data-stu-id="c1413-167">**1**</span></span> | <span data-ttu-id="c1413-168">2</span><span class="sxs-lookup"><span data-stu-id="c1413-168">2</span></span> | <span data-ttu-id="c1413-169">3</span><span class="sxs-lookup"><span data-stu-id="c1413-169">3</span></span> |

<span data-ttu-id="c1413-170">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="c1413-170">*z = 1*</span></span>
| <span data-ttu-id="c1413-171">x\y</span><span class="sxs-lookup"><span data-stu-id="c1413-171">x\y</span></span>   | <span data-ttu-id="c1413-172">0</span><span class="sxs-lookup"><span data-stu-id="c1413-172">0</span></span> | <span data-ttu-id="c1413-173">1</span><span class="sxs-lookup"><span data-stu-id="c1413-173">1</span></span> |
|-------|---|---|
| <span data-ttu-id="c1413-174">**0**</span><span class="sxs-lookup"><span data-stu-id="c1413-174">**0**</span></span> | <span data-ttu-id="c1413-175">4</span><span class="sxs-lookup"><span data-stu-id="c1413-175">4</span></span> | <span data-ttu-id="c1413-176">5</span><span class="sxs-lookup"><span data-stu-id="c1413-176">5</span></span> |
| <span data-ttu-id="c1413-177">**1**</span><span class="sxs-lookup"><span data-stu-id="c1413-177">**1**</span></span> | <span data-ttu-id="c1413-178">6</span><span class="sxs-lookup"><span data-stu-id="c1413-178">6</span></span> | <span data-ttu-id="c1413-179">7</span><span class="sxs-lookup"><span data-stu-id="c1413-179">7</span></span> |

<span data-ttu-id="c1413-180">¿Qué ocurre si desea extraer el segmento `[| 4; 5 |]` de la matriz?</span><span class="sxs-lookup"><span data-stu-id="c1413-180">What if you wanted to extract the slice `[| 4; 5 |]` from the array?</span></span> <span data-ttu-id="c1413-181">Ahora es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="c1413-181">This is now very simple!</span></span>

```fsharp
// First, create a 3D array to slice

let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="c1413-182">Esta característica implementa [F # RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-182">This feature implements [F# RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).</span></span>

## <a name="f-quotations-improvements"></a><span data-ttu-id="c1413-183">Mejoras en las comillas de F #</span><span class="sxs-lookup"><span data-stu-id="c1413-183">F# quotations improvements</span></span>

<span data-ttu-id="c1413-184">Ahora, las [expresiones de código delimitadas](../language-reference/code-quotations.md) de F # tienen la capacidad de conservar la información de restricciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="c1413-184">F# [code quotations](../language-reference/code-quotations.md) now have the ability to retain type constraint information.</span></span> <span data-ttu-id="c1413-185">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1413-185">Consider the following example:</span></span>

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

<span data-ttu-id="c1413-186">La restricción generada por la `inline` función se conserva en la expresión de código delimitada.</span><span class="sxs-lookup"><span data-stu-id="c1413-186">The constraint generated by the `inline` function is retained in the code quotation.</span></span> <span data-ttu-id="c1413-187">`negate`Ahora se puede evaluar el formulario entrecomillado de la función.</span><span class="sxs-lookup"><span data-stu-id="c1413-187">The `negate` function's quoted form can now be evaluated.</span></span>

<span data-ttu-id="c1413-188">Esta característica implementa [F # RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-188">This feature implements [F# RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).</span></span>

## <a name="applicative-computation-expressions"></a><span data-ttu-id="c1413-189">Expresiones de cálculo de procesamiento</span><span class="sxs-lookup"><span data-stu-id="c1413-189">Applicative Computation Expressions</span></span>

<span data-ttu-id="c1413-190">Las [expresiones de cálculo (CES)](../language-reference/computation-expressions.md) se usan hoy en día para modelar "cálculos contextuales", o en una terminología más descriptiva de la programación funcional, cálculos de Monad.</span><span class="sxs-lookup"><span data-stu-id="c1413-190">[Computation expressions (CEs)](../language-reference/computation-expressions.md) are used today to model "contextual computations", or in more functional programming-friendly terminology, monadic computations.</span></span>

<span data-ttu-id="c1413-191">F # 5 introduce CEs de procesamiento, que ofrecen un modelo de cálculo diferente.</span><span class="sxs-lookup"><span data-stu-id="c1413-191">F# 5 introduces applicative CEs, which offer a different computational model.</span></span> <span data-ttu-id="c1413-192">Los CEs de la capacidad de proceso permiten cálculos más eficientes siempre y cuando cada cálculo sea independiente, y los resultados se acumulan al final.</span><span class="sxs-lookup"><span data-stu-id="c1413-192">Applicative CEs allow for more efficient computations provided that every computation is independent, and their results are accumulated at the end.</span></span> <span data-ttu-id="c1413-193">Cuando los cálculos son independientes entre sí, también son trivialmente pueden paralelizar, lo que permite a los autores de CE escribir bibliotecas más eficaces.</span><span class="sxs-lookup"><span data-stu-id="c1413-193">When computations are independent of one another, they are also trivially parallelizable, allowing CE authors to write more efficient libraries.</span></span> <span data-ttu-id="c1413-194">Esta ventaja se aplica a una restricción, aunque: no se permiten los cálculos que dependen de valores calculados previamente.</span><span class="sxs-lookup"><span data-stu-id="c1413-194">This benefit comes at a restriction, though: computations that depend on previously computed values are not allowed.</span></span>

<span data-ttu-id="c1413-195">En el ejemplo siguiente se muestra un CE básico para el `Result` tipo.</span><span class="sxs-lookup"><span data-stu-id="c1413-195">The follow example shows a basic applicative CE for the `Result` type.</span></span>

```fsharp
// First, define a 'zip' function
module Result =
    let zip x1 x2 =
        match x1,x2 with
        | Ok x1res, Ok x2res -> Ok (x1res, x2res)
        | Error e, _ -> Error e
        | _, Error e -> Error e

// Next, define a builder with 'MergeSources' and 'BindReturn'
type ResultBuilder() =
    member _.MergeSources(t1: Result<'T,'U>, t2: Result<'T1,'U>) = Result.zip t1 t2
    member _.BindReturn(x: Result<'T,'U>, f) = Result.map f x

let result = ResultBuilder()

let run r1 r2 r3 =
    // And here is our applicative!
    let res1: Result<int, string> =
        result {
            let! a = r1
            and! b = r2
            and! c = r3
            return a + b - c
        }

    match res1 with
    | Ok x -> printfn "%s is: %d" (nameof res1) x
    | Error e -> printfn "%s is: %s" (nameof res1) e

let printApplicatives () =
    let r1 = Ok 2
    let r2 = Ok 3 // Error "fail!"
    let r3 = Ok 4

    run r1 r2 r3
    run r1 (Error "failure!") r3
```

<span data-ttu-id="c1413-196">Si es un autor de la biblioteca que expone CEs en su biblioteca hoy, hay algunas consideraciones adicionales que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1413-196">If you're a library author who exposes CEs in their library today, there are some additional considerations you'll need to be aware of.</span></span>

<span data-ttu-id="c1413-197">Esta característica implementa [F # RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-197">This feature implements [F# RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).</span></span>

## <a name="interfaces-can-be-implemented-at-different-generic-instantiations"></a><span data-ttu-id="c1413-198">Las interfaces se pueden implementar en distintas instancias genéricas</span><span class="sxs-lookup"><span data-stu-id="c1413-198">Interfaces can be implemented at different generic instantiations</span></span>

<span data-ttu-id="c1413-199">Ahora puede implementar la misma interfaz en distintas instancias genéricas:</span><span class="sxs-lookup"><span data-stu-id="c1413-199">You can now implement the same interface at different generic instantiations:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

<span data-ttu-id="c1413-200">Esta característica implementa [F # RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-200">This feature implements [F# RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).</span></span>

## <a name="default-interface-member-consumption"></a><span data-ttu-id="c1413-201">Consumo de miembro de interfaz predeterminado</span><span class="sxs-lookup"><span data-stu-id="c1413-201">Default interface member consumption</span></span>

<span data-ttu-id="c1413-202">F # 5 le permite consumir [interfaces con implementaciones predeterminadas](../../csharp/tutorials/default-interface-methods-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-202">F# 5 lets you consume [interfaces with default implementations](../../csharp/tutorials/default-interface-methods-versions.md).</span></span>

<span data-ttu-id="c1413-203">Considere una interfaz definida en C# similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1413-203">Consider an interface defined in C# like this:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDimasd
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="c1413-204">Puede consumirlo en F # a través de cualquiera de los métodos estándar de implementación de una interfaz:</span><span class="sxs-lookup"><span data-stu-id="c1413-204">You can consume it in F# through any of the standard means of implementing an interface:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn "DIM from C#: %d" md.Z

// You can also implement it via an object expression
let md' = { new MyDim }
printfn "DIM from C# but via Object Expression: %d" md'.Z
```

<span data-ttu-id="c1413-205">Esto le permite aprovechar de forma segura el código C# y los componentes .NET escritos en C# moderno cuando esperan que los usuarios puedan usar una implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c1413-205">This lets you safely take advantage of C# code and .NET components written in modern C# when they expect users to be able to consume a default implementation.</span></span>

<span data-ttu-id="c1413-206">Esta característica implementa [F # RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-206">This feature implements [F# RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).</span></span>

## <a name="simplified-interop-with-nullable-value-types"></a><span data-ttu-id="c1413-207">Interoperabilidad simplificada con tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="c1413-207">Simplified interop with nullable value types</span></span>

<span data-ttu-id="c1413-208">F # es compatible con los [tipos que aceptan valores NULL (valores)](https://docs.microsoft.com/dotnet/api/system.nullable-1) (denominados tradicionalmente tipos que aceptan valores NULL), pero la interacción con ellos ha sido tradicionalmente algo de un problema, ya que tendría que crear un `Nullable` `Nullable<SomeType>` contenedor o cada vez que desease pasar un valor.</span><span class="sxs-lookup"><span data-stu-id="c1413-208">[Nullable (value) types](https://docs.microsoft.com/dotnet/api/system.nullable-1) (called Nullable Types historically) have long been supported by F#, but interacting with them has traditionally been somewhat of a pain since you'd have to construct a `Nullable` or `Nullable<SomeType>` wrapper every time you wanted to pass a value.</span></span> <span data-ttu-id="c1413-209">Ahora, el compilador convertirá implícitamente un tipo de valor en `Nullable<ThatValueType>` si el tipo de destino coincide.</span><span class="sxs-lookup"><span data-stu-id="c1413-209">Now the compiler will implicitly convert a value type into a `Nullable<ThatValueType>` if the target type matches.</span></span> <span data-ttu-id="c1413-210">Ahora es posible el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="c1413-210">The following code is now possible:</span></span>

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

<span data-ttu-id="c1413-211">Esta característica implementa [F # RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-211">This feature implements [F# RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).</span></span>

## <a name="preview-reverse-indexes"></a><span data-ttu-id="c1413-212">Vista previa: índices inversos</span><span class="sxs-lookup"><span data-stu-id="c1413-212">Preview: reverse indexes</span></span>

<span data-ttu-id="c1413-213">F # 5 también presenta una vista previa para permitir índices inversos.</span><span class="sxs-lookup"><span data-stu-id="c1413-213">F# 5 also introduces a preview for allowing reverse indexes.</span></span> <span data-ttu-id="c1413-214">La sintaxis es `^idx`.</span><span class="sxs-lookup"><span data-stu-id="c1413-214">The syntax is `^idx`.</span></span> <span data-ttu-id="c1413-215">A continuación se muestra cómo puede obtener un valor de elemento 1 desde el final de una lista:</span><span class="sxs-lookup"><span data-stu-id="c1413-215">Here's how you can an element 1 value from the end of a list:</span></span>

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

<span data-ttu-id="c1413-216">También puede definir índices inversos para sus propios tipos.</span><span class="sxs-lookup"><span data-stu-id="c1413-216">You can also define reverse indexes for your own types.</span></span> <span data-ttu-id="c1413-217">Para ello, debe implementar el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1413-217">To do so, you'll need to implement the following method:</span></span>

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

<span data-ttu-id="c1413-218">Este es un ejemplo del `Span<'T>` tipo:</span><span class="sxs-lookup"><span data-stu-id="c1413-218">Here's an example for the `Span<'T>` type:</span></span>

```fsharp
open System

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

    member sp.GetReverseIndex(_, offset: int) =
        sp.Length - offset

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let run () =
    let sp = [| 1; 2; 3; 4; 5 |].AsSpan()

    // Pre-# 5.0 slicing on a Span<'T>
    printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..3] // [|1; 2; 3|]
    printSpan sp.[1..3] // |2; 3|]

    // Same slices, but only using from-the-end index
    printSpan sp.[..^0] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..^2] // [|1; 2; 3|]
    printSpan sp.[^4..^2] // [|2; 3|]

run() // Prints the same thing twice
```

<span data-ttu-id="c1413-219">Esta característica implementa [F # RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-219">This feature implements [F# RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).</span></span>

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a><span data-ttu-id="c1413-220">Versión preliminar: sobrecargas de palabras clave personalizadas en expresiones de cálculo</span><span class="sxs-lookup"><span data-stu-id="c1413-220">Preview: overloads of custom keywords in computation expressions</span></span>

<span data-ttu-id="c1413-221">Las expresiones de cálculo son una característica eficaz para los autores de bibliotecas y marcos.</span><span class="sxs-lookup"><span data-stu-id="c1413-221">Computation expressions are a powerful feature for library and framework authors.</span></span> <span data-ttu-id="c1413-222">Permiten mejorar considerablemente la expresividad de los componentes permitiéndole definir miembros conocidos y formar un DSL para el dominio en el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="c1413-222">They allow you to greatly improve the expressiveness of your components by letting you define well-known members and form a DSL for the domain you're working in.</span></span>

<span data-ttu-id="c1413-223">F # 5 agrega compatibilidad de vista previa para sobrecargar las operaciones personalizadas en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c1413-223">F# 5 adds preview support for overloading custom operations in Computation Expressions.</span></span> <span data-ttu-id="c1413-224">Permite escribir y consumir el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="c1413-224">It allows the following code to be written and consumed:</span></span>

```fsharp
open System

type InputKind =
    | Text of placeholder:string option
    | Password of placeholder: string option

type InputOptions =
  { Label: string option
    Kind : InputKind
    Validators : (string -> bool) array }

type InputBuilder() =
    member t.Yield(_) =
      { Label = None
        Kind = Text None
        Validators = [||] }

    [<CustomOperation("text")>]
    member this.Text(io, ?placeholder) =
        { io with Kind = Text placeholder }

    [<CustomOperation("password")>]
    member this.Password(io, ?placeholder) =
        { io with Kind = Password placeholder }

    [<CustomOperation("label")>]
    member this.Label(io, label) =
        { io with Label = Some label }

    [<CustomOperation("with_validators")>]
    member this.Validators(io, [<ParamArray>] validators) =
        { io with Validators = validators }

let input = InputBuilder()

let name =
    input {
    label "Name"
    text
    with_validators
        (String.IsNullOrWhiteSpace >> not)
    }

let email =
    input {
    label "Email"
    text "Your email"
    with_validators
        (String.IsNullOrWhiteSpace >> not)
        (fun s -> s.Contains "@")
    }

let password =
    input {
    label "Password"
    password "Must contains at least 6 characters, one number and one uppercase"
    with_validators
        (String.exists Char.IsUpper)
        (String.exists Char.IsDigit)
        (fun s -> s.Length >= 6)
    }
```

<span data-ttu-id="c1413-225">Antes de este cambio, podría escribir el `InputBuilder` tipo tal como está, pero no podía usarlo de la forma en que se utiliza en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c1413-225">Prior to this change, you could write the `InputBuilder` type as it is, but you couldn't use it the way it's used in the example.</span></span> <span data-ttu-id="c1413-226">Como las sobrecargas, los parámetros opcionales y los `System.ParamArray` tipos Now están permitidos, todo funciona de la forma esperada.</span><span class="sxs-lookup"><span data-stu-id="c1413-226">Since overloads, optional parameters, and now `System.ParamArray` types are allowed, everything just works as you'd expect it to.</span></span>

<span data-ttu-id="c1413-227">Esta característica implementa [F # RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).</span><span class="sxs-lookup"><span data-stu-id="c1413-227">This feature implements [F# RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).</span></span>
