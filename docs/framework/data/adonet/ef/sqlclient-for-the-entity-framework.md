---
title: SqlClient para Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 590df03857805c43b6e9a60c030cadcad3501d3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="a1df0-102">SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a1df0-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="a1df0-103">En esta sección se describe el Proveedor de datos de .NET Framework para SQL Server (SqlClient), el cual permite a Entity Framework trabajar sobre Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1df0-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="a1df0-104">Atributo Provider de Schema</span><span class="sxs-lookup"><span data-stu-id="a1df0-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="a1df0-105">`Provider` es un atributo del elemento `Schema` del lenguaje de definición de esquemas de almacenamiento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="a1df0-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="a1df0-106">Para utilizar SqlClient, asigne la cadena "System.Data.SqlClient" al atributo `Provider` del elemento `Schema`.</span><span class="sxs-lookup"><span data-stu-id="a1df0-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="a1df0-107">Atributo ProviderManifestToken de Schema</span><span class="sxs-lookup"><span data-stu-id="a1df0-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="a1df0-108">`ProviderManifestToken` es un atributo necesario del elemento `Schema` en SSDL.</span><span class="sxs-lookup"><span data-stu-id="a1df0-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="a1df0-109">Este token se utiliza para cargar el manifiesto del proveedor en escenarios sin conexión.</span><span class="sxs-lookup"><span data-stu-id="a1df0-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="a1df0-110">Para obtener más información acerca de `ProviderManifestToken` de atributo, vea [elemento de esquema de almacenamiento (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).</span><span class="sxs-lookup"><span data-stu-id="a1df0-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).</span></span>  
  
 <span data-ttu-id="a1df0-111">SqlClient se puede utilizar como proveedor de datos para diferentes versiones de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1df0-111">SqlClient can be used as a data provider for different versions of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a1df0-112">Estas versiones tienen capacidades distintas.</span><span class="sxs-lookup"><span data-stu-id="a1df0-112">These versions have different capabilities.</span></span> <span data-ttu-id="a1df0-113">Por ejemplo, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] no admite los tipos `varchar(max)` y `nvarchar(max)` que se incluyeron con [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1df0-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="a1df0-114">SqlCliente genera y acepta los tokens del manifiesto del proveedor siguientes para las diferentes versiones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1df0-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="a1df0-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="a1df0-115">SQL Server 2000</span></span>|<span data-ttu-id="a1df0-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="a1df0-116">SQL Server 2005</span></span>|<span data-ttu-id="a1df0-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="a1df0-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="a1df0-118">2000</span><span class="sxs-lookup"><span data-stu-id="a1df0-118">2000</span></span>|<span data-ttu-id="a1df0-119">2005</span><span class="sxs-lookup"><span data-stu-id="a1df0-119">2005</span></span>|<span data-ttu-id="a1df0-120">2008</span><span class="sxs-lookup"><span data-stu-id="a1df0-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a1df0-121">A partir de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, la [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) no son compatibles con SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="a1df0-121">Starting with [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, the [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="a1df0-122">Nombre del espacio de nombres de proveedor</span><span class="sxs-lookup"><span data-stu-id="a1df0-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="a1df0-123">Todos los proveedores deben especificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a1df0-123">All providers must specify a namespace.</span></span> <span data-ttu-id="a1df0-124">Esta propiedad indica a Entity Framework qué prefijo usa el proveedor para estructuras concretas, como los tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="a1df0-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="a1df0-125">El espacio de nombres para los manifiestos del proveedor SqlClient es `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="a1df0-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="a1df0-126">Para obtener más información acerca de los espacios de nombres, vea [espacios de nombres](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a1df0-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="a1df0-127">Tipos</span><span class="sxs-lookup"><span data-stu-id="a1df0-127">Types</span></span>  
 <span data-ttu-id="a1df0-128">El proveedor SqlCliente para Entity Framework proporciona información de asignación entre los tipos del modelo conceptual y los tipos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1df0-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="a1df0-129">Para obtener más información, consulte [SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="a1df0-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="a1df0-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="a1df0-130">Functions</span></span>  
 <span data-ttu-id="a1df0-131">El proveedor de SqlClient para Entity Framework define la lista de funciones admitidas por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="a1df0-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="a1df0-132">Para obtener una lista de las funciones admitidas, consulte [SqlClient para Entity Framework funciones](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="a1df0-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1df0-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1df0-133">In This Section</span></span>  
 [<span data-ttu-id="a1df0-134">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a1df0-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="a1df0-135">SqlClient para tipos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a1df0-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="a1df0-136">Problemas conocidos en SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a1df0-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="a1df0-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1df0-137">See Also</span></span>  
 [<span data-ttu-id="a1df0-138">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a1df0-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="a1df0-139">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="a1df0-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [<span data-ttu-id="a1df0-140">Problemas conocidos de proveedor de SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a1df0-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
