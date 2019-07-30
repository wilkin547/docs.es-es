---
title: Flujos de trabajo asincrónicos
description: Obtenga información sobre la compatibilidad F# en el lenguaje de programación para realizar cálculos de forma asincrónica, que se ejecutan sin bloquear la ejecución de otro trabajo.
ms.date: 05/16/2016
ms.openlocfilehash: 2d967f6bfe46b4f3916648b3063210d1ba1c210f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630003"
---
# <a name="asynchronous-workflows"></a>Flujos de trabajo asincrónicos

> [!NOTE]
> El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tema se describe F# la compatibilidad de para realizar cálculos de forma asincrónica, es decir, sin bloquear la ejecución de otro trabajo. Por ejemplo, los cálculos asincrónicos se pueden usar para escribir aplicaciones que tengan interfaces de usuario que sigan respondiendo a los usuarios a medida que la aplicación realice otro trabajo.

## <a name="syntax"></a>Sintaxis

```fsharp
async { expression }
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el cálculo representado por `expression` está configurado para ejecutarse de forma asincrónica, es decir, sin bloquear el subproceso de cálculo actual cuando se realizan operaciones asincrónicas de suspensión, e/s y otras operaciones asincrónicas. A menudo, los cálculos asincrónicos se inician en un subproceso en segundo plano mientras la ejecución continúa en el subproceso actual. El tipo de la expresión es `Async<'T>`, donde `'T` es el tipo devuelto por la expresión cuando `return` se usa la palabra clave. El código en una expresión de este tipo se conoce como un *bloque asincrónico*o un bloque *asincrónico.*

Hay varias maneras de programar de forma asincrónica y la [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) clase proporciona métodos que admiten varios escenarios. El enfoque general es crear `Async` objetos que representan el cálculo o los cálculos que desea ejecutar de forma asincrónica y, a continuación, iniciar estos cálculos mediante una de las funciones de desencadenamiento. Las distintas funciones de desencadenador proporcionan diferentes maneras de ejecutar cálculos asincrónicos y la que se usa depende de si se desea usar el subproceso actual, un subproceso en segundo plano o un objeto de tarea .NET Framework, y si hay continuación. funciones que se deben ejecutar cuando finaliza el cálculo. Por ejemplo, para iniciar un cálculo asincrónico en el subproceso actual, puede usar [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Cuando se inicia un cálculo asincrónico desde el subproceso de la interfaz de usuario, no se bloquea el bucle de eventos principal que procesa las acciones del usuario, como pulsaciones de teclas y actividad del mouse, para que la aplicación siga respondiendo.

## <a name="asynchronous-binding-by-using-let"></a>Enlace asincrónico mediante Let!

En un flujo de trabajo asincrónico, algunas expresiones y operaciones son sincrónicas y otras son cálculos más largos que están diseñados para devolver un resultado de forma asincrónica. Cuando se llama a un método de forma asincrónica, en lugar `let` de un enlace normal `let!`, se usa. El efecto de `let!` es permitir que la ejecución continúe en otros cálculos o subprocesos mientras se realiza el cálculo. Una vez que el lado derecho `let!` del enlace vuelve, el resto del flujo de trabajo asincrónico reanuda la ejecución.

En el código siguiente se muestra la `let` diferencia `let!`entre y. La línea de código que usa `let` simplemente crea un cálculo asincrónico como un objeto que se puede ejecutar más adelante mediante, por ejemplo, `Async.StartImmediate` o [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). La línea de código que usa `let!` inicia el cálculo y, a continuación, el subproceso se suspende hasta que el resultado esté disponible, momento en el que continúa la ejecución.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Además `let!`de, puede usar `use!` para realizar enlaces asincrónicos. La diferencia entre `let!` y `use!` es la misma que la diferencia entre `let` y `use`. En `use!`el caso de, el objeto se desecha al cerrar el ámbito actual. Tenga en cuenta que en la versión actual F# del lenguaje `use!` , no permite que un valor se inicialice en `use` null, aunque sí lo hace.

## <a name="asynchronous-primitives"></a>Primitivas asincrónicas

Un método que realiza una única tarea asincrónica y devuelve el resultado se denomina *primitiva asincrónica*, y se ha diseñado específicamente para su uso con `let!`. Se definen varias primitivas asincrónicas en la F# biblioteca principal. En el módulo [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003)se definen dos métodos de este tipo para las aplicaciones [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)Web: [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) y. Ambos primitivos descargan datos de una página web, dada una dirección URL. `AsyncGetResponse`genera un `System.Net.WebResponse` objeto y `AsyncDownloadString` genera una cadena que representa el código HTML de una página web.

En el [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) módulo se incluyen varios primitivos para las operaciones de e/s asincrónicas. Estos métodos de extensión de `System.IO.Stream` la clase [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) son [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618)y.

También puede escribir sus propias primitivas asincrónicas definiendo una función cuyo cuerpo completo esté incluido en un bloque asincrónico.

Para usar métodos asincrónicos en el .NET Framework que están diseñados para otros modelos asincrónicos con el F# modelo de programación asincrónica, cree una función que devuelva un F# `Async` objeto. La F# biblioteca tiene funciones que facilitan esta tarea.

Aquí se incluye un ejemplo del uso de flujos de trabajo asíncronos. Hay muchas otras en la documentación de los métodos de la [clase asincrónica](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

En este ejemplo se muestra cómo usar flujos de trabajo asincrónicos para realizar cálculos en paralelo.

En el ejemplo de código siguiente, una `fetchAsync` función obtiene el texto HTML devuelto de una solicitud Web. La `fetchAsync` función contiene un bloque de código asincrónico. Cuando se realiza un enlace al resultado de una primitiva asincrónica, en este caso [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), Let. se usa en lugar de Let.

Utilice la función [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar una operación asincrónica y esperar su resultado. Por ejemplo, puede ejecutar varias operaciones asincrónicas en paralelo mediante la [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) función junto con la `Async.RunSynchronously` función. La `Async.Parallel` función toma una lista de los `Async` objetos, configura el código para que cada `Async` objeto de tarea se ejecute en paralelo y devuelve un `Async` objeto que representa el cálculo en paralelo. Al igual que en el caso de una sola `Async.RunSynchronously` operación, se llama a para iniciar la ejecución.

La `runAll` función inicia tres flujos de trabajo asincrónicos en paralelo y espera hasta que se hayan completado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de cálculo](computation-expressions.md)
- [Control. Async (clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
