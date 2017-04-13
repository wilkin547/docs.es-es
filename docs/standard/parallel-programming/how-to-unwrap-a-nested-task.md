---
title: "How to: Unwrap a Nested Task | Microsoft Docs"
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
  - "tasks, how to unwrap nested tasks"
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unwrap a Nested Task
Puede devolver una tarea de un método y esperar o continuar a partir de esa tarea, como se muestra en el siguiente ejemplo:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 En el ejemplo anterior, la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es de tipo `string` \(`String` en Visual Basic\).  
  
 Sin embargo, en algunos casos le podría interesar crear una tarea dentro de otra y devolver la tarea anidada.  En este caso, `TResult` de la tarea que incluye es, en sí misma, una tarea.  En el siguiente ejemplo, la propiedad Result es `Task<Task<string>>` en C\# o `Task(Of Task(Of String))` en Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Aunque es posible escribir código para desempaquetar la tarea exterior y recuperar la tarea original y su propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>, tal código no es fácil de escribir porque se deben controlar las excepciones y también las solicitudes de cancelación.  En esta situación, recomendamos utilizar uno de los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Los métodos <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> se pueden utilizar para transformar `Task<Task>` o `Task<Task<TResult>>` \(`Task(Of Task)` o `Task(Of Task(Of TResult))` en Visual Basic\) en `Task` o `Task<TResult>` \(`Task(Of TResult)` en Visual Basic\).  La nueva tarea representa al completo la tarea anidada interna e incluye el estado de cancelación y todas las excepciones.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo usar los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## Vea también  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)