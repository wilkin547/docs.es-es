---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 63f83532c399f77e268913da3198327345b9c2ee
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143680"
---
# <a name="mathematical-functions"></a>Funciones matemáticas

El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones. En la tabla siguiente se describe las funciones matemáticas de SqlClient.  
  
## <a name="absexpression"></a>ABS(Expression)

Lleva a cabo la función que devuelve el valor absoluto.

**Argumentos**

`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.

**Valor devuelto**

Valor absoluto de la expresión especificada.

**Ejemplo**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(Expression)

Devuelve el valor del arcocoseno de la expresión especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(Expression)

Devuelve el valor del arcoseno de la expresión especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(Expression)

Devuelve el valor del arcotangente de la expresión numérica especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(Expression, Expression)

Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>CEILING(Expression)

Convierte la expresión especificada al número entero más pequeño mayor o igual que él.

**Argumentos**

`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.

**Valor devuelto**

Un `Int32`, `Int64`, `Double`, o `Decimal`.

**Ejemplo** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(Expression)

Calcula el coseno trigonométrico del ángulo especificado, en radianes. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(Expression)

Calcula la cotangente trigonométrica del ángulo especificado, en radianes. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>Degrees(RADIANS)

Devuelve el ángulo correspondiente en grados. 

**Argumentos** 

`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`. 

**Valor devuelto** 

Un `Int32`, `Int64`, `Double`, o `Decimal`. 

**Ejemplo** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(Expression)

Calcula el valor exponencial de la expresión numérica especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** `SqlServer.EXP(1)`

## <a name="floorexpression"></a>Floor(Expression)

Convierte la expresión especificada al número entero más grande que sea menor o igual que ella. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(Expression)

Calcula el logaritmo natural de la expresión `float` especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(Expression)

Devuelve el logaritmo en base 10 de la expresión `Double` especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI()

Devuelve el valor constante de Pi como un `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a>POWER (numeric_expression, power_expression)

Calcula el valor de la expresión especificada elevada a la potencia indicada.

**Argumentos** 

|  |  |
|--|--|
|`numeric_expression`| Un `Int32`, `Int64`, `Double`, o `Decimal`.|
|`power_expression`| Un `Double` que representa la potencia a la que se va a generar el `numeric_expression`.| 

**Valor devuelto** 

Valor de la `numeric_expression` especificada a la `power_expression` especificada. 

**Ejemplo** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(Expression)

Convierte grados en radianes. 

**Argumentos** 

`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`. 

**Valor devuelto** 

Un `Int32`, `Int64`, `Double`, o `Decimal`. 

**Ejemplo** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([SEED])

Devuelve un valor aleatorio de 0 a 1. 

**Argumentos** 

El valor de inicialización como una `Int32`. Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria. Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.

**Valor devuelto** 

Valor `Double` aleatorio de 0 a 1. 

**Ejemplo** 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a>Round(numeric_expression, Length[,Function])

Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas. 

**Argumentos** 

|  |  |
|--|--|
|`numeric_expression`| Un `Int32`, `Int64`, `Double`, o `Decimal`. 
|`length`| Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`. Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`. Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.|
|`function` | Opcional. Un `Int32` que representa el tipo de operación que se realiza. Cuando la función se omite o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea. Si un valor distinto de 0 se especifica, `numeric_expression` se trunca. |

**Valor devuelto** 

Valor de la `numeric_expression` especificada a la `power_expression` especificada.

**Ejemplo** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>Sign(Expression) 

Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada. 

**Argumentos** 

`expression`: `Int32`, `Int64`, `Double` o `Decimal` 

**Valor devuelto** 

Un `Int32`, `Int64`, `Double`, o `Decimal`. 

**Ejemplo** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(Expression)

Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** `SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT(Expression)

Devuelve la raíz cuadrada de la expresión especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** `SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>Square(Expression)

Devuelve la raíz cuadrada de la expresión especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(Expression)

Calcula la tangente de una expresión especificada.

**Argumentos** 

`expression`: `Double` 

**Valor devuelto** 

`Double` 

**Ejemplo** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Vea también

Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:  
  
**SQL Server 2005:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))  
**SQL Server 2008:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))  
**SQL Server 2012 y versiones posterior:** [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)   

 [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)
