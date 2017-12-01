---
title: "Cómo: Realizar una acción cuando un bloque de flujos de datos recibe datos"
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
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d049d20f5e685096a72857cd18a89688633883c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Cómo: Realizar una acción cuando un bloque de flujos de datos recibe datos
Los tipos *Bloque de flujo de datos de ejecución* llaman a un delegado proporcionado por el usuario cuando reciben datos. El <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> las clases son tipos de bloques de flujo de datos de ejecución. Puede usar el `delegate` palabra clave (`Sub` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), <xref:System.Action%601>, <xref:System.Func%602>, o una expresión lambda cuando se proporciona una función de trabajo a un bloque de flujo de datos de ejecución. Este documento describe cómo usar <xref:System.Func%602> y las expresiones lambda para realizar la acción en bloques de ejecución.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el flujo de datos para leer un archivo del disco y se calcula el número de bytes en el archivo que son iguales a cero. Usa <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para leer el archivo y calcule el número de cero bytes y <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> para imprimir el número de cero bytes en la consola. El <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto especifica un <xref:System.Func%602> objeto que se va a realizar el trabajo cuando reciben de los bloques de datos. La <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objeto utiliza una expresión lambda para imprimir en la consola el número de cero bytes que se leen.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Aunque puede proporcionar una expresión lambda a una <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto, este ejemplo se utiliza <xref:System.Func%602> para habilitar otro código para usar el `CountBytes` método. La <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objeto utiliza una expresión lambda debe realizar el trabajo es específico de esta tarea y no suele ser útil desde otro código. Para información sobre cómo funcionan las expresiones lambda en la biblioteca TPL, vea [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 La sección Resumen de tipos de delegado en el [flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) documento resume los tipos de delegado que puede proporcionar a <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> objetos. La tabla también especifica si el tipo de delegado funciona de forma sincrónica o asincrónica.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowExecutionBlocks.cs` (`DataflowExecutionBlocks.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
 Este ejemplo proporciona un delegado del tipo <xref:System.Func%602> a la <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto que se va a realizar la tarea del bloque de flujo de datos de forma sincrónica. Para habilitar el bloque de flujo de datos se comporten de forma asincrónica, proporcionar un delegado del tipo <xref:System.Func%601> al bloque de flujo de datos. Cuando un bloque de flujo de datos se comporta de forma asincrónica, la tarea del bloque de flujo de datos está completado solo cuando el valor devuelto <xref:System.Threading.Tasks.Task%601> objeto finaliza. En el ejemplo siguiente se modifica el método `CountBytes` y se utilizan los operadores [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) y [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) para procesar de forma asincrónica el número total de cero bytes en el archivo proporcionado. El <xref:System.IO.FileStream.ReadAsync%2A> método realiza las operaciones de lectura de archivo de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 También puede utilizar expresiones lambda asincrónicas para realizar la acción en un bloque de flujo de datos de ejecución. En el ejemplo siguiente se modifica la <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto que se usa en el ejemplo anterior para que utilice una expresión lambda para realizar el trabajo de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
