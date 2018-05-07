---
title: Varias operaciones de copia masiva
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 267103e7315e337d223ce60652bdfddedbe4ec02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="multiple-bulk-copy-operations"></a>Varias operaciones de copia masiva
Se pueden realizar varias operaciones de copia masiva con una única instancia de una clase <xref:System.Data.SqlClient.SqlBulkCopy>. Si los parámetros de operación cambian entre copias (por ejemplo, el nombre de la tabla de destino), debe actualizarlos antes de las subsiguientes llamadas a cualquiera de los **WriteToServer** métodos, como se muestra en el ejemplo siguiente. A menos que se cambien explícitamente, todos los valores de propiedades permanecen igual que estaban en la operación anterior de copia masiva de una determinada instancia.  
  
> [!NOTE]
>  Realizar varias operaciones de copia masiva con la misma instancia de <xref:System.Data.SqlClient.SqlBulkCopy> resulta generalmente más eficiente que utilizar una instancia distinta para cada operación.  
  
 Si realiza varias operaciones de copia masiva con el mismo objeto <xref:System.Data.SqlClient.SqlBulkCopy>, no existen restricciones en cuanto a si la información de origen o destino es igual o diferente en cada operación. No obstante, debe asegurarse de que la información de asociación de columnas esté establecida correctamente cada vez que escriba en el servidor.  
  
> [!IMPORTANT]
>  Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy** solo. Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de copia masiva en SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
