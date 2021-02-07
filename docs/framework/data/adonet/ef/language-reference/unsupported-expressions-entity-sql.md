---
description: 'Más información sobre: expresiones no admitidas'
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: ceb57dc78f9685a79de987d15f7fd57a583b75a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673302"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="93c0a-103">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="93c0a-103">Unsupported expressions</span></span>

<span data-ttu-id="93c0a-104">En este tema se describen las expresiones de Transact-SQL que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93c0a-104">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="93c0a-105">Para obtener más información, vea [Cómo difiere Entity SQL de Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="93c0a-105">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="93c0a-106">Predicados cuantificados</span><span class="sxs-lookup"><span data-stu-id="93c0a-106">Quantified predicates</span></span>

<span data-ttu-id="93c0a-107">Transact-SQL permite construcciones de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="93c0a-107">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="93c0a-108">, sin embargo, no admite tales construcciones.</span><span class="sxs-lookup"><span data-stu-id="93c0a-108">, however, does not support such constructs.</span></span> <span data-ttu-id="93c0a-109">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="93c0a-109">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="93c0a-110">Operador \*</span><span class="sxs-lookup"><span data-stu-id="93c0a-110">\* operator</span></span>

<span data-ttu-id="93c0a-111">Transact-SQL admite el uso del operador \* en la cláusula SELECT para indicar que se deben proyectar todas las columnas. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93c0a-111">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="93c0a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="93c0a-112">See also</span></span>

- [<span data-ttu-id="93c0a-113">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="93c0a-113">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="93c0a-114">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93c0a-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
