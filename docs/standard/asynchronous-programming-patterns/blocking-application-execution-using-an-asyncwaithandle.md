---
title: Bloquear la ejecución de una aplicación mediante AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
ms.openlocfilehash: 16b5a297c13cd9096548ed489e4994b72a48da67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121427"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Bloquear la ejecución de una aplicación mediante AsyncWaitHandle
Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación. Use una de las opciones siguientes para bloquear el subproceso principal de la aplicación mientras se espera a que se complete una operación asincrónica:  
  
- Use la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin**_OperationName_ de la operación asincrónica. Este método se muestra en este tema.  
  
- Llamar al método **End**_OperationName_ para operaciones asincrónicas. Para ver un ejemplo que ilustre este método, consulte [Bloquear la ejecución de una aplicación al finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Las aplicaciones que usan uno o varios objetos <xref:System.Threading.WaitHandle> para el bloqueo hasta que se completa una operación asincrónica normalmente llamarán al método **Begin**_OperationName_, realizarán cualquier trabajo que se pueda realizar sin los resultados de la operación y luego se bloquearán hasta que se completen las operaciones asincrónicas. Una aplicación puede bloquearse en una sola operación si llama a uno de los métodos <xref:System.Threading.WaitHandle.WaitOne%2A> con el uso de <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Para realizar el bloqueo mientras se espera a que finalicen una serie de operaciones asincrónicas, almacene los objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> asociados en una matriz y llame a uno de los métodos <xref:System.Threading.WaitHandle.WaitAll%2A>. Para realizar el bloqueo mientras se espera a que finalice cualquier serie de operaciones asincrónicas, almacene los objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> asociados en una matriz y llame a uno de los métodos <xref:System.Threading.WaitHandle.WaitAny%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase DNS para recuperar información del sistema de nombres de dominio de un equipo especificado por el usuario. En el ejemplo se muestra el bloqueo con el uso del método <xref:System.Threading.WaitHandle> asociado con la operación asincrónica. Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` y `stateObject`, porque estos no son necesarios cuando se usa este método.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
