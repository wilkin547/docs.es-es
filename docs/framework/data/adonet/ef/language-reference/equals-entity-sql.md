---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ad9eda5a3544ea157d06c57876b1b0454a25dba1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215688"
---
# <a name="-equals-entity-sql"></a>= (Igual que) (Entity SQL)
Compara la igualdad de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos convertibles implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  
 `true` Si la expresión izquierda es igual a la expresión derecha; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 El operador == es equivalente a =.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
