---
title: Asignaciones de tipos de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 1064f3be7f2548337b5dd6653c76b70a04fad980
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757676"
---
# <a name="data-type-mappings-in-adonet"></a>Asignaciones de tipos de datos en ADO.NET
.NET Framework se basa en el sistema de tipos común, que define cómo se declaran, usan y administran los tipos en tiempo de ejecución. Consta de tipos de valor y de tipos de referencia, que derivan todos del tipo base <xref:System.Object>. Al trabajar con un origen de datos, el tipo de datos se deduce del proveedor de datos si no se especifica explícitamente. Por ejemplo, un objeto <xref:System.Data.DataSet> es independiente de cualquier origen de datos específico. Los datos de `DataSet` se recuperan desde un origen de datos y los cambios que se realizan en ellos se reflejan en el origen de datos mediante el uso de `DataAdapter`. Esto significa que cuando `DataAdapter` rellena un objeto <xref:System.Data.DataTable> en `DataSet` con valores obtenidos de un origen de datos, los tipos de datos resultantes de las columnas de `DataTable` son tipos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en lugar de tipos específicos del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que se utiliza para realizar la conexión con el origen de datos.  
  
 De la misma forma, cuando un objeto `DataReader` devuelve un valor desde un origen de datos, el valor resultante se almacena en una variable local que tiene un tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. En las operaciones `Fill` de `DataAdapter` y los métodos `Get` de `DataReader`, el tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se deduce del valor devuelto del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 En lugar de confiar en el tipo de datos deducido, puede utilizar los métodos de descriptor de acceso con tipo de `DataReader` cuando conoce el tipo específico del valor que se va a devolver. Los métodos de descriptor de acceso con tipo mejoran el rendimiento, ya que devuelven un valor como un tipo determinado de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], con lo que se evita tener que efectuar conversiones adicionales de tipo.  
  
> [!NOTE]
>  Los valores nulos de los tipo de datos del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se representan mediante `DBNull.Value`.  
  
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
 [Tipos de datos de SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Configuración de parámetros y tipos de datos de parámetros](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Recuperación de información del esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Sistema de tipos comunes](../../../../docs/standard/base-types/common-type-system.md)  
 [Convertir tipos](http://msdn.microsoft.com/library/6038316e-bdaf-4f55-8006-407f591ce156)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
