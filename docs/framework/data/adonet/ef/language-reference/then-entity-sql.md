---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 8d2d7f9a3a1d6ff9f25db3f19bf8f39781469f9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305629"
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
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Vea también

- [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
