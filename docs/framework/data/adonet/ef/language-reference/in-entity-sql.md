---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833693"
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
 `true` si el valor se encuentra en la colección; NULL si el valor es null o la colección es null; de lo contrario, `false`. El uso de NOT IN niega el resultado de IN.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
