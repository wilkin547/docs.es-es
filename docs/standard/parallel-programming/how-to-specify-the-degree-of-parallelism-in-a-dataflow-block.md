---
title: 'Cómo: Especificar el grado de paralelismo en un bloque de flujos de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
ms.openlocfilehash: bd77afd3e2d8ba71541ce8159a9faf3dea3aa3fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826871"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>Cómo: Especificar el grado de paralelismo en un bloque de flujos de datos
En este documento se describe cómo establecer la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> para que un bloque de flujo de datos de ejecución pueda procesar más de un mensaje al mismo tiempo. Esto resulta útil cuando tiene un bloque de flujo de datos que realiza un cálculo de ejecución prolongada y se puede beneficiar del procesamiento de mensajes en paralelo. En el ejemplo se usa la clase <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> para llevar a cabo varias operaciones de flujo de datos simultáneamente; sin embargo, puede especificar el grado máximo de paralelismo en cualquiera de los tipos de bloque de ejecución predefinidos que la biblioteca de flujo de datos TPL proporciona, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se realizan dos cálculos de flujo de datos y se imprime el tiempo transcurrido que se necesita para cada cálculo. El primer cálculo especifica un grado máximo de paralelismo de 1, que es el valor predeterminado. Un grado máximo de paralelismo de 1 hace que el bloque de flujo de datos procese los mensajes en serie. El segundo cálculo es similar al primero, excepto que especifica un grado máximo de paralelismo igual al número de procesadores disponibles. Esto permite que el bloque de flujo de datos realice varias operaciones en paralelo.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
 De forma predeterminada, cada bloque de flujo de datos predefinido propaga los mensajes en el orden con que se reciben.  Aunque cuando se especifica un grado máximo de paralelismo mayor que 1 se procesan simultáneamente varios mensajes, se siguen propagando en el orden con que se reciben.  
  
 Dado que la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> representa el grado máximo de paralelismo, el bloque de flujo de datos puede ejecutarse con un menor grado de paralelismo que el especificado. El bloque de flujo de datos puede usar un grado de paralelismo menor para cumplir los requisitos funcionales o porque hay una falta de recursos del sistema. Un bloque de flujo de datos nunca elige un grado de paralelismo mayor que el especificado.  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
