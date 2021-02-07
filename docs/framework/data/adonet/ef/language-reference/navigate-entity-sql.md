---
description: 'Más información acerca de: navegar (Entity SQL)'
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 7fa39a988429fe0a658b01078d2369ad4767f4a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696508"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="72688-103">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="72688-103">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="72688-104">Navega por la relación establecida entre entidades.</span><span class="sxs-lookup"><span data-stu-id="72688-104">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="72688-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72688-105">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="72688-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="72688-106">Arguments</span></span>

<span data-ttu-id="72688-107">`instance-expression` Instancia de una entidad.</span><span class="sxs-lookup"><span data-stu-id="72688-107">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="72688-108">`relationship-type` El nombre de tipo de la relación, del archivo de lenguaje de definición de esquemas conceptuales (CSDL).</span><span class="sxs-lookup"><span data-stu-id="72688-108">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="72688-109">`relationship-type`Se califica como \<namespace> . \<relationship type name> .</span><span class="sxs-lookup"><span data-stu-id="72688-109">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="72688-110">`to` Final de la relación.</span><span class="sxs-lookup"><span data-stu-id="72688-110">`to` The end of the relationship.</span></span>

<span data-ttu-id="72688-111">`from` Principio de la relación.</span><span class="sxs-lookup"><span data-stu-id="72688-111">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="72688-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72688-112">Return Value</span></span>

<span data-ttu-id="72688-113">Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="72688-113">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="72688-114">Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="72688-114">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="72688-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72688-115">Remarks</span></span>

<span data-ttu-id="72688-116">Las relaciones son construcciones de primera clase en el Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="72688-116">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="72688-117">Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo (entidad) al otro.</span><span class="sxs-lookup"><span data-stu-id="72688-117">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="72688-118">`from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.</span><span class="sxs-lookup"><span data-stu-id="72688-118">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="72688-119">NAVIGATE es válido en espacios O y C.</span><span class="sxs-lookup"><span data-stu-id="72688-119">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="72688-120">La forma general de una estructura de navegación es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="72688-120">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="72688-121">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="72688-121">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="72688-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72688-122">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="72688-123">Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` (cliente) y `from-end` (pedido) de la relación.</span><span class="sxs-lookup"><span data-stu-id="72688-123">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="72688-124">Si OrderCustomer era una relación de n:1, el tipo de resultado de la expresión Navigate es Ref \<Customer> .</span><span class="sxs-lookup"><span data-stu-id="72688-124">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="72688-125">Lo forma más simple de esta expresión es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="72688-125">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="72688-126">Del mismo modo, en una consulta de la forma siguiente, la expresión Navigate produciría una colección<referencia \<Order>>.</span><span class="sxs-lookup"><span data-stu-id="72688-126">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="72688-127">El valor de instance-expression debe ser de tipo entidad/referencia.</span><span class="sxs-lookup"><span data-stu-id="72688-127">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="72688-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72688-128">Example</span></span>

<span data-ttu-id="72688-129">La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="72688-129">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="72688-130">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="72688-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="72688-131">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="72688-131">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="72688-132">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="72688-132">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="72688-133">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="72688-133">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="72688-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="72688-134">See also</span></span>

- [<span data-ttu-id="72688-135">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="72688-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="72688-136">Cómo navegar por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="72688-136">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
