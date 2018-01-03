---
title: Tipos de datos de SQL Server y ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fd3982cf8eeeb88a162e77a3ef4b9d6e75e19fc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="03e33-102">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="03e33-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="03e33-103">SQL Server y .NET Framework están basados en sistemas de tipos distintos, lo que puede dar lugar a posibles pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="03e33-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="03e33-104">Para conservar la integridad de los datos, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona métodos de descriptor de acceso con tipo para trabajar con datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03e33-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="03e33-105">Puede usar las enumeraciones de las clases <xref:System.Data.SqlDbType> para especificar los tipos de datos <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="03e33-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="03e33-106">Para obtener más información y una tabla que describe los datos de asignaciones entre tipos de datos de .NET Framework y SQL Server de tipo, consulte [asignaciones de tipos de datos de SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="03e33-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="03e33-107">SQL Server 2008 incorpora tipos de datos nuevos diseñados para satisfacer las necesidades empresariales para trabajar con datos de fecha y hora, estructurados, semiestructurados y sin estructurar.</span><span class="sxs-lookup"><span data-stu-id="03e33-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="03e33-108">Estos tipos se describen en la documentación de los Libros en pantalla de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="03e33-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="03e33-109">Los tipos de datos de SQL Server disponibles para su uso en la aplicación dependen de la versión de SQL Server que se esté usando.</span><span class="sxs-lookup"><span data-stu-id="03e33-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="03e33-110">Para obtener más información, busque la versión pertinente de los Libros en pantalla de SQL Server en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="03e33-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="03e33-111">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="03e33-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="03e33-112">Tipos de datos (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="03e33-112">Data Types (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="03e33-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="03e33-113">In This Section</span></span>  
 [<span data-ttu-id="03e33-114">SqlTypes y DataSet</span><span class="sxs-lookup"><span data-stu-id="03e33-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="03e33-115">Describe la compatibilidad de tipos con `SqlTypes` en el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="03e33-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="03e33-116">Control de valores Null</span><span class="sxs-lookup"><span data-stu-id="03e33-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="03e33-117">Muestra cómo trabajar con valores NULL y la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="03e33-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="03e33-118">Comparación de valores GUID y uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="03e33-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="03e33-119">Muestra cómo trabajar con los valores GUID y uniqueidentifier en SQL Server y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03e33-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="03e33-120">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="03e33-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="03e33-121">Describe cómo usar los nuevos tipos de datos de fecha y hora incorporados en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="03e33-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="03e33-122">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="03e33-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="03e33-123">Muestra cómo recuperar datos de tipos de definidos por el usuario de valores grandes incorporados en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="03e33-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="03e33-124">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="03e33-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="03e33-125">Describe cómo trabajar con datos XML recuperados de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03e33-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="03e33-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="03e33-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="03e33-127">Describe la clase `DataSet`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="03e33-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="03e33-128">Describe el espacio de nombres `SqlTypes`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="03e33-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="03e33-129">Describe la enumeración `SqlDbType`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="03e33-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="03e33-130">Describe la enumeración `DbType`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="03e33-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e33-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e33-131">See Also</span></span>  
 [<span data-ttu-id="03e33-132">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="03e33-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="03e33-133">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="03e33-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="03e33-134">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="03e33-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="03e33-135">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="03e33-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="03e33-136">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="03e33-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
