---
description: Más información sobre cómo cargar datos en un conjunto de datos
title: Cargar datos en un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 167a399d17257008e884fbcccc96de17398b8f88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681687"
---
# <a name="loading-data-into-a-dataset"></a>Cargar datos en un conjunto de datos

<xref:System.Data.DataSet>Primero se debe rellenar un objeto para poder realizar consultas sobre él con LINQ to DataSet. Existen varias formas de rellenar <xref:System.Data.DataSet>. Por ejemplo, puede utilizar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en <xref:System.Data.DataSet> . Para más información, vea [LINQ to SQL](./sql/linq/index.md).  
  
 Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos. Esto se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>. Una vez que se ha <xref:System.Data.DataSet> rellenado, puede escribir consultas en él mediante LINQ to DataSet. El `FillDataSet` método de este ejemplo se usa en las consultas de ejemplo de [LINQ to DataSet ejemplos](linq-to-dataset-examples.md). Para obtener más información, vea [consultar conjuntos](querying-datasets-linq-to-dataset.md)de datos.  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Vea también

- [Información general de LINQ to DataSet](linq-to-dataset-overview.md)
- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
