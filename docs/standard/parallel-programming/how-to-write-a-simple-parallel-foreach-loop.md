---
title: 'Cómo: Escribir un bucle Parallel.ForEach simple'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03aaae7cd0faa7e7628da2e2e8f622f0967102cf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205012"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Cómo: Escribir un bucle Parallel.ForEach simple
Este ejemplo muestra cómo utilizar un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para habilitar el paralelismo de datos sobre cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A>. Se divide la colección de origen y se programa el trabajo en varios subprocesos según el entorno del sistema. Mientras más procesadores haya en el sistema, más rápido se ejecutará el método paralelo. Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y del tipo de trabajo que se realiza. Para más información sobre el rendimiento, vea [Problemas potenciales en el paralelismo de datos y tareas](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).  
  
 Para más información sobre los bucles paralelos, vea [Cómo: Escribir un bucle Parallel.For simple](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una colección no genérica, puede usar el método de extensión <xref:System.Linq.Enumerable.Cast%2A> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>. PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle. Para más información, consulte [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Copie y pegue este código en un proyecto de aplicación de consola de Visual Studio 2010.  
  
-   Adición de una referencia a System.Drawing.dll  
  
-   Presione F5.  
  
## <a name="see-also"></a>Vea también

- [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)  
- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
