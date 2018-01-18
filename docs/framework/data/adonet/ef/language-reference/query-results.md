---
title: Resultados de la consulta
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d2e8dc70007a0f3a411c4c8e48015f98c23da573
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="query-results"></a><span data-ttu-id="df243-102">Resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="df243-102">Query Results</span></span>
<span data-ttu-id="df243-103">Después de que una consulta de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] se convierta en árboles de comandos y se ejecute, los resultados de la consulta se devuelven normalmente como uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="df243-103">After a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is converted to command trees and executed, the query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="df243-104">Una colección con cero o más objetos entidad con tipo o una proyección de tipos complejos en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="df243-104">A collection of zero or more typed entity objects or a projection of complex types in the conceptual model.</span></span>  
  
-   <span data-ttu-id="df243-105">Tipos CLR admitidos por el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="df243-105">CLR types supported by the conceptual model.</span></span>  
  
-   <span data-ttu-id="df243-106">Colecciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="df243-106">Inline collections.</span></span>  
  
-   <span data-ttu-id="df243-107">Tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="df243-107">Anonymous types.</span></span>  
  
 <span data-ttu-id="df243-108">Cuando la consulta se ha ejecutado en el origen de datos, los resultados se materializan en tipos de CLR y se devuelven al cliente.</span><span class="sxs-lookup"><span data-stu-id="df243-108">When the query has executed against the data source, the results are materialized into CLR types and returned to the client.</span></span> <span data-ttu-id="df243-109">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] realiza la materialización de todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="df243-109">All object materialization is performed by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="df243-110">Los errores derivados de la imposibilidad de realizar asignaciones entre [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] y CLR hará que se produzcan excepciones durante la materialización de los objetos.</span><span class="sxs-lookup"><span data-stu-id="df243-110">Any errors that result from an inability to map between the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="df243-111">Si la ejecución de la consulta devuelve tipos primitivos del modelo conceptual, los resultados están compuestos de tipos de CLR que son independientes y están desconectados de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df243-111">If the query execution returns primitive conceptual model types, the results consist of CLR types that are stand-alone and disconnected from the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="df243-112">Sin embargo, si la consulta devuelve una colección de objetos entidad con tipo, representada por <xref:System.Data.Objects.ObjectQuery%601>, dichos tipos son sometidos a seguimiento por el contexto del objeto.</span><span class="sxs-lookup"><span data-stu-id="df243-112">However, if the query returns a collection of typed entity objects, represented by <xref:System.Data.Objects.ObjectQuery%601>, those types are tracked by the object context.</span></span> <span data-ttu-id="df243-113">Todos los comportamientos de objeto (por ejemplo, colecciones de elementos primarios y secundarios, seguimiento de cambios, polimorfismo etc.) son como se define en el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df243-113">All object behavior (such as child/parent collections, change tracking, polymorphism, and so on) are as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="df243-114">Esta funcionalidad se puede utilizar en su capacidad, como se define en [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df243-114">This functionality can be used in its capacity, as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="df243-115">Para obtener más información, consulte [trabajar con objetos](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="df243-115">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="df243-116">Los tipos struct devueltos en las consultas (como tipos anónimos y tipos complejos que aceptan valores NULL) pueden ser de valor `null`.</span><span class="sxs-lookup"><span data-stu-id="df243-116">Struct types returned from queries (such as anonymous types and nullable complex types) can be of `null` value.</span></span> <span data-ttu-id="df243-117">Una propiedad de <xref:System.Data.Objects.DataClasses.EntityCollection%601> de una entidad devuelta también puede ser de valor `null`.</span><span class="sxs-lookup"><span data-stu-id="df243-117">An <xref:System.Data.Objects.DataClasses.EntityCollection%601> property of a returned entity can also be of `null` value.</span></span> <span data-ttu-id="df243-118">Esto puede deberse a la proyección de la propiedad de colección de una entidad que es de valor `null`, como la llamada a <xref:System.Linq.Queryable.FirstOrDefault%2A> en una <xref:System.Data.Objects.ObjectQuery%601> que no tiene elementos.</span><span class="sxs-lookup"><span data-stu-id="df243-118">This can result from projecting the collection property of an entity that is of `null` value, such as calling <xref:System.Linq.Queryable.FirstOrDefault%2A> on an <xref:System.Data.Objects.ObjectQuery%601> that has no elements.</span></span>  
  
 <span data-ttu-id="df243-119">En determinadas situaciones, puede que parezca que una consulta genera un resultado materializado durante su ejecución, pero la consulta se ejecutará en el servidor y el objeto entidad nunca se materializará en CLR.</span><span class="sxs-lookup"><span data-stu-id="df243-119">In certain situations, a query might appear to generate a materialized result during its execution, but the query will be executed on the server and the entity object will never be materialized in the CLR.</span></span> <span data-ttu-id="df243-120">Esto puede producir problemas si se está dependiendo de los efectos secundarios de la materialización de los objetos.</span><span class="sxs-lookup"><span data-stu-id="df243-120">This can cause problems if you are depending on side effects of object materialization.</span></span>  
  
 <span data-ttu-id="df243-121">El ejemplo siguiente contiene una clase personalizada, `MyContact`, con una propiedad `LastName`.</span><span class="sxs-lookup"><span data-stu-id="df243-121">The following example contains a custom class, `MyContact`, with a `LastName` property.</span></span> <span data-ttu-id="df243-122">Cuando se establece la propiedad `LastName`, se incrementa una variable `count`.</span><span class="sxs-lookup"><span data-stu-id="df243-122">When the `LastName` property is set, a `count` variable is incremented.</span></span> <span data-ttu-id="df243-123">Si ejecuta las dos consultas siguientes, la primera consulta incrementará `count` mientras que la segunda consulta no lo hará.</span><span class="sxs-lookup"><span data-stu-id="df243-123">If you execute the two following queries, the first query will increment `count` while the second query will not.</span></span> <span data-ttu-id="df243-124">Esto de debe a que en la segunda consulta la propiedad `LastName` se proyecta desde los resultados y nunca se crea la clase `MyContact`, porque no se requiere ejecutar la consulta en el almacén.</span><span class="sxs-lookup"><span data-stu-id="df243-124">This is because in the second query the `LastName` property is projected from the results and the `MyContact` class is never created, because it is not required to execute the query on the store.</span></span>  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
