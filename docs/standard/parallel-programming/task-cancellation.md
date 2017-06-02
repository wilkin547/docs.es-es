---
title: "Task Cancellation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, cancellation"
  - "asynchronous task cancellation"
ms.assetid: 3ecf1ea9-e399-4a6a-a0d6-8475f48dcb28
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Task Cancellation
Las clases <xref:System.Threading.Tasks.Task?displayProperty=fullName> y <xref:System.Threading.Tasks.Task%601?displayProperty=fullName> admiten la cancelación a través del uso de tokens de cancelación en .NET Framework. Para obtener más información, consulta [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md). En las clases Task, la cancelación implica la cooperación entre el delegado de usuario, que representa una operación que se puede cancelar y el código que solicitó la cancelación.  Una cancelación correcta significa que el código que la solicita llama al método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> y que el delegado de usuario finaliza la operación a tiempo. Puede finalizar la operación a través de una de estas opciones:  
  
-   Devolver simplemente un valor del delegado. En muchos escenarios esto es suficiente; sin embargo, una instancia de tarea cancelada de esta manera cambia al estado <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>, no al estado <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.  
  
-   Producir una excepción <xref:System.OperationCanceledException> y pasarle el token en el que se solicitó la cancelación. En este caso, se prefiere usar el método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>. Una tarea cancelada de esta manera cambia al estado Canceled, que sirve al código que realiza la llamada para comprobar que la tarea respondió a su solicitud de cancelación.  
  
 En el siguiente ejemplo se muestra el modelo básico para la opción de cancelación de tareas que produce la excepción. Observe que el token se pasa al delegado de usuario y a la propia instancia de la tarea.  
  
 [!code-csharp[TPL_Cancellation#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/snippet02.cs#02)]
 [!code-vb[TPL_Cancellation#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/module1.vb#02)]  
  
 Para obtener un ejemplo más completo, vea [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
 Cuando una instancia de tarea observa una excepción <xref:System.OperationCanceledException> iniciada desde el código de usuario, compara el token de la excepción con su token asociado \(el que se pasó a la API que creó la tarea\). Si son iguales y la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token devuelve true, la tarea lo interpreta como una confirmación de cancelación y pasa al estado Canceled. Si no se usa un método <xref:System.Threading.Tasks.Task.Wait%2A> o <xref:System.Threading.Tasks.Task.WaitAll%2A> para esperar a la tarea, esta simplemente establece su estado en <xref:System.Threading.Tasks.TaskStatus>.  
  
 Si espera en un elemento Task que cambia al estado “Canceled”, se crea y se inicia una excepción <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=fullName> \(encapsulada en la excepción <xref:System.AggregateException>\). Observe que esta excepción indica la cancelación correcta en lugar de una situación de error. Por consiguiente, la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> del elemento Task devuelve `null`.  
  
 Si la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token devuelve False o si el token de la excepción no coincide con el token de la tarea, <xref:System.OperationCanceledException> se trata como una excepción normal, por lo que la tarea cambia al estado Faulted. Observe también que la presencia de otras excepciones también hará que la tarea pase al estado Faulted. Puede obtener el estado de la tarea completada en la propiedad <xref:System.Threading.Tasks.Task.Status%2A>.  
  
 Es posible que una tarea continúe procesando algunos elementos una vez solicitada la cancelación.  
  
## Vea también  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)   
 [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)