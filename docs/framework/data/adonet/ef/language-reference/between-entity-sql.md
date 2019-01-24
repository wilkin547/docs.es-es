---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: cface8ab50e53f21293ad54ea6961c7e308080b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690701"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina si el resultado de una expresión es un valor incluido en un intervalo especificado. El [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión BETWEEN tiene la misma funcionalidad que la expresión BETWEEN de Transact-SQL.  
  
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
  
 AND  
 Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`. Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.  
  
## <a name="remarks"></a>Comentarios  
 Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<) en lugar de BETWEEN.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
