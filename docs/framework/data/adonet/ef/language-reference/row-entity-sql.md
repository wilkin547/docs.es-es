---
description: 'Más información acerca de: ROW (Entity SQL)'
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2d0bcf3c5be8ef3b67e170af5159ae7dd8744630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739279"
---
# <a name="row-entity-sql"></a>ROW (Entity SQL)

Crea registros anónimos con tipos asignados estructuralmente a partir de uno o varios valores.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión de consulta válida que devuelve un valor que se va a crear en un tipo de fila.  
  
 `alias`  
 Especifica un alias para el valor especificado en un tipo de fila. Si no se proporciona un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno basándose en las reglas de generación de alias de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="return-value"></a>Valor devuelto  

 Un tipo de fila.  
  
## <a name="remarks"></a>Observaciones  

 Debe utilizar constructores ROW en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para crear registros anónimos escritos estructuralmente de uno o más valores. El tipo de resultado de un constructor ROW es un tipo de fila cuyos tipos de campo corresponden a los tipos de los valores que se utilizaron para crear la fila. Por ejemplo, la expresión siguiente crea un valor de tipo `Record(a int, b string, c int)`.  
  
```sql  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 Si no proporciona un alias para una expresión en un constructor ROW, Entity Framework intentará generar uno. Para obtener más información, vea la sección "Reglas de alias" del tema [Identificadores](identifiers-entity-sql.md) .  
  
 Las reglas siguientes se aplican a expresiones que usan alias en un constructor ROW:  
  
- Las expresiones en un constructor ROW no pueden hacer referencia a otros alias del mismo constructor.  
  
- Dos expresiones en el mismo constructor ROW no pueden tener el mismo alias.  
  
 Para obtener más información sobre los constructores de consultas, vea [construir tipos](constructing-types-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador ROW para construir registros anónimos escritos estructuralmente. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ROW](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#row)]  
  
## <a name="see-also"></a>Vea también

- [Tipos de constructores](constructing-types-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
- [Definiciones de tipos](type-definitions-entity-sql.md)
