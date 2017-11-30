---
title: "Bloquear la ejecución de una aplicación al finalizar una operación asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Bloquear la ejecución de una aplicación al finalizar una operación asincrónica
Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación. Para bloquear el subproceso principal de la aplicación mientras se espera que se complete una operación asincrónica, use una de las siguientes opciones:  
  
-   Llamar a las operaciones asincrónicas **final** *OperationName* método. Este enfoque se muestra en este tema.  
  
-   Use la <xref:System.IAsyncResult.AsyncWaitHandle%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método. Para obtener un ejemplo que muestra este enfoque, consulte [bloqueo de aplicación de ejecución mediante un AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Las aplicaciones que utilizan el **final** *OperationName* método para bloquear hasta que se complete una operación asincrónica normalmente llamará el **comenzar**  *OperationName* método, realizar ningún trabajo que se puede realizar sin los resultados de la operación y, a continuación, llame a **final** *OperationName*.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario. Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` y `stateObject` parámetros porque estos argumentos no son necesarios cuando se usa este enfoque.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
