---
title: '>= (Mayor o igual que) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 9e1d7e92097713ebdaf15523a5f99f98ed8be0b3
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833747"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>> = (mayor o igual que) (Entity SQL)
Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor igual o mayor que el de la expresión de la derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos convertibles implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  
 `true` si la expresión izquierda tiene un valor igual o mayor que el de la expresión derecha; de lo contrario, `false`.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador de comparación >= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o mayor que el de la expresión derecha. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
