---
description: 'Más información acerca de: SqlClient para el Entity Framework'
title: SqlClient para Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: eba5602c13f66d1ee4404bbc27035304e34c1cd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673133"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="fdb31-103">SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fdb31-103">SqlClient for the Entity Framework</span></span>

<span data-ttu-id="fdb31-104">En esta sección se describe el Proveedor de datos de .NET Framework para SQL Server (SqlClient), el cual permite a Entity Framework trabajar sobre Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb31-104">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="fdb31-105">Atributo Provider de Schema</span><span class="sxs-lookup"><span data-stu-id="fdb31-105">Provider Schema Attribute</span></span>  

 <span data-ttu-id="fdb31-106">`Provider` es un atributo del elemento `Schema` del lenguaje de definición de esquemas de almacenamiento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="fdb31-106">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="fdb31-107">Para utilizar SqlClient, asigne la cadena "System.Data.SqlClient" al atributo `Provider` del elemento `Schema`.</span><span class="sxs-lookup"><span data-stu-id="fdb31-107">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="fdb31-108">Atributo ProviderManifestToken de Schema</span><span class="sxs-lookup"><span data-stu-id="fdb31-108">ProviderManifestToken Schema Attribute</span></span>  

 <span data-ttu-id="fdb31-109">`ProviderManifestToken` es un atributo necesario del elemento `Schema` en SSDL.</span><span class="sxs-lookup"><span data-stu-id="fdb31-109">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="fdb31-110">Este token se utiliza para cargar el manifiesto del proveedor en escenarios sin conexión.</span><span class="sxs-lookup"><span data-stu-id="fdb31-110">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="fdb31-111">Para obtener más información sobre el `ProviderManifestToken` atributo, vea [Schema (elemento) (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="fdb31-111">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="fdb31-112">SqlClient se puede usar como proveedor de datos para diferentes versiones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb31-112">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="fdb31-113">Estas versiones tienen capacidades distintas.</span><span class="sxs-lookup"><span data-stu-id="fdb31-113">These versions have different capabilities.</span></span> <span data-ttu-id="fdb31-114">Por ejemplo, SQL Server 2000 no admite los `varchar(max)` `nvarchar(max)` tipos y que se introdujeron con SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="fdb31-114">For example, SQL Server 2000 does not support `varchar(max)` and `nvarchar(max)` types that were introduced with SQL Server 2005.</span></span>  
  
 <span data-ttu-id="fdb31-115">SqlCliente genera y acepta los tokens del manifiesto del proveedor siguientes para las diferentes versiones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb31-115">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="fdb31-116">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="fdb31-116">SQL Server 2000</span></span>|<span data-ttu-id="fdb31-117">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="fdb31-117">SQL Server 2005</span></span>|<span data-ttu-id="fdb31-118">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="fdb31-118">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="fdb31-119">2000</span><span class="sxs-lookup"><span data-stu-id="fdb31-119">2000</span></span>|<span data-ttu-id="fdb31-120">2005</span><span class="sxs-lookup"><span data-stu-id="fdb31-120">2005</span></span>|<span data-ttu-id="fdb31-121">2008</span><span class="sxs-lookup"><span data-stu-id="fdb31-121">2008</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fdb31-122">A partir de Visual Studio 2010, las [herramientas de Entity Data Model de ADO.net](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) no admiten SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="fdb31-122">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="fdb31-123">Nombre del espacio de nombres de proveedor</span><span class="sxs-lookup"><span data-stu-id="fdb31-123">Provider Namespace Name</span></span>  

 <span data-ttu-id="fdb31-124">Todos los proveedores deben especificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdb31-124">All providers must specify a namespace.</span></span> <span data-ttu-id="fdb31-125">Esta propiedad indica a Entity Framework qué prefijo usa el proveedor para estructuras concretas, como los tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="fdb31-125">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="fdb31-126">El espacio de nombres para los manifiestos del proveedor SqlClient es `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="fdb31-126">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="fdb31-127">Para obtener más información sobre los espacios de nombres, vea [espacios de nombres](./language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fdb31-127">For more information about namespaces, see [Namespaces](./language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="fdb31-128">Tipos</span><span class="sxs-lookup"><span data-stu-id="fdb31-128">Types</span></span>  

 <span data-ttu-id="fdb31-129">El proveedor SqlCliente para Entity Framework proporciona información de asignación entre los tipos del modelo conceptual y los tipos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdb31-129">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="fdb31-130">Para obtener más información, vea [SqlClient para Entity Framework](sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="fdb31-130">For more information, see [SqlClient for Entity FrameworkTypes](sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="fdb31-131">Functions</span><span class="sxs-lookup"><span data-stu-id="fdb31-131">Functions</span></span>  

 <span data-ttu-id="fdb31-132">El proveedor de SqlClient para Entity Framework define la lista de funciones admitidas por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="fdb31-132">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="fdb31-133">Para obtener una lista de las funciones admitidas, vea [SqlClient para funciones de Entity Framework](sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="fdb31-133">For a list of the supported functions, see [SqlClient for Entity Framework Functions](sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdb31-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fdb31-134">In This Section</span></span>  

 [<span data-ttu-id="fdb31-135">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fdb31-135">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="fdb31-136">SqlClient para tipos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fdb31-136">SqlClient for Entity FrameworkTypes</span></span>](sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="fdb31-137">Problemas conocidos en SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fdb31-137">Known Issues in SqlClient for Entity Framework</span></span>](known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="fdb31-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdb31-138">See also</span></span>

- [<span data-ttu-id="fdb31-139">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fdb31-139">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="fdb31-140">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="fdb31-140">Language Reference</span></span>](./language-reference/index.md)
- [<span data-ttu-id="fdb31-141">Problemas conocidos del proveedor SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fdb31-141">Known Issues in SqlClient Provider for Entity Framework</span></span>](sqlclient-for-the-entity-framework.md)
