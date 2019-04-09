---
title: '&amp;&amp; (Y) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: f0b20a8c1960bd6191a35c426dbea45c30ccc1c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084074"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp; (Y) (Entity SQL)
Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor booleano.  
  
## <a name="remarks"></a>Comentarios  
 Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|false|NULL|  
|`FALSE`|false|false|false|  
|`NULL`|NULL|false|NULL|  
  
## <a name="example"></a>Ejemplo  
 En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
