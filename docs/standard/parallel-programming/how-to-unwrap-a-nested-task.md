---
title: 'Cómo: Desencapsular una tarea anidada'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: c72654a2bc21035fe706d76018bb163d8ba01ee8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106902"
---
# <a name="how-to-unwrap-a-nested-task"></a>Cómo: Desencapsular una tarea anidada
Puede devolver una tarea de un método y, a continuación, esperar o continuar a partir de dicha tarea, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 En el ejemplo anterior, la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es de tipo `string` (`String` en Visual Basic).  
  
 Sin embargo, en algunos escenarios, puede crear una tarea dentro de otra tarea y, a continuación, devolver la tarea anidada. En este caso, el delegado `TResult` de la tarea indicada es una tarea. En el ejemplo siguiente, la propiedad Result es un delegado `Task<Task<string>>` en C# o `Task(Of Task(Of String))` en Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Aunque es posible escribir código para desajustar la tarea exterior y recuperar la tarea original y su propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>, este código no es fácil de escribir porque se deben controlar las excepciones y también las solicitudes de cancelación. En esta situación, se recomienda que use uno de los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Los métodos <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> se pueden usar para transformar cualquier delegado `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` en Visual Basic) en un delegado `Task` o `Task<TResult>` (`Task(Of TResult)` en Visual Basic). La nueva tarea representa totalmente la tarea anidada interna e incluye el estado de cancelación y todas las excepciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
