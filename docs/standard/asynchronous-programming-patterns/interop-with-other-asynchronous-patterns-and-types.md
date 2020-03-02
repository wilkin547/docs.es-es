---
title: Interoperabilidad con otros tipos y patrones asincrónicos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: 981c13c68eaf1eb0c19f95eb1b097935ea02a16d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159759"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a>Interoperabilidad con otros tipos y patrones asincrónicos
.NET Framework 1.0 introdujo el patrón <xref:System.IAsyncResult>, conocido también como [Modelo de programación asincrónica (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)o el patrón `Begin/End` .  .NET Framework 2.0 agregó [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  A partir de .NET Framework 4, [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) reemplaza a APM y EAP, pero proporciona la capacidad de crear fácilmente rutinas de migración a partir de los patrones anteriores:  
  
 En este tema:  
  
- [Tareas y APM](#APM) ([de APM a TAP](#ApmToTap) o [de TAP a APM](#TapToApm))  
  
- [Tareas y EAP](#EAP)  
  
- [Tareas y controladores de espera](#WaitHandles) ([de controladores de espera a TAP](#WHToTap) o [de TAP a controladores de espera](#TapToWH))  
  
<a name="APM"></a>
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a>Tareas y el modelo de programación asincrónica (APM)  
  
<a name="ApmToTap"></a>
### <a name="from-apm-to-tap"></a>de APM a TAP  
 Como el patrón [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) está muy estructurado, es muy fácil crear un contenedor para exponer una implementación de APM como una implementación de TAP. De hecho, .NET Framework, a partir de .NET Framework 4, incluye rutinas del asistente en forma de sobrecargas del método <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> para ofrecer esta traducción.  
  
 Considere la clase <xref:System.IO.Stream> y sus métodos <xref:System.IO.Stream.BeginRead%2A> y <xref:System.IO.Stream.EndRead%2A> , que representan el equivalente de APM al método sincrónico <xref:System.IO.Stream.Read%2A> :  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 Puede usar el método <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> para implementar un contenedor de TAP para esta operación como sigue:  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 Esta implementación es similar a la siguiente:  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>
### <a name="from-tap-to-apm"></a>de TAP a APM  
 Si la infraestructura existente espera el patrón APM, también deseará realizar una implementación de TAP y usarla donde se espere una implementación de APM.  Como las tareas se pueden crear y la clase <xref:System.Threading.Tasks.Task> implementa <xref:System.IAsyncResult>, puede usar una función del asistente sencilla para ello. En el código siguiente se usa una extensión de la clase <xref:System.Threading.Tasks.Task%601> , pero puede usar una función casi idéntica para las tareas no genéricas.  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 Ahora, considere un caso donde tiene la implementación siguiente de TAP:  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 y desea proporcionar esta implementación de APM:  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 En el ejemplo siguiente se muestra una migración a APM:  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a>Tareas y el patrón asincrónico basado en eventos (EAP)  
 El encapsulamiento de una implementación de [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) es más complejo que encapsular un patrón de APM, ya que el patrón de EAP tiene más variaciones y menos estructura que el de APM.  Para mostrarlo, el código siguiente encapsula el método `DownloadStringAsync` .  `DownloadStringAsync` acepta un URI, genera el evento `DownloadProgressChanged` durante la descarga para informar de varias estadísticas sobre el progreso y genera el evento `DownloadStringCompleted` cuando termina.  El resultado final es una cadena que incluye el contenido de la página en el URI especificado.  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>
## <a name="tasks-and-wait-handles"></a>Tareas y controladores de espera  
  
<a name="WHToTap"></a>
### <a name="from-wait-handles-to-tap"></a>de controladores de espera a TAP  
 Aunque los controladores de espera no implementan un patrón asincrónico, los desarrolladores avanzados pueden usar la clase <xref:System.Threading.WaitHandle> y el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> para las notificaciones asincrónicas cuando se establece un controlador de este tipo.  Puede encapsular el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> para habilitar una alternativa basada en tareas para cualquier espera sincrónica en un controlador de espera:  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 Con este método se pueden usar las implementaciones existentes <xref:System.Threading.WaitHandle> en métodos asincrónicos.  Por ejemplo, si quiere restringir el número de operaciones asincrónicas que se ejecutan en un momento dado, puede usar un semáforo (un objeto <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ).  Se puede restringir a *N* el número de operaciones que se ejecutan simultáneamente mediante una inicialización del contador del semáforo a *N*, esperando al semáforo cuando se quiera realizar una operación y liberando el semáforo cuando se haya terminado:  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 También se puede compilar un semáforo asincrónico que no se base en controladores de espera, sino que funcione completamente con tareas. Para ello, puede usar técnicas como las descritas en [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) para crear estructuras de datos encima de <xref:System.Threading.Tasks.Task>.  
  
<a name="TapToWH"></a>
### <a name="from-tap-to-wait-handles"></a>de TAP a controladores de espera  
 Como se mencionó anteriormente, la clase <xref:System.Threading.Tasks.Task> implementa <xref:System.IAsyncResult>y esa implementación expone una propiedad <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> que devuelve un controlador de espera que se establecerá cuando la <xref:System.Threading.Tasks.Task> se haya completado.  Puede obtener la instancia de <xref:System.Threading.WaitHandle> para una <xref:System.Threading.Tasks.Task> de esta manera:  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Implementar el modelo asincrónico basado en tareas](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [Modelo asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
