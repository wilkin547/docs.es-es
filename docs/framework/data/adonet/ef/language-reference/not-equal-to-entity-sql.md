---
title: '!= (Distinto de) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: bebe85072f5a2cf6a133b88c6d3f5c97299aa63f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191780"
---
# <a name="-not-equal-to-entity-sql"></a>!= (Distinto de) (Entity SQL)

Compara dos expresiones para determinar si la expresión de la izquierda no es igual que la expresión de la derecha. El operador != (No es igual a) es funcionalmente equivalente al operador <>.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  

 `true` si la expresión de la izquierda no es igual a la expresión de la derecha; de lo contrario, `false`.  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente usa el operador != para comparar dos expresiones con el fin de determinar si la expresión de la izquierda es distinta de la expresión de la derecha. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
