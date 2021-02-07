---
description: 'Más información sobre: ejecución remota frente a ejecución local'
title: Ejecución remota o ejecución local
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: ea4d85faedd4a299da292029e64d77132e1a65a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695219"
---
# <a name="remote-vs-local-execution"></a>Ejecución remota o ejecución local

Puede decidir ejecutar las consultas de manera remota (es decir, el motor de base de datos ejecuta la consulta en la base de datos) o localmente ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ejecuta la consulta en una memoria caché local).  
  
## <a name="remote-execution"></a>Ejecución remota  

 Considere la consulta siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Si su base de datos tuviese miles de filas de pedidos, no desearía recuperarlos todos para procesar un subconjunto pequeño. En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la clase <xref:System.Data.Linq.EntitySet%601> implementa la interfaz <xref:System.Linq.IQueryable>. Este enfoque garantiza que ese tipo de consultas se puedan ejecutar de manera remota. De esta técnica se derivan dos ventajas principales:  
  
- No se recuperan datos innecesarios.  
  
- Una consulta ejecutada por el motor de base de datos suele ser más eficaz debido a los índices de la base de datos.  
  
## <a name="local-execution"></a>Ejecución local  

 En otras situaciones, podría desear tener el conjunto completo de entidades relacionadas en la memoria caché local. Para este propósito, <xref:System.Data.Linq.EntitySet%601> proporciona el método <xref:System.Data.Linq.EntitySet%601.Load%2A> para cargar explícitamente todos los miembros de <xref:System.Data.Linq.EntitySet%601>.  
  
 Si <xref:System.Data.Linq.EntitySet%601> ya está cargado, las consultas posteriores se ejecutan localmente. Este enfoque ayuda en dos sentidos:  
  
- Si se debe utilizar el conjunto completo localmente o varias veces, puede evitar las consultas remotas y la latencia asociada a las mismas.  
  
- La entidad se puede serializar como una entidad completa.  
  
 El fragmento de código siguiente muestra cómo se puede obtener la ejecución local:  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>De comparación  

 Estas dos funciones proporcionan una combinación eficaz de opciones: ejecución remota para las colecciones grandes y ejecución local para las colecciones pequeñas o si se necesita la colección completa. La ejecución remota se implementa a través de <xref:System.Linq.IQueryable> y la ejecución local en una colección <xref:System.Collections.Generic.IEnumerable%601> en memoria. Para forzar la ejecución local (es decir, <xref:System.Collections.Generic.IEnumerable%601> ), vea [convertir un tipo en un IEnumerable genérico](convert-a-type-to-a-generic-ienumerable.md).  
  
### <a name="queries-against-unordered-sets"></a>Consultas en conjuntos no ordenados  

 Tenga en cuenta la diferencia importante entre una colección local que implementa <xref:System.Collections.Generic.List%601> y una colección que proporciona consultas remotas ejecutadas en *conjuntos no ordenados* en una base de datos relacional. Los métodos <xref:System.Collections.Generic.List%601>, como los que utilizan valores de índice, requieren semántica de lista, que normalmente no se puede obtener a través de una consulta remota en un conjunto no ordenado. Por esta razón, tales métodos cargan implícitamente <xref:System.Data.Linq.EntitySet%601> para permitir la ejecución local.  
  
## <a name="see-also"></a>Vea también

- [Conceptos sobre consultas](query-concepts.md)
