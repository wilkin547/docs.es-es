---
title: Procedimiento para crear y ejecutar una consulta PLINQ simple
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 228a94323c42d7c7a5ecbd295a0db5d73f4f1f49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703699"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Procedimiento para crear y ejecutar una consulta PLINQ simple

En el ejemplo de este artículo se muestra cómo crear una consulta sencilla de Parallel Language Integrated Query (LINQ); para ello, se utiliza el método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> en la secuencia de origen y se ejecuta la consulta con el método <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 En este ejemplo se muestra el patrón básico para la creación y ejecución de cualquier consulta Parallel LINQ cuando el orden de la secuencia de resultados no importa. Por lo general, las consultas desordenadas son más rápidas que las ordenadas. La consulta crea particiones del origen, dividiéndolo en tareas que se ejecutan de forma asincrónica en varios subprocesos. El orden en el que se completa cada tarea no depende solo de la cantidad de trabajo necesario para procesar los elementos de la partición, sino también de factores externos como, por ejemplo, el modo en que el sistema operativo programa cada uno de los subprocesos. La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md). Para obtener más información sobre cómo mantener el orden de los elementos de una consulta, vea [Procedimiento para controlar la ordenación en una consulta PLINQ](how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
