---
title: 'Ejemplos de sintaxis de consulta basada en métodos: operadores de conversión (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 47e2a0a510af86055d93603c8c898b00c8d94c87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a>Ejemplos de sintaxis de consulta basada en métodos: operadores de conversión (LINQ to DataSet)
Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> y <xref:System.Linq.Enumerable.ToList%2A> para ejecutar inmediatamente una expresión de consulta.  
  
 El `FillDataSet` método que se usa en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Para obtener más información, consulte [Cómo: crear un LINQ to DataSet proyecto en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="toarray"></a>ToArray  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a>ToDictionary  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToDictionary%2A> para evaluar de forma inmediata una secuencia y una expresión de clave relacionada en un diccionario.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a>ToList  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToList%2A> para evaluar inmediatamente una secuencia en <xref:System.Collections.Generic.List%601>, donde `T` es de tipo <xref:System.Data.DataRow>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a>Vea también  
 [Carga de datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
