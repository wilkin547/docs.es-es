---
title: Programación asincrónica
description: Obtenga información sobre cómo F# programación asincrónica se logra a través de un modelo de programación de nivel de lenguaje que sea fácil de usar y el lenguaje natural.
ms.date: 06/20/2016
ms.openlocfilehash: e18697708741eef066a76bbffe35882f3639bb68
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614485"
---
# <a name="async-programming-in-f"></a>Programación de AsyncF# #

> [!NOTE]
> Se han descubierto algunas imprecisiones en este artículo.  Se está sobrescribiendo.  Consulte [problema #666](https://github.com/dotnet/docs/issues/666) para obtener información acerca de los cambios.

Programación de Async F# puede realizarse a través de un modelo de programación de nivel de lenguaje diseñado para ser fácil de usar y el lenguaje natural.

El núcleo de la programación de async F# es `Async<'T>`, una representación de trabajo que puede activarse para ejecutar en segundo plano, donde `'T` se devuelve el tipo a través de especial `return` palabra clave o `unit` si el flujo de trabajo asincrónico no tiene ningún resultado para devolver.

El concepto clave para comprender es que el tipo de una expresión de async es `Async<'T>`, que es simplemente un _especificación_ de trabajo se realice en un contexto asincrónico. No se ejecuta hasta que lo inicie explícitamente con una de las funciones de iniciales (como `Async.RunSynchronously`). Aunque se trata de una forma diferente de reflexionar sobre cómo realizar el trabajo termina siendo bastante sencillo en la práctica.

Por ejemplo, supongamos que desea descargar el código HTML de dotnetfoundation.org sin bloquear el subproceso principal. Puede realizarlo siguiente:

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

Y listo. Aparte del uso de `async`, `let!`, y `return`, esto es normal F# código.

Hay algunas construcciones sintácticas que merece la pena tener en cuenta:

*   `let!` enlaza el resultado de una expresión de async (que se ejecuta en otro contexto).
*   `use!` funciona igual que `let!`, pero elimina sus recursos enlazados cuando sale del ámbito.
*   `do!` se espera un flujo de trabajo asincrónico que no devuelve nada.
*   `return` simplemente devuelve un resultado de una expresión de async.
*   `return!` ejecuta otro flujo de trabajo asincrónico y devuelve su valor devuelto como resultado.

Además, normal `let`, `use`, y `do` palabras clave pueden utilizarse junto con las versiones asincrónicas tal como haría en una función normal.

## <a name="how-to-start-async-code-in-f"></a>Cómo iniciar el código asincrónico enF# #

Como se mencionó anteriormente, el código asincrónico es una especificación de trabajo se realice en otro contexto que se debe iniciar explícitamente. Existen dos formas principales para lograr esto:

1.  `Async.RunSynchronously` iniciará un flujo de trabajo asincrónico en otro subproceso y espera su resultado.

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  `Async.Start` iniciar un flujo de trabajo de async en otro subproceso y, le **no** espera su resultado.

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

Hay otras maneras de iniciar un flujo de trabajo asincrónicos disponible para escenarios más específicos. Se detallan [en la referencia de Async](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Una nota en subprocesos

La frase "en otro subproceso" esté mencionada anteriormente, pero es importante saber que **esto no significa que los flujos de trabajo asincrónicos son una fachada para multithreading**. El flujo de trabajo realmente "salta" entre subprocesos, de préstamo de una pequeña cantidad de tiempo para realizar trabajo útil. Cuando un flujo de trabajo asincrónico está eficazmente "esperando" (por ejemplo, esperando una llamada de red devolver algo), se libera cualquier subproceso que se toma prestado en el momento hasta vaya realice trabajo útil en alguna otra cosa. Esto permite flujos de trabajo asincrónicos para que usen el sistema que se ejecutan en forma más eficaz posible y hace que sea especialmente seguros para escenarios de E/S de gran volumen.

## <a name="how-to-add-parallelism-to-async-code"></a>Cómo agregar paralelismo a código asincrónico

En ocasiones, es posible que necesita para realizar varias tareas asincrónicas en paralelo, recopilar sus resultados e interpretarlos de alguna manera. `Async.Parallel` permite realizar esto sin necesidad de usar la biblioteca TPL, lo que implicaría la necesidad de convertir `Task<'T>` y `Async<'T>` tipos.

En el ejemplo siguiente, se usará `Async.Parallel` para descargar el código HTML de cuatro sitios más populares en paralelo, espere a que esas tareas se completen y, a continuación, imprima el código HTML que se descargó.

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a>Consejos e información importante

*   Anexa "Async" al final de cualquier función que se va a consumir

 Aunque se trata de una convención de nomenclatura, lo facilitar las cosas como la detectabilidad de las API. Especialmente si hay versiones sincrónicas y asincrónicas de la misma rutina, es una buena idea para indicar explícitamente que es asincrónico por medio del nombre.

*   Escuchar al compilador.

 F#del compilador es muy estricto, lo que casi imposible hacer algo problemáticos, como ejecutar "async" código de forma sincrónica. Si llega a través de una advertencia, que es un inicio de sesión que el código no ejecutará cómo cree que lo hará. Si puede hacer que el compilador feliz, más probable es que se ejecutará el código según lo previsto.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Para el C#programador/VB estudiandoF# #

En esta sección se da por supuesto que está familiarizado con el modelo asincrónico en C#/VB. Si no, [de programación asincrónica en C# ](../../../csharp/async.md) es un punto de partida.

Hay una diferencia fundamental entre el C#/VB async modelo y el F# modelo asincrónico.

Cuando se llama a una función que devuelve un `Task` o `Task<'T>`, ese trabajo ya ha comenzado la ejecución. El identificador devuelto representa un trabajo asincrónico está ya en ejecución. En cambio, cuando se llama a una función asincrónica F#, `Async<'a>` devuelto representa un trabajo que será **genera** en algún momento. Descripción de este modelo es eficaz, porque permite trabajos asincrónicos en F# se pueden encadenar, realiza de forma condicional y se puede iniciar con un nivel de detalle más preciso de control.

Hay algunos otros las similitudes y diferencias cabe destacar.

### <a name="similarities"></a>Similitudes

*   `let!`, `use!`, y `do!` son análogos a `await` al llamar a un trabajo asincrónico desde una `async{ }` bloque.

 Las tres palabras clave solo se pueden usar dentro de un `async { }` bloque, similar a cómo `await` solo puede invocarse dentro de un `async` método. En resumen, `let!` es para cuando desee capturar y utilizar un resultado, `use!` es el mismo pero algo cuyos recursos deben obtener limpiados tras su uso, y `do!` es para cuando desee esperar un flujo de trabajo asincrónico sin ningún valor devuelto al finalizar antes de continuar.

*   F#admite el paralelismo de datos de forma similar.

 Aunque funciona de forma muy distinta, `Async.Parallel` corresponde a `Task.WhenAll` en el caso de que los resultados de un conjunto de trabajos asincrónicos cuando se completan.

### <a name="differences"></a>Diferencias

*   Anidar `let!` no se permite, a diferencia de anidados `await`

 A diferencia de `await`, que se pueden anidar indefinidamente, `let!` no se puede y debe tener su resultado enlazados antes de usarlo dentro de otra `let!`, `do!`, o `use!`.

*   Compatibilidad con la cancelación es más sencillo en F# que en C#/VB.

 Admitir la cancelación de una tarea a mitad de camino su ejecución en C#/VB requiere comprobación el `IsCancellationRequested` propiedad o llamar a `ThrowIfCancellationRequested()` en un `CancellationToken` objeto que se pasa al método asincrónico.

En cambio, F# flujos de trabajo asincrónicos son cancelables de manera más natural. La cancelación es un proceso sencillo de tres pasos.

1.  Cree un nuevo objeto `CancellationTokenSource`.
2.  Pasarlo a una función inicial.
3.  Llamar a `Cancel` en el token.

Ejemplo:

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }
    
let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

Y listo.

## <a name="further-resources"></a>Recursos adicionales:

*   [Flujos de trabajo asincrónicos en MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
*   [Secuencias asincrónicas paraF#](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [F#Utilidades de datos HTTP](https://fsharp.github.io/FSharp.Data/library/Http.html)