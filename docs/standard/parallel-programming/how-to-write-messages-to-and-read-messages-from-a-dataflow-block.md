---
title: "How to: Write Messages to and Read Messages from a Dataflow Block | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, reading and writing messages"
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Write Messages to and Read Messages from a Dataflow Block
En este documento se describe cómo utilizar la biblioteca de TPL Dataflow para escribir y leer los mensajes de un bloque de flujo de datos.  La biblioteca de TPL Dataflow proporciona sincrónico y métodos asincrónicos para escribir y leer los mensajes de un bloque de flujo de datos.  Este documento utiliza la clase de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=fullName> .  La clase de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> almacena en búfer los mensajes y se comporta como origen del mensaje como destino del mensaje.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Escriben y la lectura de un bloque Synchronously de flujo de datos  
 El ejemplo siguiente se usa el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> para escribir en un bloque de flujo de datos de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> y el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> a la lectura del mismo objeto.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 También puede utilizar el método de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer un bloque de flujo de datos, como se muestra en el ejemplo siguiente.  El método de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> no bloquea el subproceso actual y es útil cuando se sondea en ocasiones para los datos.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Porque actúa el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> sincrónica, el objeto de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> en los ejemplos anteriores recibe todos los datos antes de que el segundo bucle leer datos.  El ejemplo siguiente extiende el primer ejemplo mediante <xref:System.Threading.Tasks.Parallel.Invoke%2A> de lectura y escritura al bloque de mensajes simultáneamente.  Dado que <xref:System.Threading.Tasks.Parallel.Invoke%2A> realiza acciones en paralelo, los valores no se escriben en el objeto de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> en ningún orden determinado.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## Escriben y la lectura de un bloque Asincrónicamente de flujo de datos  
 El ejemplo siguiente se utiliza el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> asincrónica para escribir en un objeto de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> y el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> de forma asincrónica a la lectura del mismo objeto.  Este ejemplo utiliza operadores de [async](../Topic/async%20\(C%23%20Reference\).md) y de [espera](../Topic/await%20\(C%23%20Reference\).md) \([Async](../Topic/Async%20\(Visual%20Basic\).md) y [Espera](../Topic/Await%20Operator%20\(Visual%20Basic\).md) en Visual Basic\) de forma asincrónica para enviar y para leer datos de bloque de destino.  El método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> es útil cuando se debe permitir que un bloque de flujo de datos para aplazar mensajes.  El método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> es útil cuando desea representar en datos cuando esos datos está disponible.  Para obtener más información sobre cómo la propagación de mensajes entre bloques de mensajes, vea el mensaje de la sección se pasa [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## Un ejemplo completo  
 El ejemplo siguiente se muestra el código completo de este documento.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DataflowReadWrite.cs` \(`DataflowReadWrite.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## Pasos siguientes  
 Este ejemplo muestra cómo leer y escribir en un bloque de mensajes directamente.  También puede conectar los bloques de flujo de datos para calcular *las referencias de canalizaciones*, que son secuencias lineales de bloques de flujo de datos, o *redes*, que son gráficos de bloques de flujo de datos.  En una canalización o red, los orígenes propagan datos de forma asincrónica en destinos a medida que esos datos están disponibles.  Para obtener un ejemplo que crea una canalización básica de flujo de datos, vea [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).  Para obtener un ejemplo que crea una red más compleja de flujo de datos, vea [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)