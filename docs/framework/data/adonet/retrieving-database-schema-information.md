---
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 00cf0e36dd7886897c26adf50102f32892ebb18e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43772846"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="01555-102">Recuperar información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="01555-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="01555-103">La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="01555-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="01555-104">Detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados encontraron y devuelvan información acerca del esquema de base de datos, también conocido como *metadatos*, de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="01555-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="01555-105">Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas.</span><span class="sxs-lookup"><span data-stu-id="01555-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="01555-106">Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="01555-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="01555-107">Cada una de las implementan proveedores administrados de .NET Framework la **GetSchema** método en el **conexión** clase y la información de esquema que se devuelve desde el **GetSchema**método viene en forma de un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="01555-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="01555-108">El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="01555-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="01555-109">Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un **GetSchemaTable** método que devuelve un objeto DataTable que describe los metadatos de columna de la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="01555-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="01555-110">Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="01555-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="01555-111">Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema para devolver y una matriz de restricciones en esas columnas devueltas.</span><span class="sxs-lookup"><span data-stu-id="01555-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="01555-112">**GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellena con la información de esquema solicitada.</span><span class="sxs-lookup"><span data-stu-id="01555-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01555-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="01555-113">In This Section</span></span>  
 [<span data-ttu-id="01555-114">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="01555-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="01555-115">Describe el **GetSchema** método y cómo se puede usar para recuperar y restringir información de esquema desde una base de datos.</span><span class="sxs-lookup"><span data-stu-id="01555-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="01555-116">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="01555-116">Schema Restrictions</span></span>  
 <span data-ttu-id="01555-117">Describe las restricciones de esquema que se pueden usar con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="01555-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="01555-118">Colecciones de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="01555-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="01555-119">Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01555-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="01555-120">Colecciones de esquemas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="01555-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="01555-121">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01555-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="01555-122">Colecciones de esquemas de Oracle</span><span class="sxs-lookup"><span data-stu-id="01555-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="01555-123">Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="01555-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="01555-124">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="01555-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="01555-125">Describe las colecciones de esquemas para los controladores ODBC.</span><span class="sxs-lookup"><span data-stu-id="01555-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="01555-126">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="01555-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="01555-127">Describe las colecciones de esquemas para los proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="01555-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="01555-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="01555-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="01555-129">Describe el **GetSchema** método de la <xref:System.Data.Common.DbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="01555-130">Describe el **GetSchema** método de la <xref:System.Data.Odbc.OdbcConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="01555-131">Describe el **GetSchema** método de la <xref:System.Data.OleDb.OleDbConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="01555-132">Describe el **GetSchema** método de la <xref:System.Data.OracleClient.OracleConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="01555-133">Describe el **GetSchema** método de la <xref:System.Data.SqlClient.SqlConnection> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="01555-134">Describe el **GetSchemaTable** método de la <xref:System.Data.Common.DbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="01555-135">Describe el **GetSchemaTable** método de la <xref:System.Data.Odbc.OdbcDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="01555-136">Describe el **GetSchemaTable** método de la <xref:System.Data.OleDb.OleDbDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="01555-137">Describe el **GetSchemaTable** método de la <xref:System.Data.OracleClient.OracleDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="01555-138">Describe el **GetSchemaTable** método de la <xref:System.Data.SqlClient.SqlDataReader> clase.</span><span class="sxs-lookup"><span data-stu-id="01555-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01555-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="01555-139">See Also</span></span>  
 [<span data-ttu-id="01555-140">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01555-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="01555-141">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="01555-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
