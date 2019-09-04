---
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248779"
---
# <a name="unsupported-expressions"></a>Expresiones no admitidas

En este tema se describen las expresiones de Transact-SQL que [!INCLUDE[esql](../../../../../../includes/esql-md.md)]no se admiten en. Para obtener más información, vea [Cómo difiere Entity SQL de Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Predicados cuantificados

Transact-SQL permite construcciones de la forma siguiente:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)], sin embargo, no admite tales construcciones. En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* (operador)

Transact-SQL admite el uso del operador * en la cláusula SELECT para indicar que se deben proyectar todas las columnas. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Diferencias entre Entity SQL y Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
