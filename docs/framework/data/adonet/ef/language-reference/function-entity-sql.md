---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: 1c02583400f9092dcb5008239bfd1fd73c63c326
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485552"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Define una función en el ámbito de un comando de consulta de Entity SQL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a>Argumentos  
 `function-name`  
 Nombre de la función.  
  
 `parameter-name`  
 Nombre de un parámetro de la función.  
  
 `function_expression`  
 Una expresión de Entity SQL válida que es la función. El comando de la función puede actuar sobre los parámetros `parameter_name` pasados a la función.  
  
 `data_type`  
 Nombre de un tipo compatible.  
  
 COLLECTION ( <type_definition`>` )  
 Una expresión que devuelve una colección de tipos, filas o referencias compatibles.  
  
 REF **(**`data_type`**)**  
 Una expresión que devuelve una referencia a un tipo de entidad.  
  
 ROW **(**`row_expression`**)**  
 Una expresión que devuelve registros anónimos y de tipo estructural a partir de uno o varios valores. Para obtener más información, consulta [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="remarks"></a>Comentarios  
 Es posible declarar varias funciones inline con el mismo nombre, siempre que sus firmas sean distintas. Para obtener más información, consulta [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
 Solo se puede llamar a una función inline en un comando de Entity SQL si dicha función se ha definido en el comando. Sin embargo, es posible llamar a una función inline dentro de otra función inline antes o después de definir la función llamada. En el ejemplo siguiente, la función A llama a la función B antes de que esta se haya definido:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Para obtener más información, consulte [Cómo: llamar a una función definida por el usuario](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02).  
  
 Las funciones también se pueden declarar en el modelo. Las funciones declaradas en el modelo se ejecutan de la misma manera que las funciones declaradas inline en el comando. Para obtener más información, consulte [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente de Entity SQL define una función `Products` que toma un valor entero para filtrar los productos devueltos.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente de Entity SQL define una función `StringReturnsCollection` que toma una colección de cadenas para filtrar los contactos devueltos.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Lenguaje Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
