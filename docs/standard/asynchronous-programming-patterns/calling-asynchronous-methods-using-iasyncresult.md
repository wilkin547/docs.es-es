---
title: Llamar a métodos asincrónicos mediante IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 2a9ce8bc2d2edd09ef79c060b9bb173d4d054d02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121314"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="787d6-102">Llamar a métodos asincrónicos mediante IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="787d6-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="787d6-103">Los tipos de .NET Framework y las bibliotecas de clases de terceros pueden proporcionar métodos que permiten la continuidad de la ejecución de una aplicación mientras se realizan las operaciones asincrónicas en subprocesos distintos del subproceso de aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="787d6-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="787d6-104">En las secciones siguientes se describen y proporcionan ejemplos de código que muestran las diferentes formas en que se puede llamar a métodos asincrónicos que usan el modelo de diseño <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="787d6-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="787d6-105">[Bloquear la ejecución de una aplicación al finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)</span><span class="sxs-lookup"><span data-stu-id="787d6-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="787d6-106">[Bloquear la ejecución de una aplicación mediante AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)</span><span class="sxs-lookup"><span data-stu-id="787d6-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="787d6-107">[Sondear el estado de una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="787d6-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="787d6-108">[Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="787d6-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787d6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="787d6-109">See also</span></span>

- [<span data-ttu-id="787d6-110">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="787d6-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- <span data-ttu-id="787d6-111">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="787d6-111">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
