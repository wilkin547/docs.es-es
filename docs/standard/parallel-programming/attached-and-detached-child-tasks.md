---
title: Tareas secundarias asociadas y desasociadas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, child tasks
ms.assetid: c95788bf-90a6-4e96-b7bc-58e36a228cc5
ms.openlocfilehash: 8f15ee4f136e3e2df1a4e1c7683467f2a4bc9bc0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123185"
---
# <a name="attached-and-detached-child-tasks"></a>Tareas secundarias asociadas y desasociadas
Una *tarea secundaria* o *tarea anidada* es una instancia de <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> que se crea en el delegado de usuario de otra tarea, conocida como *tarea primaria*. Una tarea secundaria puede estar desasociada o asociada. Una *tarea secundaria desasociada* es una tarea que se ejecuta independientemente de su elemento principal. Una *tarea secundaria asociada* es una tarea anidada que se crea con la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> y cuyo elemento primario no le prohíbe asociarse de forma explícita o predeterminada. Una tarea puede crear cualquier número de tareas secundarias asociadas y desasociadas, con la única limitación de los recursos del sistema.  
  
 En la tabla siguiente se muestran las diferencias básicas entre los dos tipos de tareas secundarias.  
  
|Categoría|Tareas secundarias desasociadas|Tareas secundarias asociadas|  
|--------------|--------------------------|--------------------------|  
|La tarea primaria espera a que se completen las tareas secundarias.|No|Sí|  
|La tarea primaria propaga las excepciones que producen las tareas secundarias.|No|Sí|  
|El estado de la tarea primaria depende del estado de la tarea secundaria.|No|Sí|  
  
 En la mayoría de los casos, se recomienda usar tareas secundarias desasociadas porque las relaciones con otras tareas son menos complejas. Esta es la razón por la que las tareas que se crean dentro de tareas primarias están desasociadas de forma predeterminada y es necesario especificar explícitamente la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> para crear una tarea secundaria asociada.  
  
## <a name="detached-child-tasks"></a>Tareas secundarias desasociadas  
 Aunque una tarea secundaria se crea mediante una tarea primaria, de forma predeterminada es independiente de la tarea primaria. En el ejemplo siguiente se muestra una tarea primaria que crea una tarea secundaria simple. Si se ejecuta varias veces el código de ejemplo, se observa que el resultado del ejemplo se diferencia del que se muestra, y también que el resultado puede cambiar cada vez que se ejecuta el código. Esto ocurre porque la tarea primaria y las tareas secundarias se ejecutan de forma independiente; la tarea secundaria es una tarea independiente. El ejemplo únicamente espera que se complete la tarea primaria; la tarea secundaria puede no ejecutarse o completarse antes de que finalice la aplicación de consola.  
  
 [!code-csharp[TPL_ChildTasks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/nested1.cs#1)]
 [!code-vb[TPL_ChildTasks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/nested1.vb#1)]  
  
 Si la tarea secundaria se representa mediante un objeto <xref:System.Threading.Tasks.Task%601> en lugar de un objeto <xref:System.Threading.Tasks.Task>, puede garantizarse que la tarea primaria esperará a que la tarea secundaria se complete teniendo acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> de la tarea secundaria, aunque sea una tarea secundaria desasociada. La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> se bloquea hasta que se completa su tarea, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_ChildTasks#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/childtasks.cs#4)]
 [!code-vb[TPL_ChildTasks#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/tpl_childtasks.vb#4)]  
  
## <a name="attached-child-tasks"></a>Tareas secundarias asociadas  
 A diferencia de las tareas secundarias desasociadas, las tareas secundarias asociadas se sincronizan estrechamente con la tarea primaria. En el ejemplo anterior, se puede cambiar la tarea secundaria desasociada a una tarea secundaria asociada mediante la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> en la instrucción de creación de tareas, como se muestra en el ejemplo siguiente. En este código, la tarea secundaria asociada se completa antes que su tarea primaria. Como resultado, el resultado del ejemplo es igual cada vez que se ejecuta el código.  
  
 [!code-csharp[TPL_ChildTasks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/child1.cs#2)]
 [!code-vb[TPL_ChildTasks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/child1.vb#2)]  
  
 Puede usar tareas secundarias asociadas para crear gráficos con una estrecha sincronización de operaciones asincrónicas.  
  
 Sin embargo, una tarea secundaria se puede asociar a su elemento primario solo si su elemento primario no prohíbe las tareas secundarias asociadas. Las tareas primarias pueden evitar explícitamente que las tareas secundarias se asocien a ellas especificando la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> del constructor de clase de la tarea primaria o el método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Las tareas primarias impiden implícitamente que las tareas secundarias se asocien a ellas si se crean mediante una llamada al método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>. Esto se ilustra en el siguiente ejemplo: Es idéntico al ejemplo anterior, excepto en que la tarea primaria se crea mediante una llamada al método <xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=nameWithType> en lugar de al método <xref:System.Threading.Tasks.TaskFactory.StartNew%28System.Action%29?displayProperty=nameWithType>. Como la tarea secundaria no se puede asociar a su elemento primario, el resultado del ejemplo es impredecible. Como las opciones de creación de tareas predeterminadas para las sobrecargas de <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> incluyen <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, este ejemplo es funcionalmente equivalente al primer ejemplo de la sección "Tareas secundarias desasociadas".  
  
 [!code-csharp[TPL_ChildTasks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_childtasks/cs/child1a.cs#3)]
 [!code-vb[TPL_ChildTasks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_childtasks/vb/child1a.vb#3)]  
  
## <a name="exceptions-in-child-tasks"></a>Excepciones en tareas secundarias  
 Si una tarea secundaria desasociadas inicia una excepción, esa excepción debe observarse o controlarse directamente en la tarea primaria como si se tratara de una tarea no anidada. Si una tarea secundaria asociada inicia una excepción, la excepción se propaga automáticamente a la tarea primaria y de nuevo al subproceso, que espera o intenta obtener acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> de la tarea. Por tanto, si se usan tareas secundarias asociadas, se pueden controlar todas las excepciones en un solo punto en la llamada a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> del subproceso que realiza la llamada. Para más información, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
## <a name="cancellation-and-child-tasks"></a>Cancelación y tareas secundarias  
 La cancelación de tareas es cooperativa. Es decir, para que se pueda cancelar, cada tarea secundaria asociada o desasociada debe supervisar el estado del token de cancelación. Si desea cancelar un elemento primario y todos sus elementos secundarios utilizando una solicitud de cancelación, debe pasar el mismo token como argumento a todas las tareas y proporcionar en cada tarea la lógica de respuesta a la solicitud en cada tarea. Para más información, vea [Cancelación de tareas](../../../docs/standard/parallel-programming/task-cancellation.md) y [Cómo: Cancelar una tarea y sus elementos secundarios](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
### <a name="when-the-parent-cancels"></a>Cuando la tarea primaria se cancela  
 Si una tarea primaria se cancela antes de que se inicie su tarea secundaria, la tarea secundaria nunca se inicia. Si una tarea primaria se cancela después de que se ha iniciado su tarea secundaria, la tarea secundaria se ejecutará hasta completarse a menos que tenga su propia lógica de cancelación. Para más información, vea [Cancelación de tareas](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
### <a name="when-a-detached-child-task-cancels"></a>Cuando una tarea secundaria desasociada se cancela  
 Si una tarea secundaria desasociada se cancela usando el mismo token que se pasó a la tarea primaria, y la tarea primaria no espera a la tarea secundaria, no se propagará ninguna excepción puesto que la excepción se trata cono una cancelación de cooperación benigna. Este comportamiento es igual que el de cualquier tarea de nivel superior.  
  
### <a name="when-an-attached-child-task-cancels"></a>Cuando se cancela una tarea secundaria asociada  
 Cuando una tarea secundaria asociada se cancela usando el mismo token que se pasó a su tarea primaria, se propaga una excepción <xref:System.Threading.Tasks.TaskCanceledException> al subproceso de unión dentro de <xref:System.AggregateException>. Se debe esperar a la tarea primaria para poder controlar todas las excepciones benignas además de todas las excepciones de error que se propagan de manera ascendente a través de un gráfico de tareas secundarias asociadas.  
  
 Para más información, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
## <a name="preventing-a-child-task-from-attaching-to-its-parent"></a>Impedir que una tarea secundaria se adjunte a su tarea primara  
 Una excepción no controlada producida por una tarea secundaria se propaga a la tarea primaria. Puede usar este comportamiento para observar todas las excepciones de tareas secundarias desde una tarea raíz en lugar de recorrer un árbol de tareas. Sin embargo, la propagación de excepciones puede dar problemas cuando una tarea primaria no cuenta con datos adjuntos de otro código. Por ejemplo, piense en una aplicación que llama a un componente de la biblioteca de terceros de un objeto <xref:System.Threading.Tasks.Task>. Si el componente de la biblioteca de terceros también crea un objeto <xref:System.Threading.Tasks.Task> y especifica <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> para asociarlo a la tarea primaria, las excepciones no controladas que aparecen en la tarea secundaria se propagan a la tarea primaria. Esto podría dar lugar a un comportamiento inesperado en la aplicación principal.  
  
 Para evitar que una tarea secundaria se adjunte a su tarea primaria, especifique la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> cuando cree el objeto primario <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Cuando una tarea intenta asociarse a su elemento primario y el elemento primario especifica la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, la tarea secundaria no podrá asociarse a un elemento primario y se ejecutará como si no se hubiera especificado la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>.  
  
 Puede que también desee evitar que una tarea secundaria se adjunte a su tarea primaria cuando la tarea secundaria no finaliza a tiempo. Dado que una tarea primaria no finaliza hasta que finalizan todas las tareas secundarias, una tarea secundaria que se ejecute durante mucho tiempo puede provocar que el rendimiento general de la aplicación sea mediocre. Para obtener un ejemplo en el que se muestra cómo mejorar el rendimiento de la aplicación evitando que una tarea se asocie a su tarea primaria, vea [Procedimiento para evitar que una tarea secundaria se adjunte a su elemento primario](../../../docs/standard/parallel-programming/how-to-prevent-a-child-task-from-attaching-to-its-parent.md).  
  
## <a name="see-also"></a>Vea también

- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
- [Paralelismo de datos](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
