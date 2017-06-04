---
title: "How to: Write a Simple Parallel.ForEach Loop | Microsoft Docs"
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
  - "foreach, parallel version"
  - "parallel programming, foreach"
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Write a Simple Parallel.ForEach Loop
En este ejemplo, se muestra cómo se usa un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> para habilitar el paralelismo de datos en cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en la PLINQ.  Si no está familiarizado con expresiones lambda en C\# o Visual Basic, vea [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Ejemplo  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A>.  Se crea una partición de la colección de origen y el trabajo se programa en varios subprocesos en función del entorno del sistema.  Cuantos más procesadores tenga el sistema, más rápido se ejecutará el método paralelo.  En algunas colecciones de origen, puede resultar más rápido un bucle secuencial, en función del tamaño del origen y del tipo de trabajo que se realice.  Para obtener más información acerca del rendimiento, vea [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Para obtener más información acerca de los bucles paralelos, vea [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)  
  
 Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una colección no genérica, puede emplear el método de extensión <xref:System.Linq.Enumerable.Cast%2A> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Puede usar también Parallel LINQ \(PLINQ\) con el fin de paralelizar el procesamiento de los orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>.  PLINQ permite usar una sintaxis de consulta declarativa para expresar el comportamiento del bucle.  Para obtener más información, vea [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## Compilar el código  
  
-   Copie y pegue este código en un proyecto de aplicación de consola de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010.  
  
-   Agregue una referencia a System.Drawing.dll.  
  
-   Presione F5.  
  
## Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)