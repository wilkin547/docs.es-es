---
title: SqlTypes y DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147513"
---
# <a name="sqltypes-and-the-dataset"></a>SqlTypes y DataSet

ADO.NET 2.0 introdujo la compatibilidad de tipos mejorada con `DataSet` mediante el espacio de nombres <xref:System.Data.SqlTypes>. Los tipos en <xref:System.Data.SqlTypes> se han diseñado para proporcionar tipos de datos con la misma semántica y precisión que los de una base de datos SQL Server. Cada tipo de datos de <xref:System.Data.SqlTypes> tiene un tipo de datos equivalente en SQL Server, con la misma representación de datos subyacente.  
  
 El uso de <xref:System.Data.SqlTypes> directamente en <xref:System.Data.DataSet> confiere varias ventajas cuando se trabaja con tipos de datos de SQL Server. <xref:System.Data.SqlTypes> admite la misma semántica que los tipos de datos nativos de SQL Server. Si se especifica uno de los tipos <xref:System.Data.SqlTypes> en la definición de <xref:System.Data.DataColumn>, se elimina la pérdida de precisión que se puede producir al convertir tipos de datos decimales o numéricos a uno de los tipos de datos de Common Language Runtime (CLR).  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se crea un objeto <xref:System.Data.DataTable> que define explícitamente los tipos de datos <xref:System.Data.DataColumn> mediante <xref:System.Data.SqlTypes> en lugar de tipos CLR. El código rellena <xref:System.Data.DataTable> con los datos de la tabla Sales.SalesOrderDetail de la base de datos AdventureWorks de SQL Server. La salida mostrada en la ventana de la consola muestra el tipo de datos de cada columna y los valores recuperados de SQL Server.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Configurar parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Información general de ADO.NET](../ado-net-overview.md)
