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
# <a name="unsupported-expressions"></a>Expresiones no admitidas

En este tema se describen las expresiones de Transact-SQL que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Para obtener más información, vea [Cómo difiere Entity SQL de Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

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

## <a name="-operator"></a>Operador *

Transact-SQL admite el uso del operador * en la cláusula SELECT para indicar que se deben proyectar todas las columnas. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .

## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Diferencias entre Entity SQL y Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
