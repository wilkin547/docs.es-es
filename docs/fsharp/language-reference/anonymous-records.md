---
title: Registros anónimos
description: Aprenda a usar construir y usar registros anónimos, una característica de lenguaje que ayuda con la manipulación de datos.
ms.date: 06/12/2019
ms.openlocfilehash: ef3aa8fccdb6ff406542932816e4138040845a59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187493"
---
# <a name="anonymous-records"></a><span data-ttu-id="10e39-103">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="10e39-103">Anonymous Records</span></span>

<span data-ttu-id="10e39-104">Los registros anónimos son agregados simples de valores con nombre que no es necesario declarar antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="10e39-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="10e39-105">Puede declararlos como structs o tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="10e39-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="10e39-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="10e39-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="10e39-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10e39-107">Syntax</span></span>

<span data-ttu-id="10e39-108">En los ejemplos siguientes se muestra la sintaxis de registro anónimo.</span><span class="sxs-lookup"><span data-stu-id="10e39-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="10e39-109">Elementos delimitados como `[item]` opcionales.</span><span class="sxs-lookup"><span data-stu-id="10e39-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="10e39-110">Uso básico</span><span class="sxs-lookup"><span data-stu-id="10e39-110">Basic usage</span></span>

<span data-ttu-id="10e39-111">Los registros anónimos se consideran mejor como tipos de registros de F- que no es necesario declarar antes de la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="10e39-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="10e39-112">Por ejemplo, aquí se puede interactuar con una función que genera un registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="10e39-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="10e39-113">En el ejemplo siguiente se expande el anterior con una `printCircleStats` función que toma un registro anónimo como entrada:</span><span class="sxs-lookup"><span data-stu-id="10e39-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="10e39-114">Llamar `printCircleStats` con cualquier tipo de registro anónimo que no tenga la misma "forma" que el tipo de entrada no se compilará:</span><span class="sxs-lookup"><span data-stu-id="10e39-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="10e39-115">Estructurar registros anónimos</span><span class="sxs-lookup"><span data-stu-id="10e39-115">Struct anonymous records</span></span>

<span data-ttu-id="10e39-116">Los registros anónimos también se `struct` pueden definir como struct con la palabra clave opcional.</span><span class="sxs-lookup"><span data-stu-id="10e39-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="10e39-117">En el ejemplo siguiente se aumenta el anterior mediante la producción y el consumo de un registro anónimo struct:</span><span class="sxs-lookup"><span data-stu-id="10e39-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="10e39-118">Inferencia de estructuración</span><span class="sxs-lookup"><span data-stu-id="10e39-118">Structness inference</span></span>

<span data-ttu-id="10e39-119">Los registros anónimos de estructura también permiten la "inferencia de estructuración" donde no es necesario especificar la `struct` palabra clave en el sitio de llamada.</span><span class="sxs-lookup"><span data-stu-id="10e39-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="10e39-120">En este ejemplo, se `struct` elimina la `printCircleStats`palabra clave al llamar a:</span><span class="sxs-lookup"><span data-stu-id="10e39-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="10e39-121">El patrón inverso, que especifica `struct` cuándo el tipo de entrada no es un registro anónimo struct, no se compilará.</span><span class="sxs-lookup"><span data-stu-id="10e39-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="10e39-122">Incrustar registros anónimos dentro de otros tipos</span><span class="sxs-lookup"><span data-stu-id="10e39-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="10e39-123">Es útil declarar [uniones discriminadas cuyos](discriminated-unions.md) casos son registros.</span><span class="sxs-lookup"><span data-stu-id="10e39-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="10e39-124">Pero si los datos de los registros son del mismo tipo que la unión discriminada, debe definir todos los tipos como mutuamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="10e39-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="10e39-125">El uso de registros anónimos evita esta restricción.</span><span class="sxs-lookup"><span data-stu-id="10e39-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="10e39-126">Lo que sigue es un tipo de ejemplo y una función que el patrón coincide sobre él:</span><span class="sxs-lookup"><span data-stu-id="10e39-126">What follows is an example type and function that pattern matches over it:</span></span>

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="10e39-127">Copiar y actualizar expresiones</span><span class="sxs-lookup"><span data-stu-id="10e39-127">Copy and update expressions</span></span>

<span data-ttu-id="10e39-128">Los registros anónimos admiten la construcción con expresiones de [copia y actualización.](copy-and-update-record-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="10e39-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="10e39-129">Por ejemplo, a continuación se muestra cómo puede construir una nueva instancia de un registro anónimo que copia los datos de uno existente:</span><span class="sxs-lookup"><span data-stu-id="10e39-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="10e39-130">Sin embargo, a diferencia de los registros con nombre, los registros anónimos le permiten construir formularios completamente diferentes con expresiones de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="10e39-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="10e39-131">En el ejemplo siguiente se toma el mismo registro anónimo del ejemplo anterior y se expande en un nuevo registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="10e39-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="10e39-132">También es posible construir registros anónimos a partir de instancias de registros con nombre:</span><span class="sxs-lookup"><span data-stu-id="10e39-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="10e39-133">También puede copiar datos a y desde registros anónimos de referencia y estructuración:</span><span class="sxs-lookup"><span data-stu-id="10e39-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="10e39-134">Propiedades de registros anónimos</span><span class="sxs-lookup"><span data-stu-id="10e39-134">Properties of anonymous records</span></span>

<span data-ttu-id="10e39-135">Los registros anónimos tienen una serie de características que son esenciales para comprender completamente cómo se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="10e39-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="10e39-136">Los registros anónimos son nominales</span><span class="sxs-lookup"><span data-stu-id="10e39-136">Anonymous records are nominal</span></span>

<span data-ttu-id="10e39-137">Los registros anónimos son [tipos nominales.](https://en.wikipedia.org/wiki/Nominal_type_system)</span><span class="sxs-lookup"><span data-stu-id="10e39-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="10e39-138">Se piensan mejor como tipos de [registro](records.md) con nombre (que también son nominales) que no requieren una declaración inicial.</span><span class="sxs-lookup"><span data-stu-id="10e39-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="10e39-139">Considere el siguiente ejemplo con dos declaraciones de registros anónimos:</span><span class="sxs-lookup"><span data-stu-id="10e39-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="10e39-140">Los `x` `y` valores y tienen diferentes tipos y no son compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="10e39-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="10e39-141">No son ecuatables y no son comparables.</span><span class="sxs-lookup"><span data-stu-id="10e39-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="10e39-142">Para ilustrar esto, considere un equivalente de registro con nombre:</span><span class="sxs-lookup"><span data-stu-id="10e39-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="10e39-143">No hay nada inherentemente diferente acerca de los registros anónimos en comparación con sus equivalentes de registro sen su nombre cuando se refiere a equivalencia de tipo o comparación.</span><span class="sxs-lookup"><span data-stu-id="10e39-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="10e39-144">Los registros anónimos utilizan la igualdad estructural y la comparación</span><span class="sxs-lookup"><span data-stu-id="10e39-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="10e39-145">Al igual que los tipos de registros, los registros anónimos son estructuralmente igualables y comparables.</span><span class="sxs-lookup"><span data-stu-id="10e39-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="10e39-146">Esto solo es cierto si todos los tipos constituyentes admiten la igualdad y la comparación, como con los tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="10e39-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="10e39-147">Para admitir la igualdad o la comparación, dos registros anónimos deben tener la misma "forma".</span><span class="sxs-lookup"><span data-stu-id="10e39-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="10e39-148">Los registros anónimos son serializables</span><span class="sxs-lookup"><span data-stu-id="10e39-148">Anonymous records are serializable</span></span>

<span data-ttu-id="10e39-149">Puede serializar registros anónimos del igual que con los registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="10e39-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="10e39-150">Aquí está un ejemplo usando [Newtonsoft.Json:](https://www.nuget.org/packages/Newtonsoft.Json/)</span><span class="sxs-lookup"><span data-stu-id="10e39-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="10e39-151">Los registros anónimos son útiles para enviar datos ligeros a través de una red sin necesidad de definir un dominio para los tipos serializados/deserializados por adelantado.</span><span class="sxs-lookup"><span data-stu-id="10e39-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="10e39-152">Los registros anónimos interoperan con los tipos anónimos de CTM</span><span class="sxs-lookup"><span data-stu-id="10e39-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="10e39-153">Es posible usar una API de .NET que requiera el uso de [tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)de C.</span><span class="sxs-lookup"><span data-stu-id="10e39-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="10e39-154">Los tipos anónimos de CTM son triviales de interoperar mediante el uso de registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="10e39-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="10e39-155">En el ejemplo siguiente se muestra cómo usar registros anónimos para llamar a una sobrecarga [LINQ](../../csharp/programming-guide/concepts/linq/index.md) que requiere un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="10e39-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="10e39-156">Hay una multitud de otras API utilizadas en .NET que requieren el uso de pasar un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="10e39-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="10e39-157">Los registros anónimos son su herramienta para trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="10e39-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="10e39-158">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="10e39-158">Limitations</span></span>

<span data-ttu-id="10e39-159">Los registros anónimos tienen algunas restricciones en su uso.</span><span class="sxs-lookup"><span data-stu-id="10e39-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="10e39-160">Algunos son inherentes a su diseño, pero otros son susceptibles de cambiar.</span><span class="sxs-lookup"><span data-stu-id="10e39-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="10e39-161">Limitaciones con coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="10e39-161">Limitations with pattern matching</span></span>

<span data-ttu-id="10e39-162">Los registros anónimos no admiten la coincidencia de patrones, a diferencia de los registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="10e39-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="10e39-163">Hay tres razones:</span><span class="sxs-lookup"><span data-stu-id="10e39-163">There are three reasons:</span></span>

1. <span data-ttu-id="10e39-164">Un patrón tendría que tener en cuenta cada campo de un registro anónimo, a diferencia de los tipos de registro con nombre.</span><span class="sxs-lookup"><span data-stu-id="10e39-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="10e39-165">Esto se debe a que los registros anónimos no admiten la subtipación estructural: son tipos nominales.</span><span class="sxs-lookup"><span data-stu-id="10e39-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="10e39-166">Debido a (1), no hay capacidad para tener patrones adicionales en una expresión de coincidencia de patrón, ya que cada patrón distinto implicaría un tipo de registro anónimo diferente.</span><span class="sxs-lookup"><span data-stu-id="10e39-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="10e39-167">Debido a (3), cualquier patrón de registro anónimo sería más detallado que el uso de la notación "punto".</span><span class="sxs-lookup"><span data-stu-id="10e39-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="10e39-168">Hay una sugerencia de lenguaje abierto para permitir la coincidencia de [patrones en contextos limitados.](https://github.com/fsharp/fslang-suggestions/issues/713)</span><span class="sxs-lookup"><span data-stu-id="10e39-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="10e39-169">Limitaciones con mutabilidad</span><span class="sxs-lookup"><span data-stu-id="10e39-169">Limitations with mutability</span></span>

<span data-ttu-id="10e39-170">Actualmente no es posible definir `mutable` un registro anónimo con datos.</span><span class="sxs-lookup"><span data-stu-id="10e39-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="10e39-171">Hay una sugerencia de [lenguaje abierto](https://github.com/fsharp/fslang-suggestions/issues/732) para permitir datos mutables.</span><span class="sxs-lookup"><span data-stu-id="10e39-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="10e39-172">Limitaciones con registros anónimos de estructura</span><span class="sxs-lookup"><span data-stu-id="10e39-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="10e39-173">No es posible declarar registros `IsByRefLike` `IsReadOnly`anónimos struct como o .</span><span class="sxs-lookup"><span data-stu-id="10e39-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="10e39-174">Hay una sugerencia de `IsByRefLike` lenguaje `IsReadOnly` [abierto](https://github.com/fsharp/fslang-suggestions/issues/712) para y registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="10e39-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
