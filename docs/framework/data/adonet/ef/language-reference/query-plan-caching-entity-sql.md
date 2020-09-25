---
title: Almacenamiento en caché del plan de consulta [Entity SQL]
ms.date: 03/30/2017
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
ms.openlocfilehash: 51c5de8365819065f8e505468f37a47370ec502f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175557"
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="7c1d1-102">Almacenamiento en caché del plan de consulta [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="7c1d1-102">Query Plan Caching (Entity SQL)</span></span>

<span data-ttu-id="7c1d1-103">Siempre que se intenta ejecutar una consulta, la canalización de la consulta examina la memoria caché del plan de consulta para comprobar si la citada consulta ya está compilada y disponible.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="7c1d1-104">En ese caso, vuelve a utilizar el plan almacenado en caché en lugar de compilar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="7c1d1-105">Si no se encuentra ninguna coincidencia en la memoria caché del plan de consulta, la consulta se compila y se almacena en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="7c1d1-106">Las consultas se identifican mediante su colección de parámetros (nombres y tipos) y texto de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c1d1-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="7c1d1-107">Todas las comparaciones de texto distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7c1d1-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="7c1d1-108">Configuration</span></span>  

 <span data-ttu-id="7c1d1-109">El almacenamiento en caché del plan de consulta se puede configurar a través del comando <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="7c1d1-110">Para habilitar o deshabilitar el almacenamiento en caché del plan de consulta a través de la propiedad <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, establezca esta propiedad en `true` o `false`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="7c1d1-111">Si se deshabilita el almacenamiento en caché del plan en consultas dinámicas individuales que no es probable que se usen más de una vez, mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="7c1d1-112">Puede habilitar el almacenamiento en caché del plan de consultas a través de <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="7c1d1-113">Práctica recomendada</span><span class="sxs-lookup"><span data-stu-id="7c1d1-113">Recommended Practice</span></span>  

 <span data-ttu-id="7c1d1-114">En general, se deben evitar las consultas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="7c1d1-115">El ejemplo de consulta dinámica siguiente es vulnerable a los ataques de inyección de SQL, porque toma directamente los datos proporcionados por el usuario sin efectuar ninguna validación.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 ```csharp
 var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;  
 ```

 <span data-ttu-id="7c1d1-116">Si utiliza las consultas generadas dinámicamente, considere deshabilitar el almacenamiento en memoria caché del plan de consultas para evitar el consumo de memoria innecesario para las entradas de la memoria caché que no es probable que se vuelvan a usar.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="7c1d1-117">El almacenamiento en caché del plan de consulta en consultas estáticas y parametrizadas puede proporcionar mejoras en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="7c1d1-118">A continuación se muestra un ejemplo de consulta estática:</span><span class="sxs-lookup"><span data-stu-id="7c1d1-118">The following is an example of a static query:</span></span>  
  
```csharp
var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="7c1d1-119">Para que se encuentre una coincidencia apropiada de las consultas en la memoria caché del plan de consulta, estas deben cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7c1d1-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
- <span data-ttu-id="7c1d1-120">El texto de la consulta debe ser un patrón constante, preferentemente una cadena o un recurso constante.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
- <span data-ttu-id="7c1d1-121">Se debe utilizar <xref:System.Data.EntityClient.EntityParameter> o <xref:System.Data.Objects.ObjectParameter> siempre que se deba pasar un valor proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-121"><xref:System.Data.EntityClient.EntityParameter> or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="7c1d1-122">Se deben evitar los patrones de consulta siguientes, que consumen innecesariamente espacios en la memoria caché del plan de consulta:</span><span class="sxs-lookup"><span data-stu-id="7c1d1-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
- <span data-ttu-id="7c1d1-123">Cambios en las mayúsculas o minúsculas del texto.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-123">Changes to letter case in the text.</span></span>  
  
- <span data-ttu-id="7c1d1-124">Cambios en los espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-124">Changes to white space.</span></span>  
  
- <span data-ttu-id="7c1d1-125">Cambios en los valores literales.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-125">Changes to literal values.</span></span>  
  
- <span data-ttu-id="7c1d1-126">Cambios en el texto incluido en los comentarios.</span><span class="sxs-lookup"><span data-stu-id="7c1d1-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1d1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c1d1-127">See also</span></span>

- [<span data-ttu-id="7c1d1-128">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7c1d1-128">Entity SQL Overview</span></span>](entity-sql-overview.md)
