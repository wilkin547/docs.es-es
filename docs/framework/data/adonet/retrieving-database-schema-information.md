---
description: Más información acerca de cómo recuperar información de esquema de base de datos
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 84ac94a72b23d0b1d6924600f2fd33b2a285eab8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663409"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="07a45-103">Recuperar información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="07a45-103">Retrieving Database Schema Information</span></span>

<span data-ttu-id="07a45-104">La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="07a45-104">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="07a45-105">La detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados que busquen y devuelvan información sobre el esquema de la base de datos, también conocido como los *metadatos*, de una base de datos concreta.</span><span class="sxs-lookup"><span data-stu-id="07a45-105">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="07a45-106">Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas.</span><span class="sxs-lookup"><span data-stu-id="07a45-106">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="07a45-107">Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="07a45-107">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="07a45-108">Cada uno de los proveedores administrados de .NET Framework implementa el método **GetSchema** en la clase **Connection** , y la información de esquema que se devuelve desde el método **GetSchema** tiene el formato <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="07a45-108">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="07a45-109">El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se devolverá y restringe la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="07a45-109">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="07a45-110">Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un método **GetSchemaTable** que devuelve un DataTable que describe los metadatos de columna del **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="07a45-110">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="07a45-111">Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-111">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="07a45-112">Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se va a devolver y una matriz de restricciones en esas columnas devueltas.</span><span class="sxs-lookup"><span data-stu-id="07a45-112">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="07a45-113">**GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellenado con la información de esquema solicitada.</span><span class="sxs-lookup"><span data-stu-id="07a45-113">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07a45-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07a45-114">In This Section</span></span>  

 [<span data-ttu-id="07a45-115">Colecciones GetSchema y Schema</span><span class="sxs-lookup"><span data-stu-id="07a45-115">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="07a45-116">Se describe el método **GetSchema**, y cómo se puede usar para recuperar y restringir la información del esquema de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="07a45-116">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="07a45-117">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="07a45-117">Schema Restrictions</span></span>  
 <span data-ttu-id="07a45-118">Se describen las restricciones de esquema que se pueden usar con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="07a45-118">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="07a45-119">Colecciones de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="07a45-119">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="07a45-120">Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07a45-120">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="07a45-121">SQL Server colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="07a45-121">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="07a45-122">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07a45-122">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="07a45-123">Colecciones de esquemas de Oracle</span><span class="sxs-lookup"><span data-stu-id="07a45-123">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="07a45-124">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="07a45-124">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="07a45-125">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="07a45-125">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="07a45-126">Describe las colecciones de esquemas para los controladores ODBC.</span><span class="sxs-lookup"><span data-stu-id="07a45-126">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="07a45-127">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="07a45-127">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="07a45-128">Describe las colecciones de esquemas para los proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="07a45-128">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="07a45-129">Referencia</span><span class="sxs-lookup"><span data-stu-id="07a45-129">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="07a45-130">Se describe el método **GetSchema** de la clase <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-130">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="07a45-131">Se describe el método **GetSchema** de la clase <xref:System.Data.Odbc.OdbcConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-131">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="07a45-132">Se describe el método **GetSchema** de la clase <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-132">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="07a45-133">Se describe el método **GetSchema** de la clase <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-133">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="07a45-134">Se describe el método **GetSchema** de la clase <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="07a45-134">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="07a45-135">Se describe el método **GetSchemaTable** de la clase <xref:System.Data.Common.DbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="07a45-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="07a45-136">Se describe el método **GetSchemaTable** de la clase <xref:System.Data.Odbc.OdbcDataReader>.</span><span class="sxs-lookup"><span data-stu-id="07a45-136">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="07a45-137">Se describe el método **GetSchemaTable** de la clase <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="07a45-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="07a45-138">Se describe el método **GetSchemaTable** de la clase <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="07a45-138">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="07a45-139">Se describe el método **GetSchemaTable** de la clase <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="07a45-139">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a45-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="07a45-140">See also</span></span>

- [<span data-ttu-id="07a45-141">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="07a45-141">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="07a45-142">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="07a45-142">ADO.NET Overview</span></span>](ado-net-overview.md)
