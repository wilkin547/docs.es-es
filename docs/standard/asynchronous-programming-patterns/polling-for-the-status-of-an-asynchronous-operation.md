---
title: "Sondear el estado de una operación asincrónica"
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Sondear el estado de una operación asincrónica
Las aplicaciones que pueden hacer otro trabajo mientras esperan los resultados de una operación asincrónica no deberían bloquear la espera hasta que se complete la operación. Use una de las siguientes opciones para seguir ejecutando instrucciones mientras se espera que se complete una operación asincrónica:  
  
-   Use la <xref:System.IAsyncResult.IsCompleted%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método para determinar si se ha completado la operación. Este enfoque se conoce como sondeo y se muestra en este tema.  
  
-   Use un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente. Para obtener un ejemplo que muestra este enfoque, consulte [utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario. En este ejemplo se inicia la operación asincrónica y, a continuación, imprime puntos (".") en la consola hasta que se complete la operación. Tenga en cuenta que **null** (**nada** en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> y <xref:System.Object> parámetros porque estos argumentos no son necesarios cuando se usa este enfoque.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
