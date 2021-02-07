---
description: 'Más información acerca de: SKIP (Entity SQL)'
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: f4924acae6e351e076b5795cf47d63966ebdcb43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768017"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="af96e-103">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="af96e-103">SKIP (Entity SQL)</span></span>

<span data-ttu-id="af96e-104">Puede realizar la paginación física utilizando la subcláusula SKIP en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="af96e-104">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="af96e-105">SKIP no se puede utilizar por separado de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="af96e-105">SKIP cannot be used separately from the ORDER BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="af96e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af96e-106">Syntax</span></span>

```sql
[ SKIP n ]
```

## <a name="arguments"></a><span data-ttu-id="af96e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="af96e-107">Arguments</span></span>

`n` \
<span data-ttu-id="af96e-108">Número de elementos que se han de omitir.</span><span class="sxs-lookup"><span data-stu-id="af96e-108">The number of items to skip.</span></span>

## <a name="remarks"></a><span data-ttu-id="af96e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af96e-109">Remarks</span></span>

<span data-ttu-id="af96e-110">Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP.</span><span class="sxs-lookup"><span data-stu-id="af96e-110">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="af96e-111">Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.</span><span class="sxs-lookup"><span data-stu-id="af96e-111">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>

> [!NOTE]
> <span data-ttu-id="af96e-112">Una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se no es válida si tanto el modificador TOP como la subcláusula SKIP están presentes en la misma expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="af96e-112">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="af96e-113">La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="af96e-113">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>

> [!NOTE]
> <span data-ttu-id="af96e-114">En SQL Server 2000, el uso de SKIP con ORDER BY en columnas que no son de clave puede devolver resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="af96e-114">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="af96e-115">Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella.</span><span class="sxs-lookup"><span data-stu-id="af96e-115">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="af96e-116">Esto se debe a la forma en que se traduce SKIP para SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="af96e-116">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="af96e-117">Por ejemplo, en el código siguiente se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:</span><span class="sxs-lookup"><span data-stu-id="af96e-117">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

<span data-ttu-id="af96e-118">La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta en [Cómo: paginar a través de los resultados](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) de la consulta utiliza el operador order by con SKIP para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="af96e-118">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="af96e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="af96e-119">See also</span></span>

- [<span data-ttu-id="af96e-120">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="af96e-120">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="af96e-121">[Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="af96e-121">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="af96e-122">Buscapersona</span><span class="sxs-lookup"><span data-stu-id="af96e-122">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="af96e-123">TOP</span><span class="sxs-lookup"><span data-stu-id="af96e-123">TOP</span></span>](top-entity-sql.md)
