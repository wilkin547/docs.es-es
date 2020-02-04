---
title: Tipos de datos de SQL Server y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 9baffc7a439c851ead7ec0e12899adf418174e22
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979864"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="da3a8-102">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="da3a8-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="da3a8-103">SQL Server y .NET Framework están basados en sistemas de tipos distintos, lo que puede dar lugar a posibles pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="da3a8-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="da3a8-104">Para conservar la integridad de los datos, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona métodos de descriptor de acceso con tipo para trabajar con datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da3a8-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="da3a8-105">Puede usar las enumeraciones de las clases <xref:System.Data.SqlDbType> para especificar los tipos de datos <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="da3a8-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="da3a8-106">Para obtener más información y una tabla que describa las asignaciones de tipos de datos entre SQL Server y .NET Framework tipos de datos, vea [SQL Server asignaciones de tipos de datos](../sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="da3a8-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="da3a8-107">SQL Server 2008 incorpora tipos de datos nuevos diseñados para satisfacer las necesidades empresariales para trabajar con datos de fecha y hora, estructurados, semiestructurados y sin estructurar.</span><span class="sxs-lookup"><span data-stu-id="da3a8-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="da3a8-108">Estos tipos se describen en la documentación de los Libros en pantalla de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="da3a8-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="da3a8-109">Los tipos de datos de SQL Server disponibles para su uso en la aplicación dependen de la versión de SQL Server que se esté usando.</span><span class="sxs-lookup"><span data-stu-id="da3a8-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="da3a8-110">Para obtener más información, busque la versión pertinente de los Libros en pantalla de SQL Server en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da3a8-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="da3a8-111">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="da3a8-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="da3a8-112">Tipos de datos (Motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="da3a8-112">Data Types (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="da3a8-113">Esta sección</span><span class="sxs-lookup"><span data-stu-id="da3a8-113">In This Section</span></span>  
 [<span data-ttu-id="da3a8-114">SqlTypes y DataSet</span><span class="sxs-lookup"><span data-stu-id="da3a8-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="da3a8-115">Describe la compatibilidad de tipos con `SqlTypes` en el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="da3a8-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="da3a8-116">Control de valores Null</span><span class="sxs-lookup"><span data-stu-id="da3a8-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="da3a8-117">Muestra cómo trabajar con valores NULL y la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="da3a8-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="da3a8-118">Comparación de valores GUID y uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="da3a8-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="da3a8-119">Muestra cómo trabajar con los valores GUID y uniqueidentifier en SQL Server y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da3a8-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="da3a8-120">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="da3a8-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="da3a8-121">Describe cómo usar los nuevos tipos de datos de fecha y hora incorporados en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="da3a8-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="da3a8-122">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="da3a8-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="da3a8-123">Muestra cómo recuperar datos de tipos de definidos por el usuario de valores grandes incorporados en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="da3a8-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="da3a8-124">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="da3a8-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="da3a8-125">Describe cómo trabajar con datos XML recuperados de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da3a8-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da3a8-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="da3a8-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="da3a8-127">Describe la clase `DataSet`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="da3a8-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="da3a8-128">Describe el espacio de nombres `SqlTypes`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="da3a8-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="da3a8-129">Describe la enumeración `SqlDbType`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="da3a8-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="da3a8-130">Describe la enumeración `DbType`, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="da3a8-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3a8-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="da3a8-131">See also</span></span>

- [<span data-ttu-id="da3a8-132">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="da3a8-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="da3a8-133">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="da3a8-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="da3a8-134">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="da3a8-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="da3a8-135">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="da3a8-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="da3a8-136">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="da3a8-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
