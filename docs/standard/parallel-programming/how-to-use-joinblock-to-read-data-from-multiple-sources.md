---
title: 'Cómo: Usar JoinBlock para leer datos de diferentes orígenes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
ms.openlocfilehash: 381c77ee37b2ce03e7e45ad41bef31a9bd7b6ede
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722653"
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Cómo: Usar JoinBlock para leer datos de diferentes orígenes

En este documento se explica cómo utilizar la clase <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> para realizar una operación cuando los datos están disponibles en varios orígenes. También se demuestra cómo usar el modo no expansivo para habilitar varios bloques de combinación para compartir un origen de datos más eficazmente.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Ejemplo  

 El siguiente ejemplo define tres tipos de recursos, `NetworkResource`, `FileResource` y `MemoryResource`, y realiza las operaciones cuando los recursos están disponibles. Este ejemplo requiere un par `NetworkResource` y `MemoryResource` para realizar la primera operación y un par `FileResource` y `MemoryResource` para realizar la segunda operación. Para permitir que estas operaciones se produzcan cuando todos los recursos necesarios están disponibles, este ejemplo usa la clase <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Cuando un objeto <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> recibe datos de todos los orígenes, los propaga en su destino, que en este ejemplo es un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Ambos objetos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> leen de un grupo compartido de objetos `MemoryResource`.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Para habilitar el uso eficaz del grupo compartido de objetos `MemoryResource`, este ejemplo especifica un objeto <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> que tiene la propiedad <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> establecida en `False` para crear objetos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> que actúan de modo no expansivo. Un bloque de combinación no expansivo pospone todos los mensajes entrantes hasta que uno esté disponible de cada origen. Si otro bloque aceptó cualquiera de los mensajes pospuestos, el bloque de combinación reinicia el proceso. El modo no expansivo permite que los bloques de combinación compartan uno o varios bloques de origen para avanzar mientras otros bloques esperan datos. En este ejemplo, si un objeto `MemoryResource` se agrega al grupo `memoryResources`, el primer bloque de combinación que recibe su segundo origen de datos puede progresar. Si en este ejemplo se usara el modo expansivo, que es el predeterminado, un bloque de combinación puede adoptar el objeto `MemoryResource` y esperar a que el segundo recurso esté disponible. Sin embargo, si el otro bloque de combinación tiene su segundo origen de datos disponible, no puede avanzar porque otro bloque de combinación ha adoptado el objeto `MemoryResource`.  
  
## <a name="robust-programming"></a>Programación sólida  

 El uso de las combinaciones no expansivas también puede ayudar a evitar el interbloqueo en la aplicación. En una aplicación de software, el *interbloqueo* se produce cuando dos o más procesos mantienen un recurso y esperan mutuamente a que el otro proceso libere algún otro recurso. Considere una aplicación que define dos objetos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Ambos objetos leen datos de dos bloques de origen compartidos. En modo expansivo, si un bloque de combinación lee desde el primer origen y el segundo bloque de combinación lee desde el segundo origen, se podría producir un interbloqueo de la aplicación porque los dos bloques de combinación esperan a que el otro libere su recurso. En el modo no expansivo, cada bloque de combinación lee de sus orígenes solo cuando todos los datos están disponibles y, por tanto, se elimina el riesgo del interbloqueo.  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
