---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: b267e97860a2cb071b857224455f01b73115c72d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299701"
---
# <a name="limit-entity-sql"></a>LIMIT (Entity SQL)
La paginación física se puede realizar utilizando la subcláusula LIMIT en la cláusula ORDER BY. LIMIT no se puede utilizar por separado de la cláusula ORDER BY.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `n`  
 Número de elementos que se seleccionarán.  
  
 Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT. Por ejemplo, LIMIT 5 limitará el conjunto de resultados a 5 instancias o filas. LIMIT es funcionalmente equivalente a TOP con la excepción de que LIMIT exige la presencia de la cláusula ORDER BY. SKIP y LIMIT se pueden utilizar independientemente junto con la cláusula ORDER BY.  
  
> [!NOTE]
>  Una consulta de Entity SQL se considerará no válida si el modificador TOP y la subcláusula SKIP están presentes en la misma expresión de consulta. La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente usa el operador ORDER BY con LIMIT para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Vea también

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Cómo: Página de resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paginación](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
