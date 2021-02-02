---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: abdcce0e98c924052e07b9001d7dd92051c13747
ms.sourcegitcommit: 38999dc0ec4f7c4404de5ce0951b64c55997d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "99427038"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="fc035-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fc035-102">MULTISET (Entity SQL)</span></span>

<span data-ttu-id="fc035-103">Crea una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="fc035-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="fc035-104">Todos los valores en el constructor MULTISET deben ser de un tipo `T`compatible.</span><span class="sxs-lookup"><span data-stu-id="fc035-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="fc035-105">No se permiten los constructores MULTISET vacíos.</span><span class="sxs-lookup"><span data-stu-id="fc035-105">Empty multiset constructors are not allowed.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc035-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc035-106">Syntax</span></span>

```sql
MULTISET ( expression [{, expression }] )
-- or
{ expression [{, expression }] }
```

## <a name="arguments"></a><span data-ttu-id="fc035-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fc035-107">Arguments</span></span>

`expression`  
 <span data-ttu-id="fc035-108">Cualquier lista válida de valores.</span><span class="sxs-lookup"><span data-stu-id="fc035-108">Any valid list of values.</span></span>

## <a name="return-value"></a><span data-ttu-id="fc035-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc035-109">Return Value</span></span>

<span data-ttu-id="fc035-110">Colección de tipo MULTISET \<T> .</span><span class="sxs-lookup"><span data-stu-id="fc035-110">A collection of type MULTISET\<T>.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc035-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fc035-111">Remarks</span></span>

<!-- markdownlint-disable DOCSMD001 -->

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="fc035-112">proporciona tres tipos de constructores: los constructores ROW, los constructores de objeto y los constructores MULTISET (o colección).</span><span class="sxs-lookup"><span data-stu-id="fc035-112">provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="fc035-113">Para obtener más información, vea [construir tipos](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fc035-113">For more information, see [Constructing Types](constructing-types-entity-sql.md).</span></span>

<span data-ttu-id="fc035-114">El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="fc035-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="fc035-115">Todos los valores en el constructor deben ser de un tipo compatible.</span><span class="sxs-lookup"><span data-stu-id="fc035-115">All the values in the constructor must be of a compatible type.</span></span>

<span data-ttu-id="fc035-116">Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.</span><span class="sxs-lookup"><span data-stu-id="fc035-116">For example, the following expression creates a multiset of integers.</span></span>

`MULTISET(1, 2, 3)`

`{1, 2, 3}`

> [!NOTE]
> <span data-ttu-id="fc035-117">Los literales de conjunto múltiple anidados solo se admiten cuando un conjunto múltiple de ajuste tiene un único elemento MultiSet; por ejemplo, `{{1, 2, 3}}` .</span><span class="sxs-lookup"><span data-stu-id="fc035-117">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="fc035-118">Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.</span><span class="sxs-lookup"><span data-stu-id="fc035-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>

## <a name="example"></a><span data-ttu-id="fc035-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc035-119">Example</span></span>

<span data-ttu-id="fc035-120">La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="fc035-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="fc035-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fc035-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fc035-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fc035-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="fc035-123">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fc035-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="fc035-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fc035-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

[!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]

## <a name="see-also"></a><span data-ttu-id="fc035-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc035-125">See also</span></span>

- [<span data-ttu-id="fc035-126">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="fc035-126">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="fc035-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fc035-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
