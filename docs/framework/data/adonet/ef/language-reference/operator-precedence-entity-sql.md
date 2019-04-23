---
title: Precedencia de operadores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159138"
---
# <a name="operator-precedence-entity-sql"></a>Precedencia de operadores (Entity SQL)
Cuando un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta tiene múltiples operadores, prioridad de operador determina la secuencia en que se realizan las operaciones. El orden de ejecución puede afectar de manera significativa al resultado de la consulta.  
  
 Los operadores tienen los niveles de prioridad que se muestran en la siguiente tabla. Un operador con un nivel más altos se evalúa antes que un operador con un nivel más bajo.  
  
|Nivel|Tipo de operación|Operador|  
|-----------|--------------------|--------------|  
|1|Principal|`. , [] ()`|  
|2|Unario|`! not`|  
|3|Multiplicativo|`* / %`|  
|4|Aditivo|`+ -`|  
|5|Ordenación|`< > <= >=`|  
|6|Igualdad|`= != <>`|  
|7|AND condicional|`and &&`|  
|8|OR condicional|`or &#124;&#124;`|  
  
 Cuando en una expresión dos operadores tengan el mismo nivel de prioridad de operador, se evalúan de izquierda a derecha en función de su posición dentro de la consulta. Por ejemplo, `x+y-z` se evalúa como `(x+y)-z`.  
  
 Puede utilizar paréntesis para invalidar la prioridad definida de los operadores en una consulta. Todo lo que está dentro del paréntesis se evalúa en primer lugar para producir un resultado antes de que dicho resultado lo pueda utilizar cualquier otro operador que se encuentre fuera del paréntesis. Por ejemplo, `x+y*z` multiplica `y` por `z` y, a continuación, agrega `x`, pero `(x+y)*z` agrega `x` a `y` y, a continuación, multiplica el resultado por `z`.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
