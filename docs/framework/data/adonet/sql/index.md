---
title: SQL Server y ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: 87e46ad9e83929e40daecc3e3af2eb1281c5ced9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360718"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="ddaa6-102">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="ddaa6-103">En esta sección se describen características y comportamientos específicos del proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="ddaa6-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="ddaa6-104"><xref:System.Data.SqlClient> proporciona acceso a versiones de SQL Server, que encapsula los protocolos específicos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="ddaa6-105">La funcionalidad del proveedor de datos se ha diseñado para que sea similar a la de los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="ddaa6-106"><xref:System.Data.SqlClient> incluye un analizador de flujo TDS para comunicarse directamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddaa6-107">Para utilizar el proveedor de datos .NET Framework para SQL Server, la aplicación debe hacer referencia al espacio de nombres <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddaa6-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ddaa6-108">In This Section</span></span>  
 [<span data-ttu-id="ddaa6-109">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddaa6-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="ddaa6-110">Proporciona una introducción general a las características de seguridad de SQL Server y casos de creación de aplicaciones ADO.NET seguras dirigidas a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="ddaa6-111">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="ddaa6-112">Describe cómo trabajar con tipos de datos de SQL Server y cómo interactúan con los tipos de datos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="ddaa6-113">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddaa6-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="ddaa6-114">Describe cómo trabajar con datos de valores grandes en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="ddaa6-115">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="ddaa6-116">Describe cómo trabajar con datos XML en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="ddaa6-117">Contiene secciones acerca de operaciones de copia masiva, MARS, operaciones asincrónicas y parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ddaa6-118">Características de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="ddaa6-119">Describe las características de SQL Server que resultan de utilidad para los desarrolladores de aplicaciones ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="ddaa6-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ddaa6-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="ddaa6-121">Describe los bloques de creación, procesos y técnicas básicos para crear aplicaciones LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="ddaa6-122">Para obtener documentación completa del Motor de bases de datos de SQL Server, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddaa6-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="ddaa6-123">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddaa6-123">SQL Server Books Online</span></span>](http://msdn.microsoft.com/library/ms130214.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="ddaa6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddaa6-124">See Also</span></span>  
 [<span data-ttu-id="ddaa6-125">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="ddaa6-126">Asignaciones de tipos de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="ddaa6-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="ddaa6-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ddaa6-128">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ddaa6-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="ddaa6-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ddaa6-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
