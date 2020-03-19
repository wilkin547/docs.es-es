---
title: Convenciones de código de F#
description: Aprenda las pautas generales y los modismos al escribir código de F.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401152"
---
# <a name="f-coding-conventions"></a>Convenciones de código de F#

Las siguientes convenciones se formulan a partir de la experiencia de trabajo con grandes bases de código de F. Los [cinco principios del buen código de F](index.md#five-principles-of-good-f-code) son la base de cada recomendación. Están relacionados con las directrices de diseño de [componentes](component-design-guidelines.md)de F , pero son aplicables a cualquier código de F, no solo a componentes como bibliotecas.

## <a name="organizing-code"></a>Organización del código

F- cuenta con dos formas principales de organizar el código: módulos y espacios de nombres. Estos son similares, pero tienen las siguientes diferencias:

* Los espacios de nombres se compilan como espacios de nombres .NET. Los módulos se compilan como clases estáticas.
* Los espacios de nombres siempre son de nivel superior. Los módulos pueden ser de nivel superior y anidados dentro de otros módulos.
* Los espacios de nombres pueden abarcar varios archivos. Los módulos no pueden.
* Los módulos `[<RequireQualifiedAccess>]` se `[<AutoOpen>]`pueden decorar con y .

Las siguientes directrices le ayudarán a usarlas para organizar el código.

### <a name="prefer-namespaces-at-the-top-level"></a>Prefiere espacios de nombres en el nivel superior

Para cualquier código consumible públicamente, los espacios de nombres son preferenciales a los módulos en el nivel superior. Debido a que se compilan como espacios de nombres de .NET, son consumibles de C- sin ningún problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

El uso de un módulo de nivel superior puede no parecer diferente cuando se llama solo desde `MyClass` F, pero para los consumidores de C, los llamadores pueden sorprenderse al tener que calificar con el `MyCode` módulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Aplicar con cuidado`[<AutoOpen>]`

La `[<AutoOpen>]` construcción puede contaminar el alcance de lo que está disponible para las personas que llaman, y la respuesta a donde algo viene es "magia". Esto no es algo bueno. Una excepción a esta regla es la propia biblioteca principal de F - (aunque este hecho también es un poco controvertido).

Sin embargo, es una comodidad si tiene funcionalidad de aplicación auxiliar para una API pública que desea organizar por separado de esa API pública.

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

Esto le permite separar limpiamente los detalles de implementación de la API pública de una función sin tener que calificar completamente a una aplicación auxiliar cada vez que la llame.

Además, la exposición de métodos de extensión y `[<AutoOpen>]`generadores de expresiones en el nivel de espacio de nombres se puede expresar perfectamente con .

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Usar `[<RequireQualifiedAccess>]` siempre que los nombres puedan entrar en conflicto o sienta que ayuda con la legibilidad

Agregar `[<RequireQualifiedAccess>]` el atributo a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren acceso calificado explícito. Por ejemplo, `Microsoft.FSharp.Collections.List` el módulo tiene este atributo.

Esto es útil cuando las funciones y los valores del módulo tienen nombres que probablemente entren en conflicto con los nombres de otros módulos. Requerir acceso calificado puede aumentar en gran medida la capacidad de mantenimiento y la capacidad de conexión a largo plazo de una biblioteca.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordenar `open` las declaraciones topológicamente

El orden de las declaraciones es `open` importante, incluso con las declaraciones. Esto es diferente de C- `using` `using static` , donde el efecto de y es independiente del orden de esas instrucciones en un archivo.

Los elementos abiertos en un ámbito pueden sombrear a otros ya presentes en F. Esto significa que `open` reordenar instrucciones podría alterar el significado del código. Como resultado, no se recomienda `open` cualquier ordenación arbitraria de todas las instrucciones (por ejemplo, alfanuméricamente), no sea que genere un comportamiento diferente que pueda esperar.

En su lugar, se recomienda ordenarlos [topológicamente;](https://en.wikipedia.org/wiki/Topological_sorting) es decir, `open` ordene sus estados de cuenta en el orden en que se definen _las capas_ del sistema. También se puede considerar la ordenación alfanumérica dentro de diferentes capas topológicas.

Por ejemplo, aquí está la ordenación topológica para el archivo de API pública del servicio del compilador de F:

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

Tenga en cuenta que un salto de línea separa las capas topológicas, con cada capa que se ordena alfanuméricamente después. Esto organiza limpiamente el código sin sombreado accidentalmente los valores.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Utilice clases para contener valores que tengan efectos secundarios

Hay muchas veces cuando la inicialización de un valor puede tener efectos secundarios, como crear instancias de un contexto en una base de datos u otro recurso remoto. Es tentador inicializar tales cosas en un módulo y utilizarlo en funciones posteriores:

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

Esto es con frecuencia una mala idea por algunas razones:

En primer lugar, la configuración `dep1` de `dep2`la aplicación se inserta en el código base con y . Esto es difícil de mantener en bases de código más grandes.

En segundo lugar, los datos inicializados estáticamente no deben incluir valores que no sean seguros para subprocesos si el componente utilizará varios subprocesos. Esto es claramente `dep3`violado por .

Por último, la inicialización del módulo se compila en un constructor estático para toda la unidad de compilación. Si se produce algún error en la inicialización del `TypeInitializationException` valor enlazado a let en ese módulo, se manifiesta como un que, a continuación, se almacena en caché durante toda la duración de la aplicación. Esto puede ser difícil de diagnosticar. Por lo general, hay una excepción interna sobre la que puede intentar razonar, pero si no lo hay, entonces no se sabe cuál es la causa raíz.

En su lugar, solo tiene que utilizar una clase simple para contener dependencias:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Esto permite lo siguiente:

1. Empujar cualquier estado dependiente fuera de la propia API.
2. La configuración ahora se puede realizar fuera de la API.
3. No es probable que los errores en `TypeInitializationException`la inicialización de valores dependientes se manifiesten como un archivo .
4. La API ahora es más fácil de probar.

## <a name="error-management"></a>Gestión de errores

La gestión de errores en sistemas grandes es un esfuerzo complejo y matizado, y no hay balas de plata para garantizar que sus sistemas sean tolerantes a fallas y se comporten bien. Las siguientes pautas deben ofrecer orientación para navegar por este difícil espacio.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Representar casos de error y estado ilegal en tipos intrínsecos a tu dominio

Con [las Uniones Discriminadas](../language-reference/discriminated-unions.md), F- le da la capacidad de representar el estado defectuoso del programa en su sistema de tipos. Por ejemplo:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

En este caso, hay tres maneras conocidas de que la retirada de dinero de una cuenta bancaria puede fallar. Cada caso de error se representa en el tipo, y por lo tanto se puede tratar de forma segura en todo el programa.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

En general, si puede modelar las diferentes formas en que algo puede **fallar** en su dominio, el código de control de errores ya no se trata como algo que debe tratar además del flujo de programa normal. Es simplemente una parte del flujo normal del programa, y no se considera **excepcional.** Hay dos beneficios principales para esto:

1. Es más fácil de mantener a medida que el dominio cambia con el tiempo.
2. Los casos de error son más fáciles de probar unitariamente.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Use excepciones cuando los errores no se puedan representar con tipos

No todos los errores se pueden representar en un dominio problemático. Este tipo de fallas son de naturaleza *excepcional,* de ahí la capacidad de generar y detectar excepciones en F .

En primer lugar, se recomienda que lea las Directrices de [diseño de excepciones](../../standard/design-guidelines/exceptions.md). Estos también son aplicables a F.

Las principales construcciones disponibles en F- a los efectos de la generación de excepciones deben tenerse en cuenta en el siguiente orden de preferencia:

| Función | Sintaxis | Propósito |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera a `System.ArgumentNullException` con el nombre de argumento especificado. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nombre de argumento y un mensaje especificados. |
| `invalidOp` | `invalidOp "message"` | Genera a `System.InvalidOperationException` con el mensaje especificado. |
|`raise`| `raise (ExceptionType("message"))` | Mecanismo de uso general para producir excepciones. |
| `failwith` | `failwith "message"` | Genera a `System.Exception` con el mensaje especificado. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` mensaje determinado por la cadena de formato y sus entradas. |

Utilice `nullArg` `invalidArg` , `invalidOp` y como `ArgumentNullException`mecanismo `ArgumentException` `InvalidOperationException` para lanzar , y cuando corresponda.

Las `failwith` `failwithf` funciones y generalmente deben evitarse `Exception` porque generan el tipo base, no una excepción específica. Según las directrices de diseño de [excepciones,](../../standard/design-guidelines/exceptions.md)desea generar excepciones más específicas cuando pueda.

### <a name="using-exception-handling-syntax"></a>Uso de la sintaxis de control de excepciones

F- soporta patrones de `try...with` excepción a través de la sintaxis:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

La conciliación de la funcionalidad para realizar frente a una excepción con la coincidencia de patrones puede ser un poco complicada si desea mantener el código limpio. Una de estas maneras de controlar esto es usar [patrones activos](../language-reference/active-patterns.md) como un medio para agrupar la funcionalidad que rodea un caso de error con una excepción en sí. Por ejemplo, puede estar consumiendo una API que, cuando produce una excepción, encierra información valiosa en los metadatos de la excepción. Desencapsular un valor útil en el cuerpo de la excepción capturada dentro del patrón activo y devolver ese valor puede ser útil en algunas situaciones.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>No utilice el control de errores monádicos para reemplazar las excepciones

Las excepciones se ven como algo tabú en la programación funcional. De hecho, las excepciones violan la pureza, por lo que es seguro considerarlas no del todo funcionales. Sin embargo, esto omite la realidad de dónde se debe ejecutar el código y que pueden producirse errores en tiempo de ejecución. En general, escriba código en la suposición de que la mayoría de las cosas no son puras ni totales, para minimizar sorpresas desagradables.

Es importante tener en cuenta las siguientes fortalezas/aspectos principales de las excepciones con respecto a su relevancia y adecuación en el entorno de ejecución de .NET y en el ecosistema entre idiomas en su conjunto:

1. Contienen información de diagnóstico detallada, que es muy útil al depurar un problema.
2. El tiempo de ejecución y otros lenguajes .NET los entienden bien.
3. Pueden reducir la potencia significativa en comparación con el código que hace todo lo posible para *evitar* excepciones mediante la implementación de algún subconjunto de su semántica sobre una base ad hoc.

Este tercer punto es crítico. Para operaciones complejas no triviales, no usar excepciones puede resultar en el tratamiento de estructuras como esta:

```fsharp
Result<Result<MyType, string>, string list>
```

Lo que puede conducir fácilmente a código frágil como la coincidencia de patrones en errores "con tipo de cadena":

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Además, puede ser tentador tragar cualquier excepción en el deseo de una función "simple" que devuelve un tipo "más agradable":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Desafortunadamente, `tryReadAllText` puede producir numerosas excepciones basadas en la infinidad de cosas que pueden suceder en un sistema de archivos, y este código descarta cualquier información sobre lo que realmente podría estar yendo mal en su entorno. Si reemplaza este código con un tipo de resultado, volverá al análisis de mensajes de error "con tipo de cadena":

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

Y colocar el propio `Error` objeto de excepción en el constructor sólo obliga a tratar correctamente con el tipo de excepción en el sitio de llamada en lugar de en la función. Al hacerlo, se crean excepciones comprobadas, que no pueden ser divertidas de tratar como llamador de una API.

Una buena alternativa a los ejemplos anteriores es detectar excepciones *específicas* y devolver un valor significativo en el contexto de esa excepción. Si modifica `tryReadAllText` la función `None` de la siguiente manera, tiene más significado:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

En lugar de funcionar como un catch-all, esta función ahora controlará correctamente el caso cuando no se encontró un archivo y asignará ese significado a una devolución. Este valor devuelto puede asignarse a ese caso de error, sin descartar ninguna información contextual ni forzar a los llamadores a tratar un caso que puede no ser relevante en ese momento del código.

Tipos como `Result<'Success, 'Error>` son adecuados para operaciones básicas en las que no están anidados y los tipos opcionales de F - son perfectos para representar cuando algo podría devolver *algo* o *nada.* Sin embargo, no sustituyen las excepciones y no deben usarse en un intento de reemplazar excepciones. Más bien, deberían aplicarse con prudencia para abordar aspectos específicos de la política de administración de excepciones y errores de maneras específicas.

## <a name="partial-application-and-point-free-programming"></a>Aplicación parcial y programación sin puntos

F- es compatible con la aplicación parcial, y por lo tanto, varias maneras de programar en un estilo sin puntos. Esto puede ser beneficioso para la reutilización de código dentro de un módulo o la implementación de algo, pero no es algo para exponer públicamente. En general, la programación sin puntos no es una virtud en sí misma, y puede añadir una barrera cognitiva significativa para las personas que no están inmersas en el estilo.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>No utilice la aplicación parcial y el curry en las API públicas

Con poca excepción, el uso de la aplicación parcial en las API públicas puede ser confuso para los consumidores. Por `let`lo general, los valores -bound en el código de F son **valores,** no valores de **función.** Mezclar valores y valores de función puede resultar en guardar un pequeño número de líneas de código `>>` a cambio de un poco de sobrecarga cognitiva, especialmente si se combina con operadores como para componer funciones.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Considere las implicaciones de las herramientas para la programación sin puntos

Las funciones curradas no etiquetan sus argumentos. Esto tiene implicaciones de herramientas. Considere las dos funciones siguientes:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Ambas son funciones `funcWithApplication` válidas, pero es una función curried. Cuando pasa el cursor sobre sus tipos en un editor, verá lo siguiente:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

En el sitio de llamada, la información sobre herramientas de herramientas como `string` `int` Visual Studio no le proporcionará información significativa sobre lo que realmente representan los tipos de entrada y.

Si encuentra código sin `funcWithApplication` puntos como ese es consumible públicamente, se recomienda hacer una expansión completa para que las herramientas puedan obtener nombres significativos para los argumentos.

Además, depurar código sin puntos puede ser difícil, si no imposible. Las herramientas de depuración se basan `let` en valores enlazados a nombres (por ejemplo, enlaces) para que pueda inspeccionar los valores intermedios a mitad de la ejecución. Cuando el código no tiene valores que inspeccionar, no hay nada que depurar. En el futuro, las herramientas de depuración pueden evolucionar para sintetizar estos valores en función de las rutas ejecutadas anteriormente, pero no es una buena idea cubrir sus apuestas sobre la funcionalidad de depuración *potencial.*

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Considere la aplicación parcial como una técnica para reducir la placa de caldera interna

A diferencia del punto anterior, la aplicación parcial es una herramienta maravillosa para reducir la placa reutilizable dentro de una aplicación o los internos más profundos de una API. Puede ser útil para la prueba unitaria de la implementación de API más complicadas, donde la placa reutilizable es a menudo un dolor para tratar. Por ejemplo, el código siguiente muestra cómo puede lograr lo que la mayoría de los marcos de simulación le proporcionan sin tomar una dependencia externa en dicho marco de trabajo y tener que aprender una API a medida relacionada.

Por ejemplo, considere la siguiente topografía de solución:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj`podría exponer código como:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Las `Transactions.doTransaction` pruebas `ImplementationLogic.Tests.fsproj` unitarias son fáciles:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Aplicar parcialmente `doTransaction` con un objeto de contexto de simulación le permite llamar a la función en todas las pruebas unitarias sin necesidad de construir un contexto simulado cada vez:

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

Esta técnica no se debe aplicar universalmente a toda la base de código, pero es una buena manera de reducir la placa de caldera para los internos complicados y las pruebas unitarias de esos internos.

## <a name="access-control"></a>Control de acceso

F- tiene varias opciones para [el control](../language-reference/access-control.md)de acceso , heredadas de lo que está disponible en el tiempo de ejecución de .NET. Estos no son sólo utilizables para los tipos - se puede utilizar para las funciones, también.

* Prefiere los`public` no tipos y miembros hasta que necesite que sean consumibles públicamente. Esto también minimiza lo que los consumidores se aparejan.
* Esfuércese por `private`mantener todas las funciones de la aplicación auxiliar.
* Considere el `[<AutoOpen>]` uso de en un módulo privado de funciones auxiliares si se convierten en numerosas.

## <a name="type-inference-and-generics"></a>Inferencia de tipos y genéricos

La inferencia de tipo puede ahorrarle escribir una gran cantidad de reutilizable. Además, la generalización automática en el compilador de F - puede ayudarle a escribir código más genérico sin casi ningún esfuerzo adicional por su parte. Sin embargo, estas características no son universalmente buenas.

* Considere la posibilidad de etiquetar nombres de argumentos con tipos explícitos en LAS API públicas y no se base en la inferencia de tipos para ello.

    La razón de esto es que **debe** tener el control de la forma de la API, no del compilador. Aunque el compilador puede hacer un trabajo excelente en la inferir tipos por usted, es posible tener la forma del cambio de API si los internos en los que se basa han cambiado los tipos. Esto puede ser lo que desea, pero casi con seguridad resultará en un cambio de API de última hora que los consumidores intermedios tendrán que lidiar con. En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios importantes. En términos de DDD, esto se puede considerar como una capa anticorrupción.

* Considere la posibilidad de dar un nombre significativo a los argumentos genéricos.

    A menos que escriba código verdaderamente genérico que no sea específico de un dominio determinado, un nombre significativo puede ayudar a otros programadores a comprender el dominio en el que están trabajando. Por ejemplo, un `'Document` parámetro de tipo denominado en el contexto de la interacción con una base de datos de documentos hace que sea más claro que la función o el miembro con el que está trabajando puedan aceptar tipos de documentos genéricos.

* Considere la posibilidad de nombrar parámetros de tipo genérico con PascalCase.

    Esta es la forma general de hacer las cosas en .NET, por lo que se recomienda usar PascalCase en lugar de snake_case o camelCase.

Por último, la generalización automática no siempre es una bendición para las personas que son nuevas en F o un código base grande. Hay sobrecarga cognitiva en el uso de componentes que son genéricos. Además, si las funciones generalizadas automáticamente no se utilizan con diferentes tipos de entrada (por no hablar si están destinadas a ser utilizadas como tales), entonces no hay ningún beneficio real para que sean genéricas en ese momento. Considere siempre si el código que está escribiendo realmente se beneficiará de ser genérico.

## <a name="performance"></a>Rendimiento

### <a name="prefer-structs-for-small-data-types"></a>Prefiere estructuras para tipos de datos pequeños

El uso de estructuras (también denominadatipos de valor) a menudo puede dar lugar a un mayor rendimiento para algunos códigos, ya que normalmente evita la asignación de objetos. Sin embargo, las estructuras no siempre son un botón de "ir más rápido": si el tamaño de los datos en una estructura supera los 16 bytes, copiar los datos a menudo puede dar lugar a más tiempo de CPU que a usar un tipo de referencia.

Para determinar si debe utilizar una estructura, tenga en cuenta las siguientes condiciones:

- Si el tamaño de los datos es de 16 bytes o menos.
- Si es probable que tenga muchos de estos tipos de datos residentes en la memoria en un programa en ejecución.

Si se aplica la primera condición, generalmente debe usar una estructura. Si ambos se aplican, casi siempre debe utilizar un struct. Puede haber algunos casos en los que se aplican las condiciones anteriores, pero el uso de una estructura no es mejor o peor que usar un tipo de referencia, pero es probable que sean raros. Sin embargo, es importante medir siempre al realizar cambios como este, y no operar con suposición o intuición.

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>Prefiere tuplas de estructura al agrupar tipos de valores pequeños

Considere las dos funciones siguientes:

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

Al comparar estas funciones con una herramienta de benchmarking estadística `runWithStructTuple` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que la función que utiliza tuplas struct se ejecuta un 40% más rápido y no asigna memoria.

Sin embargo, estos resultados no siempre serán el caso en su propio código. Si marca una `inline`función como , el código que usa tuplas de referencia puede obtener algunas optimizaciones adicionales, o el código que asignaría simplemente podría optimizarse. Siempre debe medir los resultados cuando se trata de rendimiento, y nunca operar en base a suposición o intuición.

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>Prefiere registros de estructura cuando el tipo de datos es pequeño

La regla general descrita anteriormente también se mantiene para los tipos de [registro de F](../language-reference/records.md). Tenga en cuenta los siguientes tipos de datos y funciones que los procesan:

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

Esto es similar al código de tupla anterior, pero esta vez el ejemplo utiliza registros y una función interna insertada.

Al comparar estas funciones con una herramienta de benchmarking estadística `processStructPoint` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que se ejecuta casi un 60% más rápido y no asigna nada en el montón administrado.

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>Prefiere las uniones discriminadas de estructura cuando el tipo de datos es pequeño

Las observaciones anteriores sobre el rendimiento con tuplas y registros de estructura también se mantienen para [las Uniones Discriminadas](../language-reference/discriminated-unions.md)de F. Observe el código siguiente:

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

Es común definir uniones discriminadas de un solo caso como esta para el modelado de dominios. Al comparar estas funciones con una herramienta de benchmarking estadística `structReverseName` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que se ejecuta aproximadamente un 25% más rápido que `reverseName` para cadenas pequeñas. Para cadenas grandes, ambas funcionan aproximadamente igual. Por lo tanto, en este caso, siempre es preferible usar una estructura. Como se mencionó anteriormente, medir siempre y no operar en supuestos o intuición.

Aunque en el ejemplo anterior se mostró que una unión discriminada de estructura tenía un mejor rendimiento, es común tener uniones discriminadas más grandes al modelar un dominio. Los tipos de datos más grandes como ese pueden no funcionar tan bien si son estructuras en función de las operaciones en ellos, ya que podría haber más copia.

### <a name="functional-programming-and-mutation"></a>Programación funcional y mutación

Los valores de F - son inmutables de forma predeterminada, lo que le permite evitar ciertas clases de errores (especialmente aquellos que implican simultaneidad y paralelismo). Sin embargo, en ciertos casos, con el fin de lograr una eficiencia óptima (o incluso razonable) del tiempo de ejecución o de las asignaciones de memoria, se puede implementar mejor un intervalo de trabajo mediante el uso de la mutación in situ del estado. Esto es posible de forma opcional con `mutable` F con la palabra clave.

El `mutable` uso de f- puede estar en desacuerdo con la pureza funcional. Esto es comprensible, pero la pureza funcional en todas partes puede estar en desacuerdo con los objetivos de rendimiento. Un compromiso es encapsular la mutación de tal manera que los llamadores no tengan que preocuparse por lo que sucede cuando llaman a una función. Esto le permite escribir una interfaz funcional sobre una implementación basada en mutaciones para el código crítico para el rendimiento.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Envolver código mutable en interfaces inmutables

Con la transparencia referencial como objetivo, es fundamental escribir código que no exponga el vientre mutable de las funciones críticas para el rendimiento. Por ejemplo, el código `Array.contains` siguiente implementa la función en la biblioteca principal de F.

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

Llamar a esta función varias veces no cambia la matriz subyacente, ni requiere que mantenga ningún estado mutable al consumirla. Es referencialmente transparente, a pesar de que casi todas las líneas de código que contiene utilizan mutaciones.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considere la posibilidad de encapsular datos mutables en clases

En el ejemplo anterior se utilizaba una sola función para encapsular operaciones mediante datos mutables. Esto no siempre es suficiente para conjuntos de datos más complejos. Considere los siguientes conjuntos de funciones:

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

Este código es performant, pero expone la estructura de datos basada en mutaciones que los llamadores son responsables de mantener. Esto se puede ajustar dentro de una clase sin miembros subyacentes que puedan cambiar:

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

`Closure1Table`encapsula la estructura de datos subyacente basada en mutaciones, por lo que no obliga a los llamadores a mantener la estructura de datos subyacente. Las clases son una forma eficaz de encapsular datos y rutinas basadas en mutaciones sin exponer los detalles a las personas que llaman.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Prefiere `let mutable` hacer referencia a las celdas

Las celdas de referencia son una forma de representar la referencia a un valor en lugar del propio valor. Aunque se pueden usar para código crítico para el rendimiento, no se recomiendan. Considere el ejemplo siguiente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

El uso de una celda de referencia ahora "contamina" todo el código subsiguiente con tener que desreferenciar y volver a hacer referencia a los datos subyacentes. En su `let mutable`lugar, considere:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Aparte del único punto de mutación en el centro de `acc` la expresión lambda, todo el demás código `let`que toca puede hacerlo de una manera que no es diferente al uso de un valor inmutable enlazado normal. Esto hará que sea más fácil cambiar con el tiempo.

## <a name="object-programming"></a>Programación de objetos

F- tiene soporte completo para objetos y conceptos orientados a objetos (OO). Aunque muchos conceptos de OO son potentes y útiles, no todos ellos son ideales para usar. Las siguientes listas ofrecen orientación sobre categorías de características de OO a un nivel alto.

**Considere el uso de estas características en muchas situaciones:**

* Notación`x.Length`de puntos ( )
* Miembros de la instancia
* Constructores implícitos
* Miembros estáticos
* Notación del`arr.[x]`indexador ( )
* Argumentos con nombre y opcionales
* Interfaces e implementaciones de interfaces

**No busques estas funciones primero, pero aplicalas juiciosamente cuando sean convenientes para resolver un problema:**

* Sobrecarga de métodos
* Datos mutables encapsulados
* Operadores en tipos
* Propiedades automáticas
* Implementación `IDisposable` y`IEnumerable`
* Extensiones de tipo
* Eventos
* Estructuras
* Delegados
* Enumeraciones

**Por lo general, evite estas características a menos que deba utilizarlas:**

* Jerarquías de tipos basadas en herencia y herencia de implementación
* Nulls y`Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Prefiere la composición sobre la herencia

[La composición sobre](https://en.wikipedia.org/wiki/Composition_over_inheritance) la herencia es un modismo de larga data al que puede adherirse un buen código de F. El principio fundamental es que no debe exponer una clase base y forzar a los llamadores a heredar de esa clase base para obtener funcionalidad.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Utilice expresiones de objeto para implementar interfaces si no necesita una clase

[Las expresiones](../language-reference/object-expressions.md) de objeto le permiten implementar interfaces sobre la marcha, enlazando la interfaz implementada a un valor sin necesidad de hacerlo dentro de una clase. Esto es conveniente, especialmente si _solo_ necesita implementar la interfaz y no tiene necesidad de una clase completa.

Por ejemplo, aquí está el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de `open` corrección de código si ha agregado un símbolo para el que no tiene una instrucción:

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

Dado que no hay necesidad de una clase al interactuar con la API de visual studio Code, las expresiones de objeto son una herramienta ideal para esto. También son valiosos para las pruebas unitarias, cuando se desea extraer una interfaz con rutinas de prueba de una manera ad hoc.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Considere las abreviaturas de tipo para acortar las firmas

[Las abreviaturas](../language-reference/type-abbreviations.md) de tipo son una forma cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo. Por ejemplo, el siguiente alias asigna una etiqueta a lo que se necesita para definir un cálculo con [CNTK,](https://docs.microsoft.com/cognitive-toolkit/)una biblioteca de aprendizaje profundo:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

El `Computation` nombre es una forma cómoda de denotar cualquier función que coincida con la firma que está aliasando. El uso de abreviaturas de tipo como esta es conveniente y permite un código más sucinto.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evita usar abreviaturas de tipo para representar tu dominio

Aunque las abreviaturas de tipo son convenientes para dar un nombre a las firmas de función, pueden ser confusas al abreviar otros tipos. Considere esta abreviatura:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Esto puede ser confuso de varias maneras:

* `BufferSize`no es una abstracción; es sólo otro nombre para un entero.
* Si `BufferSize` se expone en una API pública, se puede malinterpretar fácilmente para significar algo más que `int`. Por lo general, los tipos de dominio tienen `int`varios atributos y no son tipos primitivos como . Esta abreviatura viola esa suposición.
* La mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.
* Este alias no ofrece mayor claridad en comparación con proporcionar un argumento con nombre a una función.
* La abreviatura no se manifestará en IL compilado; es sólo un entero y este alias es una construcción en tiempo de compilación.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

En resumen, el escollo con abreviaturas de tipo es que **no** son abstracciones sobre los tipos que están abreviados. En el ejemplo `BufferSize` anterior, `int` es sólo un bajo las cubiertas, sin datos `int` adicionales, ni ningún beneficio del sistema de tipos además de lo que ya tiene.

Un enfoque alternativo al uso de abreviaturas de tipo para representar un dominio es usar uniones discriminadas de un solo caso. El ejemplo anterior se puede modelar de la siguiente manera:

```fsharp
type BufferSize = BufferSize of int
```

Si escribe código que funciona `BufferSize` en términos de y su valor subyacente, debe construir uno en lugar de pasar cualquier entero arbitrario:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

Esto reduce la probabilidad de pasar por `send` error un entero arbitrario `BufferSize` en la función, porque el llamador debe construir un tipo para ajustar un valor antes de llamar a la función.
