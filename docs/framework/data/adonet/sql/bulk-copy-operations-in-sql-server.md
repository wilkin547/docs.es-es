---
title: Operaciones de copia masiva en SQL Server
description: Aprenda a usar la clase SqlBulkCopy para escribir soluciones de código administrado que copien de forma masiva archivos grandes en tablas o vistas en bases de datos de SQL Server.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197436"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Operaciones de copia masiva en SQL Server

Microsoft SQL Server incluye una conocida utilidad de línea de comandos denominada **bcp** para copiar rápidamente y de forma masiva archivos grandes en tablas o vistas en bases de datos de SQL Server. La clase <xref:System.Data.SqlClient.SqlBulkCopy> permite escribir soluciones de código administrado que proporcionan una funcionalidad similar. Hay otras maneras de cargar datos en una tabla de SQL Server (las instrucciones INSERT, por ejemplo) pero <xref:System.Data.SqlClient.SqlBulkCopy> ofrece una importante ventaja de rendimiento sobre ellas.  
  
 La clase <xref:System.Data.SqlClient.SqlBulkCopy> puede usarse para escribir datos solo en tablas de SQL Server. Sin embargo, el origen de datos no está limitado a SQL Server; se puede utilizar cualquier origen de datos siempre y cuando pueda cargarse en una instancia <xref:System.Data.DataTable> o leerse con una instancia <xref:System.Data.IDataReader>.  
  
 Con la clase <xref:System.Data.SqlClient.SqlBulkCopy>, puede ejecutar:  
  
- Una única operación de copia masiva.  
  
- Varias operaciones de copia masiva.  
  
- Una operación de copia masiva en una transacción  
  
> [!NOTE]
> Si usa .NET Framework versión 1.1 o anterior (que no admite la clase <xref:System.Data.SqlClient.SqlBulkCopy>), puede ejecutar la instrucción **BULK INSERT** de Transact-SQL de SQL Server mediante el objeto <xref:System.Data.SqlClient.SqlCommand>.  
  
## <a name="in-this-section"></a>En esta sección  

 [Configuración de ejemplo de copia masiva](bulk-copy-example-setup.md)  
 Describe las tablas usadas en los ejemplos de copia masiva y proporciona scripts SQL para crear las tablas en la base de datos AdventureWorks.  
  
 [Operaciones de copia masiva únicas](single-bulk-copy-operations.md)  
 Describe cómo realizar una única copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy> y cómo realizar la operación de copia masiva mediante instrucciones Transact-SQL y la clase <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Varias operaciones de copia masiva](multiple-bulk-copy-operations.md)  
 Describe cómo realizar varias operaciones de copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Transacciones y operaciones de copia masiva](transaction-and-bulk-copy-operations.md)  
 Describe cómo realizar una operación de copia masiva en una transacción, incluida la forma de confirmar o revertir la transacción.  
  
## <a name="see-also"></a>Consulte también

- [SQL Server y ADO.NET](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
