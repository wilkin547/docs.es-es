---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148092"
---
# <a name="-equals-entity-sql"></a>= (Igual que) (Entity SQL)

Compara la igualdad de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  

 `true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  

 El operador == es equivalente a =.  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
