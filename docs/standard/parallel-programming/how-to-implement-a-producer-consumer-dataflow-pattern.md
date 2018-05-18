---
title: 'Cómo: Implementar un modelo de flujo de datos productor-consumidor'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d94cfeecc9556fb01dd3d72649d960ce68f929d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Cómo: Implementar un modelo de flujo de datos productor-consumidor
Este documento describe cómo utilizar la biblioteca de flujos de datos TPL para implementar un modelo productor-consumidor. En este modelo, el *productor* envía mensajes a un bloque de mensajes y el *consumidor* lee los mensajes de este bloque.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un modelo productor-consumidor básico que usa el flujo de datos. El método `Produce` escribe matrices que contienen bytes de datos aleatorios en un objeto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> y el método `Consume` lee los bytes de un objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>. Al actuar en las interfaces <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, en lugar de en sus tipos derivados, puede escribir código reutilizable que puede actuar en una variedad de tipos de bloques de flujo de datos. Este ejemplo utiliza la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>. Puesto que la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> actúa como origen y como un bloque de origen y destino, el productor y el consumidor pueden utilizar un objeto compartido para transferir datos.  
  
 El método `Produce` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> en un bucle para escribir datos de forma sincrónica en el bloque de destino. Después de que el método `Produce` escriba todos los datos en el bloque de destino, llama al método <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> para indicar que el bloque nunca tendrá datos adicionales disponibles. El método `Consume` usa los operadores [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) y [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic) para calcular de forma asincrónica el número total de bytes recibidos del objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>. Para que actúe de forma asincrónica, el método `Consume` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> para recibir una notificación cuando el bloque de origen tiene datos disponibles y cuando el bloque de origen nunca va a tener datos adicionales disponibles.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` para Visual Basic) y, luego, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 Visual Basic  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
 Este ejemplo utiliza un solo consumidor para procesar los datos de origen. Si tiene varios consumidores en la aplicación, use el método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer datos desde el bloque de origen, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 El método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> devuelve `False` cuando no hay datos disponibles. Cuando varios consumidores deben tener acceso simultáneamente al bloque de origen, este mecanismo garantiza que los datos están disponibles después de la llamada a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
