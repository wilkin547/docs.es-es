---
title: Control de excepciones (biblioteca TPL)
description: Explore el control de excepciones mediante la biblioteca TPL en .NET. Vea excepciones de agregado anidadas, excepciones internas y excepciones de tareas no observadas, entre otras.
ms.date: 04/20/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
ms.openlocfilehash: f1c1a994f4b3a8df0556a0190bc4eacb63f2921e
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662542"
---
# <a name="exception-handling-task-parallel-library"></a>Control de excepciones (biblioteca TPL)

Las excepciones no controladas que se inician mediante código de usuario que se ejecuta dentro de una tarea se propagan de vuelta al subproceso que hace la llamada, excepto en determinados escenarios que se describen posteriormente en este tema. Las excepciones se propagan cuando se usa uno de los métodos estáticos o de instancia <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, los cuales se pueden controlar si se incluye la llamada en una instrucción `try`/`catch`. Si una tarea es la tarea primaria de tareas secundarias asociadas o si se esperan varias tareas, pueden producirse varias excepciones.

Para propagar todas las excepciones de nuevo al subproceso que realiza la llamada, la infraestructura de la tarea las encapsula en una instancia de <xref:System.AggregateException> . La excepción <xref:System.AggregateException> tiene una propiedad <xref:System.AggregateException.InnerExceptions%2A> que se puede enumerar para examinar todas las excepciones originales que se produjeron y controlar (o no) cada una de ellas de forma individual. También puede controlar las excepciones originales mediante el método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> .

Incluso aunque solo se produzca una excepción, se encapsulará en una excepción <xref:System.AggregateException> , como se muestra en el ejemplo siguiente.

[!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
[!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]

Para evitar una excepción no controlada, basta con detectar el objeto <xref:System.AggregateException> y omitir las excepciones internas. Sin embargo, esta operación no resulta recomendable porque es igual que detectar el tipo <xref:System.Exception> base en escenarios no paralelos. Si desea detectar una excepción sin realizar acciones concretas que la resuelvan, puede dejar al programa en un estado indeterminado.

Si no desea llamar al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> para esperar a la finalización de una tarea, también puede recuperar la excepción <xref:System.AggregateException> de la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> de la tarea, como se muestra en el ejemplo siguiente. Para más información, consulte la sección [Observar excepciones mediante la propiedad Task.Exception](#observing-exceptions-by-using-the-taskexception-property) de este tema.

[!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
[!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]

Si no espera a una tarea que propague la excepción ni accede a su propiedad <xref:System.Threading.Tasks.Task.Exception%2A> , la excepción se escalará conforme a la directiva de excepciones de .NET cuando la tarea se recopile como elemento no utilizado.

Cuando las excepciones pueden propagarse de vuelta al subproceso de unión, es posible que una tarea continúe procesando algunos elementos después de que se haya producido la excepción.

> [!NOTE]
> Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla **Habilitar Solo mi código** bajo **Herramientas, Opciones, Depuración, General**.

## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>Tareas secundarias asociadas y objetos AggregateException anidados

Si una tarea tiene una tarea secundaria adjunta que inicia una excepción, esa excepción se encapsula en un objeto <xref:System.AggregateException> antes de que se propague a la tarea primaria, que encapsula esa excepción en su propio objeto <xref:System.AggregateException> antes de propagarla de nuevo al subproceso que realiza la llamada. En casos como este, la propiedad <xref:System.AggregateException.InnerExceptions%2A> de la excepción <xref:System.AggregateException> que se detecta en los métodos <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAny%2A> o <xref:System.Threading.Tasks.Task.WaitAll%2A> contiene una o varias instancias de <xref:System.AggregateException>, pero no las excepciones originales que produjeron el error. Para evitar tener que iterar sobre excepciones <xref:System.AggregateException>, puede usar el método <xref:System.AggregateException.Flatten%2A> para quitar todas las excepciones <xref:System.AggregateException> anidadas, de forma que la propiedad <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> contenga las excepciones originales. En el ejemplo siguiente, las instancias anidadas de <xref:System.AggregateException> se reducen y se controlan en un solo bucle.

[!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
[!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]

También puede utilizar el método <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> para volver a generar las excepciones internas de varias instancias de <xref:System.AggregateException> iniciadas por varias tareas en una sola instancia de <xref:System.AggregateException>, como se muestra en el ejemplo siguiente.

[!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
[!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]

## <a name="exceptions-from-detached-child-tasks"></a>Excepciones de tareas secundarias desasociadas

De forma predeterminada, las tareas secundarias están desasociadas cuando se crean. Las excepciones producidas por tareas desasociadas deben controlarse o reiniciarse en la tarea primaria inmediata; no se propagan de nuevo al subproceso que realiza la llamada del mismo modo que las tareas secundarias asociadas. La tarea primaria superior puede reiniciar manualmente una excepción de una tarea secundaria desasociada para que se encapsule en un objeto <xref:System.AggregateException> y propagarla de vuelta al subproceso de unión.

[!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
[!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]

Aunque se use una tarea de continuación para observar una excepción en una tarea secundaria, la tarea primaria debe seguir observando la excepción.

## <a name="exceptions-that-indicate-cooperative-cancellation"></a>Excepciones que indican la cancelación cooperativa

Cuando el código de usuario de una tarea responde a una solicitud de cancelación, el procedimiento correcto es producir una excepción <xref:System.OperationCanceledException> que se pasa en el token de cancelación con el que se comunicó la solicitud. Antes de intentar propagar la excepción, la instancia de la tarea compara el token de la excepción con el que recibió durante su creación. Si son iguales, la tarea propaga una excepción <xref:System.Threading.Tasks.TaskCanceledException> encapsulada en un elemento <xref:System.AggregateException>y puede verse cuando se examinan las excepciones internas. Sin embargo, si el subproceso que hace la llamada no está esperando la tarea, no se propagará esa excepción concreta. Para más información, vea [Cancelación de tareas](task-cancellation.md).

[!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
[!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]

## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>Usar el método Handle para filtrar excepciones internas

El método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> puede usarse para filtrar excepciones que pueden tratarse como "controladas" sin necesidad de usar ninguna otra lógica. En el delegado de usuario que se facilita al método <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> , se puede examinar el tipo de excepción, su propiedad <xref:System.Exception.Message%2A> o cualquier otra información sobre ella que permita determinar si no supone un riesgo. Las excepciones en las que el delegado devuelve `false` se reinician inmediatamente en una nueva instancia de <xref:System.AggregateException> después de que el método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> devuelva un valor.

El ejemplo siguiente es funcionalmente equivalente al primer ejemplo de este tema, que examina cada excepción de la colección <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType>.  En su lugar, este controlador de excepciones llama al objeto del método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> por cada excepción y solo vuelve a generar las excepciones que no son instancias de `CustomException`.

[!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
[!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]

A continuación, se muestra un ejemplo más completo que usa el método <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> para ofrecer un control especial para una excepción <xref:System.UnauthorizedAccessException> al enumerar los archivos.

[!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
[!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]

## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Observar excepciones mediante la propiedad Task.Exception

Si una tarea se completa con el estado <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> , se puede examinar su propiedad <xref:System.Threading.Tasks.Task.Exception%2A> para detectar qué excepción concreta produjo el error. Un mecanismo adecuado para observar la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> es usar una continuación que se ejecute solo si se produce un error en la tarea anterior, tal y como se muestra en el siguiente ejemplo.

[!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
[!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]

En una aplicación significativa, el delegado de continuación podría registrar información detallada sobre la excepción y posiblemente generar nuevas tareas para recuperarse de la excepción. Si se produce un error en una tarea, las siguientes expresiones inician la excepción:

- `await task`
- `task.Wait()`
- `task.Result`
- `task.GetAwaiter().GetResult()`

Use una instrucción [`try-catch`](../../csharp/language-reference/keywords/try-catch.md) para controlar y observar las excepciones producidas. Como alternativa, acceda a la propiedad <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> para observar la excepción.

## <a name="unobservedtaskexception-event"></a>Evento UnobservedTaskException

En algunos escenarios (por ejemplo, cuando se hospedan complementos que no son de confianza), es posible que se produzcan numerosas excepciones benignas y que resulte demasiado difícil observarlas todas manualmente. En estos casos, se puede proceder a controlar el evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> . La instancia de <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> que se pasa al controlador se puede utilizar para evitar que la excepción no observada se propague de nuevo al subproceso de unión.

## <a name="see-also"></a>Vea también

- [Biblioteca TPL](task-parallel-library-tpl.md)
