---
title: "Ejecución remota o ejecución local"
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
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c402fad49526729ba09d8f4b86a5b022ca4a12cb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="5ebc2-102">Ejecución remota o ejecución local</span><span class="sxs-lookup"><span data-stu-id="5ebc2-102">Remote vs. Local Execution</span></span>
<span data-ttu-id="5ebc2-103">Puede decidir ejecutar las consultas de manera remota (es decir, el motor de base de datos ejecuta la consulta en la base de datos) o localmente ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ejecuta la consulta en una memoria caché local).</span><span class="sxs-lookup"><span data-stu-id="5ebc2-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="5ebc2-104">Ejecución remota</span><span class="sxs-lookup"><span data-stu-id="5ebc2-104">Remote Execution</span></span>  
 <span data-ttu-id="5ebc2-105">Considere la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="5ebc2-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="5ebc2-106">Si su base de datos tuviese miles de filas de pedidos, no desearía recuperarlos todos para procesar un subconjunto pequeño.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="5ebc2-107">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la clase <xref:System.Data.Linq.EntitySet%601> implementa la interfaz <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="5ebc2-108">Este enfoque garantiza que ese tipo de consultas se puedan ejecutar de manera remota.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="5ebc2-109">De esta técnica se derivan dos ventajas principales:</span><span class="sxs-lookup"><span data-stu-id="5ebc2-109">Two major benefits flow from this technique:</span></span>  
  
-   <span data-ttu-id="5ebc2-110">No se recuperan datos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-110">Unnecessary data is not retrieved.</span></span>  
  
-   <span data-ttu-id="5ebc2-111">Una consulta ejecutada por el motor de base de datos suele ser más eficaz debido a los índices de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="5ebc2-112">ejecución local</span><span class="sxs-lookup"><span data-stu-id="5ebc2-112">Local Execution</span></span>  
 <span data-ttu-id="5ebc2-113">En otras situaciones, podría desear tener el conjunto completo de entidades relacionadas en la memoria caché local.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="5ebc2-114">Para este propósito, <xref:System.Data.Linq.EntitySet%601> proporciona el método <xref:System.Data.Linq.EntitySet%601.Load%2A> para cargar explícitamente todos los miembros de <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="5ebc2-115">Si <xref:System.Data.Linq.EntitySet%601> ya está cargado, las consultas posteriores se ejecutan localmente.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="5ebc2-116">Este enfoque ayuda en dos sentidos:</span><span class="sxs-lookup"><span data-stu-id="5ebc2-116">This approach helps in two ways:</span></span>  
  
-   <span data-ttu-id="5ebc2-117">Si se debe utilizar el conjunto completo localmente o varias veces, puede evitar las consultas remotas y la latencia asociada a las mismas.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
-   <span data-ttu-id="5ebc2-118">La entidad se puede serializar como una entidad completa.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="5ebc2-119">El fragmento de código siguiente muestra cómo se puede obtener la ejecución local:</span><span class="sxs-lookup"><span data-stu-id="5ebc2-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="5ebc2-120">Comparación</span><span class="sxs-lookup"><span data-stu-id="5ebc2-120">Comparison</span></span>  
 <span data-ttu-id="5ebc2-121">Estas dos funciones proporcionan una combinación eficaz de opciones: ejecución remota para las colecciones grandes y ejecución local para las colecciones pequeñas o si se necesita la colección completa.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="5ebc2-122">La ejecución remota se implementa a través de <xref:System.Linq.IQueryable> y la ejecución local en una colección <xref:System.Collections.Generic.IEnumerable%601> en memoria.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="5ebc2-123">Para forzar la ejecución local (es decir, <xref:System.Collections.Generic.IEnumerable%601>), consulte [convertir un tipo en una interfaz IEnumerable genérica](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="5ebc2-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="5ebc2-124">Consultas en conjuntos no ordenados</span><span class="sxs-lookup"><span data-stu-id="5ebc2-124">Queries Against Unordered Sets</span></span>  
 <span data-ttu-id="5ebc2-125">Tenga en cuenta la importante diferencia entre una colección local que implementa <xref:System.Collections.Generic.List%601> y una colección que proporciona consultas remotas ejecutadas en *desordenados conjuntos* en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <span data-ttu-id="5ebc2-126">Los métodos <xref:System.Collections.Generic.List%601>, como los que utilizan valores de índice, requieren semántica de lista, que normalmente no se puede obtener a través de una consulta remota en un conjunto no ordenado.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-126"><xref:System.Collections.Generic.List%601> methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="5ebc2-127">Por esta razón, tales métodos cargan implícitamente <xref:System.Data.Linq.EntitySet%601> para permitir la ejecución local.</span><span class="sxs-lookup"><span data-stu-id="5ebc2-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebc2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebc2-128">See Also</span></span>  
 [<span data-ttu-id="5ebc2-129">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="5ebc2-129">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
