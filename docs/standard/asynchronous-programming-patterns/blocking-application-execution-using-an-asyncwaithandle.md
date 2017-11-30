---
title: "Bloquear la ejecución de una aplicación mediante AsyncWaitHandle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Bloquear la ejecución de una aplicación mediante AsyncWaitHandle
Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación. Para bloquear el subproceso principal de la aplicación mientras se espera que se complete una operación asincrónica, use una de las siguientes opciones:  
  
-   Use la <xref:System.IAsyncResult.AsyncWaitHandle%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método. Este enfoque se muestra en este tema.  
  
-   Llame a la operación asincrónica **final** *OperationName* método. Para obtener un ejemplo que muestra este enfoque, consulte [bloquear ejecución de la aplicación al finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Las aplicaciones que utilizan uno o varios <xref:System.Threading.WaitHandle> objetos para bloquear hasta que se complete una operación asincrónica normalmente llamarán a la **comenzar** *OperationName* método, realizar ningún trabajo que se pueden realizar sin los resultados de la operación y, a continuación, se bloquean hasta que la operación asincrónica se complete. Una aplicación puede bloquear en una sola operación mediante una llamada a uno de los <xref:System.Threading.WaitHandle.WaitOne%2A> métodos mediante el <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Para bloquear mientras se espera un conjunto de operaciones asincrónicas que se complete, almacenar asociado <xref:System.IAsyncResult.AsyncWaitHandle%2A> objetos en una matriz y llame a uno de los <xref:System.Threading.WaitHandle.WaitAll%2A> métodos. Para bloquear mientras se espera uno de un conjunto de operaciones asincrónicas que se complete, almacenar asociado <xref:System.IAsyncResult.AsyncWaitHandle%2A> objetos en una matriz y llame a uno de los <xref:System.Threading.WaitHandle.WaitAny%2A> métodos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar métodos asincrónicos en la clase DNS para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario. En el ejemplo se muestra el bloqueo utilizando el <xref:System.Threading.WaitHandle> asociado a la operación asincrónica. Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` y `stateObject` parámetros ya no son necesarios cuando se usa este enfoque.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
