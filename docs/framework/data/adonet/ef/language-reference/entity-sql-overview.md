---
title: Información general sobre Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 100d616462cd76e1dde8fc855787ec3118842fc8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073475"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="83c89-102">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="83c89-103">es un lenguaje parecido a SQL que permite consultar los modelos conceptuales en [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83c89-103">is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="83c89-104">Los modelos conceptuales representan los datos como entidades y relaciones, y [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le permite consultar estas entidades y relaciones en un formato que resultará familiar a quienes ya hayan usado SQL.</span><span class="sxs-lookup"><span data-stu-id="83c89-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="83c89-105">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] trabaja con proveedores de datos específicos del almacenamiento para traducir el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] genérico en consultas específicas del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="83c89-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="83c89-106">El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="83c89-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="83c89-107">Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83c89-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="83c89-108"><xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM.</span><span class="sxs-lookup"><span data-stu-id="83c89-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="83c89-109">Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="83c89-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="83c89-110">Además del proveedor EntityClient, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] permite utilizar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para ejecutar consultas contra un modelo conceptual y devolver los datos como objetos CLR fuertemente tipados, los cuales son instancias de tipos de entidades.</span><span class="sxs-lookup"><span data-stu-id="83c89-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="83c89-111">Para obtener más información, consulte [trabajar con objetos](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="83c89-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="83c89-112">En esta sección se proporciona información conceptual de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83c89-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83c89-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="83c89-113">In This Section</span></span>  
 [<span data-ttu-id="83c89-114">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="83c89-115">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="83c89-116">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="83c89-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="83c89-117">Definiciones de tipo</span><span class="sxs-lookup"><span data-stu-id="83c89-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="83c89-118">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="83c89-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="83c89-119">Almacenamiento en caché del plan de consulta</span><span class="sxs-lookup"><span data-stu-id="83c89-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="83c89-120">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="83c89-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="83c89-121">Identificadores</span><span class="sxs-lookup"><span data-stu-id="83c89-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="83c89-122">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83c89-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="83c89-123">Variables</span><span class="sxs-lookup"><span data-stu-id="83c89-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="83c89-124">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="83c89-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="83c89-125">Literales</span><span class="sxs-lookup"><span data-stu-id="83c89-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="83c89-126">Literales NULL e inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="83c89-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="83c89-127">Juego de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="83c89-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="83c89-128">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="83c89-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="83c89-129">Funciones</span><span class="sxs-lookup"><span data-stu-id="83c89-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="83c89-130">Precedencia de operadores</span><span class="sxs-lookup"><span data-stu-id="83c89-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="83c89-131">Paginación</span><span class="sxs-lookup"><span data-stu-id="83c89-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="83c89-132">Semántica de comparación</span><span class="sxs-lookup"><span data-stu-id="83c89-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="83c89-133">Creación de consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="83c89-134">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="83c89-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="83c89-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c89-135">See also</span></span>

- [<span data-ttu-id="83c89-136">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="83c89-137">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c89-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="83c89-138">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="83c89-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
