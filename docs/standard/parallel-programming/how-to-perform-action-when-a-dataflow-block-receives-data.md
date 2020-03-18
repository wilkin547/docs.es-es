---
title: 'Cómo: Realizar una acción cuando un bloque de flujos de datos recibe datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
ms.openlocfilehash: 89ab2bb18e5fe00a4d1b79d911bb0f7524b83104
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124214"
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Cómo: Realizar una acción cuando un bloque de flujos de datos recibe datos
Los tipos *Bloque de flujo de datos de ejecución* llaman a un delegado proporcionado por el usuario cuando reciben datos. Las clases <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> son tipos de bloques de flujo de datos de ejecución. Puede usar la palabra clave `delegate` (`Sub` en Visual Basic), <xref:System.Action%601>, <xref:System.Func%602> o una expresión lambda cuando proporcione una función de trabajo a un bloque de flujo de datos de ejecución. Este documento describe cómo usar <xref:System.Func%602> y expresiones lambda para realizar la acción en bloques de ejecución.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el flujo de datos para leer un archivo del disco y se calcula el número de bytes en el archivo que son iguales a cero. Usa <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para leer el archivo y calcular el número de cero bytes, y <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> para imprimir el número de cero bytes en la consola. El objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> especifica un objeto <xref:System.Func%602> para realizar el trabajo cuando los bloques reciben datos. El objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> usa una expresión lambda para imprimir en la consola el número de cero bytes que se lee.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Aunque puede proporcionar una expresión lambda para un objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, este ejemplo utiliza <xref:System.Func%602> para habilitar otro código para usar el método `CountBytes`. El objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> utiliza una expresión lambda porque el trabajo que se debe realizar es específico de esta tarea y es probable que no sea útil desde otro código. Para información sobre cómo funcionan las expresiones lambda en la biblioteca TPL, vea [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 En la sección Resumen de tipos de delegado del documento [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) se resumen los tipos de delegado que puede proporcionar a los objetos <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>. La tabla también especifica si el tipo de delegado funciona de forma sincrónica o asincrónica.  
  
## <a name="robust-programming"></a>Programación sólida  
 En este ejemplo se proporcionada un delegado de tipo <xref:System.Func%602> para el objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, con el fin de realizar la tarea del bloque de flujo de datos de forma sincrónica. Para que el bloque de flujo de datos se comporte de forma asincrónica, proporcione un delegado de tipo <xref:System.Func%601> al bloque de flujo de datos. Cuando un bloque de flujo de datos se comporta de forma asincrónica, la tarea del bloque de flujo de datos se completa solo cuando el objeto <xref:System.Threading.Tasks.Task%601> devuelto finaliza. En el ejemplo siguiente se modifica el método `CountBytes` y se usan los operadores [async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic) para calcular de forma asincrónica el número total de bytes que son cero en el archivo proporcionado. El método <xref:System.IO.FileStream.ReadAsync%2A> realiza las operaciones de lectura de archivo de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 También puede utilizar expresiones lambda asincrónicas para realizar la acción en un bloque de flujo de datos de ejecución. En el ejemplo siguiente se modifica el objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> que se utiliza en el ejemplo anterior para que utilice una expresión lambda para realizar el trabajo de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
