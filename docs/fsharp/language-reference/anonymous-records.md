---
title: Registros anónimos
description: Obtenga información sobre cómo usar la construcción y use registros anónimos, una característica del lenguaje que ayuda en la manipulación de datos.
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041809"
---
# <a name="anonymous-records"></a><span data-ttu-id="b1cdb-103">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-103">Anonymous Records</span></span>

<span data-ttu-id="b1cdb-104">Registros anónimos son agregados simples de valores con nombre que no es necesario declarar antes de utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="b1cdb-105">Se puede declarar como tipos de structs o referencia.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="b1cdb-106">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1cdb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1cdb-107">Syntax</span></span>

<span data-ttu-id="b1cdb-108">Los ejemplos siguientes muestran la sintaxis de registro anónimo.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="b1cdb-109">Los elementos delimitados como `[item]` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="b1cdb-110">Uso básico</span><span class="sxs-lookup"><span data-stu-id="b1cdb-110">Basic usage</span></span>

<span data-ttu-id="b1cdb-111">Registros anónimos mejor están pensados como F# tipos que no necesitan declararse antes de la creación de instancias de registros.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="b1cdb-112">Por ejemplo, aquí cómo pueden interactuar con una función que genera un registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="b1cdb-113">El ejemplo siguiente se expande en el anterior con un `printCircleStats` función que toma un registro anónimo como entrada:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="b1cdb-114">Una llamada a `printCircleStats` con cualquier tipo de registro anónimo que no tiene la misma "forma" como el tipo de entrada no se compilará:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="b1cdb-115">Registros de struct anónimos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-115">Struct anonymous records</span></span>

<span data-ttu-id="b1cdb-116">Registros anónimos también pueden definirse como struct con el elemento opcional `struct` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="b1cdb-117">El ejemplo siguiente aumenta lo anterior al producir y consumir un registro de struct anónimo:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="b1cdb-118">Inferencia Structness</span><span class="sxs-lookup"><span data-stu-id="b1cdb-118">Structness inference</span></span>

<span data-ttu-id="b1cdb-119">Registros de struct anónimos también permiten "structness inferencia" donde no es necesario especificar el `struct` palabra clave en el sitio de llamada.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="b1cdb-120">En este ejemplo, elide el `struct` palabra clave al llamar a `printCircleStats`:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="b1cdb-121">El orden inverso de patrón - especificar `struct` cuando el tipo de entrada no es un registro struct anónimo: no se compilará.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="b1cdb-122">Insertar registros anónimos dentro de otros tipos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="b1cdb-123">Es útil declarar [uniones discriminadas](discriminated-unions.md) cuyos casos son los registros.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="b1cdb-124">Pero si los datos de los registros son el mismo tipo que la unión discriminada, debe definir todos los tipos como mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="b1cdb-125">Uso de registros anónimos evita esta restricción.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="b1cdb-126">Lo que sigue es un ejemplo de tipo y función coincide con ese patrón encima de él:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="b1cdb-127">Copiar y actualizar las expresiones</span><span class="sxs-lookup"><span data-stu-id="b1cdb-127">Copy and update expressions</span></span>

<span data-ttu-id="b1cdb-128">Registros anónimos admiten una construcción con [copiar y actualizar las expresiones](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b1cdb-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="b1cdb-129">Por ejemplo, mostramos cómo puede crear una nueva instancia de un registro anónimo que copia existente de datos:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="b1cdb-130">Sin embargo, a diferencia de los registros con nombre, registros anónimos le permiten construir formularios completamente diferentes con copia y actualizar las expresiones.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="b1cdb-131">El ejemplo siguiente toma el mismo registro anónimo del ejemplo anterior y expande en un nuevo registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="b1cdb-132">También es posible crear registros anónimos de instancias de registros con nombre:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="b1cdb-133">También puede copiar datos hacia y desde registros anónimos de referencia y struct:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="b1cdb-134">Propiedades de registros anónimos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-134">Properties of anonymous records</span></span>

<span data-ttu-id="b1cdb-135">Registros anónimos tienen un número de características que son esenciales para entender cómo se puede usar.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="b1cdb-136">Registros anónimos son nominales</span><span class="sxs-lookup"><span data-stu-id="b1cdb-136">Anonymous records are nominal</span></span>

<span data-ttu-id="b1cdb-137">Registros anónimos son [tipos nominales](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="b1cdb-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="b1cdb-138">Como con nombre son entiende mejor [registro](records.md) tipos (que también son nominales) que no requieren una declaración por adelantado.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="b1cdb-139">Considere el siguiente ejemplo con dos declaraciones de registro anónimo:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="b1cdb-140">El `x` y `y` tienen distintos tipos de valores y no son compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="b1cdb-141">No son equivalentes y no son comparables.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="b1cdb-142">Para ilustrar esto, considere la posibilidad de un registro con nombre equivalente:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="b1cdb-143">No hay nada esencialmente distinto en registros anónimos cuando se comparan con sus equivalentes de registro con nombre cuando relativas a la equivalencia de tipos o comparación.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="b1cdb-144">Registros anónimos, use comparación e igualdad estructural</span><span class="sxs-lookup"><span data-stu-id="b1cdb-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="b1cdb-145">Al igual que los tipos de registros, registros anónimos son estructuralmente equivalentes y comparable.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="b1cdb-146">Esto solo es true si todos los tipos constituyentes admiten igualdad y comparación, al igual que con los tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="b1cdb-147">Para admitir la comparación o igualdad, dos registros anónimos deben tener la misma "forma".</span><span class="sxs-lookup"><span data-stu-id="b1cdb-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="b1cdb-148">Registros anónimos son serializables</span><span class="sxs-lookup"><span data-stu-id="b1cdb-148">Anonymous records are serializable</span></span>

<span data-ttu-id="b1cdb-149">Puede serializar registros anónimos se puede hacer con registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="b1cdb-150">Este es un ejemplo con [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="b1cdb-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="b1cdb-151">Registros anónimos son útiles para el envío de datos ligero a través de una red sin necesidad de definir un dominio para los tipos serializa y deserializa por adelantado.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="b1cdb-152">Registros anónimos interoperan con C# tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="b1cdb-153">Es posible usar una API de .NET que requiere el uso de [ C# tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="b1cdb-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="b1cdb-154">C#tipos anónimos son triviales para interoperar con registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="b1cdb-155">En el ejemplo siguiente se muestra cómo utilizar registros anónimos para llamar a un [LINQ](../../csharp/programming-guide/concepts/linq/index.md) sobrecarga que requiere un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="b1cdb-156">Hay una gran cantidad de otra API que se usan a lo largo de .NET que requieren el uso de cómo pasar un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="b1cdb-157">Registros anónimos son la herramienta para trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="b1cdb-158">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b1cdb-158">Limitations</span></span>

<span data-ttu-id="b1cdb-159">Registros anónimos tienen algunas restricciones de su uso.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="b1cdb-160">Algunas son inherentes a su diseño, pero otras son susceptibles de cambiar.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="b1cdb-161">Limitaciones de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="b1cdb-161">Limitations with pattern matching</span></span>

<span data-ttu-id="b1cdb-162">Registros anónimos no admiten la coincidencia de patrones, a diferencia de los registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="b1cdb-163">Existen tres razones:</span><span class="sxs-lookup"><span data-stu-id="b1cdb-163">There are three reasons:</span></span>

1. <span data-ttu-id="b1cdb-164">Tendría un patrón para tener en cuenta todos los campos de un registro anónimo, a diferencia de los tipos de registros con nombre.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="b1cdb-165">Esto es porque no admiten registros anónimos subtipo estructural, sino que son tipos nominales.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="b1cdb-166">Debido a (1), no hay ninguna posibilidad de ver patrones adicionales en una expresión de coincidencia de patrón, como cada patrón distinto implicaría un tipo de registro anónimo diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="b1cdb-167">Debido a (3), cualquier modelo de registro anónimo sería más detallado que el uso de la notación "punto".</span><span class="sxs-lookup"><span data-stu-id="b1cdb-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="b1cdb-168">Hay una sugerencia de lenguaje abierto para [permiten la coincidencia de patrones limitada en contextos](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="b1cdb-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="b1cdb-169">Limitaciones con mutabilidad</span><span class="sxs-lookup"><span data-stu-id="b1cdb-169">Limitations with mutability</span></span>

<span data-ttu-id="b1cdb-170">No es actualmente posible definir un registro anónimo con `mutable` datos.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="b1cdb-171">Hay un [abrir sugerencia lenguaje](https://github.com/fsharp/fslang-suggestions/issues/732) para permitir que los datos mutables.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="b1cdb-172">Limitaciones de los registros de struct anónimos</span><span class="sxs-lookup"><span data-stu-id="b1cdb-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="b1cdb-173">No es posible declarar struct registros anónimos como `IsByRefLike` o `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="b1cdb-174">Hay un [abrir sugerencia lenguaje](https://github.com/fsharp/fslang-suggestions/issues/712) a para `IsByRefLike` y `IsReadOnly` registros anónimos.</span><span class="sxs-lookup"><span data-stu-id="b1cdb-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
