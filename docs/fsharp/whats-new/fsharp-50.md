---
title: 'Novedades de F # 5,0-Guía de F #'
description: 'Obtenga información general sobre las nuevas características disponibles en F # 5,0.'
ms.date: 11/06/2020
ms.openlocfilehash: 9b138e4801a3e599db650990acd53c0f956b78b8
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190733"
---
# <a name="whats-new-in-f-50"></a>Novedades de F# 5.0

F # 5,0 agrega varias mejoras en el lenguaje F # y F# interactivo. Se publica con **.net 5**.

Puede descargar el SDK de .NET más reciente de la [página de descargas de .NET](https://dotnet.microsoft.com/download).

## <a name="get-started"></a>Primeros pasos

F # 5,0 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. Para obtener más información, consulte Introducción a [F #](../get-started/index.md) para obtener más información.

## <a name="package-references-in-f-scripts"></a>Referencias de paquetes en scripts de F #

F # 5 proporciona compatibilidad con las referencias de paquete en scripts de F # con `#r "nuget:..."` Sintaxis. Por ejemplo, considere la siguiente referencia de paquete:

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn $"{JsonConvert.SerializeObject o}"
```

También puede proporcionar una versión explícita después del nombre del paquete como se indica a continuación:

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

Las referencias de paquete admiten paquetes con dependencias nativas, como ML.NET.

Las referencias de paquete también admiten paquetes con requisitos especiales para hacer referencia a s dependientes `.dll` . Por ejemplo, el paquete [FParsec](https://www.nuget.org/packages/FParsec/) que se usa para requerir que los usuarios se aseguren de forma manual antes de que se haga referencia a su dependiente `FParsecCS.dll` en primer lugar antes `FParsec.dll` de que se haga referencia a él en F# interactivo. Esto ya no es necesario y puede hacer referencia al paquete como se indica a continuación:

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn $"Success: {result}"
    | Failure(errorMsg, _, _) -> printfn $"Failure: {errorMsg}"

test pfloat "1.234"
```

Esta característica implementa las [herramientas de F # RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md). Para obtener más información sobre las referencias de paquetes, vea el tutorial de [F# interactivo](../tools/fsharp-interactive/index.md) .

## <a name="string-interpolation"></a>Interpolación de cadenas

Las cadenas interpoladas de F # son bastante similares a las cadenas interpoladas de C# o JavaScript, ya que permiten escribir código en "huecos" dentro de un literal de cadena. Este es un ejemplo básico:

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

Sin embargo, las cadenas interpoladas de F # también permiten las interpolaciones con tipo, al igual que la `sprintf` función, para exigir que una expresión dentro de un contexto interpolado se ajuste a un tipo determinado. Usa los mismos especificadores de formato.

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

En el ejemplo de interpolación con tipo anterior, `%s` requiere que la interpolación sea de tipo `string` , mientras que `%d` requiere que la interpolación sea `integer` .

Además, cualquier expresión (o expresiones) arbitraria de F # se puede colocar en el lado de un contexto de interpolación. Incluso es posible escribir una expresión más complicada, como la siguiente:

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

Aunque no se recomienda hacerlo demasiado en la práctica.

Esta característica implementa [F # RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).

## <a name="support-for-nameof"></a>Compatibilidad con el nombre de

F # 5 admite el `nameof` operador, que resuelve el símbolo que se usa para y genera su nombre en el origen de F #. Esto resulta útil en varios escenarios, como el registro, y protege el registro de los cambios en el código fuente.

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

printfn $"{lookupMonth 12}"
printfn $"{lookupMonth 1}"
printfn $"{lookupMonth 13}"
```

La última línea producirá una excepción y "Month" se mostrará en el mensaje de error.

Puede tomar un nombre de casi todas las construcciones de F #:

```fsharp
module M =
    let f x = nameof x

printfn $"{M.f 12}"
printfn $"{nameof M}"
printfn $"{nameof M.f}"
```

Tres adiciones finales son cambios en el funcionamiento de los operadores: la adición del `nameof<'type-parameter>` formulario para los parámetros de tipo genérico y la capacidad de usar `nameof` como patrón en una expresión de coincidencia de patrones.

Si se toma el nombre de un operador, se obtiene su cadena de origen. Si necesita el formulario compilado, use el nombre compilado de un operador:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

Tomar el nombre de un parámetro de tipo requiere una sintaxis ligeramente diferente:

```fsharp
type C<'TType> =
    member _.TypeName = nameof<'TType>
```

Esto es similar a los `typeof<'T>` `typedefof<'T>` operadores y.

F # 5 también agrega compatibilidad con un `nameof` patrón que se puede usar en `match` expresiones:

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

En el código anterior se usa ' name ' en lugar del literal de cadena en la expresión de coincidencia.

Esta característica implementa [F # RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).

## <a name="open-type-declarations"></a>Declaraciones de tipo abierto

F # 5 también agrega compatibilidad con las declaraciones de tipos abiertos. Una declaración de tipo abierto es como abrir una clase estática en C#, excepto con una sintaxis diferente y un comportamiento ligeramente diferente para ajustar la semántica de F #.

Con las declaraciones de tipos abiertos, puede `open` Mostrar cualquier tipo para exponer el contenido estático dentro de ella. Además, puede `open` definir uniones y registros definidos en F # para exponer su contenido. Por ejemplo, esto puede ser útil si tiene una Unión definida en un módulo y desea tener acceso a sus casos, pero no desea abrir todo el módulo.

```fsharp
open type System.Math

let x = Min(1.0, 2.0)

module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn $"{A}"
```

A diferencia de C#, cuando se trabaja `open type` con dos tipos que exponen un miembro con el mismo nombre, el miembro del último tipo que se va a `open` cambiar de nombre prevalece sobre el otro. Esto es coherente con la semántica de F # en torno a la sombra que ya existe.

Esta característica implementa [F # RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a>Comportamiento de división coherente para tipos de datos integrados

Comportamiento para segmentar los `FSharp.Core` tipos de datos integrados (matriz, lista, cadena, matriz 2D, matriz 3D, matriz 4D) que se usa para no ser coherente antes de F # 5. Algunos comportamientos de casos de borde han producido una excepción y otros no. En F # 5, todos los tipos integrados ahora devuelven segmentos vacíos para los segmentos que son imposibles de generar:

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

Esta característica implementa [F # RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a>Segmentos de índice fijo para matrices 3D y 4D en FSharp. Core

F # 5,0 ofrece compatibilidad para segmentar con un índice fijo en los tipos de matriz 3D y 4D integrados.

Para ilustrar esto, considere la siguiente matriz 3D:

*z = 0*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

¿Qué ocurre si desea extraer el segmento `[| 4; 5 |]` de la matriz? Ahora es muy sencillo.

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

Esta característica implementa [F # RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).

## <a name="f-quotations-improvements"></a>Mejoras en las comillas de F #

Ahora, las [expresiones de código delimitadas](../language-reference/code-quotations.md) de F # tienen la capacidad de conservar la información de restricciones de tipos. Considere el ejemplo siguiente:

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

La restricción generada por la `inline` función se conserva en la expresión de código delimitada. `negate`Ahora se puede evaluar el formulario quotated de la función.

Esta característica implementa [F # RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).

## <a name="applicative-computation-expressions"></a>Expresiones de cálculo de procesamiento

Las [expresiones de cálculo (CES)](../language-reference/computation-expressions.md) se usan hoy en día para modelar "cálculos contextuales", o en una terminología más descriptiva de la programación funcional, cálculos de Monad.

F # 5 introduce CEs de procesamiento, que ofrecen un modelo de cálculo diferente. Los CEs de la capacidad de proceso permiten cálculos más eficientes siempre y cuando cada cálculo sea independiente, y los resultados se acumulan al final. Cuando los cálculos son independientes entre sí, también son trivialmente pueden paralelizar, lo que permite a los autores de CE escribir bibliotecas más eficaces. Esta ventaja se aplica a una restricción, aunque: no se permiten los cálculos que dependen de valores calculados previamente.

En el ejemplo siguiente se muestra un CE básico para el `Result` tipo.

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
    | Ok x -> printfn $"{nameof res1} is: %d{x}"
    | Error e -> printfn $"{nameof res1} is: {e}"

let printApplicatives () =
    let r1 = Ok 2
    let r2 = Ok 3 // Error "fail!"
    let r3 = Ok 4

    run r1 r2 r3
    run r1 (Error "failure!") r3
```

Si es un autor de la biblioteca que expone CEs en su biblioteca hoy, hay algunas consideraciones adicionales que debe tener en cuenta.

Esta característica implementa [F # RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).

## <a name="interfaces-can-be-implemented-at-different-generic-instantiations"></a>Las interfaces se pueden implementar en distintas instancias genéricas

Ahora puede implementar la misma interfaz en distintas instancias genéricas:

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

Esta característica implementa [F # RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).

## <a name="default-interface-member-consumption"></a>Consumo de miembro de interfaz predeterminado

F # 5 le permite consumir [interfaces con implementaciones predeterminadas](../../csharp/tutorials/default-interface-methods-versions.md).

Considere una interfaz definida en C# similar a la siguiente:

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

Puede consumirlo en F # a través de cualquiera de los métodos estándar de implementación de una interfaz:

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

Esto le permite aprovechar de forma segura el código C# y los componentes .NET escritos en C# moderno cuando esperan que los usuarios puedan usar una implementación predeterminada.

Esta característica implementa [F # RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).

## <a name="simplified-interop-with-nullable-value-types"></a>Interoperabilidad simplificada con tipos de valor que aceptan valores NULL

F # es compatible con los [tipos que aceptan valores NULL (valores)](/dotnet/api/system.nullable-1) (denominados tradicionalmente tipos que aceptan valores NULL), pero la interacción con ellos ha sido tradicionalmente algo de un problema, ya que tendría que crear un `Nullable` `Nullable<SomeType>` contenedor o cada vez que desease pasar un valor. Ahora, el compilador convertirá implícitamente un tipo de valor en `Nullable<ThatValueType>` si el tipo de destino coincide. Ahora es posible el siguiente código:

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

Esta característica implementa [F # RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).

## <a name="preview-reverse-indexes"></a>Vista previa: índices inversos

F # 5 también presenta una vista previa para permitir índices inversos. La sintaxis es `^idx`. A continuación se muestra cómo puede obtener un valor de elemento 1 desde el final de una lista:

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

También puede definir índices inversos para sus propios tipos. Para ello, debe implementar el método siguiente:

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

Este es un ejemplo del `Span<'T>` tipo:

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
    printfn $"{arr}"

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

Esta característica implementa [F # RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a>Versión preliminar: sobrecargas de palabras clave personalizadas en expresiones de cálculo

Las expresiones de cálculo son una característica eficaz para los autores de bibliotecas y marcos. Permiten mejorar considerablemente la expresividad de los componentes permitiéndole definir miembros conocidos y formar un DSL para el dominio en el que está trabajando.

F # 5 agrega compatibilidad de vista previa para sobrecargar las operaciones personalizadas en expresiones de cálculo. Permite escribir y consumir el siguiente código:

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

Antes de este cambio, podría escribir el `InputBuilder` tipo tal como está, pero no podía usarlo de la forma en que se utiliza en el ejemplo. Como las sobrecargas, los parámetros opcionales y los `System.ParamArray` tipos Now están permitidos, todo funciona de la forma esperada.

Esta característica implementa [F # RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).
