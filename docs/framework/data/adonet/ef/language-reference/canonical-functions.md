---
description: 'Más información acerca de: funciones canónicas'
title: Funciones canónicas
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 6e84c4b5199d38e2efac44cf7e69c72abb1663f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739513"
---
# <a name="canonical-functions"></a><span data-ttu-id="2c0e7-103">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="2c0e7-103">Canonical Functions</span></span>

<span data-ttu-id="2c0e7-104">Esta sección describe las funciones canónicas que son admitidas por todos los proveedores de datos y pueden ser utilizadas por todas las tecnologías de creación de consultas.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-104">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="2c0e7-105">Las funciones canónicas no pueden ser ampliadas por un proveedor.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-105">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="2c0e7-106">Estas funciones canónicas se convertirán en la funcionalidad de origen de datos correspondiente para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-106">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="2c0e7-107">Esto permite que las llamadas a funciones se expresen de forma común en los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-107">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="2c0e7-108">Dado que estas funciones canónicas son independientes de los orígenes de datos, los tipos de argumentos y valores devueltos de las funciones canónicas se definen en función de los tipos en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-108">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="2c0e7-109">Sin embargo, puede que algunos orígenes de datos no admitan todos los tipos en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-109">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="2c0e7-110">Cuando las funciones canónicas se usan en una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se llamará a la función apropiada en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-110">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="2c0e7-111">Todas las funciones canónicas tienen comportamiento de entrada NULL y condiciones de error especificadas explícitamente.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-111">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="2c0e7-112">Los proveedores de almacenes deben cumplir ese comportamiento, pero Entity Framework no aplica este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-112">Store providers should comply with that behavior, but Entity Framework does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="2c0e7-113">En el caso de los escenarios de LINQ, las consultas en el Entity Framework implican la asignación de métodos CLR a métodos en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-113">For LINQ scenarios, queries against the Entity Framework involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="2c0e7-114">Los métodos de CLR se asignan a funciones canónicas de modo que un conjunto específico de métodos se asignará correctamente, con independencia del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-114">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="2c0e7-115">Espacio de nombres de funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="2c0e7-115">Canonical Functions Namespace</span></span>  

 <span data-ttu-id="2c0e7-116">El espacio de nombres para una función canónica es <xref:System.Data.Metadata.Edm>.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-116">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="2c0e7-117">El espacio de nombres <xref:System.Data.Metadata.Edm> se incluye automáticamente en todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-117">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="2c0e7-118">Sin embargo, si se importa otro espacio de nombres que contiene una función con el mismo nombre que una función canónica (en el espacio de nombres <xref:System.Data.Metadata.Edm>), se debe especificar el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-118">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c0e7-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2c0e7-119">In This Section</span></span>  

 [<span data-ttu-id="2c0e7-120">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="2c0e7-120">Aggregate Canonical Functions</span></span>](aggregate-canonical-functions.md)  
 <span data-ttu-id="2c0e7-121">Describe las funciones canónicas de agregado de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-121">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-122">Funciones canónicas matemáticas</span><span class="sxs-lookup"><span data-stu-id="2c0e7-122">Math Canonical Functions</span></span>](math-canonical-functions.md)  
 <span data-ttu-id="2c0e7-123">Describe las funciones canónicas matemáticas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-123">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-124">Funciones canónicas de cadena</span><span class="sxs-lookup"><span data-stu-id="2c0e7-124">String Canonical Functions</span></span>](string-canonical-functions.md)  
 <span data-ttu-id="2c0e7-125">Describe las funciones canónicas de cadena de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-125">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-126">Funciones canónicas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="2c0e7-126">Date and Time Canonical Functions</span></span>](date-and-time-canonical-functions.md)  
 <span data-ttu-id="2c0e7-127">Describe las funciones canónicas de fecha y hora de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-127">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-128">Funciones canónicas bit a bit</span><span class="sxs-lookup"><span data-stu-id="2c0e7-128">Bitwise Canonical Functions</span></span>](bitwise-canonical-functions.md)  
 <span data-ttu-id="2c0e7-129">Describe las funciones canónicas bit a bit de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-129">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-130">Funciones espaciales</span><span class="sxs-lookup"><span data-stu-id="2c0e7-130">Spatial Functions</span></span>](spatial-functions.md)  
 <span data-ttu-id="2c0e7-131">Describe las funciones canónicas y espaciales de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0e7-131">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="2c0e7-132">Otras funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="2c0e7-132">Other Canonical Functions</span></span>](other-canonical-functions.md)  
 <span data-ttu-id="2c0e7-133">Describe las funciones no clasificadas como funciones bit a bit, de fecha y hora, de cadena, matemáticas o de agregado.</span><span class="sxs-lookup"><span data-stu-id="2c0e7-133">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0e7-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c0e7-134">See also</span></span>

- [<span data-ttu-id="2c0e7-135">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c0e7-135">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="2c0e7-136">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c0e7-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="2c0e7-137">Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c0e7-137">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="2c0e7-138">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="2c0e7-138">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)
