---
title: "Cómo: Escribir un bucle Parallel.ForEach simple"
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Cómo: Escribir un bucle Parallel.ForEach simple
Este ejemplo muestra cómo utilizar un <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> bucle para habilitar el paralelismo de datos sobre cualquier <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> origen de datos.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 A <xref:System.Threading.Tasks.Parallel.ForEach%2A> bucle funciona como un <xref:System.Threading.Tasks.Parallel.For%2A> bucle. Se divide la colección de origen y se ha programado el trabajo en varios subprocesos según el entorno del sistema. Los procesadores más en el sistema, más rápida será paralelo se ejecuta el método. Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y el tipo de trabajo que se está realizando. Para obtener más información sobre el rendimiento, consulte [problemas potenciales en los datos y el paralelismo de tareas](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Para obtener más información acerca de los bucles paralelos, vea [Cómo: escribir un bucle Parallel.For Simple](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Usar <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una colección no genérica, puede usar el <xref:System.Linq.Enumerable.Cast%2A> método de extensión para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de <xref:System.Collections.Generic.IEnumerable%601> orígenes de datos. PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle. Para más información, consulte [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Copie y pegue este código en un [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] proyecto de aplicación de consola de 2010.  
  
-   Agregue una referencia a System.Drawing.dll  
  
-   Presione F5  
  
## <a name="see-also"></a>Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
