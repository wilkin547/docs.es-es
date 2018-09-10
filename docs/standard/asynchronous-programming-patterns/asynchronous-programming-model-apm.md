---
title: Modelo de programación asincrónica (APM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd2fa6219f39a8506d865d85e1ce5f84d22a92f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269038"
---
# <a name="asynchronous-programming-model-apm"></a>Modelo de programación asincrónica (APM)
Una operación asincrónica que usa el patrón de diseño <xref:System.IAsyncResult> se implementa como dos métodos con nombre **Begin***OperationName* y **End***OperationName* que comienzan y terminan la operación asincrónica *OperationName* respectivamente. Por ejemplo, la clase <xref:System.IO.FileStream> ofrece los métodos <xref:System.IO.FileStream.BeginRead%2A> y <xref:System.IO.FileStream.EndRead%2A> para leer bytes de un archivo de manera asincrónica. Estos métodos implementan la versión asincrónica del método <xref:System.IO.FileStream.Read%2A> .  
  
> [!NOTE]
>  A partir de .NET Framework 4, la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) ofrece un nuevo modelo para programación asincrónica y paralela. Para obtener más información, vea [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) y [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
 Después de llamar a *Begin***OperationName*, una aplicación puede seguir ejecutando instrucciones en el subproceso de llamada mientras la operación asincrónica tiene lugar en un subproceso diferente. Por cada llamada a **Begin***OperationName*, la aplicación debe llamar a **End***OperationName* para obtener los resultados de la operación.  
  
## <a name="beginning-an-asynchronous-operation"></a>Comenzar una operación asincrónica  
 El método **Begin***OperationName* comienza la operación asincrónica *OperationName* y devuelve un objeto que implementa la interfaz <xref:System.IAsyncResult>. Los objetos<xref:System.IAsyncResult> almacenan información sobre una operación asincrónica. En la tabla siguiente se muestra información sobre una operación asincrónica.  
  
|Miembro|Descripción|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|Objeto opcional específico de la aplicación que contiene información sobre la operación asincrónica.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|Un <xref:System.Threading.WaitHandle> que se puede usar para bloquear la ejecución de la aplicación hasta que se complete la operación asincrónica.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|Un valor que indica si la operación asincrónica se completó en el subproceso usado para llamar a **Begin***OperationName* en lugar de completarse en otro subproceso <xref:System.Threading.ThreadPool>.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|Un valor que indica si se ha completado la operación asincrónica.|  
  
 Un método **Begin***OperationName* toma los parámetros declarados en la firma de la versión sincrónica del método que se pasan por valor o por referencia. Los parámetros out no forman parte de la firma del método **Begin***OperationName*. La firma del método **Begin***OperationName* también incluye dos parámetros más. El primero de estos define un delegado <xref:System.AsyncCallback> que hace referencia a un método al que se llama cuando se completa la operación asincrónica. El llamador puede especificar `null` (`Nothing` en Visual Basic) si no quiere un método invocado cuando finalice la operación. El segundo parámetro adicional es un objeto definido por el usuario. Este objeto se puede usar para pasar información de estado específica de la aplicación al método invocado cuando finaliza la operación asincrónica. Si un método **Begin***OperationName* toma más parámetros específicos de operación, como una matriz de bytes para almacenar los bytes leídos de un archivo, el <xref:System.AsyncCallback> y el objeto de estado de la aplicación son los últimos parámetros de la firma del método **Begin***OperationName*.  
  
 **Begin***OperationName* devuelve el control inmediatamente al subproceso de llamada. Si el método **Begin***OperationName* genera excepciones, las excepciones se generan antes de iniciarse la operación asincrónica. Si el método **Begin***OperationName* genera excepciones, no se invoca el método de devolución de llamada.  
  
## <a name="ending-an-asynchronous-operation"></a>Finalizar una operación asincrónica  
 El método **End***OperationName* finaliza la operación asincrónica *OperationName*. El valor devuelto del método **End***OperationName* es del mismo tipo devuelto por su homólogo sincrónico y es específico de la operación asincrónica. Por ejemplo, el método <xref:System.IO.FileStream.EndRead%2A> devuelve el número de bytes leídos de un <xref:System.IO.FileStream> y el método <xref:System.Net.Dns.EndGetHostByName%2A> devuelve un objeto <xref:System.Net.IPHostEntry> que contiene información sobre un equipo host. El método **End***OperationName* toma los parámetros out o ref declarados en la firma de la versión sincrónica del método. Además de los parámetros del método sincrónico, el método **End***OperationName* incluye también un parámetro <xref:System.IAsyncResult>. Los llamadores deben pasar la instancia devuelta por la llamada correspondiente a **Begin***OperationName*.  
  
 Si la operación asincrónica representada por el objeto <xref:System.IAsyncResult> no ha finalizado cuando se llama a **End***OperationName*, **End***OperationName* bloquea el subproceso de llamada hasta que finalice la operación asincrónica. Las excepciones generadas por la operación asincrónica se generan desde el método **End***OperationName*. El efecto de llamar al método **End***OperationName* varias veces con el mismo <xref:System.IAsyncResult> no está definido. Del mismo modo, tampoco se ha definido la llamada al método **End***OperationName* con un <xref:System.IAsyncResult> que no fue devuelto por Begin relacionado.  
  
> [!NOTE]
>  En cualquiera de los escenarios sin definir, los implementadores deben considerar generar <xref:System.InvalidOperationException>.  
  
> [!NOTE]
>  Los implementadores de este patrón de diseño deben notificar al llamador que ha completado la operación asincrónica estableciendo <xref:System.IAsyncResult.IsCompleted%2A> en true, llamando al método de devolución de llamada asincrónica (si se especificó) y señalizando el <xref:System.IAsyncResult.AsyncWaitHandle%2A>.  
  
 Los desarrolladores de aplicaciones tienen varias opciones de diseño para tener acceso a los resultados de la operación asincrónica. La opción correcta depende de si la aplicación tiene instrucciones que se pueden ejecutar mientras se completa la operación. Si una aplicación no puede realizar ningún trabajo adicional hasta que recibe los resultados de la operación asincrónica, debe bloquearse la aplicación hasta que los resultados estén disponibles. Para bloquear hasta que finalice una operación asincrónica, puede usar uno de los siguientes enfoques:  
  
-   Llame a **End***OperationName* desde el subproceso principal de la aplicación, bloqueando la ejecución de la aplicación hasta que finalice la operación. Para ver un ejemplo que ilustre esta técnica, consulte [Bloquear la ejecución de una aplicación al finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   Use el <xref:System.IAsyncResult.AsyncWaitHandle%2A> para bloquear la ejecución de aplicaciones hasta que se completen una o más operaciones. Para ver un ejemplo que ilustre esta técnica, consulte [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Las aplicaciones que no necesiten bloquear mientras se completa la operación asincrónica pueden usar uno de los siguientes métodos:  
  
-   Sondee el estado de finalización de la operación activando la propiedad <xref:System.IAsyncResult.IsCompleted%2A> periódicamente y llamando a **End***OperationName* cuando finalice la operación. Para ver un ejemplo que ilustre esta técnica, consulte [Sondear el estado de una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   Use un delegado <xref:System.AsyncCallback> para especificar un método que se debe invocar cuando finalice la operación. Para ver un ejemplo que ilustre esta técnica, consulte [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
- [Llamada a métodos sincrónicos de forma asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
- [Utilizar un delegado AsyncCallback y un objeto State](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
