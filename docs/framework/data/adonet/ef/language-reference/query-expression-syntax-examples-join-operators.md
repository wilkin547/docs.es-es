---
title: "Ejemplos de sintaxis de expresiones de consulta: operadores de combinación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ccf76c08ccd4d28c4ad7e2b8af41fc8290968aed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-join-operators"></a>Ejemplos de sintaxis de expresiones de consulta: operadores de combinación
La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales. Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos. Para obtener más información, consulte [información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
 Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> métodos para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) utilizando la sintaxis de expresiones de consulta. El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas SalesOrderHeader y SalesOrderDetail para buscar el número de pedidos por cliente. Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se realiza una operación <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader para buscar el número de pedidos por contacto. Se muestran el recuento de pedidos y los identificadores para cada contacto.  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader. Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>Join  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente realiza una combinación en las tablas SalesOrderHeader y SalesOrderDetail para obtener los pedidos en línea del mes de agosto.  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
