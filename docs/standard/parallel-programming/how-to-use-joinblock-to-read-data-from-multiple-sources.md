---
title: "Cómo: Usar JoinBlock para leer datos de diferentes orígenes"
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
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41445e4874b94809840ecf9ebda6f27ccc955c9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Cómo: Usar JoinBlock para leer datos de diferentes orígenes
Este documento explica cómo utilizar el <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> clase para realizar una operación cuando los datos están disponibles en varios orígenes. También se muestra cómo utilizar el modo no expansivo para permitir que varios bloques de combinación puedan compartir un origen de datos más eficazmente.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo define tres tipos de recursos, `NetworkResource`, `FileResource`, y `MemoryResource`y realiza las operaciones cuando los recursos estén disponibles. Este ejemplo se necesita una `NetworkResource` y `MemoryResource` par con el fin de realizar la primera operación y un `FileResource` y `MemoryResource` par con el fin de realizar la segunda operación. Para habilitar estas operaciones que se produzca cuando todos los recursos necesarios están disponibles, este ejemplo se utiliza la <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> clase. Cuando un <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objeto recibe los datos de todos los orígenes, propaga esos datos a su destino, que en este ejemplo es un <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objeto. Ambos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> leen objetos de un grupo compartido de `MemoryResource` objetos.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Para habilitar el uso eficaz del grupo compartido de `MemoryResource` objetos, este ejemplo se especifica un <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> objeto que tiene el <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> propiedad establecida en `False` crear <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objetos que actúan en modo no expansivo. Un bloque de combinación no expansiva pospone todos los mensajes entrantes hasta que uno esté disponible de cada origen. Si cualquiera de los mensajes pospuestos ya aceptada por otro bloque, el bloque de combinación reinicia el proceso. El modo no expansivo permite bloques de combinación que comparten uno o más bloques de origen progresar mientras esperan los otros bloques de datos. En este ejemplo, si un `MemoryResource` objeto se agrega a la `memoryResources` del grupo, la combinación de primer bloque para recibir su segundo origen de datos puede progresar. Si este ejemplo se fuera a usar el modo expansivo, que es el valor predeterminado, un bloque de combinación pueden tardar la `MemoryResource` objeto y espere a que el segundo recurso esté disponible. Sin embargo, si el otro bloque de combinación tiene su segundo origen de datos disponible, no puede progresar porque la `MemoryResource` objeto ha sido tomado por otro bloque de combinación.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
 El uso de las uniones no expansivas también puede ayudar a evitar el interbloqueo en la aplicación. En una aplicación de software, *interbloqueo* se produce cuando dos o más procesos mantienen un recurso y esperan mutuamente a que otro proceso libere algún otro recurso. Considere la posibilidad de una aplicación que define dos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objetos. Ambos objetos leen datos de dos bloques de código fuente compartido. En modo expansivo, si se lee un bloque de combinación del primer origen y el segundo bloque de combinación se lee desde el origen de la segundo, la aplicación podría generar un interbloqueo porque ambos bloques de combinación esperan mutuamente a que la otra transacción libere sus recursos. En el modo no expansivo, cada bloque de combinación se elimina las lecturas de sus orígenes sólo cuando todos los datos están disponibles y, por lo tanto, el riesgo de interbloqueo.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
