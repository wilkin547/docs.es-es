---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: e7c6cf6b67dc3af29f7ca8fb22af419235a9b833
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879767"
---
# <a name="top-entity-sql"></a><span data-ttu-id="b1c43-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b1c43-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="b1c43-103">La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="b1c43-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="b1c43-104">La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1c43-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1c43-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1c43-105">Syntax</span></span>

```
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="b1c43-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b1c43-106">Arguments</span></span>

<span data-ttu-id="b1c43-107">`n` La expresión numérica que especifica el número de filas que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="b1c43-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="b1c43-108">`n` puede ser un literal numérico único o un parámetro único.</span><span class="sxs-lookup"><span data-stu-id="b1c43-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1c43-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1c43-109">Remarks</span></span>

<span data-ttu-id="b1c43-110">La expresión TOP debe ser un literal numérico único o un parámetro único.</span><span class="sxs-lookup"><span data-stu-id="b1c43-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="b1c43-111">Si se utiliza un literal constante, el tipo de literal debe poderse promocionar implícitamente a Edm.Int64 (byte, int16, int32 o int64, o cualquier tipo de proveedor que se asigna a un tipo que se puede promocionar a Edm.Int64) y su valor debe ser igual o mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="b1c43-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="b1c43-112">De lo contrario, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="b1c43-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="b1c43-113">Si un parámetro se utiliza como una expresión, el tipo de parámetro también debe poderse promocionar implícitamente a Edm.Int64, pero no habrá ninguna validación del valor de parámetro real durante la compilación porque los valores de parámetro se enlazan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b1c43-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="b1c43-114">El siguiente es un ejemplo de expresión TOP constante:</span><span class="sxs-lookup"><span data-stu-id="b1c43-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="b1c43-115">El siguiente es un ejemplo de expresión TOP con parámetros:</span><span class="sxs-lookup"><span data-stu-id="b1c43-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="b1c43-116">TOP es no determinista a menos que la consulta esté ordenada.</span><span class="sxs-lookup"><span data-stu-id="b1c43-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="b1c43-117">Si necesita un resultado determinista, utilice las subcláusulas [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) en la cláusula [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="b1c43-117">If you require a deterministic result, use the [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses in the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="b1c43-118">TOP y SKIP/LIMIT se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="b1c43-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="b1c43-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1c43-119">Example</span></span>

<span data-ttu-id="b1c43-120">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa la cláusula TOP para especificar la fila superior que se va a devolver del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1c43-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="b1c43-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b1c43-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b1c43-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b1c43-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="b1c43-123">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b1c43-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="b1c43-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b1c43-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a><span data-ttu-id="b1c43-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1c43-125">See also</span></span>

- [<span data-ttu-id="b1c43-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="b1c43-126">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [<span data-ttu-id="b1c43-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="b1c43-127">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)
- [<span data-ttu-id="b1c43-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="b1c43-128">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)
- [<span data-ttu-id="b1c43-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="b1c43-129">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [<span data-ttu-id="b1c43-130">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b1c43-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
