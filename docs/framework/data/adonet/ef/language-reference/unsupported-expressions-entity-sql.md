---
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489860"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="c552d-102">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="c552d-102">Unsupported expressions</span></span>

<span data-ttu-id="c552d-103">En este tema se describe las expresiones de Transact-SQL que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c552d-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="c552d-104">Para obtener más información, consulte [cómo Entity SQL difiere de Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c552d-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="c552d-105">Predicados cuantificados</span><span class="sxs-lookup"><span data-stu-id="c552d-105">Quantified predicates</span></span>

<span data-ttu-id="c552d-106">Transact-SQL permite construcciones con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="c552d-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c552d-107">, sin embargo, no admite tales construcciones.</span><span class="sxs-lookup"><span data-stu-id="c552d-107">, however, does not support such constructs.</span></span> <span data-ttu-id="c552d-108">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="c552d-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="c552d-109">\* (operador)</span><span class="sxs-lookup"><span data-stu-id="c552d-109">\* operator</span></span>

<span data-ttu-id="c552d-110">Transact-SQL admite el uso de la \* operador en la cláusula SELECT para indicar que todas las columnas se deberían proyectar fuera. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c552d-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="c552d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c552d-111">See also</span></span>

- [<span data-ttu-id="c552d-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c552d-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="c552d-113">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c552d-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
