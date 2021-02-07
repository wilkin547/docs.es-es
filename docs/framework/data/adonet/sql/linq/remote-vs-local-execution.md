---
description: 'Más información sobre: ejecución remota frente a ejecución local'
title: Ejecución remota o ejecución local
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: ea4d85faedd4a299da292029e64d77132e1a65a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695219"
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="2f537-103">Ejecución remota o ejecución local</span><span class="sxs-lookup"><span data-stu-id="2f537-103">Remote vs. Local Execution</span></span>

<span data-ttu-id="2f537-104">Puede decidir ejecutar las consultas de manera remota (es decir, el motor de base de datos ejecuta la consulta en la base de datos) o localmente ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ejecuta la consulta en una memoria caché local).</span><span class="sxs-lookup"><span data-stu-id="2f537-104">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="2f537-105">Ejecución remota</span><span class="sxs-lookup"><span data-stu-id="2f537-105">Remote Execution</span></span>  

 <span data-ttu-id="2f537-106">Considere la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f537-106">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="2f537-107">Si su base de datos tuviese miles de filas de pedidos, no desearía recuperarlos todos para procesar un subconjunto pequeño.</span><span class="sxs-lookup"><span data-stu-id="2f537-107">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="2f537-108">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la clase <xref:System.Data.Linq.EntitySet%601> implementa la interfaz <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="2f537-108">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="2f537-109">Este enfoque garantiza que ese tipo de consultas se puedan ejecutar de manera remota.</span><span class="sxs-lookup"><span data-stu-id="2f537-109">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="2f537-110">De esta técnica se derivan dos ventajas principales:</span><span class="sxs-lookup"><span data-stu-id="2f537-110">Two major benefits flow from this technique:</span></span>  
  
- <span data-ttu-id="2f537-111">No se recuperan datos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="2f537-111">Unnecessary data is not retrieved.</span></span>  
  
- <span data-ttu-id="2f537-112">Una consulta ejecutada por el motor de base de datos suele ser más eficaz debido a los índices de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f537-112">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="2f537-113">Ejecución local</span><span class="sxs-lookup"><span data-stu-id="2f537-113">Local Execution</span></span>  

 <span data-ttu-id="2f537-114">En otras situaciones, podría desear tener el conjunto completo de entidades relacionadas en la memoria caché local.</span><span class="sxs-lookup"><span data-stu-id="2f537-114">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="2f537-115">Para este propósito, <xref:System.Data.Linq.EntitySet%601> proporciona el método <xref:System.Data.Linq.EntitySet%601.Load%2A> para cargar explícitamente todos los miembros de <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="2f537-115">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="2f537-116">Si <xref:System.Data.Linq.EntitySet%601> ya está cargado, las consultas posteriores se ejecutan localmente.</span><span class="sxs-lookup"><span data-stu-id="2f537-116">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="2f537-117">Este enfoque ayuda en dos sentidos:</span><span class="sxs-lookup"><span data-stu-id="2f537-117">This approach helps in two ways:</span></span>  
  
- <span data-ttu-id="2f537-118">Si se debe utilizar el conjunto completo localmente o varias veces, puede evitar las consultas remotas y la latencia asociada a las mismas.</span><span class="sxs-lookup"><span data-stu-id="2f537-118">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
- <span data-ttu-id="2f537-119">La entidad se puede serializar como una entidad completa.</span><span class="sxs-lookup"><span data-stu-id="2f537-119">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="2f537-120">El fragmento de código siguiente muestra cómo se puede obtener la ejecución local:</span><span class="sxs-lookup"><span data-stu-id="2f537-120">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="2f537-121">De comparación</span><span class="sxs-lookup"><span data-stu-id="2f537-121">Comparison</span></span>  

 <span data-ttu-id="2f537-122">Estas dos funciones proporcionan una combinación eficaz de opciones: ejecución remota para las colecciones grandes y ejecución local para las colecciones pequeñas o si se necesita la colección completa.</span><span class="sxs-lookup"><span data-stu-id="2f537-122">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="2f537-123">La ejecución remota se implementa a través de <xref:System.Linq.IQueryable> y la ejecución local en una colección <xref:System.Collections.Generic.IEnumerable%601> en memoria.</span><span class="sxs-lookup"><span data-stu-id="2f537-123">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="2f537-124">Para forzar la ejecución local (es decir, <xref:System.Collections.Generic.IEnumerable%601> ), vea [convertir un tipo en un IEnumerable genérico](convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="2f537-124">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="2f537-125">Consultas en conjuntos no ordenados</span><span class="sxs-lookup"><span data-stu-id="2f537-125">Queries Against Unordered Sets</span></span>  

 <span data-ttu-id="2f537-126">Tenga en cuenta la diferencia importante entre una colección local que implementa <xref:System.Collections.Generic.List%601> y una colección que proporciona consultas remotas ejecutadas en *conjuntos no ordenados* en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="2f537-126">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <span data-ttu-id="2f537-127">Los métodos <xref:System.Collections.Generic.List%601>, como los que utilizan valores de índice, requieren semántica de lista, que normalmente no se puede obtener a través de una consulta remota en un conjunto no ordenado.</span><span class="sxs-lookup"><span data-stu-id="2f537-127"><xref:System.Collections.Generic.List%601> methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="2f537-128">Por esta razón, tales métodos cargan implícitamente <xref:System.Data.Linq.EntitySet%601> para permitir la ejecución local.</span><span class="sxs-lookup"><span data-stu-id="2f537-128">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f537-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f537-129">See also</span></span>

- [<span data-ttu-id="2f537-130">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="2f537-130">Query Concepts</span></span>](query-concepts.md)
