---
title: Asignaciones de tipos de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 4e85db4732da664848cee2ef48f9a880a86fef18
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583761"
---
# <a name="data-type-mappings-in-adonet"></a>Asignaciones de tipos de datos en ADO.NET
.NET Framework se basa en el sistema de tipos común, que define cómo se declaran, usan y administran los tipos en tiempo de ejecución. Consta de tipos de valor y de tipos de referencia, que derivan todos del tipo base <xref:System.Object>. Al trabajar con un origen de datos, el tipo de datos se deduce del proveedor de datos si no se especifica explícitamente. Por ejemplo, un objeto <xref:System.Data.DataSet> es independiente de cualquier origen de datos específico. Los datos de `DataSet` se recuperan desde un origen de datos y los cambios que se realizan en ellos se reflejan en el origen de datos mediante el uso de `DataAdapter`. Esto significa que cuando un `DataAdapter` rellena un <xref:System.Data.DataTable> en un `DataSet` con los valores de un origen de datos, los tipos de datos resultante de las columnas de la `DataTable` son tipos de .NET Framework, en lugar de tipos específicos del proveedor de datos de .NET Framework que se usa para conectarse al origen de datos.  
  
 Del mismo modo, cuando un `DataReader` devuelve un valor de un origen de datos, el valor resultante se almacena en una variable local que tiene un tipo de .NET Framework. Tanto para el `Fill` las operaciones de la `DataAdapter` y `Get` métodos de la `DataReader`, el tipo de .NET Framework se deduce del valor devuelto por el proveedor de datos de .NET Framework.  
  
 En lugar de confiar en el tipo de datos deducido, puede utilizar los métodos de descriptor de acceso con tipo de `DataReader` cuando conoce el tipo específico del valor que se va a devolver. Métodos de descriptor de acceso con tipo ofrecen un mejor rendimiento al devolver un valor como un tipo específico de .NET Framework, lo que elimina la necesidad de conversión de tipos adicionales.  
  
> [!NOTE]
>  Valores NULL para tipos de datos del proveedor de datos de .NET Framework se representan mediante `DBNull.Value`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignaciones de tipos de datos de SQL Server](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.SqlClient>.  
  
 [Asignaciones de tipos de datos de OLE DB](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OleDb>.  
  
 [Asignaciones de tipos de datos de ODBC](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.Odbc>.  
  
 [Asignaciones de tipos de datos de Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OracleClient>.  
  
 [Números de punto flotante](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Describe los problemas que con frecuencia se encuentran los programadores al trabajar con números de punto flotante.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos de SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Configuración de parámetros y tipos de datos de parámetros](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Recuperación de información del esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Sistema de tipos comunes](../../../../docs/standard/base-types/common-type-system.md)
- [Conversión de tipos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
