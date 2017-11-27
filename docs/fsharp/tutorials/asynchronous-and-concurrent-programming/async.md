---
title: "Programación asincrónica en F #"
description: "Obtenga información acerca de cómo programación asincrónica de F # se lleva a cabo a través de un modelo de programación de nivel de lenguaje que sea fácil de usar y el lenguaje natural."
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: 23528d84d0f28283868a1ea316953543d0fd566a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="async-programming-in-f"></a>Programación asincrónica en F # #

> [!NOTE]
> Se han descubierto algunos imprecisiones en este artículo.  Se está sobrescribiendo.  Vea [problema #666](https://github.com/dotnet/docs/issues/666) para obtener información acerca de los cambios.

Programación en F # asincrónico puede realizarse a través de un modelo de programación de nivel de lenguaje está diseñado para ser fácil de usar y el lenguaje natural.

El núcleo de la programación asincrónica en F # es `Async<'T>`, una representación de trabajo que se puede programar para ejecutarse en segundo plano, donde `'T` se devuelve el tipo a través de especial `return` palabra clave o `unit` si el flujo de trabajo asincrónico no tiene ningún resultados para devolver.

El concepto clave para comprender es que es el tipo de una expresión de async `Async<'T>`, que es simplemente un _especificación_ de trabajo se realice en un contexto asincrónico. No se ejecuta hasta que lo inicie explícitamente con una de las funciones de iniciales (como `Async.RunSynchronously`). Aunque se trata de una forma diferente de pensar en realizar el trabajo, lo que acabe siendo bastante simple en la práctica.

Por ejemplo, supongamos que desea descargar el código HTML de dotnetfoundation.org sin bloquear el subproceso principal. Puedes conseguir similar al siguiente:

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

let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

Y listo. Aparte del uso de `async`, `let!`, y `return`, se trata de código de F # solo normales.

Hay algunas construcciones sintácticas que se debe tener en cuenta:

*   `let!`enlaza el resultado de una expresión de async (que se ejecuta en otro contexto).
*   `use!`funciona igual que `let!`, pero elimina sus recursos enlazados cuando sale del ámbito.
*   `do!`esperar a un flujo de trabajo asincrónico que no devuelve nada.
*   `return`simplemente devuelve un resultado de una expresión asincrónica.
*   `return!`ejecuta otro flujo de trabajo asincrónico y devuelve su valor devuelto como resultado.

Además, normal `let`, `use`, y `do` palabras clave puede utilizarse junto con las versiones asincrónicas igual que lo harían en una función normal.

## <a name="how-to-start-async-code-in-f"></a>Cómo iniciar código asincrónico en F # #

Como se mencionó anteriormente, código asincrónico es una especificación de trabajo que se va a realizarse en otro contexto que tiene que iniciarse de forma explícita. Estas son dos métodos principales para lograr esto:

1.  `Async.RunSynchronously`iniciará un flujo de trabajo asincrónico en otro subproceso y espera su resultado.

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
 let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  `Async.Start`se inicia un flujo de trabajo asincrónico en otro subproceso y le **no** espera su resultado.

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

Hay otras maneras de iniciar un flujo de trabajo asincrónico disponible para escenarios más específicos. Que se explican con detalle [en la referencia de Async](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Una nota en subprocesos

La frase "en otro subproceso" esté mencionada anteriormente, pero es importante saber que **esto no significa que los flujos de trabajo asincrónicos son una fachada para multithreading**. El flujo de trabajo realmente "salta" entre los subprocesos, préstamo una pequeña cantidad de tiempo en realizar trabajo útil. Cuando un flujo de trabajo asincrónico eficazmente "espera" (por ejemplo, esperando una llamada de red devolver algo), se libera cualquier subproceso que se toma prestado en el momento hasta vaya realice trabajo útil en otra cosa. Esto permite que los flujos de trabajo asincrónico que utilizar el sistema que se ejecutan de forma más eficaz posible y hace que sean especialmente buenas para escenarios de E/S de gran volumen.

## <a name="how-to-add-parallelism-to-async-code"></a>Cómo agregar paralelismo al código asincrónico

A veces puede necesita para realizar varias tareas asincrónicas en paralelo, recopilar sus resultados e interpretarlos de alguna manera. `Async.Parallel`le permite hacerlo sin necesidad de usar la biblioteca TPL, lo que implicaría la necesidad de coerce `Task<'T>` y `Async<'T>` tipos.

En el ejemplo siguiente, se utilizará `Async.Parallel` para descargar el código HTML de los sitios más frecuentados cuatro en paralelo, espere a que esas tareas se completen y, a continuación, imprima el código HTML que se descargó.

```fsharp
open System
open System.Net

let urlList = 
    [ "http://www.microsoft.com"
      "http://www.google.com"
      "http://www.amazon.com"
      "http://www.facebook.com" ]

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

*   Anexa "Async" al final de las funciones que podrá consumir

 Aunque se trata de una convención de nomenclatura, lo facilitar las cosas como la detectabilidad de API. Especialmente si hay versiones sincrónicas y asincrónicas de la misma rutina, resulta una buena idea para indicar explícitamente que es asincrónica mediante el nombre.

*   Realizar escuchas para el compilador.

 Compilador de F # es muy estricta, lo que sea casi imposible hacer algo troubling como ejecutar código de "async" de forma sincrónica. Si llega a través de una advertencia, que es un inicio de sesión que el código no ejecute crea que hará lo siguiente. Si puede hacer que el compilador satisfecho, más probable es que se ejecutará el código según lo previsto.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Para C# /VB programador estudiando F # #

En esta sección se supone que está familiarizado con el modelo asincrónico en C# / VB. Si no, [de programación asincrónica en C#](../../../csharp/async.md) es un punto de partida.

Hay una diferencia fundamental entre el modelo de C# /VB asincrónico y el modelo asincrónico de F #.

Cuando se llama a una función que devuelve un `Task` o `Task<'T>`, que el trabajo ya ha comenzado la ejecución. El identificador devuelto representa una tarea asincrónica ya se está ejecutando. En cambio, cuando se llama a una función asincrónica en F #, la `Async<'a>` devuelto representa un trabajo que será **generado** en algún momento. Descripción de este modelo es eficaz, porque permite trabajos asincrónicos en F # para que se pueden encadenar juntos, realiza de forma condicional y puede iniciar con una granularidad más fina del control.

Hay algunas otras similitudes y diferencias que hay que tener en cuenta.

### <a name="similarities"></a>Similitudes

*   `let!`, `use!`, y `do!` son análogos a `await` al llamar a un trabajo asincrónico desde una `async{ }` bloque.

 Las tres palabras clave solo pueden utilizarse dentro de un `async { }` bloque, similar a cómo `await` sólo se puede invocar dentro de un `async` método. En resumen, `let!` es adecuada cuando desea capturar y utilizar un resultado, `use!` es el mismo, pero lo que se deben obtener limpiar cuyos recursos después de que se utiliza, y `do!` es adecuada cuando desea esperar a un flujo de trabajo asincrónico sin ningún valor devuelto para finalizar antes de continuar.

*   F # admite el paralelismo de datos de una manera similar.

 Aunque funciona de forma muy diferente, `Async.Parallel` corresponde a `Task.WhenAll` en el caso de que los resultados de un conjunto de trabajos asincrónicos cuando se completen.

### <a name="differences"></a>Diferencias

*   Anidar `let!` no permitido, a diferencia de anidados`await`

 A diferencia de `await`, que se pueden anidar indefinidamente, `let!` no se puede y debe tener su resultado enlazado antes de usarlo dentro de otro `let!`, `do!`, o `use!`.

*   Compatibilidad con la cancelación es más sencillo en F # que en C# / VB.

 Admitir la cancelación de una mitad de la tarea a través de su ejecución en C# /VB requiere la comprobación de la `IsCancellationRequested` propiedad o llamar a `ThrowIfCancellationRequested()` en un `CancellationToken` objeto que se haya pasado al método asincrónico.

En cambio, F # asincrónico los flujos de trabajo son más natural cancelables. Cancelación es un proceso sencillo de tres pasos.

1.  Cree un nuevo objeto `CancellationTokenSource`.
2.  Pasar dicho valor en una función inicial.
3.  Llamar a `Cancel` en el token.

Ejemplo:

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

Y listo.

## <a name="further-resources"></a>Recursos adicionales:

*   [Flujos de trabajo asincrónicos en MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
*   [Secuencias asincrónicas para F #](http://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [Utilidades de F # datos HTTP](https://fsharp.github.io/FSharp.Data/library/Http.html)
