---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: operadores de conjuntos (LINQ to DataSet)'
title: 'Ejemplos de sintaxis de consulta basada en métodos: operadores de conjuntos (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 3a50c9793e3af6fdab08227b4789c4042dd64931
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723756"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a>Ejemplos de sintaxis de consulta basada en métodos: operadores de conjuntos (LINQ to DataSet)

En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.Distinct%2A> los <xref:System.Linq.Enumerable.Except%2A> operadores,, <xref:System.Linq.Enumerable.Intersect%2A> y <xref:System.Linq.Enumerable.Union%2A> para realizar operaciones de comparación basadas en valores en conjuntos de filas de datos.[ Cargar datos en un conjunto de datos](loading-data-into-a-dataset.md) ; vea [comparar filas](comparing-datarows-linq-to-dataset.md) de datos para obtener más información sobre <xref:System.Data.DataRowComparer> .  
  
 El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).  
  
 Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="distinct"></a>Distinct  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo usa el método <xref:System.Linq.Enumerable.Distinct%2A> para quitar elementos duplicados de una secuencia.  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a>Except  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo usa el método <xref:System.Linq.Enumerable.Except%2A> para devolver contactos que aparecen en la primera tabla pero no en la segunda.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a>Formar intersección  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo usa el método <xref:System.Linq.Enumerable.Intersect%2A> para devolver contactos que aparecen en ambas tablas.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a>Union  
  
### <a name="example"></a>Ejemplo  

 Este ejemplo usa el método <xref:System.Linq.Enumerable.Union%2A> para devolver contactos únicos de cualquiera de las dos tablas.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a>Vea también

- [Cargar datos en un conjunto de datos](loading-data-into-a-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
- [Información general sobre operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
