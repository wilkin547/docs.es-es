---
title: Registros anónimos
description: Aprenda a usar los registros anónimos de construcción y uso, una característica de lenguaje que ayuda a la manipulación de datos.
ms.date: 06/12/2019
ms.openlocfilehash: 13950048f02ab74362f8174725f5f8615d9d7654
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739820"
---
# <a name="anonymous-records"></a><span data-ttu-id="cbe32-103">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="cbe32-103">Anonymous Records</span></span>

<span data-ttu-id="cbe32-104">Los registros anónimos son agregados simples de valores con nombre que no es necesario declarar antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="cbe32-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="cbe32-105">Puede declararlos como Structs o tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="cbe32-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="cbe32-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cbe32-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbe32-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbe32-107">Syntax</span></span>

<span data-ttu-id="cbe32-108">En los siguientes ejemplos se muestra la sintaxis de registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="cbe32-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="cbe32-109">Los elementos delimitados como `[item]` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="cbe32-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="cbe32-110">Uso básico</span><span class="sxs-lookup"><span data-stu-id="cbe32-110">Basic usage</span></span>

<span data-ttu-id="cbe32-111">Los registros anónimos se consideran como tipos de registro de F # que no es necesario declarar antes de la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="cbe32-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="cbe32-112">Por ejemplo, aquí puede interactuar con una función que genera un registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="cbe32-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="cbe32-113">En el ejemplo siguiente se expande el anterior con una `printCircleStats` función que toma un registro anónimo como entrada:</span><span class="sxs-lookup"><span data-stu-id="cbe32-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

<span data-ttu-id="cbe32-114">La llamada a `printCircleStats` con cualquier tipo de registro anónimo que no tenga la misma "forma" que el tipo de entrada no se compilará:</span><span class="sxs-lookup"><span data-stu-id="cbe32-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="cbe32-115">Struct de registros anónimos</span><span class="sxs-lookup"><span data-stu-id="cbe32-115">Struct anonymous records</span></span>

<span data-ttu-id="cbe32-116">Los registros anónimos también se pueden definir como struct con la `struct` palabra clave opcional.</span><span class="sxs-lookup"><span data-stu-id="cbe32-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="cbe32-117">En el ejemplo siguiente se aumenta el anterior generando y consumiendo un registro anónimo de struct:</span><span class="sxs-lookup"><span data-stu-id="cbe32-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a><span data-ttu-id="cbe32-118">Inferencia de Structs</span><span class="sxs-lookup"><span data-stu-id="cbe32-118">Structness inference</span></span>

<span data-ttu-id="cbe32-119">Los registros anónimos de struct también permiten la "inferencia de la estructura", donde no es necesario especificar la `struct` palabra clave en el sitio de llamada.</span><span class="sxs-lookup"><span data-stu-id="cbe32-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="cbe32-120">En este ejemplo, se Elide la `struct` palabra clave cuando se llama a `printCircleStats` :</span><span class="sxs-lookup"><span data-stu-id="cbe32-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="cbe32-121">Patrón inverso: especificar `struct` cuando el tipo de entrada no es un registro anónimo de struct: no se compilará.</span><span class="sxs-lookup"><span data-stu-id="cbe32-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="cbe32-122">Incrustar registros anónimos dentro de otros tipos</span><span class="sxs-lookup"><span data-stu-id="cbe32-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="cbe32-123">Resulta útil declarar [uniones discriminadas](discriminated-unions.md) cuyos casos son registros.</span><span class="sxs-lookup"><span data-stu-id="cbe32-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="cbe32-124">Pero si los datos de los registros son del mismo tipo que la Unión discriminada, debe definir todos los tipos como recursivos mutuamente.</span><span class="sxs-lookup"><span data-stu-id="cbe32-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="cbe32-125">El uso de registros anónimos evita esta restricción.</span><span class="sxs-lookup"><span data-stu-id="cbe32-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="cbe32-126">A continuación se muestra un tipo y una función de ejemplo que coincide con el patrón:</span><span class="sxs-lookup"><span data-stu-id="cbe32-126">What follows is an example type and function that pattern matches over it:</span></span>

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named record for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a><span data-ttu-id="cbe32-127">Expresiones de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="cbe32-127">Copy and update expressions</span></span>

<span data-ttu-id="cbe32-128">Los registros anónimos admiten la construcción con [expresiones de copia y actualización](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cbe32-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="cbe32-129">Por ejemplo, aquí se muestra cómo se puede crear una nueva instancia de un registro anónimo que copie los datos de una existente:</span><span class="sxs-lookup"><span data-stu-id="cbe32-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="cbe32-130">Sin embargo, a diferencia de los registros con nombre, los registros anónimos le permiten crear formularios totalmente diferentes con expresiones de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="cbe32-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="cbe32-131">En el ejemplo siguiente se toma el mismo registro anónimo del ejemplo anterior y se expande en un nuevo registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="cbe32-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="cbe32-132">También es posible construir registros anónimos a partir de instancias de registros con nombre:</span><span class="sxs-lookup"><span data-stu-id="cbe32-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="cbe32-133">También puede copiar datos a y desde los registros anónimos de referencia y de struct:</span><span class="sxs-lookup"><span data-stu-id="cbe32-133">You can also copy data to and from reference and struct anonymous records:</span></span>

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="cbe32-134">Propiedades de los registros anónimos</span><span class="sxs-lookup"><span data-stu-id="cbe32-134">Properties of anonymous records</span></span>

<span data-ttu-id="cbe32-135">Los registros anónimos tienen una serie de características que son esenciales para comprender mejor cómo se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="cbe32-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="cbe32-136">Los registros anónimos son nominales</span><span class="sxs-lookup"><span data-stu-id="cbe32-136">Anonymous records are nominal</span></span>

<span data-ttu-id="cbe32-137">Los registros anónimos son [tipos nominales](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="cbe32-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="cbe32-138">Se consideran mejores como tipos de [registros](records.md) con nombre (que también son nominales) que no requieren una declaración inicial.</span><span class="sxs-lookup"><span data-stu-id="cbe32-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="cbe32-139">Considere el ejemplo siguiente con dos declaraciones de registros anónimos:</span><span class="sxs-lookup"><span data-stu-id="cbe32-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="cbe32-140">Los `x` `y` valores y tienen tipos diferentes y no son compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="cbe32-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="cbe32-141">No son equiparables y no son comparables.</span><span class="sxs-lookup"><span data-stu-id="cbe32-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="cbe32-142">Para ilustrar esto, considere un equivalente de registro con nombre:</span><span class="sxs-lookup"><span data-stu-id="cbe32-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="cbe32-143">No hay nada inherentemente diferente sobre los registros anónimos cuando se compara con sus equivalentes de registro con nombre cuando se trata de una comparación o equivalencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="cbe32-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="cbe32-144">Los registros anónimos usan comparación y igualdad estructural</span><span class="sxs-lookup"><span data-stu-id="cbe32-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="cbe32-145">Al igual que los tipos de registro, los registros anónimos son estructuralmente equiparables y comparables.</span><span class="sxs-lookup"><span data-stu-id="cbe32-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="cbe32-146">Esto solo es cierto si todos los tipos constituyentes admiten la igualdad y la comparación, como sucede con los tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="cbe32-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="cbe32-147">Para admitir la igualdad o la comparación, dos registros anónimos deben tener la misma "forma".</span><span class="sxs-lookup"><span data-stu-id="cbe32-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="cbe32-148">Los registros anónimos son serializables</span><span class="sxs-lookup"><span data-stu-id="cbe32-148">Anonymous records are serializable</span></span>

<span data-ttu-id="cbe32-149">Puede serializar los registros anónimos del mismo modo que con los registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbe32-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="cbe32-150">A continuación se muestra un ejemplo en el que se usa [Newtonsoft.Js](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="cbe32-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn $"Name: {phillip.name} Age: %d{phillip.age}"
```

<span data-ttu-id="cbe32-151">Los registros anónimos son útiles para enviar datos ligeros a través de una red sin necesidad de definir por adelantado un dominio para los tipos serializados y deserializados.</span><span class="sxs-lookup"><span data-stu-id="cbe32-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="cbe32-152">Los registros anónimos interoperan con tipos anónimos de C#</span><span class="sxs-lookup"><span data-stu-id="cbe32-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="cbe32-153">Es posible usar una API de .NET que requiera el uso de [tipos anónimos de C#](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="cbe32-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="cbe32-154">Los tipos anónimos de C# son triviales para interoperar con mediante registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="cbe32-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="cbe32-155">En el ejemplo siguiente se muestra cómo usar registros anónimos para llamar a una sobrecarga de [LINQ](../../csharp/programming-guide/concepts/linq/index.md) que requiere un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="cbe32-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn $"{ng.Name} has first letter {ng.FirstLetter}"
```

<span data-ttu-id="cbe32-156">Hay muchas otras API usadas en .NET que requieren el uso del paso de un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="cbe32-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="cbe32-157">Los registros anónimos son la herramienta para trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="cbe32-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="cbe32-158">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="cbe32-158">Limitations</span></span>

<span data-ttu-id="cbe32-159">Los registros anónimos tienen algunas restricciones en su uso.</span><span class="sxs-lookup"><span data-stu-id="cbe32-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="cbe32-160">Algunos son inherentes a su diseño, pero otros pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="cbe32-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="cbe32-161">Limitaciones con la coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="cbe32-161">Limitations with pattern matching</span></span>

<span data-ttu-id="cbe32-162">Los registros anónimos no admiten la coincidencia de patrones, a diferencia de los registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbe32-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="cbe32-163">Existen tres razones:</span><span class="sxs-lookup"><span data-stu-id="cbe32-163">There are three reasons:</span></span>

1. <span data-ttu-id="cbe32-164">Un patrón tendría que tener en cuenta cada campo de un registro anónimo, a diferencia de los tipos de registro con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbe32-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="cbe32-165">Esto se debe a que los registros anónimos no admiten el subtipo estructural, sino que son tipos nominales.</span><span class="sxs-lookup"><span data-stu-id="cbe32-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="cbe32-166">Debido a (1), no hay ninguna posibilidad de tener patrones adicionales en una expresión de coincidencia de patrones, ya que cada patrón distinto implicaría un tipo de registro anónimo diferente.</span><span class="sxs-lookup"><span data-stu-id="cbe32-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="cbe32-167">Debido a (3), cualquier patrón de registro anónimo sería más detallado que el uso de la notación "punto".</span><span class="sxs-lookup"><span data-stu-id="cbe32-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="cbe32-168">Hay una sugerencia de lenguaje abierto para [permitir la coincidencia de patrones en contextos limitados](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="cbe32-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="cbe32-169">Limitaciones con mutabilidad</span><span class="sxs-lookup"><span data-stu-id="cbe32-169">Limitations with mutability</span></span>

<span data-ttu-id="cbe32-170">En la actualidad, no es posible definir un registro anónimo con `mutable` datos.</span><span class="sxs-lookup"><span data-stu-id="cbe32-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="cbe32-171">Hay una [sugerencia de lenguaje abierto](https://github.com/fsharp/fslang-suggestions/issues/732) para permitir datos mutables.</span><span class="sxs-lookup"><span data-stu-id="cbe32-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="cbe32-172">Limitaciones de los registros anónimos de struct</span><span class="sxs-lookup"><span data-stu-id="cbe32-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="cbe32-173">No es posible declarar registros anónimos de struct como `IsByRefLike` o `IsReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="cbe32-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="cbe32-174">Hay una [sugerencia de lenguaje abierto](https://github.com/fsharp/fslang-suggestions/issues/712) para `IsByRefLike` `IsReadOnly` los registros anónimos y.</span><span class="sxs-lookup"><span data-stu-id="cbe32-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
