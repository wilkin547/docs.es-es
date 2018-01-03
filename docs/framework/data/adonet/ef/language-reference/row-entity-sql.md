---
title: ROW (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 58f954d2a03e6cf1c3117ebe440513014149f819
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="row-entity-sql"></a>ROW (Entity SQL)
Crea registros anónimos con tipos asignados estructuralmente a partir de uno o varios valores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que devuelve un valor que se va a crear en un tipo de fila.  
  
 `alias`  
 Especifica un alias para el valor especificado en un tipo de fila. Si no se proporciona un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno basándose en las reglas de generación de alias de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="return-value"></a>Valor devuelto  
 Un tipo de fila.  
  
## <a name="remarks"></a>Comentarios  
 Debe utilizar constructores ROW en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para crear registros anónimos escritos estructuralmente de uno o más valores. El tipo de resultado de un constructor ROW es un tipo de fila cuyos tipos de campo corresponden a los tipos de los valores que se utilizaron para crear la fila. Por ejemplo, la expresión siguiente crea un valor de tipo `Record(a int, b string, c int)`.  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 Si no proporciona un alias para una expresión en un constructor ROW, Entity Framework intentará generar uno. Para obtener más información, vea la sección "Reglas de alias" del tema [Identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) .  
  
 Las reglas siguientes se aplican a expresiones que usan alias en un constructor ROW:  
  
-   Las expresiones en un constructor ROW no pueden hacer referencia a otros alias del mismo constructor.  
  
-   Dos expresiones en el mismo constructor ROW no pueden tener el mismo alias.  
  
 Para obtener más información sobre los constructores de consulta, vea [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador ROW para construir registros anónimos escritos estructuralmente. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a>Vea también  
 [Tipos de constructores](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Definiciones de tipo](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
