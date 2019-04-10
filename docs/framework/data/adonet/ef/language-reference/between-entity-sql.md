---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225266"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina si el resultado de una expresión es un valor incluido en un intervalo especificado. El [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión BETWEEN tiene la misma funcionalidad que la expresión BETWEEN de Transact-SQL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`. `expression` debe ser el mismo tipo que `begin_expression` y `end_expression`.  
  
 `begin_expression`  
 Cualquier expresión válida. `begin_expression` debe ser el mismo tipo que `expression` y `end_expression`. `begin_expression` debe ser menor que `end_expression`, lo contrario, el valor devuelto se negará.  
  
 `end_expression`  
 Cualquier expresión válida. `end_expression` debe ser el mismo tipo que `expression` y `begin_expression`.  
  
 NOT  
 Especifica que el resultado de BETWEEN se niega.  
  
 AND  
 Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; en caso contrario, `false`. `null` se devolverá si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.  
  
## <a name="remarks"></a>Comentarios  
 Para especificar un intervalo exclusivo, utilice el mayor que (>) y menor que (<) operadores en lugar de BETWEEN.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
