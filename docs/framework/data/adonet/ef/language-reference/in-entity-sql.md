---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 582a3b988247f1484197c0905fecf7f4407f88b0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203675"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)

Determina si un valor determinado coincide con algún valor de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `value`  
 Expresión válida que devuelve el valor que hay que buscar.  
  
 [ NOT ]  
 Especifica que el resultado `Boolean` de IN se niega.  
  
 `expression`  
 Expresión válida que devuelve la colección en la que hay que buscar una coincidencia. Todas las expresiones deben ser del mismo tipo que `value`o de un tipo base común o derivado.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` si el valor se encuentra en la colección; Null si el valor o la colección son Null; `false`, en caso contrario. El uso de NOT IN niega el resultado de IN.  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
