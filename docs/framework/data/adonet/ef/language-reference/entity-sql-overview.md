---
title: "Información general sobre Entity SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f77e3a5d0073cb13d1904f802c4d6760fc52caa9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="entity-sql-overview"></a><span data-ttu-id="a79ac-102">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a79ac-103"> es un lenguaje parecido a SQL que permite consultar los modelos conceptuales en [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a79ac-103"> is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="a79ac-104">Los modelos conceptuales representan datos como entidades y relaciones, y [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite consultar estas entidades y relaciones en un formato que sea familiar para aquellos que han trabajado con SQL.</span><span class="sxs-lookup"><span data-stu-id="a79ac-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="a79ac-105">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] trabaja con proveedores de datos específicos del almacenamiento para traducir el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] genérico en consultas específicas del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a79ac-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="a79ac-106">El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="a79ac-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="a79ac-107">Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a79ac-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a79ac-108"><xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM.</span><span class="sxs-lookup"><span data-stu-id="a79ac-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="a79ac-109">Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="a79ac-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="a79ac-110">Además del proveedor EntityClient, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] permite utilizar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para ejecutar consultas contra un modelo conceptual y devolver los datos como objetos CLR fuertemente tipados, los cuales son instancias de tipos de entidades.</span><span class="sxs-lookup"><span data-stu-id="a79ac-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="a79ac-111">Para obtener más información, consulte [trabajar con objetos](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a79ac-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="a79ac-112">En esta sección se proporciona información conceptual de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a79ac-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a79ac-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a79ac-113">In This Section</span></span>  
 [<span data-ttu-id="a79ac-114">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="a79ac-115">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="a79ac-116">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="a79ac-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-117">Definiciones de tipo</span><span class="sxs-lookup"><span data-stu-id="a79ac-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-118">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="a79ac-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-119">Almacenamiento en caché del plan de consulta</span><span class="sxs-lookup"><span data-stu-id="a79ac-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-120">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a79ac-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-121">Identificadores</span><span class="sxs-lookup"><span data-stu-id="a79ac-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-122">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a79ac-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-123">Variables</span><span class="sxs-lookup"><span data-stu-id="a79ac-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-124">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="a79ac-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-125">Literales</span><span class="sxs-lookup"><span data-stu-id="a79ac-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-126">Literales NULL e inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="a79ac-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-127">Juego de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="a79ac-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-128">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="a79ac-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-129">Funciones</span><span class="sxs-lookup"><span data-stu-id="a79ac-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-130">Precedencia de operadores</span><span class="sxs-lookup"><span data-stu-id="a79ac-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-131">Paginación</span><span class="sxs-lookup"><span data-stu-id="a79ac-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-132">Semántica de comparación</span><span class="sxs-lookup"><span data-stu-id="a79ac-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="a79ac-133">Creación de consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="a79ac-134">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="a79ac-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="a79ac-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a79ac-135">See Also</span></span>  
 [<span data-ttu-id="a79ac-136">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="a79ac-137">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a79ac-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="a79ac-138">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="a79ac-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
