---
description: 'Más información acerca de: CREATEREF (Entity SQL)'
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: c4e96f97bd3587e50b34f6cbd63c5ae9ed8d94ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724783"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="7f1ca-103">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7f1ca-103">CREATEREF (Entity SQL)</span></span>

<span data-ttu-id="7f1ca-104">Crea referencias a una entidad en un elemento entityset.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-104">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f1ca-105">Syntax</span></span>  
  
```sql  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f1ca-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7f1ca-106">Arguments</span></span>  

 `entityset_identifier`  
 <span data-ttu-id="7f1ca-107">Identificador de entityset, no un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-107">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="7f1ca-108">Expresión escrita por fila que corresponde a las propiedades de clave del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-108">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f1ca-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f1ca-109">Remarks</span></span>  

 <span data-ttu-id="7f1ca-110">`row_typed_expression` debe ser estructuralmente equivalentes al tipo de clave de la entidad.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-110">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="7f1ca-111">Es decir, debe tener el mismo número y los mismos tipos de campos en el mismo orden que las claves de entidad.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-111">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="7f1ca-112">En el ejemplo siguiente, Orders y BadOrders son ambos elementos entityset de tipo Order y se supone que Id es la propiedad de clave única de Order.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-112">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="7f1ca-113">El ejemplo muestra cómo se puede generar una referencia a una entidad en BadOrders.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-113">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="7f1ca-114">Observe que la referencia puede estar pendiente.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-114">Note that the reference may be dangling.</span></span>  <span data-ttu-id="7f1ca-115">Es decir, la referencia puede no identificar realmente una entidad concreta.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-115">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="7f1ca-116">En esos casos, una operación `DEREF` en esa referencia devuelve un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-116">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```sql  
SELECT CreateRef(LOB.BadOrders, row(o.Id))
FROM LOB.Orders AS o
```  
  
## <a name="example"></a><span data-ttu-id="7f1ca-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f1ca-117">Example</span></span>  

 <span data-ttu-id="7f1ca-118">La consulta de Entity SQL siguiente utiliza el operador CREATEREF para crear las referencias a una entidad en un conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-118">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="7f1ca-119">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="7f1ca-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7f1ca-120">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7f1ca-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7f1ca-121">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7f1ca-121">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7f1ca-122">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7f1ca-122">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CREATEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="7f1ca-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f1ca-123">See also</span></span>

- [<span data-ttu-id="7f1ca-124">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7f1ca-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="7f1ca-125">DEREF</span><span class="sxs-lookup"><span data-stu-id="7f1ca-125">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="7f1ca-126">KEY</span><span class="sxs-lookup"><span data-stu-id="7f1ca-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="7f1ca-127">CLI</span><span class="sxs-lookup"><span data-stu-id="7f1ca-127">REF</span></span>](ref-entity-sql.md)
