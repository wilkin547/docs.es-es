---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 09ae742f648f95819a8c6fc64d402c4f11c7748a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Combina dos expresiones `Boolean` .  
  
## <a name="syntax"></a>Sintaxis  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor `Boolean`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando alguna de las condiciones es `true`; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Se usa para combinar dos condiciones. Cuando se utiliza más de un operador lógico en una instrucción, los operadores OR se evalúan después de los operadores AND. Sin embargo, se puede cambiar el orden de evaluación mediante paréntesis.  
  
 Las dobles barras verticales (&#124;&#124;) tienen la misma funcionalidad que el operador OR.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
