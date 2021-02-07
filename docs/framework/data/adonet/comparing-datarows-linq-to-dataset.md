---
description: 'Más información sobre: comparar DataRows (LINQ to DataSet)'
title: Comparar objetos DataRow (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: df410432ab31d5ee284cb1d7cd15661db65ca503
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663942"
---
# <a name="comparing-datarows-linq-to-dataset"></a>Comparar objetos DataRow (LINQ to DataSet)

Language-Integrated Query (LINQ) define varios operadores de conjuntos para comparar los elementos de origen y ver si son iguales. LINQ proporciona los siguientes operadores de conjuntos:  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 Estos operadores comparan elementos origen llamando a los métodos <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> y <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> de cada colección de elementos. En el caso de <xref:System.Data.DataRow>, estos operadores realizan una comparación de referencia, lo que en general no constituye un comportamiento ideal para operaciones de conjunto en datos tabulares. Para las operaciones de conjuntos, por lo general deseará determinar si los valores del elemento son iguales o no a las referencias del elemento. Por lo tanto, se ha <xref:System.Data.DataRowComparer> agregado la clase a LINQ to DataSet. Esta clase se puede utilizar para comparar valores de fila.  
  
 La clase <xref:System.Data.DataRowComparer> contiene una implementación de comparación del valor para <xref:System.Data.DataRow>, de modo que esta clase se puede utilizar para operaciones de conjuntos como <xref:System.Linq.Enumerable.Distinct%2A>. No se puede crear una instancia directamente de esta clase. En su lugar, debe utilizarse la propiedad <xref:System.Data.DataRowComparer.Default%2A> para devolver una instancia de <xref:System.Data.DataRowComparer%601>. Entonces, se llama al método <xref:System.Data.DataRowComparer%601.Equals%2A> y los dos objetos <xref:System.Data.DataRow> que se van a comparar se pasan como parámetros de entrada. El método <xref:System.Data.DataRowComparer%601.Equals%2A> devuelve `true` si los conjuntos ordenados de valores de columna de ambos objetos <xref:System.Data.DataRow> son iguales; de lo contrario, devuelve `false`.  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo usa `Intersect` para devolver contactos que aparecen en ambas tablas.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a>Ejemplo  

 El ejemplo siguiente compara dos filas y obtiene sus códigos hash.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRowComparer>
- [Cargar datos en un conjunto de datos](loading-data-into-a-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
