---
title: "How to: Perform Action When a Dataflow Block Receives Data | Microsoft Docs"
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
  - "TPL dataflow library, receiving data"
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Action When a Dataflow Block Receives Data
Los tipos*de bloques de flujo de datos de ejecución de* llama usuario\- proporcionó el delegado cuando reciben datos.  <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName>, y las clases de <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName> son tipos de bloques de flujo de datos de la ejecución.  Puede utilizar la palabra clave de `delegate` \(`Sub` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), <xref:System.Action%601>, <xref:System.Func%602>, o una expresión lambda cuando se proporciona una función de trabajo a un bloque de flujo de datos de la ejecución.  Este documento se describe cómo usar <xref:System.Func%602> y expresiones lambda para realizar una acción en bloques de ejecución.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Ejemplo  
 El ejemplo siguiente utiliza flujo de datos para leer un archivo desde el disco y calcula el número de bytes de ese archivo que sean iguales a cero.  Utiliza <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para leer el archivo y para calcular el número de bytes cero, y <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> para imprimir el número de bytes cero en la consola.  El objeto de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> especifica un objeto de <xref:System.Func%602> para realizar el trabajo cuando los bloques reciben datos.  El objeto de <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> usa una expresión lambda para imprimir en la consola el número de bytes cero se lean que.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Aunque puede proporcionar una expresión lambda a un objeto de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> , este ejemplo utiliza <xref:System.Func%602> para permitir a otro código para utilizar el método de `CountBytes` .  El objeto de <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> usa una expresión lambda porque el trabajo que se realizará es específico de esta tarea y no es probable que sea útil de otro código.  Para obtener más información sobre cómo las expresiones lambda funcionan en la biblioteca TPL, vea [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 El resumen de la sección tipos de delegado en el documento de [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) se resumen los tipos de delegado que puede proporcionar a <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, a <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, y los objetos de <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> .  La tabla también especifica si el tipo de delegado funciona de forma sincrónica o asincrónica.  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DataflowExecutionBlocks.cs` \(`DataflowExecutionBlocks.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## Programación eficaz  
 Este ejemplo proporciona un delegado de <xref:System.Func%602> escrito en el objeto de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para realizar la tarea de flujo de datos bloqueado sincrónicamente.  Para permitir al bloque de flujo de datos para comportarse de forma asincrónica, proporcione un delegado de <xref:System.Func%601> escrito en el bloque de flujo de datos.  Cuando un bloque de flujo de datos se comporta de forma asincrónica, la tarea del bloque de flujo de datos se completa cuando el objeto devuelto de <xref:System.Threading.Tasks.Task%601> finaliza.  El ejemplo siguiente se modifica el método de `CountBytes` y utiliza [async](../Topic/async%20\(C%23%20Reference\).md) y operadores de [espera](../Topic/await%20\(C%23%20Reference\).md) \([Async](../Topic/Async%20\(Visual%20Basic\).md) y [Espera](../Topic/Await%20Operator%20\(Visual%20Basic\).md) en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) de forma asincrónica para calcular el número total de bytes que se colocan en el archivo proporcionado.  El método de <xref:System.IO.FileStream.ReadAsync%2A> realiza operaciones de archivo leído de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 También puede utilizar expresiones asincrónicas lambda para realizar una acción en un bloque de flujo de datos de la ejecución.  El ejemplo siguiente se modifica el objeto de <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> que se utiliza en el ejemplo anterior para que use una expresión lambda para realizar el trabajo de forma asincrónica.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)