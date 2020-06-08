---
title: Bloquear la ejecución de una aplicación al finalizar una operación asincrónica
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: 74976176acc0fbb948c514358b7bd323cc20c134
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289959"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Bloquear la ejecución de una aplicación al finalizar una operación asincrónica
Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación. Use una de las opciones siguientes para bloquear el subproceso principal de la aplicación mientras se espera a que se complete una operación asincrónica:  
  
- Llame al método **End**_NombreDeLaOperación_ para operaciones asincrónicas. Este método se muestra en este tema.  
  
- Use la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin**_OperationName_ de la operación asincrónica. Para ver un ejemplo que ilustre este método, consulte [Bloquear la ejecución de una aplicación mediante AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Las aplicaciones que usan el método **End**_NombreDeLaOperación_ para el bloqueo hasta que se completa una operación asincrónica normalmente llamarán al método **Begin**_NombreDeLaOperación_, realizarán cualquier trabajo que se pueda realizar sin los resultados de la operación y luego llamarán a **End**_NombreDeLaOperación_.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio de un equipo especificado por el usuario. Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` y `stateObject`, porque estos argumentos no son necesarios cuando se usa este método.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
