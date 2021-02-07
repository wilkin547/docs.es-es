---
description: 'Más información acerca de: después (Entity SQL)'
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: e1f0657cfef3786832f489434fd8fc0342e8687b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673471"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)

El resultado de una cláusula WHEN cuando se evalúa como `true`.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `when_expression`  
 Cualquier expresión Boolean válida.  
  
 `then_expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="remarks"></a>Observaciones  

 Si `when_expression` se evalúa como el valor `true`, el resultado es la `then-expression`correspondiente. Si no se cumple ninguna de las condiciones WHEN, se evalúa `else-expression` . Sin embargo, si no hay ninguna `else-expression`, el resultado es Null.  
  
 Para obtener un ejemplo, vea [Case](case-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a>Vea también

- [CASE](case-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
