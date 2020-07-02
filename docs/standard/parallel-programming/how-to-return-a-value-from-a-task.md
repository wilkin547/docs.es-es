---
title: Procedimiento para devolver un valor a partir de una tarea
description: Vea cómo el tipo System.Threading.Tasks.Task<TResult> devuelve un valor de la propiedad Result en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 051cef7cac654e4369ec1486884876004370ba0b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767980"
---
# <a name="how-to-return-a-value-from-a-task"></a>Procedimiento para devolver un valor a partir de una tarea
En este ejemplo se muestra cómo se usa el tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> para devolver un valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>. Requiere que exista el directorio de C:\Usuarios\Pública\Imágenes\Imágenes de muestra\ y que contenga archivos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> bloquea el subproceso que realiza la llamada hasta que la tarea finaliza.  
  
 Para ver cómo se pasa el resultado de <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a una tarea de continuación, consulte [Encadenar tareas mediante tareas de continuación](chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica basada en tareas](task-based-asynchronous-programming.md)
- [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md)
