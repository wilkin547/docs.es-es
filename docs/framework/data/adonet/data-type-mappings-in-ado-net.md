---
title: "Asignar tipos de datos en ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Asignar tipos de datos en ADO.NET
.NET Framework se basa en el sistema de tipos común, que define cómo se declaran, usan y administran los tipos en tiempo de ejecución.  Consta de tipos de valor y de tipos de referencia, que derivan todos del tipo base <xref:System.Object>.  Al trabajar con un origen de datos, el tipo de datos se deduce del proveedor de datos si no se especifica explícitamente.  Por ejemplo, un objeto <xref:System.Data.DataSet> es independiente de cualquier origen de datos específico.  Los datos de `DataSet` se recuperan desde un origen de datos y los cambios que se realizan en ellos se reflejan en el origen de datos mediante el uso de `DataAdapter`.  Esto significa que cuando `DataAdapter` rellena un objeto <xref:System.Data.DataTable> en `DataSet` con valores obtenidos de un origen de datos, los tipos de datos resultantes de las columnas de `DataTable` son tipos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en lugar de tipos específicos del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que se utiliza para realizar la conexión con el origen de datos.  
  
 De la misma forma, cuando un objeto `DataReader` devuelve un valor desde un origen de datos, el valor resultante se almacena en una variable local que tiene un tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. En las operaciones `Fill` de los métodos `DataAdapter` y `Get` de `DataReader`, el tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se deduce del valor devuelto del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 En lugar de confiar en el tipo de datos deducido, puede utilizar los métodos de descriptor de acceso con tipo de `DataReader` cuando conoce el tipo específico del valor que se va a devolver.  Los métodos de descriptor de acceso con tipo mejoran el rendimiento, ya que devuelven un valor como un tipo determinado de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], con lo que se evita tener que efectuar conversiones adicionales de tipo.  
  
> [!NOTE]
>  Los valores nulos de los tipo de datos del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se representan mediante `DBNull.Value`.  
  
## En esta sección  
 [Asignar tipos de datos de SQL Server](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.SqlClient>.  
  
 [Asignar tipos de datos OLE DB](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OleDb>.  
  
 [Asignar tipos de datos ODBC](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.Odbc>.  
  
 [Asignar tipos de datos de Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Enumera las asignaciones de tipos de datos deducidas y los métodos de descriptor de acceso a datos de <xref:System.Data.OracleClient>.  
  
 [Números en punto flotante](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Describe los problemas que con frecuencia se encuentran los programadores al trabajar con números de punto flotante.  
  
## Vea también  
 [Tipos de datos de SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Configurar parámetros y tipos de datos de parámetros](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)   
 [Recuperar información de esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Sistema de tipos comunes](../../../../docs/standard/base-types/common-type-system.md)   
 [Converting Types](http://msdn.microsoft.com/es-es/6038316e-bdaf-4f55-8006-407f591ce156)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)