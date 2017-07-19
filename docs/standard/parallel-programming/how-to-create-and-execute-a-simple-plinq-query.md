---
title: "How to: Create and Execute a Simple PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to create"
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Create and Execute a Simple PLINQ Query
En el ejemplo siguiente se muestra cómo crear una consulta Parallel LINQ; para ello, se utiliza el método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A> en la secuencia de origen y se ejecuta la consulta con el método <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.  Si no está familiarizado con las expresiones lambda en C\# o Visual Basic, vea [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Ejemplo  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 En este ejemplo se muestra el patrón básico para la creación y ejecución de cualquier consulta Parallel LINQ cuando el orden de la secuencia de resultado no importa; en general, las consultas desordenadas son más rápidas que las ordenadas.  La consulta crea particiones del origen, dividiéndolo en tareas que se ejecutan de forma asincrónica en varios subprocesos.  El orden en el que se completa cada tarea no depende solo de la cantidad de trabajo necesario para procesar los elementos de la partición, sino también de factores externos como, por ejemplo, el modo en que el sistema operativo programa cada uno de los subprocesos.  La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.  Para obtener más información sobre aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  Para obtener más información sobre cómo mantener el orden de los elementos de una consulta, vea [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)