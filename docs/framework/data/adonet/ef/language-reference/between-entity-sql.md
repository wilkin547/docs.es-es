---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 41036e629837bd5861368df545bed9423eac5b23
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251291"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina si el resultado de una expresión es un valor incluido en un intervalo especificado. La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión between tiene la misma funcionalidad que la expresión Transact-SQL between.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`. `expression` debe ser del mismo tipo que `begin_expression` y `end_expression`.  
  
 `begin_expression`  
 Cualquier expresión válida. `begin_expression` debe ser del mismo tipo que `expression` y `end_expression`. `begin_expression` debe ser menor que `end_expression`; de lo contrario, el valor devuelto se negará.  
  
 `end_expression`  
 Cualquier expresión válida. `end_expression` debe ser del mismo tipo que `expression` y `begin_expression`.  
  
 NOT  
 Especifica que el resultado de BETWEEN se niega.  
  
 Y  
 Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`. Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.  
  
## <a name="remarks"></a>Comentarios  
 Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<) en lugar de entre.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
