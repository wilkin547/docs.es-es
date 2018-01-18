---
title: Cargar datos en un conjunto de datos
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
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4be4c1aa449c3bd78774c6aafe1ec2b55b27b663
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="loading-data-into-a-dataset"></a>Cargar datos en un conjunto de datos
Un objeto <xref:System.Data.DataSet> se debe rellenar primero antes de poderlo consultar con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Existen varias formas de rellenar <xref:System.Data.DataSet>. Por ejemplo, puede usar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en la <xref:System.Data.DataSet>. Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos. Esto se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>. Una vez que se ha rellenado <xref:System.Data.DataSet>, se pueden escribir consultas en él mediante [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. El `FillDataSet` método en este ejemplo se utiliza en las consultas de ejemplo de [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md). Para obtener más información, consulte [consultar conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Vea también  
 [Información general de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [Consulta de conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
