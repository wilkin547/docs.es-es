---
description: 'Más información sobre: información general sobre Entity SQL'
title: Información general sobre Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: eb337ff3894b24d787d829838c9cf12c934a823c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724614"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="b239d-103">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-103">Entity SQL Overview</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b239d-104">es un lenguaje similar a SQL que permite consultar modelos conceptuales en el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="b239d-104">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="b239d-105">Los modelos conceptuales representan los datos como entidades y relaciones, y [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permiten consultar esas entidades y relaciones en un formato conocido para los usuarios que han usado SQL.</span><span class="sxs-lookup"><span data-stu-id="b239d-105">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  

 <span data-ttu-id="b239d-106">El Entity Framework funciona con proveedores de datos específicos del almacenamiento para traducir los genéricos [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en consultas específicas del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b239d-106">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="b239d-107">El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="b239d-107">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="b239d-108">Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b239d-108">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="b239d-109"><xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM.</span><span class="sxs-lookup"><span data-stu-id="b239d-109">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="b239d-110">Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="b239d-110">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="b239d-111">Además del proveedor de EntityClient, el Entity Framework permite utilizar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para ejecutar consultas en un modelo conceptual y devolver los datos como objetos CLR fuertemente tipados que son instancias de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="b239d-111">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="b239d-112">Para obtener más información, vea [trabajar con objetos](../working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="b239d-112">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="b239d-113">En esta sección se proporciona información conceptual de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b239d-113">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b239d-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b239d-114">In This Section</span></span>  

 [<span data-ttu-id="b239d-115">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-115">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="b239d-116">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-116">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="b239d-117">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="b239d-117">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="b239d-118">Definiciones de tipos</span><span class="sxs-lookup"><span data-stu-id="b239d-118">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="b239d-119">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="b239d-119">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="b239d-120">Almacenamiento en caché del plan de consulta</span><span class="sxs-lookup"><span data-stu-id="b239d-120">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="b239d-121">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="b239d-121">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="b239d-122">Identificadores</span><span class="sxs-lookup"><span data-stu-id="b239d-122">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="b239d-123">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b239d-123">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="b239d-124">Variables</span><span class="sxs-lookup"><span data-stu-id="b239d-124">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="b239d-125">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="b239d-125">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="b239d-126">Literales</span><span class="sxs-lookup"><span data-stu-id="b239d-126">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="b239d-127">Literales NULL e inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="b239d-127">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="b239d-128">Juego de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="b239d-128">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="b239d-129">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="b239d-129">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="b239d-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="b239d-130">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="b239d-131">Prioridad de los operadores</span><span class="sxs-lookup"><span data-stu-id="b239d-131">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="b239d-132">Buscapersona</span><span class="sxs-lookup"><span data-stu-id="b239d-132">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="b239d-133">Semántica de comparación</span><span class="sxs-lookup"><span data-stu-id="b239d-133">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="b239d-134">Crear consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-134">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="b239d-135">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="b239d-135">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="b239d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b239d-136">See also</span></span>

- [<span data-ttu-id="b239d-137">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b239d-138">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b239d-138">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="b239d-139">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="b239d-139">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
