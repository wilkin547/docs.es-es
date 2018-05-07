---
title: System.DateTimeOffset (Métodos)
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 7fc6502f899e953637d23c0d54cc5fe615c38eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="systemdatetimeoffset-methods"></a>System.DateTimeOffset (Métodos)
LINQ to SQL permite llamar a la mayoría de los métodos, operadores y propiedades de <xref:System.DateTimeOffset?displayProperty=nameWithType> desde las consultas LINQ to SQL, cuando se hayan asignado en el modelo de objetos o en el archivo de asignación externo.  
  
 Los únicos métodos no admitidos son los heredados de <xref:System.Object?displayProperty=nameWithType> que no tienen sentido en el contexto de las consultas LINQ to SQL, como: `Finalize`, `GetHashCode`, `GetType` y `MemberwiseClone`. Estos métodos no se admiten porque LINQ to SQL no puede convertirlos para su ejecución en SQL Server.  
  
> [!NOTE]
>  La estructura de Common Language Runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> y la funcionalidad de asignarla a una columna `DATETIMEOFFSET` de SQL con LINQ to SQL, requiere .NET Framework 3.5 SP1 o posterior. La columna `DATETIMEOFFSET` de SQL está disponible sólo en Microsoft SQL Server 2008 y posterior.  
  
## <a name="sqlmethods-date-and-time-methods"></a>Métodos Date y Time de SQLMethods  
 Además de los métodos proporcionados por la estructura <xref:System.DateTimeOffset>, LINQ to SQL proporciona los métodos citados en la siguiente tabla desde la clase <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> para trabajar con fechas y horas.  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a>Vea también  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Creación del modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Asignación de tipos entre CLR y SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
