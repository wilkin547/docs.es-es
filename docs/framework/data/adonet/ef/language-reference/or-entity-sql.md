---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: c88e041638fbe6f32717ce9c4f9c2ff6fb56d803
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249772"
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
  
 Las barras verticales dobles&#124;&#124;() tienen la misma funcionalidad que el operador o.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
