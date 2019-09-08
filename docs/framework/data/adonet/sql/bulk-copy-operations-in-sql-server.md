---
title: Operaciones de copia masiva en SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: ae97bcdd6776d573cf9e523133c2c00a42c273bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782526"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Operaciones de copia masiva en SQL Server
Microsoft SQL Server incluye una conocida utilidad de línea de comandos denominada **BCP** para la copia masiva rápida de archivos grandes en tablas o vistas en bases de datos de SQL Server. La clase <xref:System.Data.SqlClient.SqlBulkCopy> permite escribir soluciones de código administrado que ofrecen una funcionalidad similar. Aunque existen otras formas de cargar datos en una tabla SQL Server (por ejemplo, mediante instrucciones INSERT), <xref:System.Data.SqlClient.SqlBulkCopy> tiene la ventaja sobre las demás de un rendimiento significativo.  
  
 La clase <xref:System.Data.SqlClient.SqlBulkCopy> sólo se puede utilizar para escribir datos en tablas SQL Server. Sin embargo, el origen de datos no está limitado a SQL Server; se puede utilizar cualquier origen de datos siempre y cuando pueda cargarse en una instancia <xref:System.Data.DataTable> o leerse con una instancia <xref:System.Data.IDataReader>.  
  
 El uso de la clase <xref:System.Data.SqlClient.SqlBulkCopy> le permite realizar:  
  
- una única operación de copia masiva  
  
- varias operaciones de copia masiva  
  
- una operación de copia masiva en una transacción  
  
> [!NOTE]
> Cuando se usa .NET Framework versión 1,1 o anterior (que no admite la <xref:System.Data.SqlClient.SqlBulkCopy> clase), se puede ejecutar la instrucción SQL Server **Bulk Insert** de Transact-SQL mediante <xref:System.Data.SqlClient.SqlCommand> el objeto.  
  
## <a name="in-this-section"></a>En esta sección  
 [Configuración de ejemplos de copia masiva](bulk-copy-example-setup.md)  
 Describe las tablas usadas en los ejemplos de copia masiva y proporciona scripts SQL para crear las tablas de la base de datos AdventureWorks.  
  
 [Operaciones de copia masiva únicas](single-bulk-copy-operations.md)  
 Describe cómo realizar una sola copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>, y cómo realizar la operación de copia masiva con las instrucciones Transact-SQL y la clase <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Varias operaciones de copia masiva](multiple-bulk-copy-operations.md)  
 Describe cómo realizar varias operaciones de copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Transacción y operaciones de copia masiva](transaction-and-bulk-copy-operations.md)  
 Describe cómo realizar una operación de copia masiva en una transacción, lo que incluye cómo confirmar o revertir la transacción.  
  
## <a name="see-also"></a>Vea también

- [SQL Server y ADO.NET](index.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
