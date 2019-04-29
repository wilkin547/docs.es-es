---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 993c07b824d30c89773c5cfea90c7c194c6b3869
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760420"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="2ebe5-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2ebe5-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="2ebe5-103">Navega por la relación establecida entre entidades.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ebe5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ebe5-104">Syntax</span></span>

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="2ebe5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2ebe5-105">Arguments</span></span>

<span data-ttu-id="2ebe5-106">`instance-expression` Una instancia de una entidad.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="2ebe5-107">`relationship-type` El nombre de tipo de la relación desde el archivo conceptual schema definition language) (CSDL).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="2ebe5-108">El `relationship-type` se califica como \<espacio de nombres >.\< nombre de tipo de relación >.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="2ebe5-109">`to` El extremo de la relación.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="2ebe5-110">`from` El comienzo de la relación.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="2ebe5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ebe5-111">Return Value</span></span>

<span data-ttu-id="2ebe5-112">Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="2ebe5-113">Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ebe5-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ebe5-114">Remarks</span></span>

<span data-ttu-id="2ebe5-115">Las relaciones son estructuras de primera clase en [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="2ebe5-116">Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo (entidad) al otro.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="2ebe5-117">`from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="2ebe5-118">NAVIGATE es válido en espacios O y C.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="2ebe5-119">La forma general de una estructura de navegación es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ebe5-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="2ebe5-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="2ebe5-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="2ebe5-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2ebe5-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="2ebe5-122">Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` (cliente) y `from-end` (pedido) de la relación.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="2ebe5-123">Si OrderCustomer es una relación de n a 1, entonces el tipo de resultado de la expresión navigate es Ref\<Customer >.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="2ebe5-124">Lo forma más simple de esta expresión es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ebe5-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="2ebe5-125">De forma similar, en una consulta de la forma siguiente, la expresión navigate generaría una colección < Ref\<orden >>.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="2ebe5-126">El valor de instance-expression debe ser de tipo entidad/referencia.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="2ebe5-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ebe5-127">Example</span></span>

<span data-ttu-id="2ebe5-128">La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="2ebe5-129">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2ebe5-130">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2ebe5-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="2ebe5-131">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="2ebe5-132">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2ebe5-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a><span data-ttu-id="2ebe5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ebe5-133">See also</span></span>

- [<span data-ttu-id="2ebe5-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2ebe5-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="2ebe5-135">Cómo: Navegar por relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="2ebe5-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
