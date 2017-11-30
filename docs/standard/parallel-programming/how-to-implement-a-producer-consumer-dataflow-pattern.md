---
title: "Cómo: Implementar un modelo de flujo de datos productor-consumidor"
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
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1aba08e8364d8a21f70ab480d58041115a4849e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Cómo: Implementar un modelo de flujo de datos productor-consumidor
Este documento describe cómo utilizar la biblioteca de flujos de datos TPL para implementar un modelo productor-consumidor. En este modelo, el *productor* envía mensajes a un bloque de mensajes y el *consumidor* lee los mensajes de este bloque.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un modelo productor-consumidor básico que usa el flujo de datos. El `Produce` método escribe matrices que contienen los bytes aleatorios de datos a un <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> objeto y el `Consume` método lee los bytes de un <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> objeto. Al actuar en el <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces en lugar de sus tipos derivados, puede escribir código reutilizable que puede actuar en una variedad de tipos de bloques de flujo de datos. Este ejemplo se utiliza la <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> clase. Dado que el <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> bloquear clase actúa como origen y como un bloque de destino, el productor y el consumidor pueden utilizar un objeto compartido para transferir datos.  
  
 El `Produce` llamadas al método el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> método en un bucle para escribir datos en el bloque de destino de forma sincrónica. Después de la `Produce` método escribe todos los datos al bloque de destino, llama a la <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> método para indicar que el bloque nunca tendrá datos adicionales disponibles. El `Consume` método usa la [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) operadores ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) y [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) a calcular de forma asincrónica el número total de bytes que se reciben desde la <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objeto. Para que actúe de forma asincrónica, el `Consume` llamadas al método el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> método para recibir una notificación cuando el bloque de origen tiene datos disponibles y cuando el bloque de origen nunca tendrá datos adicionales disponibles.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
 Este ejemplo utiliza un solo consumidor para procesar los datos de origen. Si tiene varios consumidores en la aplicación, use la <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> método para leer datos desde el bloque de origen, tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 El <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> método `False` cuando no hay datos disponibles. Cuando varios consumidores deben acceder simultáneamente al bloque de origen, este mecanismo garantiza que los datos son estando disponibles después de llamar a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
