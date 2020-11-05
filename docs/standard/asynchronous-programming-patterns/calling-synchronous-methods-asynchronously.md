---
title: Llamar a métodos sincrónicos de forma asincrónica
description: Aprenda a llamar a métodos sincrónicos de forma asincrónica en .NET mediante los métodos BeginInvoke y EndInvoke.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- asynchronous programming, delegates
- asynchronous delegates
- AsyncWaitHandle property
- callback methods
- calling synchronous methods in asynchronous manner
- WaitHandle class, code examples
- asynchronous programming, status polling
- polling asynchronous operation status
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
- waiting for asynchronous calls
- status information [.NET], asynchronous operations
ms.assetid: 41972034-92ed-450a-9664-ab93fcc6f1fb
ms.openlocfilehash: d518e5f64096fde5c9b14222dc4fe0634e6bb7b1
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888898"
---
# <a name="calling-synchronous-methods-asynchronously"></a>Llamar a métodos sincrónicos de forma asincrónica

.NET permite llamar a cualquier método de forma asincrónica. Para ello, defina un delegado con la misma signatura que el método al que quiera llamar. Common Language Runtime define automáticamente los métodos `BeginInvoke` y `EndInvoke` para este delegado, con las signaturas adecuadas.

> [!NOTE]
> Las llamadas de delegado asincrónicas, específicamente los métodos `BeginInvoke` y `EndInvoke` , no se admiten en .NET Compact Framework.

El método `BeginInvoke` inicia la llamada asincrónica. Tiene los mismos parámetros que el método que desea ejecutar de forma asincrónica, más dos parámetros opcionales adicionales. El primer parámetro es un delegado <xref:System.AsyncCallback> que hace referencia a un método que se habrá de llamar cuando finalice la llamada asincrónica. El segundo parámetro es un objeto definido por el usuario que pasa información al método de devolución de llamada. `BeginInvoke` vuelve inmediatamente y no espera que se complete la llamada asincrónica. `BeginInvoke` devuelve <xref:System.IAsyncResult>, que se puede usar para supervisar el progreso de la llamada asincrónica.

El método `EndInvoke` recupera los resultados de la llamada asincrónica. Se puede llamar en cualquier momento después de ejecutar `BeginInvoke`. Si la llamada asincrónica no ha completado, `EndInvoke` bloquea el subproceso que realiza la llamada hasta que se completa. Entre los parámetros de `EndInvoke` se incluyen los parámetros `out` y `ref` (`<Out>` `ByRef` y `ByRef` en Visual Basic) del método que se quiere ejecutar de forma asincrónica, además de la interfaz <xref:System.IAsyncResult> devuelta por `BeginInvoke`.

> [!NOTE]
> La característica IntelliSense en Visual Studio muestra los parámetros de `BeginInvoke` y `EndInvoke`. Si no utiliza Visual Studio u otra herramienta similar, o si está utilizando C# con Visual Studio, consulte [Modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md), donde encontrará una descripción de los parámetros definidos para estos métodos.

En los ejemplos de código de este tema se muestran cuatro de las formas más comunes de utilizar los métodos `BeginInvoke` y `EndInvoke` para realizar llamadas asincrónicas. Después de llamar a `BeginInvoke` , puede hacer lo siguiente:

- Realizar algunas operaciones y, a continuación, llamar al método `EndInvoke` para que mantenga un bloqueo hasta que se complete la llamada.

- Obtener un objeto <xref:System.Threading.WaitHandle> mediante la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A?displayProperty=nameWithType> , utilizar su método <xref:System.Threading.WaitHandle.WaitOne%2A> para bloquear la ejecución hasta que se señalice <xref:System.Threading.WaitHandle> y, a continuación, llamar al método `EndInvoke`.

- Sondear el resultado <xref:System.IAsyncResult> devuelto por `BeginInvoke` para determinar cuándo se completa la llamada asincrónica y, a continuación, llamar al método `EndInvoke`.

- Pasar un delegado de un método de devolución de llamada a `BeginInvoke`. El método se ejecuta en un subproceso <xref:System.Threading.ThreadPool> una vez finalizada la llamada asincrónica. El método de devolución de llamada llama a `EndInvoke`.

> [!IMPORTANT]
> Con independencia de la técnica que utilice, llame siempre a `EndInvoke` para completar la llamada asincrónica.

## <a name="defining-the-test-method-and-asynchronous-delegate"></a>Definir el método Test y el delegado asincrónico
 En los ejemplos de código siguientes se muestran distintas maneras de llamar al mismo método de ejecución prolongada, `TestMethod`, de forma asincrónica. El método `TestMethod` muestra un mensaje en la consola para indicar que ha comenzado el procesamiento, espera unos segundos y, a continuación, finaliza. `TestMethod` tiene un parámetro `out` para mostrar la manera en que esos parámetros se agregan a las firmas de `BeginInvoke` y `EndInvoke`. Los parámetros `ref` se pueden controlar de manera similar.

 En el ejemplo de código siguiente se muestra la definición de `TestMethod` y el delegado denominado `AsyncMethodCaller` que se puede utilizar para llamar a `TestMethod` de forma asincrónica. Para compilar cualquiera de los ejemplos de código, debe incluir las definiciones del método `TestMethod` y el delegado `AsyncMethodCaller` .

 [!code-cpp[AsyncDelegateExamples#1](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/TestMethod.cpp#1)]
 [!code-csharp[AsyncDelegateExamples#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/TestMethod.cs#1)]
 [!code-vb[AsyncDelegateExamples#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/TestMethod.vb#1)]

## <a name="waiting-for-an-asynchronous-call-with-endinvoke"></a>Esperar una llamada asincrónica con EndInvoke
 La manera más sencilla de ejecutar un método de forma asincrónica es empezar a ejecutar el método llamando al método `BeginInvoke` del delegado, hacer algún trabajo en el subproceso principal y, a continuación, llamar al método `EndInvoke` del delegado. `EndInvoke` podrían bloquear el subproceso que realiza la llamada porque no vuelve hasta que no se completa la llamada asincrónica. Ésta es una buena técnica para utilizarla con operaciones de archivos o red.

> [!IMPORTANT]
> Dado que `EndInvoke` podría mantener un bloqueo, nunca debe llamar a este método desde los subprocesos que dan servicio a la interfaz de usuario.

 [!code-cpp[AsyncDelegateExamples#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/EndInvoke.cpp#2)]
 [!code-csharp[AsyncDelegateExamples#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/EndInvoke.cs#2)]
 [!code-vb[AsyncDelegateExamples#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/EndInvoke.vb#2)]

## <a name="waiting-for-an-asynchronous-call-with-waithandle"></a>Esperar una llamada asincrónica con WaitHandle
 Puede obtener un objeto <xref:System.Threading.WaitHandle> utilizando la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> de <xref:System.IAsyncResult> devuelta por `BeginInvoke`. <xref:System.Threading.WaitHandle> se señaliza cuando finaliza la llamada asincrónica y puede esperar a que termine llamando al método <xref:System.Threading.WaitHandle.WaitOne%2A> .

 Si utiliza un objeto <xref:System.Threading.WaitHandle>, puede realizar otros procesamientos adicionales antes o después de que se complete la llamada asincrónica, pero antes de llamar al método `EndInvoke` para recuperar los resultados.

> [!NOTE]
> El identificador de espera no se cierra automáticamente cuando llama a `EndInvoke`. Si libera todas las referencias al identificador de espera, se liberarán los recursos del sistema cuando la recolección de elementos no utilizados reclame el identificador de espera. Para liberar los recursos del sistema tan pronto como se deje de utilizar el identificador de espera, elimínelo llamando al método <xref:System.Threading.WaitHandle.Close%2A?displayProperty=nameWithType> . La recolección de elementos no utilizados funciona más eficazmente cuando los objetos descartables se eliminan de forma explícita.

 [!code-cpp[AsyncDelegateExamples#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/waithandle.cpp#3)]
 [!code-csharp[AsyncDelegateExamples#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/waithandle.cs#3)]
 [!code-vb[AsyncDelegateExamples#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/WaitHandle.vb#3)]

## <a name="polling-for-asynchronous-call-completion"></a>Sondear la finalización de una llamada asincrónica
 Puede utilizar la propiedad <xref:System.IAsyncResult.IsCompleted%2A> del objeto <xref:System.IAsyncResult> devuelto por `BeginInvoke` para detectar el momento en que se completa la llamada asincrónica. Puede hacer esto último cuando realice la llamada asincrónica desde un subproceso que dé servicio a la interfaz de usuario. Sondear la finalización de una llamada asincrónica permite al subproceso de llamada seguirse ejecutando mientras la llamada asincrónica se ejecuta en un subproceso <xref:System.Threading.ThreadPool> .

 [!code-cpp[AsyncDelegateExamples#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/polling.cpp#4)]
 [!code-csharp[AsyncDelegateExamples#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/polling.cs#4)]
 [!code-vb[AsyncDelegateExamples#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/polling.vb#4)]

## <a name="executing-a-callback-method-when-an-asynchronous-call-completes"></a>Ejecutar un método de devolución de llamada cuando finaliza una llamada asincrónica
 Si no es necesario que el subproceso que inicia la llamada asincrónica sea el mismo que procesa los resultados, puede ejecutar un método de devolución de llamada cuando se complete la llamada. El método de devolución de llamada se ejecuta en un subproceso <xref:System.Threading.ThreadPool> .

 Para utilizar un método de devolución de llamada, debe pasar al método `BeginInvoke` un delegado <xref:System.AsyncCallback> que represente al método de devolución de llamada. También puede pasar un objeto que contenga la información que va a utilizar el método de devolución de llamada. En el método de devolución de llamada, puede convertir <xref:System.IAsyncResult>, que es el único parámetro del método de devolución de llamada, en un objeto <xref:System.Runtime.Remoting.Messaging.AsyncResult> . A continuación, puede utilizar la propiedad <xref:System.Runtime.Remoting.Messaging.AsyncResult.AsyncDelegate%2A?displayProperty=nameWithType> para obtener el delegado que se utilizó para iniciar la llamada y, de ese modo, pueda llamar a `EndInvoke`.

 Notas sobre el ejemplo:

- El parámetro `threadId` de `TestMethod` es un parámetro `out` (`<Out>` `ByRef` en Visual Basic), por lo que `TestMethod` nunca usa el valor de entrada. Una variable ficticia se pasa a la llamada a `BeginInvoke` . Si el parámetro `threadId` fuera un parámetro `ref` (`ByRef` en Visual Basic), la variable tendría que ser un campo de nivel de clase para que pudiera pasarse a los métodos `BeginInvoke` y `EndInvoke`.

- La información de estado que se pasa a `BeginInvoke` es una cadena de formato, que el método de devolución de llamada utiliza para dar formato a un mensaje de salida. Dado que se pasa como un tipo <xref:System.Object>, la información de estado tiene que convertirse a su tipo apropiado antes de poderse utilizar.

- La devolución de llamada se realiza en un subproceso <xref:System.Threading.ThreadPool> . Los subprocesos<xref:System.Threading.ThreadPool> son subprocesos en segundo plano, que no mantienen la aplicación en ejecución si el subproceso principal finaliza, por lo que el subproceso principal del ejemplo debe permanecer en suspensión el tiempo suficiente para que la devolución de llamada finalice.

 [!code-cpp[AsyncDelegateExamples#5](../../../samples/snippets/cpp/VS_Snippets_CLR/AsyncDelegateExamples/cpp/callback.cpp#5)]
 [!code-csharp[AsyncDelegateExamples#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDelegateExamples/CS/callback.cs#5)]
 [!code-vb[AsyncDelegateExamples#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDelegateExamples/VB/callback.vb#5)]

## <a name="see-also"></a>Vea también

- <xref:System.Delegate>
- [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)
