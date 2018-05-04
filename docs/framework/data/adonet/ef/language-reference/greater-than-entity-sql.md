---
title: '&gt; (Mayor que) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: b9cf4d5445060bbd013ae2d769c407e7f9ee9314
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="gt-greater-than-entity-sql"></a>&gt; (Mayor que) (Entity SQL)
Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos convertibles implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  
 `true` si la expresión izquierda tiene un valor mayor que el de la expresión derecha; de lo contrario, `false`.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador de comparación > para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor mayor que el de la expresión derecha. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
