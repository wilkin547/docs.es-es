---
title: "Cómo: Escribir y leer mensajes en un bloque de flujo de datos"
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
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf609a8c350a44fc802cce0ec10693431bbf4f42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Cómo: Escribir y leer mensajes en un bloque de flujo de datos
En este documento se describe cómo usar la biblioteca de flujos de datos TPL para escribir y leer mensajes en un bloque de flujo de datos. La biblioteca de flujos de datos TPL proporciona métodos sincrónicos y asincrónicos para escribir y leer mensajes en un bloque de flujo de datos. Este documento usa la <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> clase. La <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> clase almacena en búfer los mensajes y se comporta como un origen de mensaje, como un destino de mensaje.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Escribir y leer en un bloque de flujo de datos de forma sincrónica  
 En el ejemplo siguiente se usa el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> método para escribir en un <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> bloque de flujo de datos y la <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> método para leer desde el mismo objeto.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 También puede usar el <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> método para leer desde un bloque de flujo de datos, como se muestra en el ejemplo siguiente. El <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> método no bloquea el subproceso actual y es útil cuando en ocasiones, el sondeo de datos.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Dado que la <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> método actúa de forma sincrónica, la <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> objeto en los ejemplos anteriores recibe todos los datos antes de que el segundo bucle lee los datos. En el ejemplo siguiente se amplía el primer ejemplo usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> para leer y escribir en el bloque de mensajes al mismo tiempo. Dado que <xref:System.Threading.Tasks.Parallel.Invoke%2A> realiza acciones al mismo tiempo, los valores no se escriben en la <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> objeto en un orden específico.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Escribir y leer en un bloque de flujo de datos de forma asincrónica  
 En el ejemplo siguiente se usa el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> método escribir asincrónicamente en un <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> objeto y el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> método para leer de forma asincrónica el mismo objeto. En este ejemplo se usan los operadores [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) y [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic) para, asincrónicamente, enviar datos al bloque de destino y leerlos en él. El <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> método resulta útil si debe habilitar un bloque de flujo de datos posponer mensajes. El <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> método resulta útil cuando desea actuar en los datos cuando dichos datos estarán disponibles. Para más información sobre la propagación de los mensajes entre los bloques de mensajes, consulte la sección Paso de mensajes en [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Un ejemplo completo  
 En el siguiente ejemplo se muestra el código completo de este documento.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowReadWrite.cs` (`DataflowReadWrite.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este ejemplo se muestra cómo leer y escribir directamente en un bloque de mensajes. También puede conectar los bloques de flujo de datos para establecer *canalizaciones*, que son secuencias lineales de bloques de flujo de datos, o *redes*, que son gráficos de bloques de flujo de datos. En una canalización o red, los orígenes propagan datos de forma asincrónica en destinos a medida que esos datos están disponibles. Para obtener un ejemplo en el que se cree una canalización de flujo de datos básica, consulte [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md) (Tutorial: Crear una canalización de flujo de datos). Para obtener un ejemplo en el que se cree una red de flujo de datos más compleja, consulte [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md) (Tutorial: Usar el flujo de datos en una aplicación de Windows Forms).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
