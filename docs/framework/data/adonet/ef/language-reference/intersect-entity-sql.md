---
description: 'Más información sobre: INTERSECT (Entity SQL)'
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 45c0434f6fc0ed6c110162d7e34d76c336635b0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748521"
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)

Devuelve una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.  
  
## <a name="return-value"></a>Valor devuelto  

 Colección del mismo tipo que `expression`o de un tipo base común o derivado.  
  
## <a name="remarks"></a>Observaciones  

 INTERSECT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador INTERSECT para devolver una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
