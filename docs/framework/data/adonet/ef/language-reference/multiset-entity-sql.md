---
title: MULTISET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6389051ae1244a2a38699704c67217d9807fe7e4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor MULTISET deben ser de un tipo `T`compatible. No se permiten los constructores MULTISET vacíos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier lista válida de valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Una colección de tipo MULTISET\<T >.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona tres tipos de constructores: los constructores ROW, los constructores de objeto y los constructores MULTISET (o colección). Para obtener más información, consulte [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor deben ser de un tipo compatible.  
  
 Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Solo se admiten los literales de conjunto múltiple anidados cuando un conjunto múltiple contenedor tiene un único elemento de conjunto múltiple; por ejemplo, `{{1, 2, 3}}`. Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Vea también  
 [Tipos de constructores](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
