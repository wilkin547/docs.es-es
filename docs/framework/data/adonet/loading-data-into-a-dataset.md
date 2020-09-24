---
title: Cargar datos en un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166721"
---
# <a name="loading-data-into-a-dataset"></a>Cargar datos en un conjunto de datos

<xref:System.Data.DataSet>Primero se debe rellenar un objeto para poder realizar consultas sobre él con LINQ to DataSet. Existen varias formas de rellenar <xref:System.Data.DataSet>. Por ejemplo, puede utilizar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en <xref:System.Data.DataSet> . Para más información, vea [LINQ to SQL](./sql/linq/index.md).  
  
 Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos. Esto se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>. Una vez que se ha <xref:System.Data.DataSet> rellenado, puede escribir consultas en él mediante LINQ to DataSet. El `FillDataSet` método de este ejemplo se usa en las consultas de ejemplo de [LINQ to DataSet ejemplos](linq-to-dataset-examples.md). Para obtener más información, vea [consultar conjuntos](querying-datasets-linq-to-dataset.md)de datos.  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Consulte también

- [Información general de LINQ to DataSet](linq-to-dataset-overview.md)
- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
