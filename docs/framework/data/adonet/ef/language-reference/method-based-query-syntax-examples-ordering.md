---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: ordenación'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Ordenación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 7b1c67ba66f549e82a57b5b34c645d36d1255a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696703"
---
# <a name="method-based-query-syntax-examples-ordering"></a>Ejemplos de sintaxis de consulta basada en métodos: Ordenación

En los ejemplos de este tema se muestra cómo usar el <xref:System.Linq.Enumerable.ThenBy%2A> método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizando la sintaxis de consulta basada en métodos. El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo con la sintaxis de consulta basada en métodos usa <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenBy%2A> para devolver una lista de contactos ordenados primero por el apellido y después por el nombre:  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a>ThenByDescending  
  
### <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utilizan los métodos <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenByDescending%2A> para ordenar primero por precio de venta y después realizar una ordenación en orden descendente de los nombres de producto.  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a>Vea también

- [Consultas en LINQ to Entities](queries-in-linq-to-entities.md)
