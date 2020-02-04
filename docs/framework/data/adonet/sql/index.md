---
title: SQL Server y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: 6e88c35936de72f0d426c23493bbe5a08e707ee1
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979981"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="2c87e-102">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="2c87e-103">En esta sección se describen características y comportamientos específicos del proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="2c87e-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="2c87e-104"><xref:System.Data.SqlClient> proporciona acceso a versiones de SQL Server, que encapsula los protocolos específicos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2c87e-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="2c87e-105">La funcionalidad del proveedor de datos se ha diseñado para que sea similar a la de los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="2c87e-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="2c87e-106"><xref:System.Data.SqlClient> incluye un analizador de flujo TDS para comunicarse directamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c87e-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c87e-107">Para utilizar el proveedor de datos .NET Framework para SQL Server, la aplicación debe hacer referencia al espacio de nombres <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="2c87e-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c87e-108">Esta sección</span><span class="sxs-lookup"><span data-stu-id="2c87e-108">In This Section</span></span>  
 [<span data-ttu-id="2c87e-109">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c87e-109">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="2c87e-110">Proporciona una introducción general a las características de seguridad de SQL Server y casos de creación de aplicaciones ADO.NET seguras dirigidas a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c87e-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="2c87e-111">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-111">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="2c87e-112">Describe cómo trabajar con tipos de datos de SQL Server y cómo interactúan con los tipos de datos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c87e-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="2c87e-113">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c87e-113">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="2c87e-114">Describe cómo trabajar con datos de valores grandes en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c87e-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="2c87e-115">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-115">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="2c87e-116">Describe cómo trabajar con datos XML en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c87e-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="2c87e-117">Contiene secciones acerca de operaciones de copia masiva, MARS, operaciones asincrónicas y parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="2c87e-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="2c87e-118">Características de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-118">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="2c87e-119">Describe las características de SQL Server que resultan de utilidad para los desarrolladores de aplicaciones ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2c87e-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="2c87e-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2c87e-120">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="2c87e-121">Describe los bloques de creación, procesos y técnicas básicos para crear aplicaciones LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="2c87e-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="2c87e-122">Para obtener documentación completa del Motor de bases de datos de SQL Server, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c87e-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="2c87e-123">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c87e-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="2c87e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c87e-124">See also</span></span>

- [<span data-ttu-id="2c87e-125">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-125">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="2c87e-126">Asignaciones de tipos de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-126">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="2c87e-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="2c87e-127">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="2c87e-128">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-128">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="2c87e-129">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c87e-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
