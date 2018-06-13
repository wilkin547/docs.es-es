---
title: 'Convenciones de código de F #'
description: 'Obtenga información acerca de expresiones y directrices generales al escribir código de F #.'
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457987"
---
# <a name="f-coding-conventions"></a>Convenciones de código de F #

Las siguientes convenciones Formula de experiencia de trabajar con grandes F # dotarlo. El [cinco principios de buen código F #](index.md#five-principles-of-good-f-code) constituyen el fundamento de cada recomendación. Están relacionados con el [directrices de diseño del componente de F #](component-design-guidelines.md), pero son aplicables a cualquier código de F #, no sólo componentes, como las bibliotecas.

## <a name="organizing-code"></a>Organización del código

F # incluye dos métodos principales para organizar el código: módulos y espacios de nombres. Estos son similares, pero tienen las siguientes diferencias:

* Espacios de nombres se compilan como espacios de nombres. NET. Los módulos se compilan como las clases estáticas.
* Espacios de nombres siempre son de nivel superior. Pueden ser módulos anidados dentro de otros módulos y de nivel superior.
* Espacios de nombres pueden abarcar varios archivos. No se pueden módulos.
* Los módulos se pueden decorar con `[<RequireQualifiedAccess>]` y `[<AutoOpen>]`.

Las instrucciones siguientes le ayudará a utilizar para organizar el código.

### <a name="prefer-namespaces-at-the-top-level"></a>Prefiere espacios de nombres en el nivel superior

Para cualquier código públicamente consumible, espacios de nombres son preferenciales para módulos en el nivel superior. Dado que se compilen como espacios de nombres. NET, son de C# pueden utilizar con ningún problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Uso de un módulo de nivel superior no puede parecer diferente cuando se les llame solo desde F #, pero para los consumidores de C#, quizá le sorprenda llamadores al tener que calificar `MyClass` con el `MyCode` módulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Se aplican con cuidado `[<AutoOpen>]`

El `[<AutoOpen>]` construcción puede contamina el ámbito de lo que está disponible para los llamadores y la respuesta a algo procedencia es "mágica". Esto no suele ser muy útil. Una excepción a esta regla es la biblioteca básica de F # propio (aunque este hecho es un poco controvertido).

Sin embargo, resulta una comodidad si dispone de funcionalidad de la aplicación auxiliar para una API pública que desea organizar por separado a través de esa API pública.

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

Esto le permite detalles de implementación independiente correctamente a través de la API pública de una función sin tener que calificar totalmente un Ayudante cada vez que lo llama.

Además, exponer los métodos de extensión y generadores de expresiones en el nivel de espacio de nombres puede claridad expresarse con `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Use `[<RequireQualifiedAccess>]` siempre nombres pudieron entrar en conflicto o le parecería que ayuda a mejorar la legibilidad

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto es útil cuando las funciones y los valores en el módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos. Que necesiten acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y evolvability de una biblioteca.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordenación `open` instrucciones topológicamente

En F #, el orden de las declaraciones es importante, incluidos con `open` instrucciones. Esto es distinto de C#, donde el efecto de `using` y `using static` es independiente de la orden de esas instrucciones en un archivo.

En F #, pueden reemplazar elementos abiertos en un ámbito otros ya está presente. Esto significa que la reordenación `open` instrucciones podrían alterar el significado del código. Como resultado, cualquier arbitrario ordenar de todos los `open` instrucciones (por ejemplo, por orden alfanumérico) generalmente no se recomienda, menos generar un comportamiento diferente que cabría esperar.

En su lugar, se recomienda que las ordenar [topológicamente](https://en.wikipedia.org/wiki/Topological_sorting); es decir, ordenar su `open` las instrucciones en el orden en que _capas_ del sistema se definen. También se puede considerar realizar alfanumérico de ordenación en diferentes capas topológicas.

Por ejemplo, mostramos la ordenación topológica para el archivo F # compilador servicio público API:

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

Tenga en cuenta que un salto de línea separa las capas de topología con cada capa que se ordenan alfabéticamente posteriormente. Esto organiza limpiamente código sin accidentalmente sombrear valores.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Usar las clases para contener valores que tienen efectos secundarios

Hay muchas veces al inicializar un valor puede tener efectos secundarios, como crear instancias de un contexto de una base de datos u otro recurso remoto. Es tentador inicializar estas cosas en un módulo y usar en las funciones siguientes:

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

En primer lugar, se inserta la configuración de la aplicación en el código base con `dep1` y `dep2`. Esto es difícil de mantener en dotarlo mayor.

En segundo lugar, inicializadas estáticamente datos no deben incluir valores que no son seguros para subprocesos si su componente utilice varios subprocesos. Esto se infringe claramente `dep3`.

Por último, inicialización del módulo se compila en un constructor estático para la unidad de compilación completo. Si se produce un error en la inicialización de un valor de límite permiten en ese módulo, se manifiesta como un `TypeInitializationException` que se almacena en la caché durante toda la duración de la aplicación. Esto puede ser difícil de diagnosticar. Normalmente hay una excepción interna que puede intentar volver a analizar, pero, a continuación, si no existe, no hay ningún indicando la causa raíz.

En su lugar, puede utilizar una clase simple para almacenar las dependencias:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Esto permite lo siguiente:

1. Insertar cualquier estado dependiente fuera de la propia API.
2. Ahora es posible fuera de la API de configuración.
3. Errores de inicialización de los valores dependientes no suelen presentarse como un `TypeInitializationException`.
4. La API ahora es más fácil de probar.

## <a name="error-management"></a>Administración de errores

La administración de errores en sistemas de gran tamaño es una tarea muy compleja y matizada y no hay ningún silver viñetas de asegurarse de sus sistemas son tolerantes a errores y se comportan correctamente. Las siguientes directrices deberían proporcionar instrucciones para navegar por este espacio difícil.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Representar los casos de error y el estado no válido en tipos intrínsecos a su dominio

Con [uniones discriminadas](../language-reference/discriminated-unions.md), F # proporciona la capacidad para representar el estado del programa defectuoso en el sistema de tipos. Por ejemplo:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

En este caso, hay tres maneras conocidos que retirar dinero de una cuenta bancaria puede producir un error. Cada caso de error está representado en el tipo y, por tanto, se puede tratar con seguridad en todo el sistema.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

En general, si puede modelar las distintas maneras en que algo puede **producirá un error** en su dominio, a continuación, código de control de errores ya no se tratan como algo que debe tratar con además de flujo del programa normal. Es simplemente una parte del flujo normal del programa y no se considera **excepcional**. Hay dos ventajas principales para esto:

1. Es fácil de mantener a medida que cambia su dominio con el tiempo.
2. Casos de error son fáciles de prueba unitaria.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Utilizar excepciones cuando no se puede representar errores con tipos

No todos los errores se pueden representar en un dominio del problema. Estos tipos de errores están *excepcional* por naturaleza, por lo tanto, la capacidad de generar y capturar excepciones en F #.

En primer lugar, se recomienda que lea la [directrices de diseño de excepción](../../standard/design-guidelines/exceptions.md). También son aplicables a F #.

Deben tener en cuenta las construcciones principales disponibles en F # para los propósitos de producir excepciones en el siguiente orden de preferencia:

| Función | Sintaxis | Propósito |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera un `System.ArgumentNullException` con el nombre de argumento especificados. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nombre de argumento especificado y un mensaje. |
| `invalidOp` | `invalidOp "message"` | Genera un `System.InvalidOperationException` con el mensaje especificado. |
|`raise`| `raise (ExceptionType("message"))` | Mecanismo de uso general para producir excepciones. |
| `failwith` | `failwith "message"` | Genera un `System.Exception` con el mensaje especificado. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` con un mensaje determinado por la cadena de formato y sus entradas. |

Use `nullArg`, `invalidArg` y `invalidOp` como mecanismo para producir `ArgumentNullException`, `ArgumentException` y `InvalidOperationException` cuando sea necesario.

El `failwith` y `failwithf` funciones deben evitar en general porque activan la base de `Exception` escriba, no una excepción específica. Según la [directrices de diseño de excepción](../../standard/design-guidelines/exceptions.md), que desea producir excepciones más específicas cuando sea posible.

### <a name="using-exception-handling-syntax"></a>Con la sintaxis de control de excepciones

F # admite patrones de excepción mediante la `try...with` sintaxis:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Reconciliar funcionalidad para realizar en el caso de una excepción con la coincidencia de modelos puede ser un poco difícil si desea mantener el código de limpieza. Un modo para controlar esto consiste en usar [modelos activos](../language-reference/active-patterns.md) como medio para la funcionalidad de grupo que rodea a un caso de error con una excepción propia. Por ejemplo, puede consumir una API que, cuando produce una excepción, incluye información valiosa en los metadatos de excepción. Desempaquetar un valor adecuado en el cuerpo de la excepción capturada en el modelo activo y devolver que el valor puede ser útil en algunas situaciones.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>No use para reemplazar las excepciones de control de errores monádico

Las excepciones se ven como algo taboo en la programación funcional. De hecho, las excepciones infringen pureza, por lo que es seguro para tener en cuenta no es funcional. Sin embargo, esto omite la realidad de donde se debe ejecutar código y que pueden producirse errores en tiempo de ejecución. Por lo general, escribir código en la suposición de que la mayoría de aspectos no son puro ni total, para minimizar las sorpresas desagradables.

Es importante tener en cuenta los siguientes puntos fuertes/aspectos básicos de excepciones con respecto a su relevancia y adecuación en el tiempo de ejecución de .NET y el ecosistema de idiomas como un todo:

1. Contienen información de diagnóstico detallada, lo cual es muy útil al depurar un problema.
2. Están bien definidas por el tiempo de ejecución y otros lenguajes. NET.
3. Pueden reducir reutilizable significativo en comparación con el código sale del camino a *evitar* excepciones mediante la implementación de un subconjunto de sus semánticas de manera ad hoc.

Este tercer punto es fundamental. No triviales para operaciones más complejas, si no se puede utilizar excepciones puede producir trabajar con estructuras similar al siguiente:

```fsharp
Result<Result<MyType, string>, string list>
```

Fácilmente lo que puede provocar frágil código como en "stringly escrito" errores de coincidencia de patrón:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Además, puede resultar tentador pasar cualquier excepción en el deseo de una función de "simple" que devuelva un tipo "más adecuado":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Por desgracia, `tryReadAllText` puede producir numerosas excepciones en función de la gran cantidad de cosas que pueden ocurrir en un sistema de archivos, y este código inmediatamente descarta toda la información sobre lo que podría realmente se causa del error en su entorno. Si reemplaza este código con un tipo de resultado, le volver a analizar el mensaje "stringly escrito" error:

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

Y la colocación del propio objeto de excepción en el `Error` constructor simplemente obliga a tratar correctamente con el tipo de excepción en el sitio de llamada en lugar de en la función. Hacerlo de forma eficaz crea excepciones comprobadas, que son notablemente unfun tratar como un llamador de una API.

Es una buena alternativa a los ejemplos anteriores detectar *específico* excepciones y devolver un valor significativo en el contexto de esta excepción. Si modifica la `tryReadAllText` funcionar como sigue, `None` tiene más significado:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

En lugar de funcionar como comodín, esta función ahora controlará correctamente el caso cuando un archivo no se encontró y asignar ese significado para un carácter de retorno. Este valor devuelto puede asignar a ese caso de error, mientras no descarta cualquier información contextual o hacer que los llamadores para tratar un caso que podrían no ser pertinente en ese momento en el código.

Tipos como `Result<'Success, 'Error>` son adecuados para las operaciones básicas que no están anidados y son perfectos para representar algo podría cualquier valor devuelto opcionales tipos en F # *algo* o *nada*. Sin embargo, no son un sustituto para las excepciones y no debe usarse en un intento de reemplazar las excepciones. En su lugar, se debe aplicar con prudencia a los aspectos específicos de dirección de la excepción y la directiva de administración de errores de maneras de destino.

## <a name="partial-application-and-point-free-programming"></a>Aplicación parcial y libre de punto de programación

F # admite la aplicación parcial y por lo tanto, varias maneras de programa en un estilo libre de punto. Esto puede ser beneficioso para reutilizar el código dentro de un módulo o la implementación de algo, pero en general no es algo para exponer públicamente. En general, libre de punto de programación no es un virtud de por sí y puede agregar una barrera cognitiva significativa para las personas que no se sumergen en el estilo.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>No use aplicación parcial y la currificación en las API públicas

Con pocas excepciones, el uso de la aplicación parcial en las API públicas puede resultar confuso para los consumidores. Por lo general, `let`-son valores enlazados en el código de F # **valores**, no **función valores**. Combinación de los valores y los valores de función puede dar lugar a para guardar un pequeño número de líneas de código a cambio de una gran cantidad de sobrecarga cognitiva, especialmente si se combina con operadores como `>>` para la creación de funciones.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Tenga en cuenta las implicaciones de herramientas para la programación libre de punto

Funciones currificadas no etiqueta sus argumentos. Esto tiene implicaciones de herramientas. Tenga en cuenta las dos funciones siguientes:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Ambas son funciones válidas, pero `funcWithApplication` es una función currificada. Cuando sitúa sobre sus tipos en un editor, verá lo siguiente:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

En el sitio de llamada, información sobre herramientas en herramientas como Visual Studio, no tendrá información significativa para saber lo que el `string` y `int` realmente representan tipos de entrada.

Si se producen libre de punto de código como `funcWithApplication` es públicamente consumible, se recomienda realizar una expansión de η completa para que las herramientas pueden elegir en hasta nombres significativos para los argumentos.

Además, libre de punto de código de depuración puede ser complicada, si no imposible. Herramientas de depuración se basan en valores enlazados a los nombres (por ejemplo, `let` enlaces) que puede inspeccionar la mitad de los valores intermedios a través de la ejecución. Cuando el código no tiene ningún valor para inspeccionar, no hay nada para depurar. En el futuro, herramientas de depuración pueden evolucionar para sintetizar estos valores en función de las rutas de acceso ejecutadas con anterioridad, pero no es una buena idea para protegerse de los resultados probables en *posibles* funciones de depuración.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Considere la posibilidad de aplicación parcial como una técnica para reducir reutilizable interno

A diferencia de lo anterior, aplicación parcial es una herramienta maravillosa para reducir reutilizable dentro de una aplicación o el funcionamiento interno de un poco más de una API. Puede resultar útil para la implementación de las API más complicadas, donde reutilizable a menudo es una molestia para tratar de pruebas unitarias. Por ejemplo, el código siguiente muestra cómo puede llevar a cabo los marcos de simulación más ofrecen sin realizar una dependencia externa en un marco de trabajo y tener que aprender un relacionados personalizada API.

Por ejemplo, considere la topografía de solución siguientes:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` puede exponer el código, como:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Pruebas unitarias `Transactions.doTransaction` en `ImplementationLogic.Tests.fspoj` es fácil:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Aplicar parcialmente `doTransaction` con un contexto de simulación objeto le permite llamar a la función en todas las pruebas unitarias sin necesidad de crear un contexto simulado cada vez:

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

Esta técnica no se debe aplicar universalmente a todo el código de base, pero es una buena manera de reducir reutilizable para complejas funciones internas y los elementos internos de pruebas unitarias.

## <a name="access-control"></a>Control de acceso

F # tiene varias opciones para [el control de acceso](../language-reference/access-control.md)heredar del lo que está disponible en el tiempo de ejecución. NET. Estos no son simplemente puede usar para los tipos: puede usarlos para funciones, demasiado.

* Prefiere no -`public` tipos y miembros hasta que se necesiten para poder usarse públicamente. Esto también reduce el par de los consumidores a
* Intentar mantener toda la funcionalidad de aplicación auxiliar `private`.
* Considere el uso de `[<AutoOpen>]` en un módulo de funciones de aplicación auxiliar que dejen de estar numerosas privado.

## <a name="type-inference-and-generics"></a>Inferencia de tipos y tipos genéricos

Inferencia de tipos puede evitarle escribir mucho código reutilizable. Y generalización automática en el compilador de F # puede ayudarle a escribir código más genérico con casi ningún esfuerzo adicional por su parte. Sin embargo, estas características no están universalmente buenas.

* Considere la posibilidad de etiquetar los nombres de argumento con un tipo explícito en las API públicas y no se debe confiar en la inferencia de tipo para este.

    La razón de ello es que **debe tener** el control de la forma de la API, no el compilador. Aunque el compilador puede realizar un trabajo bien en inferir tipos para usted, es posible tener la forma de cambiar su API si el funcionamiento interno en que se basa ha cambiado los tipos. Puede tratarse de lo que desee, pero casi con toda seguridad supondrá un cambio de la API de importante que los consumidores de nivel inferiores, a continuación, tendrá que tratar con. En su lugar, si puede controlar explícitamente la forma de la API pública, puede controlar estos cambios. En términos DDD, esto puede considerarse como una capa contra daño.

* Considere la posibilidad de dar un nombre descriptivo para los argumentos genéricos.

    A menos que se está escribiendo código realmente genérico que no es específico de un dominio en particular, un nombre descriptivo puede ayudar a otros programadores comprender el dominio que está trabajando en. Por ejemplo, un parámetro de tipo denominado `'Document` en el contexto de la interacción con un documento de base de datos resulta más claro que se pueden aceptar tipos de documento genérico por la función o el miembro que está trabajando.

* Considere la posibilidad de nomenclatura de parámetros de tipo genérico con PascalCase.

    Se trata de la forma general para realizar acciones en. NET, por lo que se recomienda que use PascalCase en lugar de snake_case o camelCase.

Por último, la generalización automática no siempre es una ventaja para las personas que son nuevas en F # o un código base grande. Hay sobrecarga cognitiva en utilización de componentes que son genéricos. Además, si automáticamente generalizadas funciones no se utilizan con diferentes tipos de entrada (si están destinadas a usarse como tales let), entonces representa ningún beneficio real a ellos ser genérico en ese momento en el tiempo. Siempre tenga en cuenta si el código que se escribe realmente se beneficiará de ser genérico.

## <a name="performance"></a>Rendimiento

Valores de F # son inmutables de forma predeterminada, lo que permite evitar ciertas clases de errores (especialmente los relacionados con simultaneidad y el paralelismo). Sin embargo, en algunos casos, para lograr una eficiencia óptima (o incluso razonable) de tiempo de ejecución o las asignaciones de memoria, un intervalo de trabajo puede mejor implementarse mediante el uso de mutación en lugar de estado. Esto es posible en una base de participación con F # con el `mutable` palabra clave.

Sin embargo, uso de `mutable` en F # pueden considerar no concuerda con pureza funcional. Esto es correcto, si está ajustando las expectativas de pureza a [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency). La transparencia referencial - no pureza - es el objetivo final al escribir funciones de F #. Esto le permite escribir una interfaz funcional a través de una implementación basada en mutación para código crítico en rendimiento.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Incluir código mutable en interfaces inmutable

Con transparencia referencial como un objetivo, es fundamental para escribir código que no expone el underbelly mutable de las funciones esenciales para el rendimiento. Por ejemplo, el código siguiente implementa la `Array.contains` función en la biblioteca básica de F #:

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

Llamar varias veces a esta función no modifica la matriz subyacente, ni es necesario mantener cualquier estado mutable en usarlo. Es forma referencial transparente, incluso aunque casi todas las líneas de código dentro de él emplea mutación.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considere la posibilidad de encapsulación de datos mutables en clases

En el ejemplo anterior se utiliza una única función para encapsular las operaciones con datos mutables. No siempre es suficiente para conjuntos más complejos de datos. Tenga en cuenta los siguientes conjuntos de funciones:

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

Este código es un rendimiento superior, pero expone la estructura de datos basados en mutaciones que los llamadores son responsables de mantener. Esto puede colocarse dentro de una clase sin miembros subyacente que puede cambiar:

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

`Closure1Table` Encapsula la estructura de datos basados en mutación subyacente, por lo que no forzar los llamadores para mantener la estructura de datos subyacente. Las clases son una manera eficaz para encapsular datos y las rutinas que están basados en mutación sin exponer los detalles a los llamadores.

### <a name="prefer-let-mutable-to-reference-cells"></a>Prefiere `let mutable` a las celdas de referencia

Celdas de referencia son una manera de representar la referencia a un valor en lugar de como el propio valor. Aunque se puede utilizar para el código crítico para el rendimiento, que generalmente no se recomiendan. Considere el ejemplo siguiente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

El uso de una celda de referencia "contamina" todo el código subsiguiente con necesidad de desreferenciación y volver a hacer referencia a los datos subyacentes. En su lugar, considere la posibilidad de `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Además el punto único de mutación en medio de la expresión lambda, todos los demás código que toca `acc` puede hacerlo de manera que es similar al uso de una normal `let`-valor inmutable del enlace. Así resultará más fácil cambiar con el tiempo.

## <a name="object-programming"></a>Programación de objetos

F # es totalmente compatible con objetos y conceptos de (orientado a objetos) orientada a objetos. Aunque muchos de los conceptos de orientado a objetos son eficaces y útil, no todas ellas son idóneos para su uso. Las listas siguientes proporcionan directrices sobre categorías de características de orientado a objetos en un nivel superior.

**Considere la posibilidad de utilizar estas características en muchas situaciones:**

* La notación de puntos (`x.Length`)
* Miembros de instancia
* Constructores implícitos
* Miembros estáticos
* Notación de indizador (`arr.[x]`)
* Argumentos opcionales y con nombre
* Interfaces y las implementaciones de interfaz

**No alcanzar para estas características en primer lugar, pero con prudencia aplicarlos cuando están cómodos solucionar un problema:**

* Sobrecarga de métodos
* Datos mutables encapsulados
* Operadores en tipos
* Propiedades de automático
* Implementar `IDisposable` y `IEnumerable`
* Extensiones de tipo
* Eventos
* Estructuras
* Delegados
* Enumeraciones

**Por lo general evitar estas características a menos que se debe utilizar:**

* Las jerarquías de tipos basado en la herencia y la herencia de implementación
* Valores NULL y `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferir composición de herencia

[Composición con herencia](https://en.wikipedia.org/wiki/Composition_over_inheritance) es un muy larga que puede cumplir buen código F #. El principio fundamental es que no debería exponer una clase base y forzar que los llamadores pueden heredar de esa clase base para obtener funcionalidad.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usar expresiones de objeto para implementar interfaces si ya no necesita una clase

[Expresiones de objeto](../language-reference/object-expressions.md) te permiten implementar interfaces sobre la marcha, enlazar la interfaz implementada a un valor sin necesidad de hacerlo dentro de una clase. Esto resulta útil, sobre todo si se _sólo_ tiene que implementar la interfaz y no es necesario para una clase completa.

Por ejemplo, este es el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de corrección del código si ha agregado un símbolo que no tiene un `open` instrucción para:

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

Dado que no es necesario para una clase al interactuar con la API de código de Visual Studio, expresiones de objeto son una herramienta ideal para este. También son valiosos para pruebas unitarias, cuando desea extraer una interfaz con rutinas de prueba el código auxiliar de manera ad hoc.

## <a name="type-abbreviations"></a>Abreviaturas de tipo

[Abreviaturas de tipo](../language-reference/type-abbreviations.md) son una forma cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo. Por ejemplo, el siguiente alias asigna una etiqueta a lo que se necesita para definir un cálculo con [CNTK](https://www.microsoft.com/cognitive-toolkit/), un profundo aprendizaje biblioteca:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

El `Computation` nombre es una forma cómoda para indicar cualquier función que coincide con la signatura es alias. Utilizando las abreviaturas de tipo parecido a esto es cómodo y permite el código más conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evite el uso de las abreviaturas de tipo para representar el dominio

Aunque las abreviaturas de tipo son convenientes para asignar un nombre a las firmas de función, puede resultar confusos cuando abreviar otros tipos. Tenga en cuenta esta abreviatura:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Esto puede resultar confuso de varias maneras:

* `BufferSize` no es una abstracción; es simplemente otro nombre para un número entero.
* Si `BufferSize` se expone en una API pública, puede fácilmente malinterpretarse implica algo más que `int`. En general, los tipos de dominio tiene varios atributos a ellos y no son tipos primitivos como `int`. Esta abreviatura infringe esa suposición.
* Las mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.
* Este alias no ofrece una mayor claridad, en comparación con el suministro de un argumento con nombre a una función.
* La abreviatura no se manifestará en IL compilado; es simplemente un entero y este alias es una construcción de tiempo de compilación.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

En resumen, el problema con las abreviaturas de tipo es que son **no** abstracciones de los tipos que son abreviar. En el ejemplo anterior, `BufferSize` es simplemente una `int` tras los bastidores, con ningún dato adicional ni cualquier mejora en el sistema de tipo además de lo que `int` ya tiene.
