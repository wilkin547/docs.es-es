---
title: Procedimiento para devolver un valor a partir de una tarea
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df928ec6494da6da368b3cef1f1d25a84a692aa2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741790"
---
# <a name="how-to-return-a-value-from-a-task"></a>Procedimiento para devolver un valor a partir de una tarea
En este ejemplo se muestra cómo se usa el tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> para devolver un valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>. Requiere que exista el directorio de C:\Usuarios\Pública\Imágenes\Imágenes de muestra\ y que contenga archivos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> bloquea el subproceso que realiza la llamada hasta que la tarea finaliza.  
  
 Para ver cómo se pasa el resultado de <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a una tarea de continuación, consulte [Encadenar tareas mediante tareas de continuación](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
