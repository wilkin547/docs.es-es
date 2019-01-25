---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 3ea9b8cebdec2dc6fc7284907d8183750009678f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725225"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a>Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos (LINQ to DataSet)
Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet> usando la sintaxis de expresiones de consulta.  
  
 El `FillDataSet` método usado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 Para obtener más información, vea [Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="elementat"></a>ElementAt  
  
### <a name="example"></a>Ejemplo  
 Este ejemplo usa el método <xref:System.Linq.Enumerable.ElementAt%2A> para recuperar la quinta dirección donde `PostalCode` == "M4B 1V7".  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a>First  
  
### <a name="example"></a>Ejemplo  
 Este ejemplo usar el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es 'Brooke'.  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a>Vea también
- [Carga de datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Información general sobre operadores de consulta estándar](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
