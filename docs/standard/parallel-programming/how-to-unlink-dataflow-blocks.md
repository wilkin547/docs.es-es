---
title: "How to: Unlink Dataflow Blocks | Microsoft Docs"
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
  - "dataflow blocks, unlinking in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, unlinking dataflow blocks"
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unlink Dataflow Blocks
Este documento describe cómo desenlazar un flujo de datos de destino del origen.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Ejemplo  
 El ejemplo siguiente se crean tres objetos de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> , que llama al método de `TrySolution` para calcular un valor.  Este ejemplo requiere sólo el resultado de la primera llamada a `TrySolution` finalice.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Para recibir el valor del primer objeto de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> que finaliza, en este ejemplo se define el método de `ReceiveFromAny(T)` .  El método de `ReceiveFromAny(T)` acepta una matriz de los objetos de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y vínculos cada uno de estos objetos a un objeto de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> .  Cuando se utiliza el método del <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> para vincular un bloque de flujo de datos de origen a un bloque de destino, el origen propaga mensajes al destino mientras los datos disponible.  Dado que la clase de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> solo acepta el primer mensaje que proporciona, el método de `ReceiveFromAny(T)` genera el resultado llamando al método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> .  Esto muestra el primer mensaje que se proporciona al objeto de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> .  El método de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> tiene una versión sobrecargada que toma un parámetro de <xref:System.Boolean> , `unlinkAfterOne` que, cuando se establece en `True`, pida al origen para bloquear desenlazar de destino después del destino recibe un mensaje de origen.  Es importante que el objeto de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> desvincular de sus orígenes porque la relación entre la matriz de orígenes y el objeto de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> ya no se requiere después de que el objeto de <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> recibe un mensaje.  
  
 Para que las llamadas restantes a `TrySolution` para finalizar después de que una de ellas calcula un valor, el método de `TrySolution` toma un objeto de <xref:System.Threading.CancellationToken> que se cancele después de la llamada a `ReceiveFromAny(T)` vuelva.  El método de <xref:System.Threading.SpinWait.SpinUntil%2A> devuelve cuando este objeto de <xref:System.Threading.CancellationToken> se cancela.  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DataflowReceiveAny.cs` \(`DataflowReceiveAny.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## Programación eficaz  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)