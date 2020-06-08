---
title: 'Cómo: Escribir y leer mensajes en un bloque de flujo de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: 917892e16a3517800953437f2fce877a57a64575
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290712"
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Cómo: Escribir y leer mensajes en un bloque de flujo de datos
En este documento se describe cómo usar la biblioteca de flujos de datos TPL para escribir y leer mensajes en un bloque de flujo de datos. La biblioteca de flujos de datos TPL proporciona métodos sincrónicos y asincrónicos para escribir y leer mensajes en un bloque de flujo de datos. Este documento usa la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>. La clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> almacena mensajes en búfer y se comporta como origen y destino de los mismos.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Escribir y leer en un bloque de flujo de datos de forma sincrónica  
 En el ejemplo siguiente se usa el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> para escribir en un bloque de flujo de datos <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> y el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> para leer desde el mismo objeto.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 También puede usar el método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer desde un bloque de flujo de datos, como se muestra en el ejemplo siguiente. El método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> no bloquea el subproceso actual y es útil cuando se realizan sondeos ocasionales de los datos.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Dado que el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> actúa de forma sincrónica, el objeto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> de los ejemplos anteriores recibe todos los datos antes de que el segundo bucle los lea. En el siguiente ejemplo se amplía el primer ejemplo mediante <xref:System.Threading.Tasks.Parallel.Invoke%2A> para leer y escribir en el bloque de mensajes simultáneamente. Dado que <xref:System.Threading.Tasks.Parallel.Invoke%2A> realiza acciones al mismo tiempo, los valores no se escriben en el objeto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> en un orden específico.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Escribir y leer en un bloque de flujo de datos de forma asincrónica  
 En el ejemplo siguiente se usa el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> para escribir de forma asincrónica en un objeto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> y el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> para leer de forma asincrónica desde el mismo objeto. En este ejemplo se usan los operadores [async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic) para, asincrónicamente, enviar datos al bloque de destino y leerlos en él. El método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> resulta útil si debe habilitar un bloque de flujo de datos para posponer mensajes. El método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> resulta útil cuando desea actuar en los datos cuando dichos datos están disponibles. Para más información sobre la propagación de los mensajes entre los bloques de mensajes, consulte la sección Paso de mensajes en [Flujo de datos](dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Un ejemplo completo  
 En el siguiente ejemplo se muestra el código completo de este documento.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este ejemplo se muestra cómo leer y escribir directamente en un bloque de mensajes. También puede conectar los bloques de flujo de datos para establecer *canalizaciones*, que son secuencias lineales de bloques de flujo de datos, o *redes*, que son gráficos de bloques de flujo de datos. En una canalización o red, los orígenes propagan datos de forma asincrónica en destinos a medida que esos datos están disponibles. Para obtener un ejemplo en el que se cree una canalización de flujo de datos básica, consulte [Walkthrough: Creating a Dataflow Pipeline](walkthrough-creating-a-dataflow-pipeline.md) (Tutorial: Crear una canalización de flujo de datos). Para obtener un ejemplo en el que se cree una red de flujo de datos más compleja, consulte [Walkthrough: Using Dataflow in a Windows Forms Application](walkthrough-using-dataflow-in-a-windows-forms-application.md) (Tutorial: Usar el flujo de datos en una aplicación de Windows Forms).  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
