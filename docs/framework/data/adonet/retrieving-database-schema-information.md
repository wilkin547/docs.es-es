---
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782730"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="9199a-102">Recuperar información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="9199a-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="9199a-103">La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="9199a-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="9199a-104">La detección de esquemas permite a las aplicaciones solicitar que los proveedores administrados busquen y devuelvan información sobre el esquema de la base de datos, también conocido como *metadatos*, de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="9199a-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="9199a-105">Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas.</span><span class="sxs-lookup"><span data-stu-id="9199a-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="9199a-106">Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="9199a-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="9199a-107">Cada uno de los proveedores administrados de .NET Framework implementa el método **GetSchema** en la clase **Connection** , y la información de esquema que se devuelve desde el método **GetSchema** tiene el <xref:System.Data.DataTable>formato.</span><span class="sxs-lookup"><span data-stu-id="9199a-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9199a-108">El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se va a devolver y restringir la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="9199a-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="9199a-109">Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un método **GetSchemaTable** que devuelve un DataTable que describe los metadatos de columna del **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9199a-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="9199a-110">Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="9199a-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="9199a-111">Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se va a devolver y una matriz de restricciones en esas columnas devueltas.</span><span class="sxs-lookup"><span data-stu-id="9199a-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="9199a-112">**GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellenado con la información de esquema solicitada.</span><span class="sxs-lookup"><span data-stu-id="9199a-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9199a-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9199a-113">In This Section</span></span>  
 [<span data-ttu-id="9199a-114">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="9199a-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="9199a-115">Describe el método **GetSchema** y cómo se puede utilizar para recuperar y restringir la información de esquema de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="9199a-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="9199a-116">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="9199a-116">Schema Restrictions</span></span>  
 <span data-ttu-id="9199a-117">Describe las restricciones de esquema que se pueden usar con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="9199a-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="9199a-118">Colecciones de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="9199a-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="9199a-119">Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9199a-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="9199a-120">Colecciones de esquemas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9199a-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="9199a-121">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9199a-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="9199a-122">Colecciones de esquemas de Oracle</span><span class="sxs-lookup"><span data-stu-id="9199a-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="9199a-123">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="9199a-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="9199a-124">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="9199a-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="9199a-125">Describe las colecciones de esquemas para los controladores ODBC.</span><span class="sxs-lookup"><span data-stu-id="9199a-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="9199a-126">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="9199a-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="9199a-127">Describe las colecciones de esquemas para los proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9199a-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9199a-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="9199a-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="9199a-129">Describe el método **GetSchema** de la <xref:System.Data.Common.DbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="9199a-130">Describe el método **GetSchema** de la <xref:System.Data.Odbc.OdbcConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="9199a-131">Describe el método **GetSchema** de la <xref:System.Data.OleDb.OleDbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="9199a-132">Describe el método **GetSchema** de la <xref:System.Data.OracleClient.OracleConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="9199a-133">Describe el método **GetSchema** de la <xref:System.Data.SqlClient.SqlConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="9199a-134">Describe el método **GetSchemaTable** de la <xref:System.Data.Common.DbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="9199a-135">Describe el método **GetSchemaTable** de la <xref:System.Data.Odbc.OdbcDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="9199a-136">Describe el método **GetSchemaTable** de la <xref:System.Data.OleDb.OleDbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="9199a-137">Describe el método **GetSchemaTable** de la <xref:System.Data.OracleClient.OracleDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="9199a-138">Describe el método **GetSchemaTable** de la <xref:System.Data.SqlClient.SqlDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="9199a-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9199a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="9199a-139">See also</span></span>

- [<span data-ttu-id="9199a-140">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9199a-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="9199a-141">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9199a-141">ADO.NET Overview</span></span>](ado-net-overview.md)
