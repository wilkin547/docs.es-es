---
description: 'Más información acerca de: | | DE (Entity SQL)'
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 83af0211de1dd86b057237c36312e3ce33a3512a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696339"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)

Combina dos expresiones `Boolean` .  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor `Boolean`.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` cuando alguna de las condiciones es `true`; de lo contrario, `false`.  
  
## <a name="remarks"></a>Observaciones  

 OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Se usa para combinar dos condiciones. Cuando en una instrucción se utiliza más de un operador lógico, los operadores OR se evalúan después de los operadores AND. Sin embargo, se puede cambiar el orden de evaluación gracias a los paréntesis.  
  
 Las barras verticales dobles (&#124;&#124;) tienen la misma funcionalidad que el operador o.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
