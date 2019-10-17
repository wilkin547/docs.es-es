---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319282"
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
  
## <a name="remarks"></a>Comentarios  
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
