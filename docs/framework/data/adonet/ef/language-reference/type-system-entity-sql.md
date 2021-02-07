---
description: 'Más información acerca de: sistema de tipos (Entity SQL)'
title: Sistema de tipos (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: 8d0d50a2c82a309a6a496642836aabe23b6bb9bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673393"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="d4094-103">Sistema de tipos (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d4094-103">Type System (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="d4094-104">admite varios tipos:</span><span class="sxs-lookup"><span data-stu-id="d4094-104">supports a number of types:</span></span>  
  
- <span data-ttu-id="d4094-105">Tipos primitivos (simples), como `Int32` y `String.`.</span><span class="sxs-lookup"><span data-stu-id="d4094-105">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="d4094-106">Tipos nominales que se definen en el esquema, como <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> y <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="d4094-106">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="d4094-107">Tipos anónimos que no se definen explícitamente en el esquema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> y <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="d4094-107">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="d4094-108">En esta sección se describen los tipos anónimos que no se definen explícitamente en el esquema, pero que son compatibles con Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="d4094-108">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="d4094-109">Para obtener información sobre los tipos primitivos y los tipos nominales, vea [tipos de modelos conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="d4094-109">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="d4094-110">Filas</span><span class="sxs-lookup"><span data-stu-id="d4094-110">Rows</span></span>  

 <span data-ttu-id="d4094-111">La estructura de una fila depende de la secuencia de miembros con nombre y con tipo de que consta la misma.</span><span class="sxs-lookup"><span data-stu-id="d4094-111">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="d4094-112">Un tipo de fila no tiene ninguna identidad y no se puede heredar.</span><span class="sxs-lookup"><span data-stu-id="d4094-112">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="d4094-113">Las instancias del mismo tipo de fila son equivalentes si los miembros son respectivamente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d4094-113">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="d4094-114">Las filas no tienen ningún otro comportamiento más allá de su equivalencia estructural y no tienen ningún equivalente en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d4094-114">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="d4094-115">Las consultas pueden producir estructuras que contienen filas o colecciones de filas.</span><span class="sxs-lookup"><span data-stu-id="d4094-115">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="d4094-116">El enlace de API entre las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y el lenguaje del host define el modo en que las filas se materializan en la consulta que generó el resultado.</span><span class="sxs-lookup"><span data-stu-id="d4094-116">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="d4094-117">Para obtener información sobre cómo construir una instancia de fila, vea [construir tipos](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d4094-117">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="d4094-118">Colecciones</span><span class="sxs-lookup"><span data-stu-id="d4094-118">Collections</span></span>  

 <span data-ttu-id="d4094-119">Los tipos de colección representan cero o más instancias de otros objetos.</span><span class="sxs-lookup"><span data-stu-id="d4094-119">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="d4094-120">Para obtener información sobre cómo construir una colección, vea [construir tipos](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d4094-120">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="d4094-121">Referencias</span><span class="sxs-lookup"><span data-stu-id="d4094-121">References</span></span>  

 <span data-ttu-id="d4094-122">Una referencia es un puntero lógico a una entidad concreta en un conjunto de entidades específico.</span><span class="sxs-lookup"><span data-stu-id="d4094-122">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="d4094-123">admite los operadores siguientes para construir, anular la construcción y navegar a través de referencias.</span><span class="sxs-lookup"><span data-stu-id="d4094-123">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="d4094-124">CLI</span><span class="sxs-lookup"><span data-stu-id="d4094-124">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="d4094-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="d4094-125">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="d4094-126">KEY</span><span class="sxs-lookup"><span data-stu-id="d4094-126">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="d4094-127">DEREF</span><span class="sxs-lookup"><span data-stu-id="d4094-127">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="d4094-128">Puede navegar por una referencia utilizando el operador de acceso a miembros (`.`) (punto).</span><span class="sxs-lookup"><span data-stu-id="d4094-128">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="d4094-129">El fragmento de código siguiente extrae la propiedad Id (de Order) navegando por la propiedad r (referencia).</span><span class="sxs-lookup"><span data-stu-id="d4094-129">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 <span data-ttu-id="d4094-130">Si el valor de referencia es NULL o si el destino de la referencia no existe, el resultado es NULL.</span><span class="sxs-lookup"><span data-stu-id="d4094-130">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4094-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4094-131">See also</span></span>

- [<span data-ttu-id="d4094-132">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d4094-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="d4094-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d4094-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d4094-134">CAST</span><span class="sxs-lookup"><span data-stu-id="d4094-134">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="d4094-135">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="d4094-135">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
