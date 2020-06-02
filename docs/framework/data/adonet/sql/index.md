---
title: SQL Server y ADO.NET
description: Obtenga información sobre las características y los comportamientos del proveedor de datos de .NET Framework para SQL Server, que encapsula los protocolos específicos de la base de datos.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286447"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="f96a7-103">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-103">SQL Server and ADO.NET</span></span>
<span data-ttu-id="f96a7-104">En esta sección se describen características y comportamientos específicos del proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="f96a7-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="f96a7-105"><xref:System.Data.SqlClient> proporciona acceso a versiones de SQL Server, que encapsula los protocolos específicos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f96a7-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="f96a7-106">La funcionalidad del proveedor de datos se ha diseñado para que sea similar a la de los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="f96a7-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="f96a7-107"><xref:System.Data.SqlClient> incluye un analizador de flujos de datos tabulares (TDS) para comunicarse directamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f96a7-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f96a7-108">Para utilizar el proveedor de datos .NET Framework para SQL Server, la aplicación debe hacer referencia al espacio de nombres <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="f96a7-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f96a7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f96a7-109">In This Section</span></span>  
 [<span data-ttu-id="f96a7-110">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f96a7-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="f96a7-111">Proporciona una introducción general a las características de seguridad de SQL Server y casos de creación de aplicaciones ADO.NET seguras dirigidas a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f96a7-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="f96a7-112">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="f96a7-113">Describe cómo trabajar con tipos de datos de SQL Server y cómo interactúan con los tipos de datos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f96a7-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="f96a7-114">SQL Server datos binarios y de valores grandes</span><span class="sxs-lookup"><span data-stu-id="f96a7-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="f96a7-115">Describe cómo trabajar con datos de valores grandes en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f96a7-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="f96a7-116">SQL Server operaciones de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="f96a7-117">Describe cómo trabajar con datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f96a7-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="f96a7-118">Contiene secciones sobre las operaciones de copia masiva, MARS, las operaciones asincrónicas y los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="f96a7-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="f96a7-119">Características de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="f96a7-120">Describe características de SQL Server que son útiles para los desarrolladores de aplicaciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f96a7-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="f96a7-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f96a7-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="f96a7-122">Describe los bloques de creación, procesos y técnicas básicos para crear aplicaciones LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="f96a7-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="f96a7-123">Para obtener la documentación completa sobre el motor de base de datos de SQL Server, vea los Libros en pantalla de SQL Server de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="f96a7-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="f96a7-124">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f96a7-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="f96a7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f96a7-125">See also</span></span>

- [<span data-ttu-id="f96a7-126">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="f96a7-127">Asignaciones de tipos de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="f96a7-128">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="f96a7-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f96a7-129">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="f96a7-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f96a7-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
