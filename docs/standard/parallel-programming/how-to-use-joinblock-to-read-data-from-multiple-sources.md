---
title: "How to: Use JoinBlock to Read Data From Multiple Sources | Microsoft Docs"
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
  - "TPL dataflow library, joining blocks in"
  - "dataflow blocks, joining in TPL"
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Use JoinBlock to Read Data From Multiple Sources
En este documento se explica cómo utilizar la clase de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> para realizar una operación cuando los datos están disponibles de varios orígenes.  También muestra cómo utilizar el modo no expansivo para permitir a los bloques de combinación múltiple para compartir un origen de datos más eficazmente.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Ejemplo  
 El ejemplo siguiente define tres tipos de recursos, `NetworkResource`, `FileResource`, y `MemoryResource`, y realizar operaciones cuando los recursos estén disponibles.  Este ejemplo requiere un par de `NetworkResource` y de `MemoryResource` para realizar la primera operación y un par de `FileResource` y de `MemoryResource` para realizar la segunda operación.  Para permitir que estas operaciones se produzca cuando todos los recursos necesarios están disponibles, este ejemplo utiliza la clase de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> .  Cuando un objeto de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> recibe los datos de todos los orígenes, propaga ese datos a su destino, que en este ejemplo es un objeto de <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> .  Lectura de ambos objetos de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> de un conjunto compartido de objetos de `MemoryResource` .  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Para habilitar el uso eficaz de conjunto compartido de objetos de `MemoryResource` , este ejemplo especifica un objeto de <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> que tiene la propiedad de <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> establecida en `False` para crear los objetos de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> que actúan en modo no expansivo.  Un bloque no expansivo join posponer todos los mensajes entrantes hasta que uno esté disponible de cada origen.  Si los mensajes pospuestos cualquiera de los se aceptados por otro bloque, el bloque de unión reinicie el proceso.  Los bloques no expansivos de la unión de los permisos de modo que comparten uno o más bloques de origen para progresar como los otros bloques esperan datos.  En este ejemplo, si un objeto de `MemoryResource` se agrega al conjunto de `memoryResources` , el primer bloque de unión para recibir el segundo origen de datos puede progresar.  Si este ejemplo es utilizar el modo expansivo, que es el valor predeterminado, un bloque combinado puede tomar el objeto y espera de `MemoryResource` para que el segundo recurso está disponible.  Sin embargo, si otro bloque de unión tiene el segundo origen de datos disponible, no puede progresar porque el objeto de `MemoryResource` ha realizado por otro bloque de unión.  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DataflowNonGreedyJoin.cs` \(`DataflowNonGreedyJoin.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## Programación eficaz  
 El uso de no expansivas también puede ayudar a evitar el interbloqueo en la aplicación.  En una aplicación de software, el *interbloqueo* se produce cuando dos o más procesos mantienen un recurso y esperan mutuamente a que el otro proceso libere algún otro recurso.  Considere una aplicación que define dos objetos de <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> .  Ambos objetos cada datos de lectura con dos pasos compartidos bloques de origen.  En modo expansivo, si lee combinadas de un bloque del primer origen y la segunda lee del bloque de la unión del segundo origen, la aplicación podría bloquear porque los dos bloques de unión esperan mutuamente otro libere el recurso.  En modo no expansivo, cada combina las lecturas de bloque de sus orígenes cuando todos los datos disponible, por consiguiente, el riesgo de interbloqueo se elimina.  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)