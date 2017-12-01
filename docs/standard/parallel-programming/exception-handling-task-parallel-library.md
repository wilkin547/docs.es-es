---
title: Control de excepciones (Task Parallel Library)
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
helpviewer_keywords: tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e62498376d321d8ff22a53315b9d5f18a8865056
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling-task-parallel-library"></a>Control de excepciones (Task Parallel Library)
Las excepciones no controladas que se inician mediante código de usuario que se ejecuta dentro de una tarea se propagan de vuelta al subproceso que hace la llamada, excepto en determinados escenarios que se describen posteriormente en este tema. Las excepciones se propagan cuando se usa uno de los métodos estático o de instancia <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> o <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` métodos y se pueden controlar si se incluye la llamada en un `try` / `catch` instrucción. Si una tarea es la tarea primaria de tareas secundarias asociadas o si se esperan varias tareas, pueden producirse varias excepciones.  
  
 Para propagar todas las excepciones de nuevo al subproceso que realiza la llamada, la infraestructura de la tarea las encapsula en una instancia de <xref:System.AggregateException> . La excepción <xref:System.AggregateException> tiene una propiedad <xref:System.AggregateException.InnerExceptions%2A> que se puede enumerar para examinar todas las excepciones originales que se produjeron y controlar (o no) cada una de ellas de forma individual. También puede controlar las excepciones originales mediante el <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> método.  
  
 Incluso aunque solo se produzca una excepción, se encapsulará en una excepción <xref:System.AggregateException> , como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 Para evitar una excepción no controlada, basta con detectar el objeto <xref:System.AggregateException> y omitir las excepciones internas. Sin embargo, esta operación no resulta recomendable porque es igual que detectar el tipo <xref:System.Exception> base en escenarios no paralelos. Si desea detectar una excepción sin realizar acciones concretas que la resuelvan, puede dejar al programa en un estado indeterminado.  
  
 Si no desea llamar a la <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> o <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` método para esperar la finalización de una tarea, también se puede recuperar el <xref:System.AggregateException> excepción de la tarea <xref:System.Threading.Tasks.Task.Exception%2A> propiedad, como se muestra en el ejemplo siguiente. Para más información, consulte la sección [Observar excepciones mediante la propiedad Task.Exception](#ExceptionProp) de este tema.  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 Si no espera a una tarea que propague la excepción ni accede a su propiedad <xref:System.Threading.Tasks.Task.Exception%2A> , la excepción se escalará conforme a la directiva de excepciones de .NET cuando la tarea se recopile como elemento no utilizado.  
  
 Cuando las excepciones pueden propagarse de vuelta al subproceso de unión, es posible que una tarea continúe procesando algunos elementos después de que se haya producido la excepción.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla **Habilitar Solo mi código** bajo **Herramientas, Opciones, Depuración, General**.  
  
## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>Tareas secundarias asociadas y objetos AggregateException anidados  
 Si una tarea tiene una tarea secundaria adjunta que inicia una excepción, esa excepción se encapsula en un objeto <xref:System.AggregateException> antes de que se propague a la tarea primaria, que encapsula esa excepción en su propio objeto <xref:System.AggregateException> antes de propagarla de nuevo al subproceso que realiza la llamada. En tales casos, la <xref:System.AggregateException.InnerExceptions%2A> propiedad de la <xref:System.AggregateException> excepción detectada en el <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> o <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` o <xref:System.Threading.Tasks.Task.WaitAny%2A> o <xref:System.Threading.Tasks.Task.WaitAll%2A> método contiene uno o varios <xref:System.AggregateException> instancias, no el excepciones originales que produjeron el error. Para evitar tener que iterar sobre anidado <xref:System.AggregateException> excepciones, puede usar el <xref:System.AggregateException.Flatten%2A> método para quitar todos los anidado <xref:System.AggregateException> excepciones, por lo que el <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> propiedad contiene las excepciones originales. En el ejemplo siguiente, las instancias anidadas de <xref:System.AggregateException> se reducen y se controlan en un solo bucle.  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 También puede usar el <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> método volver a producir las excepciones internas de varias <xref:System.AggregateException> instancias iniciadas por varias tareas en una sola <xref:System.AggregateException> instancia, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## <a name="exceptions-from-detached-child-tasks"></a>Excepciones de tareas secundarias desasociadas  
 De forma predeterminada, las tareas secundarias están desasociadas cuando se crean. Las excepciones producidas por tareas desasociadas deben controlarse o reiniciarse en la tarea primaria inmediata; no se propagan de nuevo al subproceso que realiza la llamada del mismo modo que las tareas secundarias asociadas. La tarea primaria superior puede reiniciar manualmente una excepción de una tarea secundaria desasociada para que se encapsule en un objeto <xref:System.AggregateException> y propagarla de vuelta al subproceso de unión.  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 Aunque se use una tarea de continuación para observar una excepción en una tarea secundaria, la tarea primaria debe seguir observando la excepción.  
  
## <a name="exceptions-that-indicate-cooperative-cancellation"></a>Excepciones que indican la cancelación cooperativa  
 Cuando el código de usuario de una tarea responde a una solicitud de cancelación, el procedimiento correcto es producir una excepción <xref:System.OperationCanceledException> que se pasa en el token de cancelación con el que se comunicó la solicitud. Antes de intentar propagar la excepción, la instancia de la tarea compara el token de la excepción con el que recibió durante su creación. Si son iguales, la tarea propaga una excepción <xref:System.Threading.Tasks.TaskCanceledException> encapsulada en un elemento <xref:System.AggregateException>y puede verse cuando se examinan las excepciones internas. Sin embargo, si el subproceso que hace la llamada no está esperando la tarea, no se propagará esa excepción concreta. Para obtener más información, consulta [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>Usar el método Handle para filtrar excepciones internas  
 El método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> puede usarse para filtrar excepciones que pueden tratarse como "controladas" sin necesidad de usar ninguna otra lógica. En el delegado de usuario que se proporciona a la <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> método, puede examinar el tipo de excepción, su <xref:System.Exception.Message%2A> propiedad o cualquier otra información sobre lo que le permitirá determinar si es benigna. Las excepciones para el que el delegado devuelve `false` se reinician en un nuevo <xref:System.AggregateException> inmediatamente después de la instancia la <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> devuelve del método.  
  
 En el ejemplo siguiente es funcionalmente equivalente al primer ejemplo de este tema, que examina cada excepción de la <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> colección.  En su lugar, llama a este controlador de excepciones del <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> objeto del método para cada excepción y solo vuelve a generar excepciones no `CustomException` instancias.  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 Éste es un ejemplo más completo que usa el <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> método para proporcionar un control especial para un <xref:System.UnauthorizedAccessException> excepción al enumerar los archivos.  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Observar excepciones mediante la propiedad Task.Exception  
 Si una tarea se completa con el estado <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType>, se puede examinar su propiedad <xref:System.Threading.Tasks.Task.Exception%2A> para detectar qué excepción concreta produjo el error. Un mecanismo adecuado para observar la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> es usar una continuación que se ejecute solo si se produce un error en la tarea anterior, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 En una aplicación real, el delegado de continuación podría registrar información detallada sobre la excepción y posiblemente generar nuevas tareas para recuperarse de la excepción.  
  
## <a name="unobservedtaskexception-event"></a>Evento UnobservedTaskException  
 En algunos escenarios (por ejemplo, cuando se hospedan complementos que no son de confianza), es posible que se produzcan numerosas excepciones benignas y que resulte demasiado difícil observarlas todas manualmente. En estos casos, se puede proceder a controlar el evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType>. La instancia de <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> que se pasa al controlador se puede utilizar para evitar que la excepción no observada se propague de nuevo al subproceso de unión.  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
