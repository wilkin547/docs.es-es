---
description: 'Más información sobre: SQL Server tipos de datos y ADO.NET'
title: Tipos de datos de SQL Server y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 841fa5864bf54b5e4fc4dc24dab64e6ac1435c7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767302"
---
# <a name="sql-server-data-types-and-adonet"></a>Tipos de datos de SQL Server y ADO.NET

SQL Server y .NET Framework están basados en sistemas de tipos distintos, lo que puede dar lugar a posibles pérdidas de datos. Para conservar la integridad de los datos, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona métodos de descriptor de acceso con tipo para trabajar con datos de SQL Server. Puede usar las enumeraciones de las clases <xref:System.Data.SqlDbType> para especificar tipos de datos <xref:System.Data.SqlClient.SqlParameter>.  
  
 Para obtener más información y una tabla que describa las asignaciones de tipos de datos entre SQL Server y .NET Framework tipos de datos, vea [SQL Server asignaciones de tipos de datos](../sql-server-data-type-mappings.md).  
  
 SQL Server 2008 introduce nuevos tipos de datos que están diseñados para satisfacer las necesidades empresariales de trabajar con datos de fecha y hora, estructurados, semiestructurados y no estructurados. Están documentados en los Libros en pantalla de SQL Server 2008.  
  
 Los tipos de datos de SQL Server que están disponibles para su uso en la aplicación dependen de la versión de SQL Server que esté usando. Para obtener más información, busque la versión pertinente de los Libros en pantalla de SQL Server en la tabla siguiente.  
  
 **Documentación de SQL Server**  
  
1. [Tipos de datos (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>En esta sección  

 [SqlTypes y DataSet](sqltypes-and-the-dataset.md)  
 Describe la compatibilidad de tipos con `SqlTypes` en `DataSet`.  
  
 [Controlar valores NULL](handling-null-values.md)  
 Demuestra cómo trabajar con valores NULL y la lógica de tres valores.  
  
 [Comparar valores GUID y uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Muestra cómo trabajar con los valores GUID y uniqueidentifier en SQL Server y .NET Framework.  
  
 [Datos de fecha y hora](date-and-time-data.md)  
 Describe cómo usar los nuevos tipos de datos de hora y fecha incorporados en SQL Server 2008.  
  
 [UDT grandes](large-udts.md)  
 Muestra cómo recuperar datos de UDT de valores grandes introducidos en SQL Server 2008.  
  
 [Datos XML en SQL Server](xml-data-in-sql-server.md)  
 Muestra cómo recuperar datos XML recuperados de SQL Server y cómo trabajar con ellos.  
  
## <a name="reference"></a>Referencia  

 <xref:System.Data.DataSet>  
 Describe la clase `DataSet` y todos sus miembros.  
  
 <xref:System.Data.SqlTypes>  
 Describe el espacio de nombres `SqlTypes` y todos sus miembros.  
  
 <xref:System.Data.SqlDbType>  
 Describe la enumeración `SqlDbType` y todos sus miembros.  
  
 <xref:System.Data.DbType>  
 Describe la enumeración `DbType` y todos sus miembros.  
  
## <a name="see-also"></a>Vea también

- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Configurar parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Parámetros con valores de tabla](table-valued-parameters.md)
- [Datos binarios y datos de valores grandes de SQL Server](sql-server-binary-and-large-value-data.md)
- [Información general de ADO.NET](../ado-net-overview.md)
