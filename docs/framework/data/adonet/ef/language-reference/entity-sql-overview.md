---
title: Información general sobre Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 8f40a34f361669d2b8d89b63b3187cae6bf705d2
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854489"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="e15d6-102">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e15d6-103">es un lenguaje similar a SQL que permite consultar modelos conceptuales en el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e15d6-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="e15d6-104">Los modelos conceptuales representan los datos como entidades y [!INCLUDE[esql](../../../../../../includes/esql-md.md)] relaciones, y permiten consultar esas entidades y relaciones en un formato conocido para los usuarios que han usado SQL.</span><span class="sxs-lookup"><span data-stu-id="e15d6-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
      
 <span data-ttu-id="e15d6-105">El Entity Framework funciona con proveedores de datos específicos del almacenamiento para traducir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] los genéricos en consultas específicas del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e15d6-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="e15d6-106">El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="e15d6-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="e15d6-107">Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e15d6-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e15d6-108"><xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM.</span><span class="sxs-lookup"><span data-stu-id="e15d6-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="e15d6-109">Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="e15d6-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="e15d6-110">Además del proveedor de EntityClient, el Entity Framework permite utilizar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para ejecutar consultas en un modelo conceptual y devolver los datos como objetos CLR fuertemente tipados que son instancias de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="e15d6-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="e15d6-111">Para obtener más información, vea [trabajar con objetos](../working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e15d6-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="e15d6-112">En esta sección se proporciona información conceptual de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e15d6-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e15d6-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e15d6-113">In This Section</span></span>  
 [<span data-ttu-id="e15d6-114">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="e15d6-115">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="e15d6-116">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="e15d6-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-117">Definiciones de tipo</span><span class="sxs-lookup"><span data-stu-id="e15d6-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-118">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="e15d6-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-119">Almacenamiento en caché del plan de consulta</span><span class="sxs-lookup"><span data-stu-id="e15d6-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-120">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="e15d6-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-121">Identificadores</span><span class="sxs-lookup"><span data-stu-id="e15d6-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-122">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e15d6-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-123">Variables</span><span class="sxs-lookup"><span data-stu-id="e15d6-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-124">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="e15d6-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-125">Literales</span><span class="sxs-lookup"><span data-stu-id="e15d6-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-126">Literales NULL e inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="e15d6-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-127">Juego de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="e15d6-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-128">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="e15d6-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-129">Funciones</span><span class="sxs-lookup"><span data-stu-id="e15d6-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-130">Precedencia de operadores</span><span class="sxs-lookup"><span data-stu-id="e15d6-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-131">Paginación</span><span class="sxs-lookup"><span data-stu-id="e15d6-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-132">Semántica de comparación</span><span class="sxs-lookup"><span data-stu-id="e15d6-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="e15d6-133">Creación de consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="e15d6-134">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="e15d6-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="e15d6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e15d6-135">See also</span></span>

- [<span data-ttu-id="e15d6-136">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e15d6-137">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e15d6-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="e15d6-138">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="e15d6-138">CSDL, SSDL, and MSL Specifications</span></span>](csdl-ssdl-and-msl-specifications.md)
