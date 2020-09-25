---
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: 637b815553d7c7f9a5fb4ffe644d2975468e1090
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189102"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a>Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)

La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales. Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos. Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.  
  
 El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).  
  
 Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `SalesOrderHeader` y `SalesOrderDetail` para buscar el número de pedidos por cliente. Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `Contact` y `SalesOrderHeader`. Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>Join  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo realiza una combinación en las tablas `SalesOrderHeader` y `SalesOrderDetail` para obtener pedidos en línea del mes de agosto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Consulte también

- [Cargar datos en un conjunto de datos](loading-data-into-a-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
- [Información general sobre operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
