---
title: Recuperar y modificar datos
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980059"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="30570-102">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="30570-103">La principal función de cualquier aplicación de base de datos es conectarse a un origen de datos y recuperar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="30570-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="30570-104">Los .NET Framework proveedores de datos de ADO.NET sirven como puente entre una aplicación y un origen de datos, lo que le permite ejecutar comandos, así como recuperar datos mediante un **DataReader** o un **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="30570-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="30570-105">Una función clave de cualquier aplicación de base de datos es la capacidad de actualizar los datos almacenados en la misma.</span><span class="sxs-lookup"><span data-stu-id="30570-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="30570-106">En ADO.NET, la actualización de datos implica el uso de los objetos **DataAdapter** y <xref:System.Data.DataSet>, y de los objetos de **comando** . también puede implicar el uso de transacciones.</span><span class="sxs-lookup"><span data-stu-id="30570-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30570-107">Esta sección</span><span class="sxs-lookup"><span data-stu-id="30570-107">In This Section</span></span>  
 [<span data-ttu-id="30570-108">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="30570-108">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="30570-109">Describe cómo se establece una conexión con un origen de datos y cómo trabajar con eventos de conexión.</span><span class="sxs-lookup"><span data-stu-id="30570-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="30570-110">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="30570-110">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="30570-111">Contiene temas en los que se describen varios aspectos del uso de cadenas de conexión, entre los que se incluyen las palabras clave de cadena de conexión, información sobre seguridad y el almacenamiento y recuperación de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="30570-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="30570-112">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="30570-112">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="30570-113">Describe la agrupación de conexiones para los proveedores de datos .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30570-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="30570-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="30570-114">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="30570-115">Contiene temas en los que se describe cómo crear comandos y generadores de comandos, configurar parámetros y cómo ejecutar comandos para recuperar y modificar datos.</span><span class="sxs-lookup"><span data-stu-id="30570-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="30570-116">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="30570-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="30570-117">Contiene temas en los que se describen DataReaders, DataAdapters, los parámetros, el control de eventos DataAdapter y la ejecución de operaciones por lotes.</span><span class="sxs-lookup"><span data-stu-id="30570-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="30570-118">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="30570-118">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="30570-119">Contiene temas en los que se describe cómo realizar transacciones locales y transacciones distribuidas, y cómo trabajar con la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="30570-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="30570-120">Recuperación de valores autonuméricos y de identidad</span><span class="sxs-lookup"><span data-stu-id="30570-120">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="30570-121">Proporciona un ejemplo de asignación de los valores generados para una columna de **identidad** en una tabla de SQL Server o para un campo **Autonumber** de una tabla de Microsoft Access, a una columna de una fila insertada en una tabla.</span><span class="sxs-lookup"><span data-stu-id="30570-121">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="30570-122">Describe la combinación de valores de identidad en una `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="30570-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="30570-123">Recuperación de datos binarios</span><span class="sxs-lookup"><span data-stu-id="30570-123">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="30570-124">Describe cómo recuperar datos binarios o estructuras de datos de gran tamaño mediante `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="30570-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="30570-125">para modificar el comportamiento predeterminado de un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="30570-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="30570-126">Modificación de datos con procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="30570-126">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="30570-127">Describe cómo utilizar parámetros de entrada y parámetros de salida de procedimientos almacenados para insertar una fila en una base de datos y devolver un nuevo valor de identidad.</span><span class="sxs-lookup"><span data-stu-id="30570-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="30570-128">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="30570-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="30570-129">Describe cómo obtener de un origen de dstos las bases de datos o catálogos disponibles, las tablas y vistas de una base de datos, las restricciones que existen para las tablas y otra información de esquema.</span><span class="sxs-lookup"><span data-stu-id="30570-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="30570-130">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="30570-130">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="30570-131">Describe el modelo de generador de proveedor y demuestra cómo usar las clases base del espacio de nombres `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="30570-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="30570-132">Traza de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-132">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="30570-133">Describe cómo ADO.NET proporciona funcionalidad integrada de traza de datos.</span><span class="sxs-lookup"><span data-stu-id="30570-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="30570-134">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="30570-134">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="30570-135">Describe los contadores de rendimiento disponibles para `SqlClient` y `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="30570-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="30570-136">Programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="30570-136">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="30570-137">Describe la compatibilidad de ADO.NET con la programación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="30570-137">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="30570-138">Compatibilidad de streaming de SqlClient</span><span class="sxs-lookup"><span data-stu-id="30570-138">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="30570-139">Describe cómo escribir aplicaciones que transmiten datos de SQL Server sin que se carguen por completo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="30570-139">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30570-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="30570-140">See also</span></span>

- [<span data-ttu-id="30570-141">Asignaciones de tipos de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-141">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="30570-142">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="30570-142">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="30570-143">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-143">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="30570-144">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-144">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="30570-145">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30570-145">ADO.NET Overview</span></span>](ado-net-overview.md)
