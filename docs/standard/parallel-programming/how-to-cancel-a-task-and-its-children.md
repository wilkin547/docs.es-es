---
title: Procedimiento para cancelar una tarea y sus elementos secundarios
description: Vea ejemplos de cómo cancelar una tarea y sus elementos secundarios en .NET. En los ejemplos se incluyen los pasos de la creación de tareas cancelables, hasta el aviso de que se canceló la tarea.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 66daf00680b65aace1ce6367761e3ed81596d33b
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662685"
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Procedimiento para cancelar una tarea y sus elementos secundarios
En estos ejemplos se muestra cómo realizar las tareas siguientes:  
  
1. Crear e iniciar una tarea cancelable.  
  
2. Pasar un token de cancelación a un delegado de usuario y, opcionalmente, a la instancia de la tarea.  
  
3. Observar y responder a la solicitud de cancelación en el delegado de usuario.  
  
4. Opcionalmente, observar en el subproceso que realiza la llamada que la tarea se canceló.  
  
 El subproceso que realiza la llamada no finaliza la tarea forzosamente, sino que solo señala que se solicita la cancelación. Si la tarea ya se está ejecutando, es el delegado de usuario el que debe observar la solicitud y responder según corresponda. Si la cancelación se solicita antes de ejecutarse la tarea, el delegado de usuario nunca se ejecuta y el objeto de tarea pasa al estado Cancelado.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo finalizar un objeto <xref:System.Threading.Tasks.Task> y sus elementos secundarios en respuesta a una solicitud de cancelación. También se muestra que, cuando un delegado de usuario finaliza con una excepción <xref:System.Threading.Tasks.TaskCanceledException>, el subproceso que realiza la llamada puede usar opcionalmente el método <xref:System.Threading.Tasks.Task.Wait%2A> o el método <xref:System.Threading.Tasks.Task.WaitAll%2A> para esperar a que las tareas finalicen. En este caso, se debe usar un bloque `try/catch` para controlar las excepciones en el subproceso que realiza la llamada.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 La clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> está totalmente integrada con el modelo de cancelación basado en los tipos <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> y <xref:System.Threading.CancellationToken?displayProperty=nameWithType>. Para más información, consulte el tema sobre la [cancelación en subprocesos administrados](../threading/cancellation-in-managed-threads.md) y la [cancelación de tareas](task-cancellation.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Programación asincrónica basada en tareas](task-based-asynchronous-programming.md)
- [Tareas secundarias asociadas y desasociadas](attached-and-detached-child-tasks.md)
- [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md)
