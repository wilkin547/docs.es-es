---
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-ado
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
dev_langs:
- sql
ms.openlocfilehash: 075daf0e4f0477dda50231760fbb3d990a9f8468
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2018
---
# <a name="unsupported-expressions"></a>Expresiones no admitidas

En este tema se describen las expresiones de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Para obtener más información, consulte [cómo Entity SQL difiere de Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Predicados cuantificados

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] Permite construcciones con el formato siguiente:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)], sin embargo, no admite tales construcciones. En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:

```sql
not exists(select 0 from employees as e where sal > e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* (operador)

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] admite el uso de la * operador en la cláusula SELECT para indicar que todas las columnas se deberían proyectar fuera. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

## <a name="see-also"></a>Vea también

[Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
[Diferencias entre Entity SQL y Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
