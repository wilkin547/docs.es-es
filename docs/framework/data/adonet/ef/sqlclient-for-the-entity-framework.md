---
title: SqlClient para Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: 7f3a1d4bbd18977bbb1dc9ce65140428ea6fe2f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156542"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="b7ded-102">SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b7ded-102">SqlClient for the Entity Framework</span></span>

<span data-ttu-id="b7ded-103">En esta sección se describe el Proveedor de datos de .NET Framework para SQL Server (SqlClient), el cual permite a Entity Framework trabajar sobre Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7ded-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="b7ded-104">Atributo Provider de Schema</span><span class="sxs-lookup"><span data-stu-id="b7ded-104">Provider Schema Attribute</span></span>  

 <span data-ttu-id="b7ded-105">`Provider` es un atributo del elemento `Schema` del lenguaje de definición de esquemas de almacenamiento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="b7ded-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="b7ded-106">Para utilizar SqlClient, asigne la cadena "System.Data.SqlClient" al atributo `Provider` del elemento `Schema`.</span><span class="sxs-lookup"><span data-stu-id="b7ded-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="b7ded-107">Atributo ProviderManifestToken de Schema</span><span class="sxs-lookup"><span data-stu-id="b7ded-107">ProviderManifestToken Schema Attribute</span></span>  

 <span data-ttu-id="b7ded-108">`ProviderManifestToken` es un atributo necesario del elemento `Schema` en SSDL.</span><span class="sxs-lookup"><span data-stu-id="b7ded-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="b7ded-109">Este token se utiliza para cargar el manifiesto del proveedor en escenarios sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b7ded-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="b7ded-110">Para obtener más información sobre el `ProviderManifestToken` atributo, vea [Schema (elemento) (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="b7ded-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="b7ded-111">SqlClient se puede usar como proveedor de datos para diferentes versiones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7ded-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="b7ded-112">Estas versiones tienen capacidades distintas.</span><span class="sxs-lookup"><span data-stu-id="b7ded-112">These versions have different capabilities.</span></span> <span data-ttu-id="b7ded-113">Por ejemplo, SQL Server 2000 no admite los `varchar(max)` `nvarchar(max)` tipos y que se introdujeron con SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="b7ded-113">For example, SQL Server 2000 does not support `varchar(max)` and `nvarchar(max)` types that were introduced with SQL Server 2005.</span></span>  
  
 <span data-ttu-id="b7ded-114">SqlCliente genera y acepta los tokens del manifiesto del proveedor siguientes para las diferentes versiones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7ded-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="b7ded-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="b7ded-115">SQL Server 2000</span></span>|<span data-ttu-id="b7ded-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="b7ded-116">SQL Server 2005</span></span>|<span data-ttu-id="b7ded-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="b7ded-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="b7ded-118">2000</span><span class="sxs-lookup"><span data-stu-id="b7ded-118">2000</span></span>|<span data-ttu-id="b7ded-119">2005</span><span class="sxs-lookup"><span data-stu-id="b7ded-119">2005</span></span>|<span data-ttu-id="b7ded-120">2008</span><span class="sxs-lookup"><span data-stu-id="b7ded-120">2008</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b7ded-121">A partir de Visual Studio 2010, las [herramientas de Entity Data Model de ADO.net](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) no admiten SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="b7ded-121">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="b7ded-122">Nombre del espacio de nombres de proveedor</span><span class="sxs-lookup"><span data-stu-id="b7ded-122">Provider Namespace Name</span></span>  

 <span data-ttu-id="b7ded-123">Todos los proveedores deben especificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b7ded-123">All providers must specify a namespace.</span></span> <span data-ttu-id="b7ded-124">Esta propiedad indica a Entity Framework qué prefijo usa el proveedor para estructuras concretas, como los tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="b7ded-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="b7ded-125">El espacio de nombres para los manifiestos del proveedor SqlClient es `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="b7ded-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="b7ded-126">Para obtener más información sobre los espacios de nombres, vea [espacios de nombres](./language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b7ded-126">For more information about namespaces, see [Namespaces](./language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="b7ded-127">Tipos</span><span class="sxs-lookup"><span data-stu-id="b7ded-127">Types</span></span>  

 <span data-ttu-id="b7ded-128">El proveedor SqlCliente para Entity Framework proporciona información de asignación entre los tipos del modelo conceptual y los tipos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7ded-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="b7ded-129">Para obtener más información, vea [SqlClient para Entity Framework](sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="b7ded-129">For more information, see [SqlClient for Entity FrameworkTypes](sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="b7ded-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="b7ded-130">Functions</span></span>  

 <span data-ttu-id="b7ded-131">El proveedor de SqlClient para Entity Framework define la lista de funciones admitidas por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="b7ded-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="b7ded-132">Para obtener una lista de las funciones admitidas, vea [SqlClient para funciones de Entity Framework](sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="b7ded-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7ded-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7ded-133">In This Section</span></span>  

 [<span data-ttu-id="b7ded-134">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b7ded-134">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="b7ded-135">SqlClient para tipos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b7ded-135">SqlClient for Entity FrameworkTypes</span></span>](sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="b7ded-136">Problemas conocidos en SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b7ded-136">Known Issues in SqlClient for Entity Framework</span></span>](known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7ded-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7ded-137">See also</span></span>

- [<span data-ttu-id="b7ded-138">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b7ded-138">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="b7ded-139">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="b7ded-139">Language Reference</span></span>](./language-reference/index.md)
- [<span data-ttu-id="b7ded-140">Problemas conocidos del proveedor SqlClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b7ded-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](sqlclient-for-the-entity-framework.md)
