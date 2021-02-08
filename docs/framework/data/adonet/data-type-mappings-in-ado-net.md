---
description: Más información sobre las asignaciones de tipos de datos en ADO.NET
title: Asignaciones de tipos de datos
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: c1829fdc2ebc053d1fd3a76e827a81e582572233
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786451"
---
# <a name="data-type-mappings-in-adonet"></a>Asignaciones de tipos de datos en ADO.NET

.NET Framework se basa en el sistema de tipos común, que define cómo se declaran, usan y administran los tipos en tiempo de ejecución. Consta de tipos de valor y de tipos de referencia, que derivan todos del tipo base <xref:System.Object>. Al trabajar con un origen de datos, el tipo de datos se deduce del proveedor de datos si no se especifica explícitamente. Por ejemplo, un objeto <xref:System.Data.DataSet> es independiente de cualquier origen de datos específico. Los datos de `DataSet` se recuperan desde un origen de datos y los cambios que se realizan en ellos se reflejan en el origen de datos mediante el uso de `DataAdapter`. Esto significa que cuando un `DataAdapter` rellena un <xref:System.Data.DataTable> en un `DataSet` con valores de un origen de datos, los tipos de datos resultantes de las columnas de `DataTable` son .NET Framework tipos, en lugar de tipos específicos del .NET Framework proveedor de datos que se utiliza para conectarse al origen de datos.  
  
 Del mismo modo, cuando un elemento `DataReader` devuelve un valor de un origen de datos, el valor resultante se almacena en una variable local que tiene un tipo de .NET Framework. En el caso de las `Fill` operaciones de `DataAdapter` y los `Get` métodos de `DataReader` , el tipo de .NET Framework se deduce del valor devuelto del proveedor de datos de .NET Framework.  
  
 En lugar de confiar en el tipo de datos deducido, puede utilizar los métodos de descriptor de acceso con tipo de `DataReader` cuando conoce el tipo específico del valor que se va a devolver. Los métodos del descriptor de acceso con tipo proporcionan un mejor rendimiento al devolver un valor como un tipo de .NET Framework específico, lo que elimina la necesidad de conversión de tipos adicional.  
  
> [!NOTE]
> Los valores NULL de los tipos de datos del proveedor de datos de .NET Framework se representan mediante `DBNull.Value` .  
  
## <a name="in-this-section"></a>En esta sección  

 [Asignaciones de tipos de datos de SQL Server](sql-server-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.SqlClient>.  
  
 [Asignaciones de tipos de datos de OLE DB](ole-db-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OleDb>.  
  
 [Asignaciones de tipos de datos de ODBC](odbc-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.Odbc>.  
  
 [Asignaciones de tipos de datos de Oracle](oracle-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OracleClient>.  
  
 [Números de punto flotante](floating-point-numbers.md)  
 Describe los problemas que con frecuencia se encuentran los programadores al trabajar con números de punto flotante.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos de SQL Server y ADO.NET](./sql/sql-server-data-types.md)
- [Configurar parámetros y tipos de datos de parámetros](configuring-parameters-and-parameter-data-types.md)
- [Recuperación de la información del esquema de la base de datos](retrieving-database-schema-information.md)
- [Sistema de tipos comunes](../../../standard/base-types/common-type-system.md)
- [Convertir tipos](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Información general de ADO.NET](ado-net-overview.md)
