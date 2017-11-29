---
title: Objetos DataAdapter y DataReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3e7a0af0b5fabdfacfcc825258242868b0fbb513
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="14de0-102">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="14de0-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="14de0-103">Puede usar ADO.NET **DataReader** para recuperar un flujo de datos de solo avance de solo lectura de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="14de0-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="14de0-104">Resultados se devuelven cuando se ejecuta la consulta y se almacenan en el búfer de red en el cliente hasta que se solicitan con el **lectura** método de la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="14de0-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="14de0-105">Mediante el **DataReader** puede aumentar el rendimiento de la aplicación mediante la recuperación de datos tan pronto como está disponible y (de forma predeterminada) almacenar solo una fila cada vez en la memoria, reducir la sobrecarga del sistema.</span><span class="sxs-lookup"><span data-stu-id="14de0-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="14de0-106">Un <xref:System.Data.Common.DataAdapter> se utiliza para recuperar datos de un origen de datos y llenar tablas con un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="14de0-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="14de0-107">`DataAdapter` también resuelve los cambios realizados en `DataSet` de vuelta al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="14de0-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="14de0-108">Mediante el objeto `DataAdapter` del proveedor de datos .NET Framework, `Connection` se conecta a un origen de datos y utiliza objetos `Command` para recuperar datos del origen de datos y resolver los cambios a dicho origen.</span><span class="sxs-lookup"><span data-stu-id="14de0-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="14de0-109">Cada proveedor de datos .NET Framework incluido con .NET Framework tiene un objeto <xref:System.Data.Common.DbDataReader> y un objeto <xref:System.Data.Common.DbDataAdapter>, el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbDataReader> y un objeto <xref:System.Data.OleDb.OleDbDataAdapter>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlDataReader> y un objeto <xref:System.Data.SqlClient.SqlDataAdapter>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcDataReader> y un objeto <xref:System.Data.Odbc.OdbcDataAdapter>, y el proveedor de datos .NET Framework para Oracle incluyes un objeto <xref:System.Data.OracleClient.OracleDataReader> y un objeto <xref:System.Data.OracleClient.OracleDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="14de0-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14de0-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="14de0-110">In This Section</span></span>  
 [<span data-ttu-id="14de0-111">Recuperar datos mediante DataReader</span><span class="sxs-lookup"><span data-stu-id="14de0-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="14de0-112">Describe ADO.NET **DataReader** objeto y cómo utilizarlo para devolver una secuencia de resultados desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="14de0-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="14de0-113">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14de0-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="14de0-114">Describe cómo llenar un `DataSet`  de tablas, columnas y filas mediante un `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="14de0-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="14de0-115">Parámetros de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14de0-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="14de0-116">Describe cómo utilizar parámetros con las propiedades de comando de `DataAdapter`, lo que incluye cómo asignar el contenido de una columna de `DataSet` a un parámetro de comando.</span><span class="sxs-lookup"><span data-stu-id="14de0-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="14de0-117">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="14de0-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="14de0-118">Describe cómo agregar restricciones existentes a un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="14de0-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="14de0-119">DataAdapter asignaciones de DataTable y DataColumn</span><span class="sxs-lookup"><span data-stu-id="14de0-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="14de0-120">Describe cómo configurar `DataTableMappings` y `ColumnMappings` para `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="14de0-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="14de0-121">Paginar a través de un resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="14de0-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="14de0-122">Proporciona un ejemplo de cómo ver los resultados de una consulta como páginas de datos.</span><span class="sxs-lookup"><span data-stu-id="14de0-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="14de0-123">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14de0-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="14de0-124">Describe cómo se utiliza `DataAdapter` para resolver modificaciones en `DataSet` en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14de0-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="14de0-125">Control de eventos de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14de0-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="14de0-126">Describe los eventos de `DataAdapter` y cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="14de0-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="14de0-127">Realizar operaciones por lotes mediante DataAdapters</span><span class="sxs-lookup"><span data-stu-id="14de0-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="14de0-128">Describe cómo mejorar el rendimiento de la aplicación mediante la reducción del número de viajes de ida y vuelta (round trip) al servidor SQL Server al aplicar las actualizaciones desde el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="14de0-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14de0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="14de0-129">See Also</span></span>  
 [<span data-ttu-id="14de0-130">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="14de0-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="14de0-131">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="14de0-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="14de0-132">Las transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="14de0-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="14de0-133">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="14de0-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="14de0-134">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="14de0-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
