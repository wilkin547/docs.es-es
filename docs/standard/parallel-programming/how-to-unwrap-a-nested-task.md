---
title: "Cómo: Desencapsular una tarea anidada"
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>Cómo: Desencapsular una tarea anidada
Puede devolver una tarea de un método y, a continuación, esperar o continuar a partir de dicha tarea, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 En el ejemplo anterior, el <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad es de tipo `string` (`String` en Visual Basic).  
  
 Sin embargo, en algunos escenarios, puede crear una tarea dentro de otra tarea, y, a continuación, devolver la tarea anidada. En este caso, el `TResult` de la tarea indicada es una tarea. En el ejemplo siguiente, la propiedad Result es un `Task<Task<string>>` en C# o `Task(Of Task(Of String))` en Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Aunque es posible escribir código para desempaquetar la tarea exterior y recuperar la tarea original y su <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad, este código no es fácil de escribir porque se deben controlar las excepciones y también las solicitudes de cancelación. En esta situación, se recomienda que realice uno de los <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos de extensión, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 El <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos pueden usarse para transformar cualquier `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` en Visual Basic) a un `Task` o `Task<TResult>` (`Task(Of TResult)` en Visual Basic). La nueva tarea totalmente representa la tarea anidada interna e incluye el estado de cancelación y todas las excepciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos de extensión.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
