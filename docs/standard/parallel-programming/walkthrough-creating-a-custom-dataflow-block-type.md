---
title: "Walkthrough: Creating a Custom Dataflow Block Type | Microsoft Docs"
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
  - "TPL dataflow library, creating custom dataflow blocks"
  - "dataflow blocks, creating custom in TPL"
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Creating a Custom Dataflow Block Type
Aunque la biblioteca de TPL Dataflow proporciona varios flujos de datos bloquee los tipos que permiten una variedad de funcionalidades, también puede crear tipos de bloques de personalizadas.  Este documento se describe cómo crear un flujo de datos en bloques que implementa un comportamiento personalizado.  
  
## Requisitos previos  
 Lectura [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) antes de leer este documento.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Definición del bloque de flujo de datos de la ventana el deslizar  
 Considere una aplicación de flujo de datos que requiere que escribir valores están almacenados en búfer y después generarse de una manera de la ventana el deslizar.  Por ejemplo, los valores de entrada {0, 1, 2, 3, 4, 5} y un tamaño de la ventana de tres, un bloque de flujo de datos de la ventana el deslizar genera las matrices de salida {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, y {3, 4, 5}.  Las secciones siguientes se describen dos maneras de crear un flujo de datos en bloques que implementa este comportamiento personalizado.  La primera técnica utiliza el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> para combinar la funcionalidad de un objeto de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y un objeto de <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> en un bloque propagador.  La segunda técnica define una clase que deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> y combinar la funcionalidad existente para realizar el comportamiento personalizado.  
  
## Mediante el método de encapsular los Define el bloque de flujo de datos de la ventana el deslizar  
 El ejemplo siguiente se utiliza el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> para crear un bloque propagador de un destino y un origen.  Un bloque propagador habilita un bloque de origen y un destino bloqueados actúe como receptor y remitente de los datos.  
  
 Esta técnica es útil si necesita funcionalidad personalizada de flujo de datos, pero no requiere un tipo que proporciona métodos adicionales, propiedades, campos o.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## Derivando de IPropagatorBlock para Definir el bloque de flujo de datos de la ventana el deslizar  
 En el siguiente ejemplo se muestra la clase `SlidingWindowBlock`.  Esta clase se deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> de modo que pueda actuar como origen y destino de datos.  Como en el ejemplo anterior, la clase de `SlidingWindowBlock` se compila en tipos existentes de bloques de flujo de datos.  Sin embargo, la clase de `SlidingWindowBlock` también implementa los métodos requeridos por <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, e interfaces de <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> .  Todos estos métodos transmiten a trabajo los miembros en bloques predefinidos de flujo de datos.  Por ejemplo, el método de `Post` deja el trabajo al miembro de datos de `m_target` , que también es un objeto de <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> .  
  
 Esta técnica es útil si necesita funcionalidad personalizada de flujo de datos, y también requiere un tipo que proporciona métodos adicionales, propiedades, campos o.  Por ejemplo, la clase de `SlidingWindowBlock` también se deriva de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> para poder proporcionar métodos de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> y de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> .  La clase de `SlidingWindowBlock` también muestra extensibilidad proporcionando la propiedad de `WindowSize` , que recupera el número de elementos en la ventana el deslizar.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## Ejemplo completo  
 El ejemplo siguiente se muestra el código completo de este tutorial.  También muestra cómo utilizar el ambos que deslizan bloques de ventana en un método que escriba el bloque, lea de ella, e imprimir los resultados en la consola.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `SlidingWindowBlock.cs` \(`SlidingWindowBlock.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) y después se ejecute el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## Pasos siguientes  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)