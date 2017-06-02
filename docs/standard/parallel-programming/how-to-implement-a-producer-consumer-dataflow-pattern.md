---
title: "How to: Implement a Producer-Consumer Dataflow Pattern | Microsoft Docs"
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
  - "TPL dataflow library, implementing producer-consumer pattern"
  - "Task Parallel Library, dataflows"
  - "producer-consumer patterns, implementing [TPL]"
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Implement a Producer-Consumer Dataflow Pattern
En este documento se describe cómo utilizar la biblioteca de TPL Dataflow para implementar un modelo productor\-consumidor.  En este modelo, el *productor* envía mensajes a un bloque de mensajes y el *consumidor* lee los mensajes de este bloque.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Ejemplo  
 El ejemplo siguiente muestra un modelo básico de consumidor\-productor que utilice flujo de datos.  El método de `Produce` escribe las matrices que contienen bytes aleatorios de datos a un objeto de <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=fullName> y el método de `Consume` lee bytes de un objeto de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=fullName> .  Actuando en las interfaces de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y de <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> , en lugar de sus tipos derivados, puede escribir código reutilizable que puede representar en una variedad de tipos de bloques de flujo de datos.  Este ejemplo utiliza la clase de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> .  Dado que actúa la clase de <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> mientras un origen y como bloque de destino, el productor y el consumidor pueden utilizar un objeto compartido a los datos de transferencia.  
  
 Las llamadas al método de `Produce` el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> en un bucle para escribir sincrónicamente datos al bloque de destino.  Después de que el método de `Produce` escriba todos los datos al bloque de destino, llama al método de <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> para indicar que el bloque nunca tendrá datos adicionales disponibles.  El método de `Consume` usan operadores de [async](../Topic/async%20\(C%23%20Reference\).md) y de [espera](../Topic/await%20\(C%23%20Reference\).md) \([Async](../Topic/Async%20\(Visual%20Basic\).md) y [Espera](../Topic/Await%20Operator%20\(Visual%20Basic\).md) en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) de forma asincrónica para calcular el número total de bytes que se reciben del objeto de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> .  Para representar de forma asincrónica, las llamadas al método de `Consume` el método de <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> para recibir una notificación cuando el bloque de origen tiene datos disponibles y cuando el bloque de origen nunca tendrá datos adicionales disponibles.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DataflowProducerConsumer.cs` \(`DataflowProducerConsumer.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## Programación eficaz  
 Este ejemplo utiliza un solo un consumidor para procesar los datos de origen.  Si tiene varios consumidores en la aplicación, utilice el método de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer datos de bloque de origen, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 El método de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> devuelve `False` cuando no hay datos disponibles.  Cuando son varios consumidores deben tener acceso al origen bloqueado en paralelo, las garantías de este mecanismo que los datos aún está disponible después de la llamada al <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)