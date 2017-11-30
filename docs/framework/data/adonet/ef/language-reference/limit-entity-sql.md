---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c890bf6950f94c04350902276193f5a43239f63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Vea también  
 [ORDENAR POR](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Cómo: resultados de la página a través de consulta](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Paginación](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [ARRIBA](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
