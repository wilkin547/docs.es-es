---
title: 'Convenciones de código de F #'
description: 'Obtenga información sobre expresiones y directrices generales al escribir código de F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 21119b6d69e00f359104bfb6eab7681bdbfb8d78
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087393"
---
# <a name="f-coding-conventions"></a>Convenciones de código de F #

Las siguientes convenciones Formula de la experiencia de trabajar con F # grandes bases de datos. El [cinco principios del buen código de F #](index.md#five-principles-of-good-f-code) constituyen el fundamento de cada recomendación. Están relacionadas con la [instrucciones de diseño del componente de F #](component-design-guidelines.md), pero son aplicables a cualquier código de F #, no solo los componentes, como las bibliotecas.

## <a name="organizing-code"></a>Organización del código

Dos métodos principales para organizar el código de características de F #: módulos y espacios de nombres. Estas son similares, pero tienen las siguientes diferencias:

* Los espacios de nombres se compilan como espacios de nombres. NET. Los módulos se compilan como las clases estáticas.
* Espacios de nombres siempre son de nivel superior. Pueden ser módulos anidados dentro de otros módulos y de nivel superior.
* Los espacios de nombres pueden abarcar varios archivos. No de los módulos.
* Los módulos se pueden decorar con `[<RequireQualifiedAccess>]` y `[<AutoOpen>]`.

Las siguientes directrices le ayudará a utilizar para organizar el código.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferir espacios de nombres en el nivel superior

Para cualquier código públicamente, espacios de nombres son preferenciales a los módulos en el nivel superior. Dado que se compilan como espacios de nombres. NET, son consumibles desde C# con ningún problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Uso de un módulo de nivel superior no puede aparecer diferente cuando se llama solo desde F #, pero para los consumidores de C#, los llamadores pueden sorprenderse de tener que calificar `MyClass` con el `MyCode` módulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Aplicar con cuidado `[<AutoOpen>]`

El `[<AutoOpen>]` construcción puede contamina el ámbito de lo que está disponible para los llamadores y la respuesta a algo procedencia es "mágica". Por lo general esto no es algo bueno. Una excepción a esta regla es la biblioteca básica de F # propio (aunque este hecho también es algo controvertido).

Sin embargo, es una ventaja si dispone de funcionalidad auxiliar para una API pública que desea organizar por separado desde esa API pública.

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

Esto permite detalles más limpia de implementación independiente desde la API pública de una función sin tener que calificar completamente una aplicación auxiliar de cada vez que lo llama.

Además, expone los métodos de extensión y los generadores de expresiones en el nivel de espacio de nombres puede perfectamente expresarse con `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Use `[<RequireQualifiedAccess>]` cada vez que podrían causar conflictos con nombres o cree ayuda a mejorar la legibilidad

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto es útil cuando las funciones y los valores del módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos. Necesidad de tener acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y la capacidad de evolución de una biblioteca.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordenación `open` instrucciones topológicamente

En F #, se importa el orden de las declaraciones, incluidos con `open` instrucciones. Esto es distinto de C#, donde el efecto de `using` y `using static` es independiente de la ordenación de esas instrucciones en un archivo.

En F #, elementos abiertos en un ámbito pueden verse ocultado por otros usuarios ya está presente. Esto significa que la reordenación `open` instrucciones podrían alterar el significado del código. Como resultado, cualquier arbitrario ordenar de todos los `open` instrucciones (por ejemplo, en orden alfanumérico) generalmente no se recomienda, para evitar que generar un comportamiento diferente que podría esperar.

En su lugar, se recomienda que se ordenen [topológicamente](https://en.wikipedia.org/wiki/Topological_sorting); es decir, ordenar su `open` instrucciones en el orden en que _capas_ del sistema se definen. También se puede considerar haciendo alfanumérica de ordenación en las capas de topológicas diferentes.

Por ejemplo, aquí está la ordenación topológica para el archivo F # del compilador servicio público API:

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

Tenga en cuenta que un salto de línea separa topológicas capas, cada capa que se ordena en orden alfanumérico posteriormente. Esto limpiamente organiza el código sin sombrear accidentalmente los valores.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Utilizar clases para contener los valores que tienen efectos secundarios

Hay muchas veces cuando la inicialización de un valor puede tener efectos secundarios, como crear una instancia de un contexto de una base de datos u otro recurso remoto. Es tentador inicializar estas cosas en un módulo y su uso en las funciones siguientes:

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

Esto suele ser una mala idea por diversas razones:

En primer lugar, se inserta la configuración de la aplicación en el código base con `dep1` y `dep2`. Esto es difícil de mantener en códigos base más grandes.

Los datos en segundo lugar, de manera estática no deben incluir los valores que no son seguros para subprocesos si el componente a usar varios subprocesos. Esto es claramente infringida por `dep3`.

Por último, inicialización del módulo se compila en un constructor estático para la unidad de compilación completo. Si se produce un error en la inicialización de un valor enlazado a let en ese módulo, se manifiesta como un `TypeInitializationException` que se almacena en caché para toda la duración de la aplicación. Esto puede ser difícil de diagnosticar. Normalmente es una excepción interna que puede intentar volver a analizar, pero si no existe, a continuación, no es lo que es la causa raíz.

En su lugar, use simplemente una clase simple para contener las dependencias:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Esto permite lo siguiente:

1. Inserción de cualquier estado dependiente fuera de la propia API.
2. Configuración ahora puede realizarse fuera de la API.
3. Errores de inicialización de los valores dependientes no están probable que manifiesta como un `TypeInitializationException`.
4. Ahora es más fácil probar la API.

## <a name="error-management"></a>Administración de errores

Administración de errores en sistemas grandes es una tarea muy compleja y matizada y no hay ningún silver viñetas en asegurar sus sistemas son tolerantes a errores y se comporten bien. Las siguientes directrices deben ofrecer instrucciones de navegar por este espacio difícil.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Representar los casos de error y el estado no válido en tipos intrínsecos a su dominio

Con [uniones discriminadas](../language-reference/discriminated-unions.md), F # proporciona la capacidad para representar el estado del programa defectuoso en el sistema de tipos. Por ejemplo:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

En este caso, hay tres maneras conocidos que puede producir un error al retirar dinero de una cuenta bancaria. Cada caso de error está representado en el tipo y, por tanto, se puede solucionar en forma segura en todo el programa.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

En general, si puede modelar las distintas formas que algo puede **producirá un error** en su dominio, a continuación, código de control de errores ya no se tratan como algo que debe tratar con además de flujo del programa normal. Es simplemente una parte del flujo normal del programa y no se considera **excepcionales**. Hay dos ventajas principales para esto:

1. Es más fácil de mantener a medida que cambia el dominio con el tiempo.
2. Casos de error son más fáciles de realizar una prueba unitaria.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Utilice excepciones cuando no se puede representar errores con tipos

No todos los errores se pueden representar en un dominio del problema. Estos tipos de errores son *excepcionales* por naturaleza, por lo tanto, la capacidad de generar y capturar excepciones en F #.

En primer lugar, se recomienda que lea el [directrices de diseño de la excepción](../../standard/design-guidelines/exceptions.md). También son aplicables a F #.

Deben tener en cuenta las construcciones principales disponibles en F # con el fin de generar excepciones en el siguiente orden de preferencia:

| Función | Sintaxis | Propósito |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera un `System.ArgumentNullException` con el nombre del argumento especificado. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nombre de argumento especificado y un mensaje. |
| `invalidOp` | `invalidOp "message"` | Genera un `System.InvalidOperationException` con el mensaje especificado. |
|`raise`| `raise (ExceptionType("message"))` | Mecanismo de uso general para generar excepciones. |
| `failwith` | `failwith "message"` | Genera un `System.Exception` con el mensaje especificado. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` con un mensaje determinado por la cadena de formato y sus entradas. |

Use `nullArg`, `invalidArg` y `invalidOp` como mecanismo para producir `ArgumentNullException`, `ArgumentException` y `InvalidOperationException` cuando sea apropiado.

El `failwith` y `failwithf` funciones por lo general deben evitarse porque genera la base de `Exception` escriba, no una excepción concreta. Tal como se indicó el [directrices de diseño de la excepción](../../standard/design-guidelines/exceptions.md), que desea producir excepciones más específicas cuando sea posible.

### <a name="using-exception-handling-syntax"></a>Mediante la sintaxis de control de excepciones

F # admite patrones de la excepción a través de la `try...with` sintaxis:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Reconciliar funcionalidad para realizar en el caso de una excepción con el patrón de coincidencia puede ser un poco complicado si desea mantener limpio el código. Una manera para controlar esto es usar [modelos activos](../language-reference/active-patterns.md) como un medio para la funcionalidad de grupo que rodea a un caso de error con una excepción propia. Por ejemplo, es posible que consume una API que, cuando produce una excepción, se incluye información valiosa en los metadatos de excepción. Un valor útil en el cuerpo de la excepción capturada dentro del modelo activo de la acción de desencapsular y devolver el que el valor puede ser útil en algunas situaciones.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>No use monádico tratamiento de errores para reemplazar las excepciones

Las excepciones se consideran un poco taboo en la programación funcional. De hecho, las excepciones infringen la pureza, por lo que es seguro tenerlos en cuenta no muy funcional. Sin embargo, esto pasa por alto la realidad de que el código debe ejecutarse y que pueden producirse errores en tiempo de ejecución. En general, puede escribir código en la suposición de que la mayoría de las cosas son puros ni total, para minimizar las sorpresas desagradables.

Es importante tener en cuenta los siguientes puntos fuertes y aspectos básicos de las excepciones con respecto a su relevancia y la adecuación en el tiempo de ejecución de .NET y el ecosistema de idiomas como un todo:

1. Contienen información de diagnóstico detallada que resulta muy útil al depurar un problema.
2. Están bien definidas por el tiempo de ejecución y otros lenguajes. NET.
3. Pueden reducir reutilizable significativa en comparación con el código que se sale del camino a *evitar* excepciones mediante la implementación de algún subconjunto de sus semánticas en forma ad-hoc.

Este tercer punto es fundamental. Las operaciones complejas no trivial, no se puede utilizar excepciones puede producir tratar con estructuras similar al siguiente:

```fsharp
Result<Result<MyType, string>, string list>
```

Lo que puede provocar fácilmente a código frágil, como "stringly escrito" errores de coincidencia de patrones:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Además, puede resultar tentador pasar cualquier excepción en la necesidad de una función "simple" que devuelve un tipo de "mejor":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Por desgracia, `tryReadAllText` puede producir numerosas excepciones según la infinidad de cosas que pueden ocurrir en un sistema de archivos, y este código ubicación descarta toda la información sobre lo que es posible que en realidad estar funcionando mal en su entorno. Si reemplaza este código con un tipo de resultado, va al analizar el mensaje "stringly escrito" error:

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

Y colocando el propio objeto de excepción en el `Error` constructor obliga a trabajar correctamente con el tipo de excepción en el sitio de llamada en lugar de en la función. Hacerlo de forma eficaz crea excepciones comprobadas, que son notoriamente unfun tratar como un llamador de una API.

Es una buena alternativa a los ejemplos anteriores detectar *específico* excepciones y devuelva un valor significativo en el contexto de esa excepción. Si modifica el `tryReadAllText` funcione como sigue, `None` tiene más sentido:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

En lugar de funcionar como un comodín, esta función ahora controlará correctamente el caso cuando no se encontró y asignar ese significado a una devolución de un archivo. Este valor devuelto puede asignar a ese caso de error, mientras no descarta cualquier información contextual o al exigir que los llamadores para tratar con un caso de que no puede ser importante en ese momento en el código.

Los tipos, como `Result<'Success, 'Error>` son adecuadas para las operaciones básicas donde no están anidados y tipos de F # opcionales son perfectos para representar cuando algo podría devolver *algo* o *nada*. Sin embargo, no son un reemplazo para las excepciones y no debe usarse en un intento de reemplazar las excepciones. En su lugar, se debe aplicar con prudencia a determinados aspectos de la dirección de excepción y la directiva de administración de errores de maneras de destino.

## <a name="partial-application-and-point-free-programming"></a>Aplicación parcial y libre de punto de programación

F # admite la aplicación parcial y, por lo tanto, las diversas formas al programa en un estilo libre de punto. Esto puede ser beneficioso para reutilizar el código dentro de un módulo o la implementación de algo, pero generalmente no es algo para exponer públicamente. En general, libre de punto de programación no es una virtud de por sí y puede agregar una barrera importante cognitiva para las personas que no se sumergen en el estilo.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>No use la aplicación parcial y currificación en las API públicas

Con pocas excepciones, el uso de la aplicación parcial en las API públicas puede resultar confuso para los consumidores. Por lo general, `let`-valores enlazados en el código de F # son **valores**, no **los valores de función**. Combinación de valores y los valores de función puede dar lugar al guardar un pequeño número de líneas de código a cambio de un poco de esfuerzo especial, especialmente si se combina con los operadores como `>>` para componer las funciones.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Tenga en cuenta las implicaciones de las herramientas para la programación punto libre

Funciones currificadas no etiquete sus argumentos. Esto tiene implicaciones de herramientas. Tenga en cuenta las dos funciones siguientes:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Ambas son funciones válidas, pero `funcWithApplication` es una función currificada. Cuando mantenga el mouse sobre sus tipos en un editor, verá lo siguiente:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

En el sitio de llamada, información sobre herramientas en herramientas como Visual Studio no le proporcionará información significativa para saber lo que el `string` y `int` realmente representan tipos de entrada.

Si encuentra libre de punto de código como `funcWithApplication` es públicamente, se recomienda hacer una expansión η completa para que las herramientas pueden ocupará de nombres descriptivos para los argumentos.

Además, depuración de código sin punto puede resultar complicado, si no imposible. Herramientas de depuración se basan en valores enlazados a los nombres (por ejemplo, `let` enlaces) para que puede inspeccionar la mitad de los valores intermedios a través de la ejecución. Cuando el código no tiene ningún valor para inspeccionar, no hay nada para depurar. En el futuro, las herramientas de depuración pueden evolucionar para sintetizar estos valores en función de las rutas de acceso ejecutadas anteriormente, pero no es una buena idea intentan contenerlos sus apuestas en *posibles* funcionalidad de depuración.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Considere la posibilidad de aplicación parcial como una técnica para reducir el texto modelo interno

A diferencia de lo anterior, aplicación parcial es una excelente herramienta para reducir el código reutilizable dentro de una aplicación o los aspectos internos de más de una API. Puede ser útil para la implementación de API más complicadas, donde reutilizable a menudo es complicado para tratar de pruebas unitarias. Por ejemplo, el código siguiente muestra cómo se puede realizar qué marcos de simulación más ofrecen sin tomar una dependencia externa en un marco y tener que aprender un relacionados personalizada API.

Por ejemplo, considere la topografía de solución siguientes:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` Por ejemplo, podría exponer el código:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Las pruebas unitarias `Transactions.doTransaction` en `ImplementationLogic.Tests.fspoj` es fácil:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Aplicar parcialmente `doTransaction` con un contexto de simulación objeto le permite llamar a la función en todas las pruebas unitarias sin necesidad de construir un contexto ficticio cada vez:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Esta técnica no se debe aplicar universalmente a la base de código completo, pero es una buena forma de reducir el código reutilizable para internals complicadas y los aspectos internos de pruebas unitarias.

## <a name="access-control"></a>Control de acceso

F # tiene varias opciones para [control de acceso](../language-reference/access-control.md), al heredar de lo que está disponible en el tiempo de ejecución. NET. Estos no son sólo puede usar para los tipos: se pueden usar para las funciones, demasiado.

* Prefiere que no sean de`public` tipos y miembros hasta que se tienen que ser públicamente. Esto minimiza también qué par de los consumidores a.
* Intente mantener toda la funcionalidad de aplicación auxiliar `private`.
* Considere el uso de `[<AutoOpen>]` en un módulo de funciones de aplicación auxiliar que dejen de estar numerosos privado.

## <a name="type-inference-and-generics"></a>Inferencia de tipos y tipos genéricos

Inferencia de tipos puede evitarle escribir mucho código reutilizable. Y generalización automática en el compilador de F # puede ayudarle a escribir código más genérico casi sin esfuerzo adicional por su parte. Sin embargo, estas características no son buenas universalmente.

* Considere la posibilidad de etiquetado de los nombres de argumento con los tipos explícitos en las API públicas y no confíe en la inferencia de tipos para este.

    La razón de ello es que **debe tener** el control de la forma de la API, no el compilador. Aunque el compilador puede hacer un gran trabajo al inferir tipos para usted, es posible tener la forma de los cambios de la API si los aspectos internos que se basa en han cambiado los tipos. Esto puede ser lo que desea, pero seguramente supondrá una novedad de API que los consumidores de nivel inferiores, a continuación, tendrá que tratar con. En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios. En términos DDD, esto puede considerarse como una capa anticorrupción.

* Dele un nombre significativo para los argumentos genéricos.

    A menos que se está escribiendo código realmente genérico que no es específico a un dominio determinado, un nombre descriptivo puede ayudar a otros programadores entender el dominio que están trabajando en. Por ejemplo, un parámetro de tipo denominado `'Document` en el contexto de la interacción con un documento de base de datos deja más claro que se pueden aceptar tipos de documento genérico por la función o el miembro que está trabajando.

* Considere la posibilidad de asignar nombres a parámetros de tipo genérico con PascalCase.

    Esta es la forma general para hacer cosas en. NET, por lo que se recomienda usar PascalCase en lugar de snake_case o camelCase.

Por último, la generalización automática no siempre es una bendición para las personas que están familiarizadas con F # o código base es grande. No hay esfuerzo especial en el uso de componentes que son genéricos. Además, si automáticamente no se usan funciones generalizadas con diferentes tipos de entrada (let por sí solo si se han diseñado para usarse como tales), entonces no supone ninguna ventaja real a ellos que se va a genérico en ese momento dado. Siempre tenga en cuenta si el código que se va a escribir realmente se beneficiará de ser genérico.

## <a name="performance"></a>Rendimiento

Los valores de F # son inmutables de manera predeterminada, lo que permite evitar ciertas clases de errores (especialmente los relacionados con simultaneidad y paralelismo). Sin embargo, en algunos casos, con el fin de conseguir eficiencia óptima (o incluso razonable) de tiempo de ejecución o las asignaciones de memoria, un intervalo de trabajo puede mejor implementarse mediante el uso de mutación en lugar del estado. Esto es posible en una base de participación en F # con el `mutable` palabra clave.

Sin embargo, usar de `mutable` en F # se puede sentir no concuerda con la pureza funcional. Esto está bien, si ajusta las expectativas de pureza a [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency). Transparencia referencial - no pureza - es el objetivo final al escribir las funciones de F #. Esto le permite escribir una interfaz funcional a través de una implementación basada en mutación para código crítico de rendimiento.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Incluya código mutable en interfaces inmutables

Con una transparencia referencial como objetivo, es fundamental para escribir código que no expone el underbelly mutable de las funciones esenciales para el rendimiento. Por ejemplo, el código siguiente implementa el `Array.contains` función en la biblioteca básica de F #:

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

Llamar varias veces a esta función no modifica la matriz subyacente, ni es necesario mantener cualquier estado mutable en que lo consume. Es forma referencial transparente, aunque casi todas las líneas de código dentro de él usa mutación.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considere la posibilidad de encapsular datos mutables en clases

El ejemplo anterior usa una sola función para encapsular las operaciones con datos mutables. No siempre es suficiente para conjuntos más complejos de datos. Tenga en cuenta los siguientes conjuntos de funciones:

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

Este código es eficaz, pero expone la estructura de datos en función de mutación que son responsables de mantener los llamadores. Esto puede colocarse dentro de una clase sin miembros subyacente que puede cambiar:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` Encapsula la estructura de datos basados en mutación subyacente, por lo que no forzar los llamadores para mantener la estructura de datos subyacente. Las clases son una forma eficaz para encapsular datos y las rutinas que están basados en mutación sin exponer los detalles a los llamadores.

### <a name="prefer-let-mutable-to-reference-cells"></a>Prefiere `let mutable` a las celdas de referencia

Las celdas de referencia son una forma para representar la referencia a un valor en lugar de como el propio valor. Aunque puede usarse para el código crítico para el rendimiento, por lo general no se recomienda. Considere el ejemplo siguiente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

El uso de una celda de referencia "contamina" todo el código subsiguiente con tener que desreferenciar y vuelva a hacer referencia a los datos subyacentes. En su lugar, considere la posibilidad de `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

El único punto de mutación en medio de la expresión lambda, aparte de todos los demás código que toca `acc` puede hacerlo de manera que es similar al uso de un mapa normal `let`-valor inmutable del límite. Así resultará más fácil cambiar con el tiempo.

## <a name="object-programming"></a>Programación de objetos

F # es totalmente compatible con objetos y conceptos orientados a objetos de (objetos OO). Aunque muchos conceptos OO son eficaz y útil, no todos ellos son idóneos para su uso. Las listas siguientes ofrecen instrucciones en las categorías de características orientado a objetos en un nivel alto.

**Considere el uso de estas características en muchas situaciones:**

* La notación de puntos (`x.Length`)
* Miembros de instancia
* Constructores implícitos
* Miembros estáticos
* Notación de indizador (`arr.[x]`)
* Argumentos opcionales y con nombre
* Interfaces y las implementaciones de interfaz

**No llegan a estas características en primer lugar, pero con prudencia aplicarlos cuando están cómodas resolver un problema:**

* Sobrecarga de métodos
* Datos mutables encapsulados
* Operadores de tipos
* Propiedades automáticas
* Implementar `IDisposable` y `IEnumerable`
* Extensiones de tipo
* Eventos
* Estructuras
* Delegados
* Enumeraciones

**Por lo general debe evitar estas características, a menos que se debe usar:**

* Las jerarquías de tipo basado en la herencia y herencia de implementación
* Los valores NULL y `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferir composición herencia

[Composición con herencia](https://en.wikipedia.org/wiki/Composition_over_inheritance) es una expresión desde hace mucho tiempo que puede cumplir buen código de F #. El principio fundamental es que no debe exponer una clase base y forzar que los llamadores hereden de esa clase base para obtener funcionalidad.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usar expresiones de objeto para implementar interfaces si no necesita una clase

[Expresiones de objeto](../language-reference/object-expressions.md) le permiten implementar interfaces sobre la marcha, enlace de la interfaz implementada en un valor sin necesidad de hacerlo dentro de una clase. Esto es práctico, especialmente si se _sólo_ debe implementar la interfaz y no es necesario para una clase completa.

Por ejemplo, este es el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de corrección de código si ha agregado un símbolo que no tiene un `open` instrucción para:

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

Dado que no hay ninguna necesidad de una clase al interactuar con la API de código de Visual Studio, las expresiones de objeto son una herramienta ideal para este. También son valiosos para las pruebas unitarias, cuando desea extraer una interfaz con las rutinas de prueba el código auxiliar de manera ad hoc.

## <a name="type-abbreviations"></a>Abreviaturas de tipo

[Abreviaturas de tipo](../language-reference/type-abbreviations.md) son una manera cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo. Por ejemplo, el siguiente alias asigna una etiqueta a qué hace falta para definir un cálculo con [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), una biblioteca de aprendizaje profundo:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

El `Computation` nombre es una manera cómoda para indicar cualquier función que coincida con la firma es el suavizado de contorno. Mediante las abreviaturas de tipo como esto es conveniente y permite código más concisa.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evite el uso de las abreviaturas de tipo para representar el dominio

Aunque las abreviaturas de tipo son convenientes para asignar un nombre a las firmas de función, puede resultar confusos cuando abreviar otros tipos. Tenga en cuenta esta abreviatura:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Esto puede resultar confuso de varias maneras:

* `BufferSize` no es una abstracción; es simplemente otro nombre para un número entero.
* Si `BufferSize` se expone en una API pública, fácilmente se puedan interpretar erróneamente implica algo más que `int`. Por lo general, los tipos de dominio tiene varios atributos a ellos y no son tipos primitivos, como `int`. Esta abreviatura infringe esa suposición.
* El uso de mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.
* Este alias no ofrece una mayor en comparación con el suministro de un argumento con nombre a una función.
* La abreviatura no se manifiesta en IL compilado; es simplemente un número entero y este alias es una construcción de tiempo de compilación.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

En resumen, la dificultad con abreviaturas de tipo es que son **no** abstracciones a través de los tipos que son abreviar. En el ejemplo anterior, `BufferSize` es simplemente un `int` en segundo plano, con ningún dato adicional ni ningún beneficio desde el sistema de tipos, además de lo que `int` ya tiene.
