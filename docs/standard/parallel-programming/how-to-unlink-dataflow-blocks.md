---
title: "Cómo: Desvincular bloques de flujos de datos"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a>Cómo: Desvincular bloques de flujos de datos
Este documento describe cómo desvincular un bloque de flujo de datos de destino de su origen.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea tres <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objetos, cada uno de los que llama el `TrySolution` método para calcular un valor. Este ejemplo requiere sólo el resultado de la primera llamada a `TrySolution` para finalizar.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Para recibir el valor de la primera <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto que termina, este ejemplo se define la `ReceiveFromAny(T)` método. El `ReceiveFromAny(T)` método acepta una matriz de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objetos y vincula cada uno de estos objetos a un <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto. Cuando se usa el <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método para vincular un bloque de flujo de datos de origen a un bloque de destino, el origen propaga mensajes al destino tal y como los datos están disponibles. Dado que el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> clase acepta solo el primer mensaje que ofrece, el `ReceiveFromAny(T)` método genera su resultado mediante una llamada a la <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> (método). Esto produce el primer mensaje que se ofrece a los <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto. El <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método tiene una versión sobrecargada que toma un <xref:System.Boolean> parámetro, `unlinkAfterOne` que, cuando se establece en `True`, indica el bloque de origen para desvincular desde el destino después de que el destino recibe un mensaje desde el origen. Es importante para la <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto desvinculación de sus orígenes porque la relación entre la matriz de los orígenes y el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto ya no es necesario una vez el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object recibe un mensaje.  
  
 Para habilitar las llamadas restantes a `TrySolution` a finalizar después de que uno de ellos calcula un valor, el `TrySolution` método toma un <xref:System.Threading.CancellationToken> objeto que se cancela después de llamar a `ReceiveFromAny(T)` devuelve. El <xref:System.Threading.SpinWait.SpinUntil%2A> método devuelve cuando esto <xref:System.Threading.CancellationToken> objeto está cancelado.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
