---
title: "DataAdapters y DataReaders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataAdapters y DataReaders
Puede usar el **DataReader** de ADO.NET para recuperar flujos de datos de solo lectura y solo avance de una base de datos.  Los resultados se devuelven a medida que se ejecuta la consulta y se almacenan en el búfer de red del cliente hasta que se solicitan con el método **Read** del **DataReader**.  Con el **DataReader** puede aumentar el rendimiento de la aplicación al recuperar datos en cuanto están disponibles y almacenar \(de forma predeterminada\) una sola fila cada vez en memoria, lo que reduce la sobrecarga del sistema.  
  
 Un <xref:System.Data.Common.DataAdapter> se utiliza para recuperar datos de un origen de datos y llenar tablas con un <xref:System.Data.DataSet>.  `DataAdapter` también resuelve los cambios realizados en `DataSet` de vuelta al origen de datos.  Mediante el objeto `Connection` del proveedor de datos .NET Framework, `DataAdapter` se conecta a un origen de datos y utiliza objetos `Command` para recuperar datos del origen de datos y resolver los cambios a dicho origen.  
  
 Cada proveedor de datos .NET Framework incluido con .NET Framework tiene un objeto <xref:System.Data.Common.DbDataReader> y un objeto <xref:System.Data.Common.DbDataAdapter>, el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbDataReader> y un objeto <xref:System.Data.OleDb.OleDbDataAdapter>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlDataReader> y un objeto <xref:System.Data.SqlClient.SqlDataAdapter>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcDataReader> y un objeto <xref:System.Data.Odbc.OdbcDataAdapter>, y el proveedor de datos .NET Framework para Oracle incluyes un objeto <xref:System.Data.OracleClient.OracleDataReader> y un objeto <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## En esta sección  
 [Recuperar datos mediante DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Describe el objeto **DataReader** de ADO.NET, así como la forma de utilizarlo para devolver una secuencia de resultados desde un origen de datos.  
  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Describe cómo llenar un `DataSet` de tablas, columnas y filas mediante un `DataAdapter`.  
  
 [Parámetros DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Describe cómo utilizar parámetros con las propiedades de comando de `DataAdapter`, lo que incluye cómo asignar el contenido de una columna de `DataSet` a un parámetro de comando.  
  
 [Agregar restricciones existentes a DataSet](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Describe cómo agregar restricciones existentes a un `DataSet`.  
  
 [Asignaciones DataAdapter, DataTable y DataColumn](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Describe cómo configurar `DataTableMappings` y `ColumnMappings` para `DataAdapter`.  
  
 [Paginar a través de un resultado de consulta](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Proporciona un ejemplo de cómo ver los resultados de una consulta como páginas de datos.  
  
 [Actualizar orígenes de datos con DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Describe cómo se utiliza `DataAdapter` para resolver modificaciones en `DataSet` en la base de datos.  
  
 [Control de eventos DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Describe los eventos de `DataAdapter` y cómo utilizarlos.  
  
 [Realizar operaciones por lotes mediante DataAdapters](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Describe cómo mejorar el rendimiento de la aplicación mediante la reducción del número de viajes de ida y vuelta \(round trip\) al servidor SQL Server al aplicar las actualizaciones desde el `DataSet`.  
  
## Vea también  
 [Conectarse a un origen de datos](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [DataSets, DataTables y DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)