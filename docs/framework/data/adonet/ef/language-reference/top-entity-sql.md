---
description: 'Más información acerca de: TOP (Entity SQL)'
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 51e4ce53cff4b47f6f57b6b856ccb09b38e639cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673445"
---
# <a name="top-entity-sql"></a><span data-ttu-id="89fc9-103">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="89fc9-103">TOP (Entity SQL)</span></span>

<span data-ttu-id="89fc9-104">La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="89fc9-104">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="89fc9-105">La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="89fc9-105">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="89fc9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89fc9-106">Syntax</span></span>

```sql
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="89fc9-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89fc9-107">Arguments</span></span>

<span data-ttu-id="89fc9-108">`n` Expresión numérica que especifica el número de filas que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="89fc9-108">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="89fc9-109">`n` puede ser un literal numérico único o un parámetro único.</span><span class="sxs-lookup"><span data-stu-id="89fc9-109">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="89fc9-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89fc9-110">Remarks</span></span>

<span data-ttu-id="89fc9-111">La expresión TOP debe ser un literal numérico único o un parámetro único.</span><span class="sxs-lookup"><span data-stu-id="89fc9-111">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="89fc9-112">Si se utiliza un literal constante, el tipo de literal debe poderse promocionar implícitamente a Edm.Int64 (byte, int16, int32 o int64, o cualquier tipo de proveedor que se asigna a un tipo que se puede promocionar a Edm.Int64) y su valor debe ser igual o mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="89fc9-112">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="89fc9-113">De lo contrario, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="89fc9-113">Otherwise an exception will be raised.</span></span> <span data-ttu-id="89fc9-114">Si un parámetro se utiliza como una expresión, el tipo de parámetro también debe poderse promocionar implícitamente a Edm.Int64, pero no habrá ninguna validación del valor de parámetro real durante la compilación porque los valores de parámetro se enlazan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="89fc9-114">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="89fc9-115">El siguiente es un ejemplo de expresión TOP constante:</span><span class="sxs-lookup"><span data-stu-id="89fc9-115">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="89fc9-116">El siguiente es un ejemplo de expresión TOP parametrizada:</span><span class="sxs-lookup"><span data-stu-id="89fc9-116">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="89fc9-117">TOP es no determinista a menos que la consulta esté ordenada.</span><span class="sxs-lookup"><span data-stu-id="89fc9-117">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="89fc9-118">Si necesita un resultado determinista, utilice las subcláusulas [SKIP](skip-entity-sql.md) y [LIMIT](limit-entity-sql.md) en la cláusula [ORDER BY](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="89fc9-118">If you require a deterministic result, use the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="89fc9-119">TOP y SKIP/LIMIT se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="89fc9-119">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="89fc9-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89fc9-120">Example</span></span>

<span data-ttu-id="89fc9-121">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa la cláusula TOP para especificar la fila superior que se va a devolver del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="89fc9-121">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="89fc9-122">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="89fc9-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="89fc9-123">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="89fc9-123">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="89fc9-124">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="89fc9-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="89fc9-125">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="89fc9-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a><span data-ttu-id="89fc9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="89fc9-126">See also</span></span>

- [<span data-ttu-id="89fc9-127">SELECT</span><span class="sxs-lookup"><span data-stu-id="89fc9-127">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="89fc9-128">IRÁ</span><span class="sxs-lookup"><span data-stu-id="89fc9-128">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="89fc9-129">ILIMITADO</span><span class="sxs-lookup"><span data-stu-id="89fc9-129">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="89fc9-130">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="89fc9-130">ORDER BY</span></span>](order-by-entity-sql.md)
- [<span data-ttu-id="89fc9-131">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="89fc9-131">Entity SQL Reference</span></span>](entity-sql-reference.md)
