---
title: Objetos DataAdapter y DataReader
description: Obtenga información sobre ADO.NET DataReader, que recupera datos de una base de datos, y DataAdapter, que recupera datos de un origen de datos y rellena un DataSet.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 2584f8b382dd90f2f8b4554663dc545b9ccceb62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177610"
---
# <a name="dataadapters-and-datareaders"></a>Objetos DataAdapter y DataReader

Puede usar ADO.NET **DataReader** para recuperar una secuencia de datos de solo lectura y de solo avance desde una base de datos. Los resultados se devuelven cuando se ejecuta la consulta y se almacenan en el búfer de red en el cliente hasta que se solicitan mediante el método **Read** del **DataReader**. El uso de **DataReader** puede aumentar el rendimiento de la aplicación al recuperar los datos tan pronto como estén disponibles y, de forma predeterminada, almacenar solo una fila a la vez en la memoria, lo que reduce la sobrecarga del sistema.  
  
 Un <xref:System.Data.Common.DataAdapter> se utiliza para recuperar datos de un origen de datos y llenar tablas con un <xref:System.Data.DataSet>. `DataAdapter` también resuelve los cambios realizados en `DataSet` de vuelta al origen de datos. Mediante el objeto `DataAdapter` del proveedor de datos .NET Framework, `Connection` se conecta a un origen de datos y utiliza objetos `Command` para recuperar datos del origen de datos y resolver los cambios a dicho origen.  
  
 Cada proveedor de datos .NET Framework incluido con .NET Framework tiene un objeto <xref:System.Data.Common.DbDataReader> y un objeto <xref:System.Data.Common.DbDataAdapter>, el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbDataReader> y un objeto <xref:System.Data.OleDb.OleDbDataAdapter>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlDataReader> y un objeto <xref:System.Data.SqlClient.SqlDataAdapter>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcDataReader> y un objeto <xref:System.Data.Odbc.OdbcDataAdapter>, y el proveedor de datos .NET Framework para Oracle incluyes un objeto <xref:System.Data.OracleClient.OracleDataReader> y un objeto <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## <a name="in-this-section"></a>En esta sección  

 [Recuperar datos utilizando un objeto DataReader](retrieving-data-using-a-datareader.md)  
 Describe el objeto **datareader** ADO.net y cómo usarlo para devolver una secuencia de resultados de un origen de datos.  
  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](populating-a-dataset-from-a-dataadapter.md)  
 Describe cómo llenar un `DataSet`  de tablas, columnas y filas mediante un `DataAdapter`.  
  
 [Parámetros de DataAdapter](dataadapter-parameters.md)  
 Describe cómo utilizar parámetros con las propiedades de comando de `DataAdapter`, lo que incluye cómo asignar el contenido de una columna de `DataSet` a un parámetro de comando.  
  
 [Agregar restricciones existentes a un conjunto de datos](adding-existing-constraints-to-a-dataset.md)  
 Describe cómo agregar restricciones existentes a un `DataSet`.  
  
 [Correspondencias de DataTable y DataColumn en un objeto DataAdapter](dataadapter-datatable-and-datacolumn-mappings.md)  
 Describe cómo configurar `DataTableMappings` y `ColumnMappings` para `DataAdapter`.  
  
 [Paginar un resultado de consulta](paging-through-a-query-result.md)  
 Proporciona un ejemplo de cómo ver los resultados de una consulta como páginas de datos.  
  
 [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)  
 Describe cómo se utiliza `DataAdapter` para resolver modificaciones en `DataSet` en la base de datos.  
  
 [Controlar eventos de DataAdapter](handling-dataadapter-events.md)  
 Describe los eventos de `DataAdapter` y cómo utilizarlos.  
  
 [Realizar operaciones por lotes utilizando objetos DataAdapter](performing-batch-operations-using-dataadapters.md)  
 Describe cómo mejorar el rendimiento de la aplicación mediante la reducción del número de viajes de ida y vuelta (round trip) al servidor SQL Server al aplicar las actualizaciones desde el `DataSet`.  
  
## <a name="see-also"></a>Consulte también

- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)
- [Información general de ADO.NET](ado-net-overview.md)
