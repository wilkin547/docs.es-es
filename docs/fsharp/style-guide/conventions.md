---
title: Convenciones de código de F#
description: 'Aprenda instrucciones generales y expresiones al escribir código de F #.'
ms.date: 01/5/2021
ms.openlocfilehash: e69ceb2f3c37404ca8d8ed972f985340e62ecb59
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938694"
---
# <a name="f-coding-conventions"></a>Convenciones de código de F#

Las siguientes convenciones se formulan a partir de experiencias que trabajan con códigos base de F # de gran tamaño. Los [cinco principios de buen código de F #](index.md#five-principles-of-good-f-code) son la base de cada recomendación. Están relacionados con las [instrucciones de diseño del componente de f #](component-design-guidelines.md), pero son aplicables a cualquier código de f #, no solo a los componentes como las bibliotecas.

## <a name="organizing-code"></a>Organizar código

F # presenta dos maneras principales de organizar el código: los módulos y los espacios de nombres. Son similares, pero tienen las siguientes diferencias:

* Los espacios de nombres se compilan como espacios de nombres .NET. Los módulos se compilan como clases estáticas.
* Los espacios de nombres siempre son de nivel superior. Los módulos pueden ser de nivel superior y estar anidados dentro de otros módulos.
* Los espacios de nombres pueden abarcar varios archivos. Los módulos no pueden.
* Los módulos se pueden decorar con `[<RequireQualifiedAccess>]` y `[<AutoOpen>]` .

Las instrucciones siguientes le ayudarán a usarlos para organizar el código.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferir espacios de nombres en el nivel superior

En el caso de cualquier código consumible públicamente, los espacios de nombres son preferentes para los módulos en el nivel superior. Dado que se compilan como espacios de nombres .NET, se pueden consumir desde C# sin ningún problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

El uso de un módulo de nivel superior no puede aparecer de forma diferente cuando se llama solo desde F #, pero para los consumidores de C#, es posible que los autores de llamadas se sorprendan al tener que calificar `MyClass` con el `MyCode` módulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Aplicar cuidadosamente `[<AutoOpen>]`

La `[<AutoOpen>]` construcción puede contaminar el ámbito de lo que está disponible para los autores de llamadas y la respuesta a la que procede algo de es "Magic". Esto no es una buena cosa. Una excepción a esta regla es la propia biblioteca básica de F # (aunque este hecho también es un poco polémico).

Sin embargo, es una comodidad si tiene una funcionalidad auxiliar para una API pública que desea organizar por separado de esa API pública.

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

Esto le permite separar claramente los detalles de implementación de la API pública de una función sin tener que calificar totalmente una aplicación auxiliar cada vez que la llame.

Además, exponer los métodos de extensión y los generadores de expresiones en el nivel de espacio de nombres se puede expresar perfectamente con `[<AutoOpen>]` .

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Usar `[<RequireQualifiedAccess>]` siempre que los nombres puedan entrar en conflicto o se sienta útil para mejorar la legibilidad

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren un acceso calificado explícito. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto resulta útil cuando las funciones y los valores del módulo tienen nombres que es probable que entren en conflicto con los nombres de otros módulos. Requerir acceso cualificado puede aumentar considerablemente el mantenimiento a largo plazo y la evolución de una biblioteca.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordenar `open` instrucciones topológicamente

En F #, el orden de las declaraciones es importante, incluidas las `open` instrucciones with. Esto es a diferencia de C#, donde el efecto de `using` y `using static` es independiente del orden de esas instrucciones en un archivo.

En F #, los elementos abiertos en un ámbito pueden prevalecer sobre otros. Esto significa que la reordenación `open` de las instrucciones podría modificar el significado del código. Como resultado, no se recomienda ninguna ordenación arbitraria de todas las `open` instrucciones (por ejemplo, alfanuméricamente), consulta generar un comportamiento diferente que podría esperar.

En su lugar, se recomienda ordenarlas [topológicamente](https://en.wikipedia.org/wiki/Topological_sorting); es decir, ordene las `open` instrucciones en el orden en el que se definen las _capas_ del sistema. También se puede tener en cuenta la ordenación alfanumérica en diferentes capas topológicas.

Por ejemplo, esta es la Ordenación topológica del archivo de API pública del servicio del compilador de F #:

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open FSharp.Compiler
open FSharp.Compiler.AbstractIL
open FSharp.Compiler.AbstractIL.Diagnostics
open FSharp.Compiler.AbstractIL.IL
open FSharp.Compiler.AbstractIL.ILBinaryReader
open FSharp.Compiler.AbstractIL.Internal
open FSharp.Compiler.AbstractIL.Internal.Library

open FSharp.Compiler.AccessibilityLogic
open FSharp.Compiler.Ast
open FSharp.Compiler.CompileOps
open FSharp.Compiler.CompileOptions
open FSharp.Compiler.Driver

open Internal.Utilities
open Internal.Utilities.Collections
```

Tenga en cuenta que un salto de línea separa las capas topológicas, y cada capa se ordena de forma alfanumérica después. Esto organiza correctamente el código sin sombrear los valores accidentalmente.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Usar clases para contener valores que tengan efectos secundarios

Hay muchas ocasiones en las que la inicialización de un valor puede tener efectos secundarios, como la creación de instancias de un contexto en una base de datos u otro recurso remoto. Es tentador inicializar estos elementos en un módulo y usarlo en las funciones siguientes:

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/<name>/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

Esta suele ser una mala idea por varias razones:

En primer lugar, la configuración de la aplicación se inserta en el código base con `dep1` y `dep2` . Esto es difícil de mantener en códigos base mayores.

En segundo lugar, los datos inicializados de forma estática no deben incluir valores que no sean seguros para subprocesos si el componente utilizará varios subprocesos. Esto es claramente infringido por `dep3` .

Por último, la inicialización del módulo se compila en un constructor estático para toda la unidad de compilación. Si se produce algún error en la inicialización de los valores enlazados en ese módulo, se manifiesta como un `TypeInitializationException` que se almacena en caché para toda la duración de la aplicación. Esto puede ser difícil de diagnosticar. Normalmente, hay una excepción interna que se puede tratar de explicar, pero si no lo está, no hay que indicar cuál es la causa raíz.

En su lugar, use simplemente una clase simple para almacenar las dependencias:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Esto permite lo siguiente:

1. Inserción de cualquier estado dependiente fuera de la propia API.
2. La configuración ahora se puede realizar fuera de la API.
3. No es probable que los errores de inicialización de los valores dependientes se manifiesten como `TypeInitializationException` .
4. La API es ahora más fácil de probar.

## <a name="error-management"></a>Administración de errores

La administración de errores en grandes sistemas es un esfuerzo complejo y con matices, y no hay ninguna viñeta Silver para asegurarse de que los sistemas son tolerantes a errores y se comportan correctamente. Las siguientes directrices deben proporcionar orientación para navegar por este espacio difícil.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Representar casos de error y estado no válido en tipos intrínsecos de su dominio

Con las [uniones discriminadas](../language-reference/discriminated-unions.md), F # ofrece la capacidad de representar el estado de un programa defectuoso en el sistema de tipos. Por ejemplo:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

En este caso, se puede producir un error en las tres formas conocidas de retirar dinero de una cuenta bancaria. Cada caso de error se representa en el tipo y, por tanto, se puede tratar con seguridad en todo el programa.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn $"Successfully withdrew %f{am}"
    | InsufficientFunds balance -> printfn $"Failed: balance is %f{balance}"
    | CardExpired expiredDate -> printfn $"Failed: card expired on {expiredDate}"
    | UndisclosedFailure -> printfn "Failed: unknown"
```

En general, si puede modelar las distintas formas en que se puede **producir un error** en el dominio, el código de control de errores ya no se trata como algo que debe abordar además del flujo normal del programa. Es simplemente parte del flujo normal del programa y no se considera **excepcional**. Esto tiene dos ventajas principales:

1. Es más fácil de mantener a medida que su dominio cambia con el tiempo.
2. Los casos de error son más fáciles de probar unitarias.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Usar excepciones cuando los errores no se pueden representar con tipos

No todos los errores se pueden representar en un dominio problemático. Estos tipos de errores son *excepcionales* por naturaleza; por lo tanto, la capacidad de generar y detectar excepciones en F #.

En primer lugar, se recomienda leer las [instrucciones de diseño de excepciones](../../standard/design-guidelines/exceptions.md). También se aplican a F #.

Las construcciones principales disponibles en F # con el fin de generar excepciones se deben considerar en el orden de preferencia siguiente:

| Función | Sintaxis | Propósito |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera una `System.ArgumentNullException` con el nombre de argumento especificado. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera una `System.ArgumentException` con el nombre de argumento y el mensaje especificados. |
| `invalidOp` | `invalidOp "message"` | Genera una `System.InvalidOperationException` con el mensaje especificado. |
|`raise`| `raise (ExceptionType("message"))` | Mecanismo de uso general para producir excepciones. |
| `failwith` | `failwith "message"` | Genera una `System.Exception` con el mensaje especificado. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera una `System.Exception` con un mensaje determinado por la cadena de formato y sus entradas. |

Use `nullArg` `invalidArg` y `invalidOp` como el mecanismo que se va a iniciar `ArgumentNullException` `ArgumentException` y `InvalidOperationException` cuando corresponda.

`failwith` `failwithf` Por lo general, las funciones y deben evitarse porque generan el `Exception` tipo base, no una excepción concreta. En función de las [instrucciones de diseño de excepciones](../../standard/design-guidelines/exceptions.md), desea producir excepciones más específicas cuando sea posible.

### <a name="use-exception-handling-syntax"></a>Usar sintaxis de control de excepciones

F # admite patrones de excepción a través de la `try...with` Sintaxis:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

La reconciliación de la funcionalidad para realizar en el caso de una excepción con la coincidencia de patrones puede ser un poco complicada si desea mantener el código limpio. Una manera de controlar esto es usar [patrones activos](../language-reference/active-patterns.md) como medio para agrupar la funcionalidad en torno a un caso de error con una excepción. Por ejemplo, puede que esté consumiendo una API que, cuando se produce una excepción, incluye información valiosa en los metadatos de la excepción. Desencapsular un valor útil en el cuerpo de la excepción capturada dentro del modelo activo y devolver ese valor puede ser útil en algunas situaciones.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>No usar el control de errores Monad para reemplazar excepciones

A menudo, las excepciones se ven como Taboo en la programación funcional. De hecho, las excepciones infringen la pureza, por lo que es seguro considerarlas que no son bastante funcionales. Sin embargo, esto omite la realidad de dónde se debe ejecutar el código y que se pueden producir errores en tiempo de ejecución. En general, escriba código en el supuesto de que la mayoría de las cosas no son puras ni totales, con el fin de minimizar las sorpresas desagradables.

Es importante tener en cuenta los siguientes aspectos principales y aspectos de las excepciones con respecto a su relevancia y adecuadaidad en el entorno de tiempo de ejecución .NET y el ecosistema multilingüe:

1. Contienen información de diagnóstico detallada, que es muy útil al depurar un problema.
2. Son perfectamente entendidos por el tiempo de ejecución y otros lenguajes de .NET.
3. Pueden reducir el REUTILIZADOR significativo cuando se comparan con el código que sale de su forma de *evitar* excepciones mediante la implementación de un subconjunto de su semántica de manera ad hoc.

Este tercer punto es crítico. En el caso de las operaciones complejas no triviales, el uso de excepciones puede tener como resultado la gestión de estructuras como esta:

```fsharp
Result<Result<MyType, string>, string list>
```

Que puede conducir fácilmente a un código frágil, como la coincidencia de patrones en errores "con tipo de cadena":

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Además, puede ser tentador admitir cualquier excepción en el deseo de una función "simple" que devuelva un tipo "agradable":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Desgraciadamente, `tryReadAllText` puede producir numerosas excepciones basadas en la infinidad de cosas que pueden producirse en un sistema de archivos, y este código descarta cualquier información sobre lo que podría estar realmente mal en su entorno. Si reemplaza este código por un tipo de resultado, volverá al análisis de mensajes de error "con tipo de cadena":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

Y colocar el propio objeto de excepción en el `Error` constructor simplemente obliga a tratar correctamente el tipo de excepción en el sitio de llamada en lugar de en la función. De este modo, se crean excepciones comprobadas, que son muy unfuns de tratar como llamador de una API.

Una buena alternativa a los ejemplos anteriores es detectar excepciones *específicas* y devolver un valor significativo en el contexto de esa excepción. Si modifica la función de la `tryReadAllText` manera siguiente, `None` tiene un significado más:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

En lugar de funcionar como una instrucción catch-all, esta función controlará correctamente el caso cuando no se encuentre un archivo y lo asigne a una devolución. Este valor devuelto se puede asignar a ese caso de error, sin descartar ninguna información contextual ni obligar a los autores de llamadas a tratar con un caso que puede no ser relevante en ese punto del código.

Los tipos como `Result<'Success, 'Error>` son adecuados para las operaciones básicas en las que no están anidados y los tipos opcionales de F # son perfectos para representar cuando algo puede devolver *algo* o *nada*. Sin embargo, no sustituyen a las excepciones y no se deben usar en un intento de reemplazar excepciones. En su lugar, deben aplicarse prudentemente para abordar aspectos específicos de la Directiva de administración de errores y excepciones de manera dirigida.

## <a name="partial-application-and-point-free-programming"></a>Aplicación parcial y programación sin punto

F # admite aplicaciones parciales y, por tanto, varias maneras de programar en un estilo sin punto. Esto puede ser beneficioso para la reutilización de código dentro de un módulo o la implementación de algo, pero no es algo que exponer públicamente. En general, la programación sin puntos no es un marco de sí mismo y puede Agregar una barrera cognitiva significativa para personas que no están sumergidas en el estilo.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>No use la aplicación parcial y currificación en las API públicas

Con poca excepción, el uso de una aplicación parcial en las API públicas puede resultar confuso para los consumidores. Normalmente, `let` los valores enlazados en el código de F # son **valores**, no **valores de función**. La combinación de valores y valores de función puede dar lugar a que se guarde un pequeño número de líneas de código en Exchange para un poco de sobrecarga cognitiva, especialmente si se combina con operadores como `>>` para crear funciones.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Tenga en cuenta las implicaciones de las herramientas para la programación sin puntos

Las funciones currificadas no etiquetan sus argumentos. Esto tiene implicaciones para las herramientas. Tenga en cuenta las dos funciones siguientes:

```fsharp
let func name age =
    printfn $"My name is {name} and I am %d{age} years old!"

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Ambos son funciones válidas, pero `funcWithApplication` es una función currificada. Al mantener el mouse sobre sus tipos en un editor, verá lo siguiente:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

En el sitio de la llamada, la información sobre herramientas en herramientas como Visual Studio le proporcionará la firma de tipo, pero como no hay ningún nombre definido, no se mostrarán los nombres. Los nombres son esenciales para un buen diseño de API porque ayudan a los autores de llamadas a comprender mejor el significado de la API. El uso de código sin punto en la API pública puede dificultar la comprensión de los llamadores.

Si se encuentra con código sin punto, como el `funcWithApplication` que se puede utilizar públicamente, se recomienda realizar una expansión η completa para que las herramientas puedan recoger los nombres descriptivos de los argumentos.

Además, el código sin punto de depuración puede ser desafiante, si no imposible. Las herramientas de depuración se basan en valores enlazados a nombres (por ejemplo, `let` enlaces) para que pueda inspeccionar valores intermedios a mitad de la ejecución. Cuando el código no tiene valores para inspeccionar, no hay nada que depurar. En el futuro, es posible que las herramientas de depuración evolucionen para sintetizar estos valores en función de las rutas de acceso ejecutadas anteriormente, pero no es una buena idea repartir sus *posibilidades* de depuración.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Considere la aplicación parcial como una técnica para reducir el uso del texto interno.

A diferencia del punto anterior, la aplicación parcial es una herramienta maravillosa para reducir el contenido Reutilizable dentro de una aplicación o los aspectos internos más profundos de una API. Puede ser útil para las pruebas unitarias de la implementación de API más complicadas, donde reutilizable suele ser un problema. Por ejemplo, en el código siguiente se muestra cómo puede realizar lo que la mayoría de los marcos ficticios le proporciona sin tomar una dependencia externa de este marco de trabajo y tener que aprender una API relacionada relacionada.

Por ejemplo, considere la siguiente topografía de la solución:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` podría exponer código como:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Las pruebas unitarias `Transactions.doTransaction` en `ImplementationLogic.Tests.fsproj` son fáciles:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Aplicar parcialmente `doTransaction` con un objeto de contexto ficticio le permite llamar a la función en todas las pruebas unitarias sin necesidad de crear un contexto ficticio cada vez:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Esta técnica no se debe aplicar universalmente a toda la base de código, pero es una buena forma de reducir los elementos reutilizables para las pruebas unitarias e internas complicadas.

## <a name="access-control"></a>Control de acceso

F # tiene varias opciones para el [control de acceso](../language-reference/access-control.md), que se heredan de lo que está disponible en el tiempo de ejecución de .net. No solo se pueden usar para los tipos. también puede utilizarlos para funciones.

* Prefiere `public` los tipos y miembros que no sean de tipo y hasta que los necesite para que los consuma públicamente. Esto también minimiza lo que los consumidores acoplan a.
* Procure mantener toda la funcionalidad de la aplicación auxiliar `private` .
* Considere el uso de `[<AutoOpen>]` en un módulo privado de funciones auxiliares si son numerosas.

## <a name="type-inference-and-generics"></a>Inferencia de tipos y genéricos

La inferencia de tipos puede ahorrarle escribir una gran cantidad de texto reutilizable. Y la generalización automática en el compilador de F # pueden ayudarle a escribir código más genérico sin ningún esfuerzo adicional por su parte. Sin embargo, estas características no son universalmente buenas.

* Considere la posibilidad de etiquetar nombres de argumento con tipos explícitos en las API públicas y no confíe en la inferencia de tipos para este.

    El **motivo es que debería tener** el control de la forma de la API, no del compilador. Aunque el compilador puede realizar un trabajo adecuado en la inferencia de tipos automáticamente, es posible que la forma de la API cambie si el interno en el que se basa ha cambiado de tipo. Esto puede ser lo que desea, pero es muy probable que se produzca un cambio de API importante que los consumidores de nivel inferior tendrán que tratar. En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios importantes. En términos de DDD, esto puede considerarse como una capa contra daños.

* Considere la posibilidad de asignar un nombre descriptivo a los argumentos genéricos.

    A menos que esté escribiendo código realmente genérico que no sea específico de un dominio determinado, un nombre descriptivo puede ayudar a otros programadores a entender el dominio en el que están trabajando. Por ejemplo, un parámetro de tipo denominado `'Document` en el contexto de interactuar con una base de datos de documento hace que sea más claro que la función o el miembro con el que está trabajando puede aceptar los tipos de documentos genéricos.

* Considere la posibilidad de asignar nombres a los parámetros de tipo genérico con PascalCase.

    Esta es la manera general de hacer cosas en .NET, por lo que se recomienda que use PascalCase en lugar de snake_case o camelCase.

Por último, la generalización automática no siempre es una gran ventaja para las personas que no están familiarizadas con F # o con un código base grande. El uso de componentes que son genéricos es una sobrecarga cognitiva. Además, si las funciones generalizadas automáticamente no se usan con distintos tipos de entrada (por sí solo si están pensadas para usarse como tal), no hay ninguna ventaja real de que sean genéricas en ese momento. Considere siempre si el código que está escribiendo se beneficiará de ser genérico.

## <a name="performance"></a>Rendimiento

### <a name="consider-structs-for-small-types-with-high-allocation-rates"></a>Considere Structs para tipos pequeños con tasas de asignación elevadas.

El uso de Structs (también denominados tipos de valor) puede dar lugar a un mayor rendimiento en el código, ya que normalmente evita la asignación de objetos. Sin embargo, los Structs no siempre son un botón "ir más rápido": Si el tamaño de los datos de una estructura supera los 16 bytes, la copia de los datos a menudo puede producir más tiempo de CPU que el uso de un tipo de referencia.

Para determinar si debe usar un struct, tenga en cuenta las siguientes condiciones:

- Si el tamaño de los datos es de 16 bytes o menos.
- Si es probable que tenga muchas instancias de estos tipos residentes en memoria en un programa en ejecución.

Si se aplica la primera condición, generalmente debería usar un struct. Si ambos se aplican, casi siempre debe usar un struct. Puede haber algunos casos en los que se apliquen las condiciones anteriores, pero el uso de una estructura no es mejor o peor que el uso de un tipo de referencia, pero es probable que no sean habituales. Es importante medir siempre cuando se realizan cambios como este, sin embargo, y no funcionan en supuestos o Intuition.

#### <a name="consider-struct-tuples-when-grouping-small-value-types-with-high-allocation-rates"></a>Considerar tuplas de struct al agrupar tipos de valores pequeños con tasas de asignación elevadas

Tenga en cuenta las dos funciones siguientes:

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

Cuando realice una prueba comparativa de estas funciones con una herramienta estadística de pruebas comparativas como [BenchmarkDotNet](https://benchmarkdotnet.org/), verá que la `runWithStructTuple` función que usa las tuplas de struct se ejecuta un 40% más rápido y no asigna memoria.

Sin embargo, estos resultados no siempre serán el caso en su propio código. Si marca una función como `inline` , el código que usa tuplas de referencia puede obtener algunas optimizaciones adicionales, o el código que asignaría podría simplemente estar optimizado. Siempre debe medir los resultados siempre que el rendimiento esté relacionado y nunca funcione en función de supuestos o Intuition.

#### <a name="consider-struct-records-when-the-type-is-small-and-has-high-allocation-rates"></a>Considerar los registros de struct cuando el tipo es pequeño y tiene tasas de asignación elevadas

La regla de Thumb descrita anteriormente también contiene los [tipos de registro de F #](../language-reference/records.md). Tenga en cuenta los siguientes tipos de datos y funciones que los procesan:

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

Esto es similar al código de tupla anterior, pero esta vez el ejemplo usa registros y una función interna insertada.

Al realizar una prueba comparativa de estas funciones con una herramienta estadística de pruebas comparativas como [BenchmarkDotNet](https://benchmarkdotnet.org/), observará que `processStructPoint` se ejecuta casi un 60% más rápido y asigna nada en el montón administrado.

#### <a name="consider-struct-discriminated-unions-when-the-data-type-is-small-with-high-allocation-rates"></a>Considere uniones discriminadas de struct cuando el tipo de datos sea pequeño con tasas de asignación elevadas.

Las observaciones anteriores sobre el rendimiento con tuplas y registros de struct también contienen [uniones discriminadas de F #](../language-reference/discriminated-unions.md). Tenga en cuenta el código siguiente:

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

Es habitual definir uniones discriminadas de un solo caso como esta para el modelado de dominios. Cuando realice pruebas comparativas de estas funciones con una herramienta estadística comparativa como [BenchmarkDotNet](https://benchmarkdotnet.org/), encontrará que `structReverseName` se ejecuta aproximadamente un 25% más rápido que `reverseName` para cadenas pequeñas. En el caso de las cadenas grandes, ambos realizan aproximadamente el mismo. Por lo tanto, en este caso, siempre es preferible usar un struct. Como se mencionó anteriormente, mida siempre y no opere en suposiciones o Intuition.

Aunque en el ejemplo anterior se mostró que una Unión discriminada de struct produjeron un mejor rendimiento, es habitual tener uniones discriminadas más grandes al modelar un dominio. Los tipos de datos de mayor tamaño, como, pueden no funcionar también si son Structs en función de las operaciones que contengan, ya que pueden estar implicados más copias.

### <a name="functional-programming-and-mutation"></a>Programación funcional y mutación

Los valores de F # son inmutables de forma predeterminada, lo que permite evitar ciertas clases de errores (especialmente los que implican la simultaneidad y el paralelismo). Sin embargo, en algunos casos, para lograr una eficiencia óptima (o incluso razonable) de tiempo de ejecución o asignaciones de memoria, es posible que se pueda implementar un intervalo de trabajo mediante la mutación en contexto del estado. Esto es posible en función de la inclusión de F # con la `mutable` palabra clave.

El uso de `mutable` en F # puede sentirse en probabilidades de la pureza funcional. Esto es comprensible, pero la pureza funcional en todo el mundo puede ser probable con objetivos de rendimiento. Un compromiso es encapsular la mutación de modo que los llamadores no tengan que preocuparse de lo que sucede cuando llaman a una función. Esto le permite escribir una interfaz funcional sobre una implementación basada en mutación para el código crítico para el rendimiento.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Ajuste del código mutable en interfaces inmutables

Con la transparencia referencial como objetivo, es fundamental escribir código que no exponga la subclave mutable de las funciones críticas para el rendimiento. Por ejemplo, el código siguiente implementa la `Array.contains` función en la biblioteca básica de F #:

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

Si se llama a esta función varias veces, no se cambia la matriz subyacente, ni se requiere que se mantenga ningún estado mutable en su consumo. Es referencialmente transparente, aunque casi todas las líneas de código dentro de él utilicen mutación.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considere la posibilidad de encapsular datos mutables en clases

En el ejemplo anterior se usaba una sola función para encapsular operaciones mediante datos mutables. Esto no siempre es suficiente para conjuntos de datos más complejos. Tenga en cuenta los siguientes conjuntos de funciones:

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

Este código tiene un rendimiento, pero expone la estructura de datos basada en mutación que los llamadores son responsables de mantener. Esto puede ajustarse dentro de una clase sin miembros subyacentes que puedan cambiar:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` encapsula la estructura de datos basada en mutación subyacente, de modo que no obliga a los llamadores a mantener la estructura de datos subyacente. Las clases son una manera eficaz de encapsular datos y rutinas que se basan en la mutación sin exponer los detalles a los llamadores.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Prefiere `let mutable` a las celdas de referencia

Las celdas de referencia son una manera de representar la referencia a un valor en lugar del propio valor. Aunque se pueden usar para el código crítico para el rendimiento, no se recomiendan. Considere el ejemplo siguiente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

El uso de una celda de referencia ahora "contamina" todo el código subsiguiente con tener que desreferenciar y volver a hacer referencia a los datos subyacentes. En su lugar, tenga en cuenta lo `let mutable` siguiente:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Aparte del punto único de mutación en el medio de la expresión lambda, el resto del código que toca `acc` puede hacerlo de una manera diferente al uso de un `let` valor inmutable enlazado normal. Esto hará que sea más fácil cambiar con el tiempo.

## <a name="object-programming"></a>Programación de objetos

F # es totalmente compatible con los objetos y los conceptos orientados a objetos (OO). Aunque muchos conceptos de OO son eficaces y útiles, no todos ellos son ideales para su uso. En las listas siguientes se ofrecen instrucciones sobre las categorías de características de OO en un nivel alto.

**Considere la posibilidad de usar estas características en muchas situaciones:**

* Notación de puntos ( `x.Length` )
* Miembros de instancia
* Constructores implícitos
* Miembros estáticos
* Notación de indexador ( `arr.[x]` )
* Argumentos opcionales y con nombre
* Interfaces e implementaciones de interfaz

**No se debe llegar a estas características en primer lugar, pero se aplican de forma prudente cuando sea conveniente solucionar un problema:**

* Sobrecarga de métodos
* Datos mutables encapsulados
* Operadores en tipos
* Propiedades automáticas
* Implementación `IDisposable` de y `IEnumerable`
* Extensiones de tipo
* Eventos
* Estructuras
* Delegados
* Enumeraciones

**Normalmente, evite estas características a menos que deba utilizarlas:**

* Jerarquías de tipos basados en herencia y herencia de implementación
* Valores NULL y `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferir composición sobre herencia

La [composición sobre la herencia](https://en.wikipedia.org/wiki/Composition_over_inheritance) es una expresión de larga duración que puede cumplir el código de F #. El principio fundamental es que no se debe exponer una clase base y forzar que los llamadores hereden de esa clase base para obtener la funcionalidad.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usar expresiones de objeto para implementar interfaces si no se necesita una clase

Las [expresiones de objeto](../language-reference/object-expressions.md) permiten implementar interfaces sobre la marcha, enlazando la interfaz implementada a un valor sin necesidad de hacerlo dentro de una clase. Esto resulta cómodo, especialmente si _solo_ necesita implementar la interfaz y no necesita una clase completa.

Por ejemplo, este es el código que se ejecuta en [Ionide](https://ionide.io/) para proporcionar una acción de corrección de código si ha agregado un símbolo para el que no tiene una `open` instrucción:

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

Dado que no hay necesidad de una clase al interactuar con la API de Visual Studio Code, las expresiones de objeto son una herramienta ideal para esto. También son útiles para las pruebas unitarias, cuando se desea realizar un código auxiliar de una interfaz con rutinas de prueba de forma ad hoc.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Considere las abreviaturas de tipo para acortar las firmas

Las [abreviaturas de tipo](../language-reference/type-abbreviations.md) son una manera cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo. Por ejemplo, el alias siguiente asigna una etiqueta a lo que se necesita para definir un cálculo con [CNTK](/cognitive-toolkit/), una biblioteca de aprendizaje profundo:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

El `Computation` nombre es una manera cómoda de indicar cualquier función que coincida con la firma a la que se asignan alias. El uso de abreviaturas de tipo como esta es cómodo y permite el código más conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evite el uso de abreviaturas de tipo para representar su dominio

Aunque las abreviaturas de tipo son convenientes para asignar un nombre a las firmas de función, pueden resultar confusos al abreviar otros tipos. Tenga en cuenta esta abreviatura:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Esto puede resultar confuso de varias maneras:

* `BufferSize` no es una abstracción; es simplemente otro nombre para un entero.
* Si `BufferSize` se expone en una API pública, se puede malinterpretar fácilmente que significa algo más que simplemente `int` . Por lo general, los tipos de dominio tienen varios atributos y no son tipos primitivos como `int` . Esta abreviatura infringe esa hipótesis.
* El uso de mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.
* Este alias no ofrece mayor claridad en comparación con proporcionar un argumento con nombre a una función.
* La abreviatura no emitirá un manifiesto en IL compilado; es simplemente un entero y este alias es una construcción en tiempo de compilación.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

En Resumen, el inconveniente de las abreviaturas de tipo es que **no** son abstracciones sobre los tipos que se van a abreviar. En el ejemplo anterior, `BufferSize` se trata simplemente de una parte `int` inferior, sin datos adicionales ni de las ventajas del sistema de tipos, además de lo que `int` ya tiene.

Un enfoque alternativo al uso de las abreviaturas de tipo para representar un dominio es utilizar uniones discriminadas de un solo caso. El ejemplo anterior se puede modelar como sigue:

```fsharp
type BufferSize = BufferSize of int
```

Si escribe código que funciona en términos de `BufferSize` y su valor subyacente, debe construir uno en lugar de pasarlo en cualquier entero arbitrario:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

Esto reduce la probabilidad de pasar erróneamente un entero arbitrario a la `send` función, ya que el llamador debe construir un `BufferSize` tipo para encapsular un valor antes de llamar a la función.
