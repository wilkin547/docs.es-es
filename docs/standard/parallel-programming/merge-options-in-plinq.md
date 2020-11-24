---
title: Opciones de fusión mediante combinación en PLINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
ms.openlocfilehash: e6690a600b7b00272471362bc087633d52a98f25
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824849"
---
# <a name="merge-options-in-plinq"></a>Opciones de fusión mediante combinación en PLINQ
Cuando una consulta se ejecuta en paralelo, PLINQ crea particiones de la secuencia de origen para que varios subprocesos puedan funcionar en diferentes partes al mismo tiempo, por lo general en subprocesos independientes. Si los resultados se van a usar en un subproceso, por ejemplo, en un bucle `foreach` (`For Each` en Visual Basic), los resultados de cada subproceso deben volver a combinarse en una secuencia. El tipo de combinación que PLINQ realiza depende de los operadores que están presentes en la consulta. Por ejemplo, los operadores que imponen un nuevo orden de los resultados deben almacenar en búfer todos los elementos de todos los subprocesos. Desde la perspectiva del subproceso utilizado (que también es el del usuario de la aplicación), una consulta totalmente almacenada en búfer podría ejecutarse durante un período de tiempo considerable antes de generar su primer resultado. Otros operadores, de forma predeterminada, están parcialmente almacenados en búfer; producen sus resultados en lotes. Un operador, <xref:System.Linq.ParallelEnumerable.ForAll%2A>, no se almacena en búfer de forma predeterminada. Genera inmediatamente todos los elementos de todos los subprocesos.  
  
 Mediante el uso del método <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>, como se muestra en el ejemplo siguiente, puede proporcionar una sugerencia a PLINQ que indica qué tipo de combinación se debe llevar a cabo.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Para obtener el ejemplo completo, vea [Cómo: Especificar opciones de fusión mediante combinación en PLINQ](how-to-specify-merge-options-in-plinq.md).  
  
 Si la consulta determinada no puede admitir la opción solicitada, simplemente se omitirá la opción. En la mayoría de los casos, no es necesario especificar una opción de combinación para una consulta PLINQ. Sin embargo, en algunos casos puede observar mediante pruebas y mediciones que una consulta se ejecuta mejor en un modo no predeterminado. Un uso común de esta opción es forzar a un operador de combinación de fragmentos a transmitir por secuencias sus resultados con el fin de proporcionar una interfaz de usuario más dinámica.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 La enumeración <xref:System.Linq.ParallelMergeOptions> incluye las siguientes opciones que especifican, para las formas de consulta compatibles, cómo se produjo el resultado final de la consulta cuando se usan los resultados en un subproceso:  
  
- `Not Buffered`  
  
     La opción <xref:System.Linq.ParallelMergeOptions.NotBuffered> hace que cada elemento procesado devuelva cada subproceso en cuanto se produzca. Este comportamiento es análogo a la salida "streaming". Si el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> está presente en la consulta, `NotBuffered` conserva el orden de los elementos de origen. Aunque `NotBuffered` empieza a producir resultados en cuanto están disponibles, el tiempo total para generar todos los resultados puede ser más largo con respecto al uso de alguna de las demás opciones de combinación.  
  
- `Auto Buffered`  
  
     La opción <xref:System.Linq.ParallelMergeOptions.AutoBuffered> hace que la consulta recopile los elementos en un búfer y, a continuación, proporcionará periódicamente el contenido del búfer a la vez para el subproceso utilizado. Esto es análogo a producir los datos de origen en "fragmentos" en lugar de usar el comportamiento de "streaming" de `NotBuffered`. `AutoBuffered` puede tardar más que `NotBuffered` en habilitar el primer elemento en el subproceso utilizado. El tamaño del búfer y el comportamiento productivo exacto no se pueden configurar y pueden variar en función de varios factores relacionados con la consulta.  
  
- `FullyBuffered`  
  
     La opción <xref:System.Linq.ParallelMergeOptions.FullyBuffered> hace que el resultado de la consulta completa se almacene en búfer antes de que se produzca cualquiera de los elementos. Al usar esta opción, puede tardar más tiempo antes de que el primer elemento esté disponible en el subproceso utilizado, pero los resultados completos pueden producirse más rápido en comparación con el uso de otras opciones.  
  
## <a name="query-operators-that-support-merge-options"></a>Operadores de consulta que admiten opciones de combinación  
 En la tabla siguiente se enumeran los operadores que admiten todos los modos de opción de combinación, sujetos a las restricciones especificadas.  
  
|Operador|Restricciones|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Consultas no ordenadas que tienen solo un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Consultas no ordenadas que tienen solo un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|None|  
  
 Todos los demás operadores de consulta PLINQ podrían omitir opciones de combinación proporcionadas por el usuario. Algunos operadores de consulta, por ejemplo <xref:System.Linq.ParallelEnumerable.Reverse%2A> y <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, no pueden proporcionar todos los elementos hasta que no se hayan producido y reordenado. Por lo tanto, cuando se utiliza <xref:System.Linq.ParallelMergeOptions> en una consulta que también contiene un operador como <xref:System.Linq.ParallelEnumerable.Reverse%2A>, el comportamiento de combinación no se aplicará en la consulta hasta después de que el operador genere sus resultados.  
  
 La capacidad de algunos operadores para controlar las opciones de combinación depende del tipo de la secuencia de origen y de si el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> se usó anteriormente en la consulta. <xref:System.Linq.ParallelEnumerable.ForAll%2A> siempre es <xref:System.Linq.ParallelMergeOptions.NotBuffered>; produce inmediatamente sus elementos. <xref:System.Linq.ParallelEnumerable.OrderBy%2A> siempre es <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; debe ordenar toda la lista antes de producirla.  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
- [Cómo: Especificar opciones de fusión mediante combinación en PLINQ](how-to-specify-merge-options-in-plinq.md)
