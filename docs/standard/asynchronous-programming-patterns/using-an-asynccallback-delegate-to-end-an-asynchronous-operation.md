---
title: "Utilizar un delegado AsyncCallback para finalizar una operación asincrónica"
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Utilizar un delegado AsyncCallback para finalizar una operación asincrónica
Las aplicaciones que pueden hacer otro trabajo mientras esperan los resultados de una operación asincrónica no deberían bloquear la espera hasta que se complete la operación. Use una de las siguientes opciones para seguir ejecutando instrucciones mientras se espera que se complete una operación asincrónica:  
  
-   Use un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente. Este enfoque se muestra en este tema.  
  
-   Use la <xref:System.IAsyncResult.IsCompleted%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método para determinar si se ha completado la operación. Para obtener un ejemplo que muestra este enfoque, consulte [sondear el estado de una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio (DNS) para equipos especificados por el usuario. Este ejemplo se crea un <xref:System.AsyncCallback> delegado que hace referencia el `ProcessDnsInformation` método. Este método se llama una vez por cada solicitud asincrónica para obtener información de DNS.  
  
 Tenga en cuenta que el host especificado por el usuario se pasa a la <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> parámetro. Para obtener un ejemplo que muestra cómo definir y utilizar un objeto de estado más complejo, consulte [mediante un delegado AsyncCallback y un objeto de estado](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)  
 [Llamar a métodos asincrónicos mediante IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [Utilizar un delegado AsyncCallback y un objeto State](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
