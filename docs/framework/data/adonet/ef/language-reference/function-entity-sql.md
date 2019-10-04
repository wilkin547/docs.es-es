---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: bacc773351812a5db60f493f3025c8e4b07dbaa2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833799"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Define una función en el ámbito de un comando de consulta de Entity SQL.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
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
  
 COLECCIÓN (< type_definition @ no__t-0)  
 Una expresión que devuelve una colección de tipos, filas o referencias compatibles.  
  
 REF **(** `data_type` **)**  
 Una expresión que devuelve una referencia a un tipo de entidad.  
  
 ROW **(** `row_expression` **)**  
 Una expresión que devuelve registros anónimos y de tipo estructural a partir de uno o varios valores. Para obtener más información, consulta [ROW](row-entity-sql.md).  
  
## <a name="remarks"></a>Comentarios  
 Es posible declarar varias funciones inline con el mismo nombre, siempre que sus firmas sean distintas. Para obtener más información, consulta [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
 Solo se puede llamar a una función inline en un comando de Entity SQL si dicha función se ha definido en el comando. Sin embargo, es posible llamar a una función inline dentro de otra función inline antes o después de definir la función llamada. En el ejemplo siguiente, la función A llama a la función B antes de que esta se haya definido:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Para obtener más información, vea [Cómo: Llame a una función definida por el usuario @ no__t-0.  
  
 Las funciones también se pueden declarar en el modelo. Las funciones declaradas en el modelo se ejecutan de la misma manera que las funciones declaradas inline en el comando. Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente de Entity SQL define una función `Products` que toma un valor entero para filtrar los productos devueltos.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente de Entity SQL define una función `StringReturnsCollection` que toma una colección de cadenas para filtrar los contactos devueltos.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Lenguaje Entity SQL](entity-sql-language.md)
