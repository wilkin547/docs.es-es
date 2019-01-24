---
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628027"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="8c944-102">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="8c944-102">Unsupported expressions</span></span>

<span data-ttu-id="8c944-103">En este tema se describen las expresiones de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c944-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="8c944-104">Para obtener más información, consulte [cómo Entity SQL difiere de Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8c944-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="8c944-105">Predicados cuantificados</span><span class="sxs-lookup"><span data-stu-id="8c944-105">Quantified predicates</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="8c944-106">permite construcciones con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c944-106">allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="8c944-107">, sin embargo, no admite tales construcciones.</span><span class="sxs-lookup"><span data-stu-id="8c944-107">, however, does not support such constructs.</span></span> <span data-ttu-id="8c944-108">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="8c944-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="8c944-109">\* (operador)</span><span class="sxs-lookup"><span data-stu-id="8c944-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="8c944-110">admite el uso del operador \* en la cláusula SELECT para indicar que todas las columnas se deberían proyectar fuera. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c944-110">supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="8c944-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c944-111">See also</span></span>

- [<span data-ttu-id="8c944-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8c944-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="8c944-113">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c944-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
