---
description: 'Más información sobre: SQL Server tipos de datos y ADO.NET'
title: Tipos de datos de SQL Server y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 841fa5864bf54b5e4fc4dc24dab64e6ac1435c7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767302"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="4613b-103">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4613b-103">SQL Server Data Types and ADO.NET</span></span>

<span data-ttu-id="4613b-104">SQL Server y .NET Framework están basados en sistemas de tipos distintos, lo que puede dar lugar a posibles pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="4613b-104">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="4613b-105">Para conservar la integridad de los datos, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona métodos de descriptor de acceso con tipo para trabajar con datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4613b-105">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="4613b-106">Puede usar las enumeraciones de las clases <xref:System.Data.SqlDbType> para especificar tipos de datos <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="4613b-106">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="4613b-107">Para obtener más información y una tabla que describa las asignaciones de tipos de datos entre SQL Server y .NET Framework tipos de datos, vea [SQL Server asignaciones de tipos de datos](../sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="4613b-107">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="4613b-108">SQL Server 2008 introduce nuevos tipos de datos que están diseñados para satisfacer las necesidades empresariales de trabajar con datos de fecha y hora, estructurados, semiestructurados y no estructurados.</span><span class="sxs-lookup"><span data-stu-id="4613b-108">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="4613b-109">Están documentados en los Libros en pantalla de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4613b-109">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="4613b-110">Los tipos de datos de SQL Server que están disponibles para su uso en la aplicación dependen de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="4613b-110">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="4613b-111">Para obtener más información, busque la versión pertinente de los Libros en pantalla de SQL Server en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4613b-111">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="4613b-112">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4613b-112">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="4613b-113">Tipos de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4613b-113">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="4613b-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4613b-114">In This Section</span></span>  

 [<span data-ttu-id="4613b-115">SqlTypes y DataSet</span><span class="sxs-lookup"><span data-stu-id="4613b-115">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="4613b-116">Describe la compatibilidad de tipos con `SqlTypes` en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="4613b-116">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="4613b-117">Controlar valores NULL</span><span class="sxs-lookup"><span data-stu-id="4613b-117">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="4613b-118">Demuestra cómo trabajar con valores NULL y la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="4613b-118">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="4613b-119">Comparar valores GUID y uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4613b-119">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="4613b-120">Muestra cómo trabajar con los valores GUID y uniqueidentifier en SQL Server y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4613b-120">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="4613b-121">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="4613b-121">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="4613b-122">Describe cómo usar los nuevos tipos de datos de hora y fecha incorporados en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4613b-122">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4613b-123">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="4613b-123">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="4613b-124">Muestra cómo recuperar datos de UDT de valores grandes introducidos en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4613b-124">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4613b-125">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="4613b-125">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="4613b-126">Muestra cómo recuperar datos XML recuperados de SQL Server y cómo trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="4613b-126">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4613b-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="4613b-127">Reference</span></span>  

 <xref:System.Data.DataSet>  
 <span data-ttu-id="4613b-128">Describe la clase `DataSet` y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4613b-128">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="4613b-129">Describe el espacio de nombres `SqlTypes` y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4613b-129">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="4613b-130">Describe la enumeración `SqlDbType` y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4613b-130">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="4613b-131">Describe la enumeración `DbType` y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4613b-131">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4613b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4613b-132">See also</span></span>

- [<span data-ttu-id="4613b-133">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4613b-133">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="4613b-134">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="4613b-134">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="4613b-135">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="4613b-135">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="4613b-136">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4613b-136">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="4613b-137">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4613b-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
