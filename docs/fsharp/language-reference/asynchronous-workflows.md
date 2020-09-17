---
title: Flujos de trabajo asincrónicos
description: 'Obtenga información sobre la compatibilidad en el lenguaje de programación de F # para realizar cálculos de forma asincrónica, que se ejecutan sin bloquear la ejecución de otro trabajo.'
ms.date: 08/15/2020
ms.openlocfilehash: 14146cc8a643f31831475075212cc06da5f8d6ff
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720275"
---
# <a name="asynchronous-workflows"></a>Flujos de trabajo asincrónicos

En este artículo se describe la compatibilidad de F # para realizar cálculos de forma asincrónica, es decir, sin bloquear la ejecución de otro trabajo. Por ejemplo, los cálculos asincrónicos se pueden usar para escribir aplicaciones que tengan interfaces de usuario que sigan respondiendo a los usuarios a medida que la aplicación realice otro trabajo.

## <a name="syntax"></a>Sintaxis

```fsharp
async { expression }
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el cálculo representado por `expression` está configurado para ejecutarse de forma asincrónica, es decir, sin bloquear el subproceso de cálculo actual cuando se realizan operaciones asincrónicas de suspensión, e/s y otras operaciones asincrónicas. A menudo, los cálculos asincrónicos se inician en un subproceso en segundo plano mientras la ejecución continúa en el subproceso actual. El tipo de la expresión es `Async<'T>` , donde `'T` es el tipo devuelto por la expresión cuando `return` se usa la palabra clave. El código en una expresión de este tipo se conoce como un *bloque asincrónico*o un *bloque asincrónico.*

Hay varias maneras de programar de forma asincrónica y la [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html) clase proporciona métodos que admiten varios escenarios. El enfoque general es crear `Async` objetos que representan el cálculo o los cálculos que desea ejecutar de forma asincrónica y, a continuación, iniciar estos cálculos mediante una de las funciones de desencadenamiento. Las distintas funciones de desencadenador proporcionan diferentes maneras de ejecutar cálculos asincrónicos y la que se usa depende de si se desea usar el subproceso actual, un subproceso en segundo plano o un objeto de tarea .NET Framework, y si hay funciones de continuación que se deben ejecutar cuando finalice el cálculo. Por ejemplo, para iniciar un cálculo asincrónico en el subproceso actual, puede usar [`Async.StartImmediate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#StartImmediate) . Cuando se inicia un cálculo asincrónico desde el subproceso de la interfaz de usuario, no se bloquea el bucle de eventos principal que procesa las acciones del usuario, como pulsaciones de teclas y actividad del mouse, para que la aplicación siga respondiendo.

## <a name="asynchronous-binding-by-using-let"></a>Enlace asincrónico mediante Let!

En un flujo de trabajo asincrónico, algunas expresiones y operaciones son sincrónicas y otras son cálculos más largos que están diseñados para devolver un resultado de forma asincrónica. Cuando se llama a un método de forma asincrónica, en lugar de un `let` enlace normal, se usa `let!` . El efecto de `let!` es permitir que la ejecución continúe en otros cálculos o subprocesos mientras se realiza el cálculo. Una vez que el lado derecho del `let!` enlace vuelve, el resto del flujo de trabajo asincrónico reanuda la ejecución.

En el código siguiente se muestra la diferencia entre `let` y `let!` . La línea de código que usa `let` simplemente crea un cálculo asincrónico como un objeto que se puede ejecutar más adelante mediante, por ejemplo, `Async.StartImmediate` o [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) . La línea de código que usa `let!` inicia el cálculo y, a continuación, el subproceso se suspende hasta que el resultado esté disponible, momento en el que continúa la ejecución.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Además de `let!` , puede usar `use!` para realizar enlaces asincrónicos. La diferencia entre `let!` y `use!` es la misma que la diferencia entre `let` y `use` . En el caso de `use!` , el objeto se desecha al cerrar el ámbito actual. Tenga en cuenta que en la versión actual del lenguaje F #, no `use!` permite inicializar un valor en null, aunque `use` sí lo hace.

## <a name="asynchronous-primitives"></a>Primitivas asincrónicas

Un método que realiza una única tarea asincrónica y devuelve el resultado se denomina *primitiva asincrónica*, y se ha diseñado específicamente para su uso con `let!` . Se definen varias primitivas asincrónicas en la biblioteca básica de F #. En el módulo se definen dos métodos de este tipo para las aplicaciones Web [`FSharp.Control.WebExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html) : [`WebRequest.AsyncGetResponse`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncGetResponse) y [`WebClient.AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) . Ambos primitivos descargan datos de una página web, dada una dirección URL. `AsyncGetResponse` genera un `System.Net.WebResponse` objeto y `AsyncDownloadString` genera una cadena que representa el código HTML de una página web.

En el módulo se incluyen varios primitivos para las operaciones de e/s asincrónicas [`FSharp.Control.CommonExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html) . Estos métodos de extensión de la `System.IO.Stream` clase son [`Stream.AsyncRead`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncRead) y [`Stream.AsyncWrite`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncWrite) .

También puede escribir sus propias primitivas asincrónicas definiendo una función cuyo cuerpo completo esté incluido en un bloque asincrónico.

Para usar métodos asincrónicos en el .NET Framework que están diseñados para otros modelos asincrónicos con el modelo de programación asincrónica de F #, se crea una función que devuelve un objeto de F # `Async` . La biblioteca de F # tiene funciones que facilitan esta tarea.

Aquí se incluye un ejemplo del uso de flujos de trabajo asíncronos. Hay muchas otras en la documentación de los métodos de la [clase asincrónica](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html).

En este ejemplo se muestra cómo usar flujos de trabajo asincrónicos para realizar cálculos en paralelo.

En el ejemplo de código siguiente, una función `fetchAsync` obtiene el texto HTML devuelto de una solicitud Web. La `fetchAsync` función contiene un bloque de código asincrónico. Cuando se realiza un enlace al resultado de una primitiva asincrónica, en este caso [`AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) , `let!` se usa en lugar de `let` .

Utilice la función [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) para ejecutar una operación asincrónica y esperar su resultado. Por ejemplo, puede ejecutar varias operaciones asincrónicas en paralelo mediante la [`Async.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#Parallel) función junto con la `Async.RunSynchronously` función. La `Async.Parallel` función toma una lista de los `Async` objetos, configura el código para que cada `Async` objeto de tarea se ejecute en paralelo y devuelve un `Async` objeto que representa el cálculo en paralelo. Al igual que en el caso de una sola operación, se llama `Async.RunSynchronously` a para iniciar la ejecución.

La `runAll` función inicia tres flujos de trabajo asincrónicos en paralelo y espera hasta que se hayan completado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de cálculo](computation-expressions.md)
- [Control. Async (clase)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html)
