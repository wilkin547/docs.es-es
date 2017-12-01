---
title: "Opciones de fusión mediante combinación en PLINQ"
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>Opciones de fusión mediante combinación en PLINQ
Cuando una consulta ejecuta en paralelo, PLINQ crea particiones la secuencia de origen para que varios subprocesos puedan funcionar en diferentes partes al mismo tiempo, por lo general en subprocesos independientes. Si los resultados son que vayan a usar en un subproceso, por ejemplo, en un `foreach` (`For Each` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) bucle, a continuación, los resultados de cada subproceso deben volver a combinar en una secuencia. El tipo de combinación que PLINQ realiza depende de los operadores que están presentes en la consulta. Por ejemplo, los operadores que imponen un nuevo orden de los resultados deben almacenar en búfer todos los elementos de todos los subprocesos. Desde la perspectiva del subproceso utilizado (que también es que el usuario de la aplicación) una consulta totalmente almacenada en búfer podría ejecutarse durante un período de tiempo antes de generar su primer resultado apreciable. Otros operadores, de forma predeterminada, están parcialmente almacenados en búfer; producen sus resultados en lotes. Un operador, <xref:System.Linq.ParallelEnumerable.ForAll%2A> no se almacena en búfer de forma predeterminada. Genera inmediatamente todos los elementos de todos los subprocesos.  
  
 Mediante el uso de la <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> método, como se muestra en el ejemplo siguiente, puede proporcionar una sugerencia a PLINQ que indica qué tipo de combinación para llevar a cabo.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Para obtener un ejemplo completo, vea [Cómo: especificar opciones de combinación en PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Si la consulta determinada no puede admitir la opción solicitada, simplemente se omitirá la opción. En la mayoría de los casos, no es necesario especificar una opción de combinación para una consulta PLINQ. Sin embargo, en algunos casos puede encontrar mediante pruebas y mediciones que una consulta se ejecuta mejor en un modo no predeterminado. Un uso común de esta opción es forzar un operador de combinación de fragmentos a transmitir por secuencias sus resultados con el fin de proporcionar una interfaz de usuario más sensible.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 El <xref:System.Linq.ParallelMergeOptions> enumeración incluye las siguientes opciones que especifican las formas de consulta compatibles, cómo se produjo el resultado final de la consulta cuando se usan los resultados en un subproceso:  
  
-   `Not Buffered`  
  
     El <xref:System.Linq.ParallelMergeOptions.NotBuffered> opción hace que cada elemento procesado devuelva cada subproceso tan pronto como se ha producido. Este comportamiento es análogo a la salida "streaming". Si el <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operador está presente en la consulta, `NotBuffered` conserva el orden de los elementos de origen. Aunque `NotBuffered` inicia producir resultados en cuanto están disponibles, el tiempo total para generar todos los resultados puede que el servidor puede superar los utilizando una de las otras opciones de combinación.  
  
-   `Auto Buffered`  
  
     El <xref:System.Linq.ParallelMergeOptions.AutoBuffered> opción hace que la consulta recopile los elementos en un búfer y, a continuación, proporcionará periódicamente el contenido del búfer a la vez para el subproceso utilizado. Esto es análogo a producir los datos de origen en "fragmentos" en lugar de usar el comportamiento de "transmisión por secuencias" `NotBuffered`. `AutoBuffered`puede tardar más `NotBuffered` para que el primer elemento esté disponible en el subproceso utilizado. El tamaño del búfer y el comportamiento productivo exacto no es configurable y puede variar en función de varios factores relacionados con la consulta.  
  
-   `FullyBuffered`  
  
     El <xref:System.Linq.ParallelMergeOptions.FullyBuffered> opción hace que el resultado de la consulta completa se almacenen en búfer antes de cualquiera de los elementos se producen. Cuando se usa esta opción, puede tardar más tiempo antes de que el primer elemento está disponible en el subproceso utilizado, pero todavía se pueden producir los resultados completos más rápido que con las otras opciones.  
  
## <a name="query-operators-that-support-merge-options"></a>Operadores de consulta que admiten opciones de combinación  
 En la tabla siguiente se enumera los operadores que admiten todos los modos de opción de combinación, sujetos a las restricciones especificadas.  
  
|Operador|Restricciones|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Ninguna|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Ninguna|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Consultas no ordenadas que tienen solo un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Ninguna|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Ninguna|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Consultas no ordenadas que tienen solo un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Ninguna|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Ninguno|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Ninguno|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Ninguno|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Ninguna|  
  
 Todos los demás operadores de consulta PLINQ podrían omitir opciones de combinación proporcionado por el usuario. Algunos operadores de consulta, por ejemplo, <xref:System.Linq.ParallelEnumerable.Reverse%2A> y <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, no se puede proporcionar todos los elementos hasta que todos se han producido y ordenar de nuevo. Por lo tanto, cuando <xref:System.Linq.ParallelMergeOptions> se utiliza en una consulta que también contiene un operador como <xref:System.Linq.ParallelEnumerable.Reverse%2A>, el comportamiento de combinación no se aplicará en la consulta hasta después de que el operador ha generado sus resultados.  
  
 La capacidad de algunos operadores para controlar las opciones de combinación depende del tipo de la secuencia de origen y si el <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operador se usó anteriormente en la consulta. <xref:System.Linq.ParallelEnumerable.ForAll%2A>siempre es <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; produce inmediatamente sus elementos. <xref:System.Linq.ParallelEnumerable.OrderBy%2A>siempre es <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; debe ordenar toda la lista antes de que produce.  
  
## <a name="see-also"></a>Vea también  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Especificación de opciones de combinación en PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
