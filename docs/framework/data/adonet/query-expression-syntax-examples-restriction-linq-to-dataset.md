---
title: 'Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 04a7b2027ac956d14086f94527b10d253749949d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794667"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a>Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)
Los ejemplos de este tema muestran cómo utilizar el método <xref:System.Linq.Enumerable.Where%2A> para consultar <xref:System.Data.DataSet> utilizando sintaxis de expresión de consultas.  
  
 El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).  
  
 Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 Para obtener más información, vea [Cómo: Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.  
  
## <a name="where"></a>Where  
  
### <a name="example"></a>Ejemplo  
 Este ejemplo devuelve todos los pedidos en línea.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a>Ejemplo  
 Este ejemplo devuelve los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a>Ejemplo  
 Este ejemplo devuelve todos los productos de color rojo.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Where%2A> para buscar pedidos efectuados con posterioridad al 1 de diciembre de 2002 y, a continuación, se utiliza el método <xref:System.Data.DataRow.GetChildRows%2A> para obtener los detalles de cada pedido.  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a>Vea también

- [Carga de datos en un conjunto de datos](loading-data-into-a-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
- [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
