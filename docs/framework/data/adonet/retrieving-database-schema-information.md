---
title: "Recuperar información del esquema de la base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 19fee0f90c1f460d253cfdc865035a6b8aa3db48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="fe707-102">Recuperar información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="fe707-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="fe707-103">La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="fe707-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="fe707-104">Detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados buscan y devuelvan información acerca del esquema de base de datos, también conocido como *metadatos*, de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="fe707-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="fe707-105">Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas.</span><span class="sxs-lookup"><span data-stu-id="fe707-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="fe707-106">Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="fe707-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="fe707-107">Cada uno de lo proveedores administrados de .NET Framework implementan la **GetSchema** método en el **conexión** clase y la información de esquema que se devuelve desde el **GetSchema**método viene en forma de un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="fe707-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="fe707-108">El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="fe707-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="fe707-109">Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un **GetSchemaTable** método que devuelve una DataTable donde se describen los metadatos de columna de la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="fe707-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="fe707-110">Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="fe707-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="fe707-111">Como argumentos, **GetOleDbSchemaTable** toma una <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se devuelve y una matriz de restricciones en esas columnas devueltas.</span><span class="sxs-lookup"><span data-stu-id="fe707-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="fe707-112">**GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellena con la información de esquema solicitada.</span><span class="sxs-lookup"><span data-stu-id="fe707-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe707-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fe707-113">In This Section</span></span>  
 [<span data-ttu-id="fe707-114">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="fe707-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="fe707-115">Describe la **GetSchema** método y cómo se puede utilizar para recuperar y restringir información de esquema desde una base de datos.</span><span class="sxs-lookup"><span data-stu-id="fe707-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="fe707-116">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="fe707-116">Schema Restrictions</span></span>  
 <span data-ttu-id="fe707-117">Describe las restricciones de esquema que se pueden utilizar con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="fe707-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="fe707-118">Colecciones de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="fe707-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="fe707-119">Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fe707-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="fe707-120">Colecciones de esquemas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe707-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="fe707-121">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe707-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="fe707-122">Colecciones de esquemas de Oracle</span><span class="sxs-lookup"><span data-stu-id="fe707-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="fe707-123">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="fe707-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="fe707-124">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="fe707-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="fe707-125">Describe las colecciones de esquemas para los controladores ODBC.</span><span class="sxs-lookup"><span data-stu-id="fe707-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="fe707-126">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="fe707-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="fe707-127">Describe las colecciones de esquemas para los proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fe707-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fe707-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="fe707-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="fe707-129">Describe la **GetSchema** método de la <xref:System.Data.Common.DbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="fe707-130">Describe la **GetSchema** método de la <xref:System.Data.Odbc.OdbcConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="fe707-131">Describe la **GetSchema** método de la <xref:System.Data.OleDb.OleDbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="fe707-132">Describe la **GetSchema** método de la <xref:System.Data.OracleClient.OracleConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="fe707-133">Describe la **GetSchema** método de la <xref:System.Data.SqlClient.SqlConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="fe707-134">Describe la **GetSchemaTable** método de la <xref:System.Data.Common.DbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="fe707-135">Describe la **GetSchemaTable** método de la <xref:System.Data.Odbc.OdbcDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="fe707-136">Describe la **GetSchemaTable** método de la <xref:System.Data.OleDb.OleDbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="fe707-137">Describe la **GetSchemaTable** método de la <xref:System.Data.OracleClient.OracleDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="fe707-138">Describe la **GetSchemaTable** método de la <xref:System.Data.SqlClient.SqlDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="fe707-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe707-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe707-139">See Also</span></span>  
 [<span data-ttu-id="fe707-140">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fe707-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="fe707-141">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="fe707-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
