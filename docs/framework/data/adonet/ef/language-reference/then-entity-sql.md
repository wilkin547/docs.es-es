---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 5f0bbb0cadd736d476077685e08ba1a03b9c4001
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762889"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
El resultado de una cláusula WHEN cuando se evalúa como `true`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `when_expression`  
 Cualquier expresión Boolean válida.  
  
 `then_expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="remarks"></a>Comentarios  
 Si `when_expression` se evalúa como el valor `true`, el resultado es la `then-expression`correspondiente. Si no se cumple ninguna de las condiciones WHEN, se evalúa `else-expression` . Sin embargo, si no hay ninguna `else-expression`, el resultado es Null.  
  
 Para obtener un ejemplo, vea [caso](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Vea también  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
