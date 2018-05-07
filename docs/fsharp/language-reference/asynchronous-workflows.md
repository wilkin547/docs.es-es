---
title: Flujos de trabajo asincrónicos (F#)
description: 'Obtenga información acerca del soporte técnico en el lenguaje de programación para realizar cálculos de forma asincrónica, F # que se ejecutan sin bloquear la ejecución de otro trabajo.'
ms.date: 05/16/2016
ms.openlocfilehash: 5f7a1a623e143e1bedf51c1a1ed477bb867b280a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-workflows"></a>Flujos de trabajo asincrónicos

> [!NOTE]
El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Este tema describe la compatibilidad de F # para realizar cálculos de forma asincrónica, es decir, sin bloquear la ejecución de otro trabajo. Por ejemplo, los cálculos asincrónicos se pueden utilizar para escribir aplicaciones que tienen interfaces de usuario que sigan respondiendo a los usuarios mientras la aplicación realiza otro trabajo.

## <a name="syntax"></a>Sintaxis

```fsharp
async { expression }
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el cálculo se representa mediante `expression` está configurado para ejecutar de forma asincrónica, es decir, sin bloquear el subproceso de cálculo actual cuando se realizan operaciones de suspensión asincrónica, la E/S y otras operaciones asincrónicas. A menudo, los cálculos asincrónicos se inician en un subproceso en segundo plano mientras continúa la ejecución en el subproceso actual. El tipo de la expresión es `Async<'T>`, donde `'T` es el tipo devuelto por la expresión cuando el `return` se utiliza la palabra clave. El código de dicha expresión se conoce como un *bloque asincrónico*, o *bloque asincrónico*.

Hay una variedad de formas de programación asincrónica y el [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) clase proporciona métodos que admiten varios escenarios. El enfoque general consiste en crear `Async` objetos que representan el cálculo o los cálculos que se va a ejecutar de forma asincrónica y, a continuación, inician estos cálculos mediante una de las funciones de activación. Las diversas funciones desencadenadoras proporcionan diferentes maneras de ejecución de cálculos asincrónicos y que utilice depende de si desea usar el subproceso actual, un subproceso en segundo plano o un objeto de tarea de .NET Framework, y determinar si hay continuación funciones que deben ejecutarse cuando finaliza el cálculo. Por ejemplo, para iniciar un cálculo asincrónico en el subproceso actual, puede usar [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Cuando se inicia un cálculo asincrónico desde el subproceso de interfaz de usuario, no se bloquean el bucle de eventos principal que procesa las acciones del usuario, como pulsaciones de teclas y la actividad del mouse, por lo que la aplicación sigue respondiendo.

## <a name="asynchronous-binding-by-using-let"></a>¡Enlace asincrónico mediante let!

En un flujo de trabajo asincrónico, algunas expresiones y operaciones son sincrónicas y otras son más largas que están diseñados para devolver un resultado de forma asincrónica. Cuando se llama a un método de forma asincrónica, en lugar de una normal `let` enlace, use `let!`. El efecto de `let!` es permitir que continúe en otros cálculos o subprocesos, tal y como se realiza el cálculo de la ejecución. Después de la derecha de la `let!` devuelve el enlace, el resto del flujo de trabajo asincrónico reanuda la ejecución.

El código siguiente muestra la diferencia entre `let` y `let!`. La línea de código que usa `let` simplemente crea un cálculo asincrónico como un objeto que se puede ejecutar más adelante mediante, por ejemplo, `Async.StartImmediate` o [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). La línea de código que usa `let!` inicia el cálculo y, a continuación, se suspende el subproceso hasta que el resultado esté disponible, en qué punto de la ejecución continúa.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Además `let!`, puede usar `use!` para realizar enlaces asincrónicos. La diferencia entre `let!` y `use!` es igual que la diferencia entre `let` y `use`. Para `use!`, se elimina el objeto al final del ámbito actual. Tenga en cuenta que en la versión actual del lenguaje de F #, `use!` no permite un valor que se inicializa como null, aunque `use` does.

## <a name="asynchronous-primitives"></a>Métodos primitivos asincrónicos

Se llama a un método que realiza una sola tarea asincrónica y devuelve el resultado un *primitivo asincrónico*, y estos están diseñados específicamente para su uso con `let!`. Varios métodos primitivos asincrónicos se definen en la biblioteca básica de F #. Dos de estos métodos para las aplicaciones Web se definen en el módulo [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) y [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Ambos métodos primitivos descargan datos desde una página Web, especificar una dirección URL. `AsyncGetResponse` genera un `System.Net.WebResponse` objeto, y `AsyncDownloadString` genera una cadena que representa el código HTML de una página Web.

Varias primitivas para operaciones de E/S asincrónicas se incluyen en el [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) módulo. Estos métodos de extensión de la `System.IO.Stream` clase [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) y [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

Primitivas asincrónicas adicionales están disponibles en la [F # PowerTools](https://fsprojects.github.io/VisualFSharpPowerTools/). También puede escribir a sus propios métodos primitivos asincrónicos definiendo una función cuyo cuerpo completo se incluye en un bloque asincrónico.

Para usar métodos asincrónicos de .NET Framework que se han diseñado para otros modelos asincrónicos con el modelo de programación asincrónico de F #, cree una función que devuelve una F # `Async` objeto. La biblioteca de F # tiene funciones que facilitan este proceso realizar.

Aquí, y se incluye un ejemplo del uso de flujos de trabajo asincrónicos Hay muchas otras en la documentación de los métodos de la [Async (clase)](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

En este ejemplo se muestra cómo usar flujos de trabajo asincrónicos para realizar cálculos en paralelo.

En el ejemplo de código siguiente, una función `fetchAsync` Obtiene el texto HTLM devuelto por una solicitud Web. El `fetchAsync` función contiene un bloque de código asincrónico. Cuando se realiza un enlace con el resultado de un método primitivo asincrónico, en este caso [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), permiten! se utiliza en lugar de let.

Use la función [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar una operación asincrónica y espera su resultado. Por ejemplo, puede ejecutar varias operaciones asincrónicas en paralelo mediante la [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) funciona junto con el `Async.RunSynchronously` función. El `Async.Parallel` función toma una lista de los `Async` los objetos, configura el código para cada `Async` que se ejecute en paralelo y devuelve el objeto de tarea un `Async` objeto que representa el cálculo en paralelo. Como ocurre con una sola operación, se llama a `Async.RunSynchronously` para iniciar la ejecución.

El `runAll` función inicia tres flujos de trabajo asincrónicos en paralelo y espera hasta que todos hayan finalizado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)

[Expresiones de cálculo](computation-expressions.md)

[Control.Async (clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
