---
title: Flujos de trabajo asincrónicos (F#)
description: Obtenga información sobre la compatibilidad en el F# lenguaje de programación para realizar cálculos de forma asincrónica, que se ejecutan sin bloquear la ejecución de otro trabajo.
ms.date: 05/16/2016
ms.openlocfilehash: 720996106d2b90392eacc75eb99147691ee83334
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297080"
---
# <a name="asynchronous-workflows"></a>Flujos de trabajo asincrónicos

> [!NOTE]
> El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Este tema describe la compatibilidad en F# para realizar cálculos de forma asincrónica, es decir, sin bloquear la ejecución de otro trabajo. Por ejemplo, los cálculos asincrónicos pueden usarse para escribir aplicaciones que tienen interfaces de usuario que sigan respondiendo a los usuarios mientras la aplicación realiza otro trabajo.

## <a name="syntax"></a>Sintaxis

```fsharp
async { expression }
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el cálculo se representa mediante `expression` está configurado para ejecutar de forma asincrónica, es decir, sin bloquear el subproceso de cálculo actual cuando se realizan operaciones de suspensión asincrónica, la E/S y otras operaciones asincrónicas. Los cálculos asincrónicos suelen iniciarse en un subproceso en segundo plano mientras continúa la ejecución en el subproceso actual. El tipo de la expresión es `Async<'T>`, donde `'T` es el tipo devuelto por la expresión cuando el `return` se utiliza la palabra clave. El código de dicha expresión se conoce como un *bloque asincrónico*, o *bloque async*.

Hay una gran variedad de formas de programación asincrónica y el [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) clase proporciona métodos que admiten varios escenarios. El enfoque general consiste en crear `Async` objetos que representan los cálculos que se desean ejecutar de forma asincrónica y, a continuación, inician estos cálculos mediante una de las funciones de desencadenamiento. Las distintas funciones de desencadenamiento proporcionan diferentes maneras de ejecutar los cálculos asincrónicos y que utilice depende de si desea usar el subproceso actual, un subproceso en segundo plano o un objeto de tarea de .NET Framework, y determinar si hay continuación funciones que deben ejecutarse cuando finaliza el cálculo. Por ejemplo, para iniciar un cálculo asincrónico en el subproceso actual, puede usar [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Cuando se inicia un cálculo asincrónico desde el subproceso de interfaz de usuario, no bloquean el bucle de eventos principal que procesa las acciones del usuario, como pulsaciones de teclas y la actividad del mouse, por lo que la aplicación sigue respondiendo.

## <a name="asynchronous-binding-by-using-let"></a>¡Enlace asincrónico mediante let!

En un flujo de trabajo asincrónico, algunas expresiones y operaciones son sincrónicas, y algunas son más largas que están diseñadas para devolver un resultado de forma asincrónica. Cuando se llama a un método de forma asincrónica, en lugar de una normal `let` enlace, use `let!`. El efecto de `let!` consiste en habilitar la ejecución continúe en otros cálculos o subprocesos, tal como se realiza el cálculo. Después de la parte derecha de la `let!` devuelve el enlace, el resto del flujo de trabajo asincrónico reanuda la ejecución.

El código siguiente muestra la diferencia entre `let` y `let!`. La línea de código que usa `let` simplemente crea un cálculo asincrónico como un objeto que se puede ejecutar más adelante mediante el uso, por ejemplo, `Async.StartImmediate` o [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). La línea de código que usa `let!` inicia el cálculo y, a continuación, se suspende el subproceso hasta que el resultado está disponible, en qué punto la ejecución continúa.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Además `let!`, puede usar `use!` para realizar enlaces asíncronos. La diferencia entre `let!` y `use!` es igual que la diferencia entre `let` y `use`. Para `use!`, se elimina el objeto al final del ámbito actual. Tenga en cuenta que en la actual versión de la F# lenguaje, `use!` no permite un valor que se inicializa en null, aunque `use` does.

## <a name="asynchronous-primitives"></a>Primitivos asincrónicos

Se llama a un método que realiza una sola tarea asincrónica y devuelve el resultado un *primitivo asincrónico*, y están diseñadas específicamente para su uso con `let!`. Varios elementos primitivos asincrónicos se definen en el F# biblioteca principal. Dos de estos métodos para las aplicaciones Web se definen en el módulo [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) y [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Ambos tipos primitivos descargan datos desde una página Web, dada una dirección URL. `AsyncGetResponse` genera un `System.Net.WebResponse` objeto, y `AsyncDownloadString` genera una cadena que representa el código HTML de una página Web.

Varios elementos primitivos para operaciones de E/S asincrónicas se incluyen en el [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) módulo. Estos métodos de extensión de la `System.IO.Stream` clase [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) y [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

También puede escribir a sus propios tipos primitivos asincrónicos definiendo una función cuyo cuerpo está incluido en un bloque async.

Para usar los métodos asincrónicos en .NET Framework que están diseñados para otros modelos asincrónicos con el F# modelo de programación asincrónica, crea una función que devuelve un F# `Async` objeto. El F# biblioteca tiene funciones que facilitan esta tarea.

Un ejemplo del uso de flujos de trabajo asincrónicos se incluye aquí; Hay muchas otras en la documentación de los métodos de la [clase Async](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

En este ejemplo se muestra cómo usar flujos de trabajo asincrónicos para realizar cálculos en paralelo.

En el ejemplo de código siguiente, una función `fetchAsync` Obtiene el texto HTLM se devuelve de una solicitud Web. El `fetchAsync` función contiene un bloque de código asincrónico. Cuando se realiza un enlace al resultado de un tipo primitivo asincrónico, en este caso [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), let! se utiliza en lugar de let.

Use la función [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar una operación asincrónica y esperar su resultado. Por ejemplo, puede ejecutar varias operaciones asincrónicas en paralelo mediante la [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) función junto con el `Async.RunSynchronously` función. El `Async.Parallel` función toma una lista de los `Async` los objetos, Establece el código para cada `Async` que se ejecute en paralelo y devuelve el objeto de tarea un `Async` objeto que representa el cálculo en paralelo. Al igual que para una sola operación, llame a `Async.RunSynchronously` para iniciar la ejecución.

El `runAll` función inicia tres flujos de trabajo asincrónicos en paralelo y espera hasta que todos hayan finalizado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de cálculo](computation-expressions.md)
- [Control.Async clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
