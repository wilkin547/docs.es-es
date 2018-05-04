---
title: Consultas entre tablas (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 17f9e683161fba0fe57279952acecd9e4399d0aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="cross-table-queries-linq-to-dataset"></a>Consultas entre tablas (LINQ to DataSet)
Además de realizar consultas a una tabla única, en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] se pueden efectuar consultas entre tablas. Esto se realiza mediante un *combinación*. Una combinación es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en otro origen de datos, como un identificador de contacto o de producto. En la programación orientada a objetos, las relaciones entre dichos objetos son relativamente fáciles de navegar debido a que cada uno de ellos tiene un miembro que hace referencia a otro. Sin embargo, en tablas de bases de datos externas, navegar por relaciones no es tan sencillo. Las tablas de bases de datos no contienen relaciones integradas. En estos casos, la operación de combinación se puede utilizar para hacer coincidir elementos de cada origen. Por ejemplo, con dos tablas que contienen información de producto y de ventas, se puede utilizar una operación de combinación para hacer coincidir información de ventas y producto del mismo pedido de ventas.  
  
 El marco de trabajo [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] proporciona dos operadores de combinación, <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>. Estos operadores realizan *combinaciones equivalentes*: es decir, las combinaciones que coinciden con los datos de dos orígenes solo cuando sus claves son iguales. (por el contrario, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] admite operadores de combinación distintos de `equals`, como el operador `less than`).  
  
 En cuanto a las bases de datos relacionales, <xref:System.Linq.Enumerable.Join%2A> implementa una combinación interna. Una combinación interna es un tipo de combinación en la que solamente se devuelven los objetos que tienen una correspondencia en el conjunto de datos opuesto.  
  
 El <xref:System.Linq.Enumerable.GroupJoin%2A> operadores no tienen equivalente directo en términos de bases de datos relacionales; implementan un superconjunto de combinaciones internas y combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada elemento de la primera colección (izquierda), aunque éste no tenga elementos correlacionados en la segunda colección.  
  
 Para obtener más información acerca de las combinaciones, vea [operaciones de combinación](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente realiza una combinación tradicional de las tablas `SalesOrderHeader` y `SalesOrderDetail` de la base de datos de ejemplo AdventureWorks para obtener pedidos en línea del mes de agosto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Vea también  
 [Consulta de conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [Consultar objetos DataSet con tipo](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [Operaciones de combinación](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
