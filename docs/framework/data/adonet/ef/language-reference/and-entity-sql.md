---
title: '&amp;&amp; ETC (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198046"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp; ETC (Entity SQL)

Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
boolean_expression AND boolean_expression
```

o  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor booleano.  
  
## <a name="remarks"></a>Observaciones  

 Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|false|FALSE|FALSE|  
|`NULL`|NULL|FALSE|NULL|  
  
## <a name="example"></a>Ejemplo  

 En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
