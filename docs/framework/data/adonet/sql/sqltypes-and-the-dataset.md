---
title: SqlTypes y DataSet
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
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3235581ca3328307396796f01ff728ab798d3ad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sqltypes-and-the-dataset"></a>SqlTypes y DataSet
ADO.NET 2.0 incorporó compatibilidad mejorada de tipos con el `DataSet` mediante el espacio de nombres <xref:System.Data.SqlTypes>. Los tipos de <xref:System.Data.SqlTypes> se han diseñado para proporcionar tipos de datos con la misma semántica y precisión que los de una base de datos SQL Server. Cada tipo de datos de <xref:System.Data.SqlTypes> tiene un tipo de datos equivalente en SQL Server, con la misma representación de datos subyacente.  
  
 El uso de <xref:System.Data.SqlTypes> directamente en un <xref:System.Data.DataSet> otorga varias ventajas cuando se trabaja con tipos de datos de SQL Server. <xref:System.Data.SqlTypes> admite la misma semántica que los tipos de datos nativos de SQL Server. La especificación de uno de los <xref:System.Data.SqlTypes> en la definición de un objeto <xref:System.Data.DataColumn> elimina la pérdida de precisión que se produce al convertir tipos de datos decimales o numéricos en uno de los tipos de datos de Common Language Runtime (CLR).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Data.DataTable>, que define explícitamente los tipos de datos <xref:System.Data.DataColumn> utilizando <xref:System.Data.SqlTypes> en lugar de tipos CLR. El código llena la <xref:System.Data.DataTable> con los datos de la tabla Sales.SalesOrderDetail de la base de datos AdventureWorks de SQL Server. El resultado que aparece en la ventana de la consola muestra el tipo de datos de cada columna y los valores recuperados de SQL Server.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de tipos de datos de SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Configuración de parámetros y tipos de datos de parámetros](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
