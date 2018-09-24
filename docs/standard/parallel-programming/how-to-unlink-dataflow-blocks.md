---
title: 'Cómo: Desvincular bloques de flujos de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc0f266169a2d82bb76355febd58b2268907fe97
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46540611"
---
# <a name="how-to-unlink-dataflow-blocks"></a>Cómo: Desvincular bloques de flujos de datos
En este documento se describe cómo desvincular un bloque de flujo de datos de destino de su origen.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean tres objetos <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, y cada uno de ellos llama al método `TrySolution` para calcular un valor. Este ejemplo requiere solo el resultado de la primera llamada a `TrySolution` para finalizar.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Para recibir el valor del primer objeto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> que termina, este ejemplo define el método `ReceiveFromAny(T)`. El método `ReceiveFromAny(T)` acepta una matriz de objetos <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y vincula cada uno de estos objetos a un objeto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. Cuando se usa el método <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> para vincular un bloque de flujo de datos de origen a un bloque de destino, el origen propaga mensajes al destino a medida que los datos están disponibles. Dado que la clase <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> acepta solo el primer mensaje que se ofrece, el método `ReceiveFromAny(T)` genera su resultado mediante una llamada al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>. Esto produce el primer mensaje que se ofrece al objeto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. El método <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> tiene una versión sobrecargada que adopta un objeto <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> con una propiedad <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> que, cuando se establece en `1`, indica al bloque de origen que se desvincule del destino después de que el destino reciba un mensaje del origen. Es importante que el objeto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> se desvincule de sus orígenes porque la relación entre la matriz de orígenes y el objeto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> ya no es necesaria una vez que el objeto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> recibe un mensaje.  
  
 Para habilitar las llamadas restantes a `TrySolution` para terminar una vez que una de ellas calcula un valor, el método `TrySolution` adopta un objeto <xref:System.Threading.CancellationToken> que se cancela después de llamar a las devoluciones `ReceiveFromAny(T)`. El método <xref:System.Threading.SpinWait.SpinUntil%2A> realiza la devolución cuando este objeto <xref:System.Threading.CancellationToken> se cancela.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` para Visual Basic) y, luego, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 Visual Basic  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  

## <a name="see-also"></a>Vea también

- [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
