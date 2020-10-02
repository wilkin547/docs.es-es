---
title: 'Procedimiento: Implementación de un modelo de flujo de datos productor-consumidor'
description: Aprenda a implementar un modelo de flujo de datos productor-consumidor con la biblioteca de flujos de datos TPL en .NET.
ms.date: 09/24/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
ms.openlocfilehash: fc68d9e678dab88ec5008b6c15ef17a5d20f25ae
ms.sourcegitcommit: d04388f94dbcd756ffd608536c869aee3242cdb0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91206385"
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Procedimiento: Implementación de un modelo de flujo de datos productor-consumidor

En este artículo, aprenderá a utilizar la biblioteca de flujos de datos TPL para implementar un modelo productor-consumidor. En este modelo, el *productor* envía mensajes a un bloque de mensajes y el *consumidor* lee los mensajes de este bloque.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un modelo productor-consumidor básico que usa el flujo de datos. El método `Produce` escribe matrices que contienen bytes de datos aleatorios en un objeto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> y el método `Consume` lee los bytes de un objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>. Al actuar en las interfaces <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, en lugar de en sus tipos derivados, puede escribir código reutilizable que puede actuar en una variedad de tipos de bloques de flujo de datos. Este ejemplo utiliza la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>. Puesto que la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> actúa como origen y como un bloque de origen y destino, el productor y el consumidor pueden utilizar un objeto compartido para transferir datos.

 El método `Produce` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> en un bucle para escribir datos de forma sincrónica en el bloque de destino. Después de que el método `Produce` escriba todos los datos en el bloque de destino, llama al método <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> para indicar que el bloque nunca tendrá datos adicionales disponibles. El método `Consume` usa los operadores [async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic) para calcular de forma asincrónica el número total de bytes recibidos del objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>. Para que actúe de forma asincrónica, el método `Consume` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> para recibir una notificación cuando el bloque de origen tiene datos disponibles y cuando el bloque de origen nunca va a tener datos adicionales disponibles.

 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]

## <a name="robust-programming"></a>Programación sólida

 En el ejemplo anterior se usa un solo consumidor para procesar los datos de origen. Si tiene varios consumidores en la aplicación, use el método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer datos desde el bloque de origen, como se muestra en el siguiente ejemplo.

 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]

 El método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> devuelve `False` cuando no hay datos disponibles. Cuando varios consumidores deben tener acceso simultáneamente al bloque de origen, este mecanismo garantiza que los datos están disponibles después de la llamada a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.

## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
