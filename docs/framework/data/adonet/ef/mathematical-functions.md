---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 5e5658e28c7d806f7fd38f941bfa7254e7806e11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182481"
---
# <a name="mathematical-functions"></a>Funciones matemáticas

El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones. En la tabla siguiente se describen las funciones matemáticas de SqlClient.  
  
## <a name="absexpression"></a>ABS (expresión)

Lleva a cabo la función que devuelve el valor absoluto.

**Argumentos**

`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`

**Valor devuelto**

Valor absoluto de la expresión especificada.

**Ejemplo**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS (expresión)

Devuelve el valor del arcocoseno de la expresión especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN (expresión)

Devuelve el valor del arcoseno de la expresión especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN (expresión)

Devuelve el valor del arcotangente de la expresión numérica especificada.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2 (expresión, expresión)

Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.

**Argumentos**

`expression`: OBJETO `Double`.

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>CEILING (expresión)

Convierte la expresión especificada al número entero más pequeño mayor o igual que él.

**Argumentos**

`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`

**Valor devuelto**

`Int32`, ,`Int64` O`Decimal`. `Double`

**Ejemplo** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS (expresión)

Calcula el coseno trigonométrico del ángulo especificado, en radianes. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT (expresión)

Calcula la cotangente trigonométrica del ángulo especificado, en radianes. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>GRADOS (radianes)

Devuelve el ángulo correspondiente en grados. 

**Argumentos** 

`expression`: `Int32`, ,`Int64` O`Decimal`. `Double` 

**Valor devuelto** 

`Int32`, ,`Int64` O`Decimal`. `Double` 

**Ejemplo** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP (expresión)

Calcula el valor exponencial de la expresión numérica especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** de`SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR (expresión)

Convierte la expresión especificada al número entero más grande que sea menor o igual que ella. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG (expresión)

Calcula el logaritmo natural de la expresión `float` especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10 (expresión)

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

## <a name="powernumeric_expression-power_expression"></a>POWER (numeric_expression, power_expression)

Calcula el valor de la expresión especificada elevada a la potencia indicada.

**Argumentos** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, ,`Int64` O`Decimal`. `Double`|
|`power_expression`| Que representa la potencia a la que se eleva el `numeric_expression`. `Double`| 

**Valor devuelto** 

Valor de la `numeric_expression` especificada a la `power_expression` especificada. 

**Ejemplo** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIAnes (expresión)

Convierte grados en radianes. 

**Argumentos** 

`expression`: `Int32`, ,`Int64` O`Decimal`. `Double` 

**Valor devuelto** 

`Int32`, ,`Int64` O`Decimal`. `Double` 

**Ejemplo** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND ([SEED])

Devuelve un valor aleatorio de 0 a 1. 

**Argumentos** 

Valor de inicialización como `Int32`. Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria. Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.

**Valor devuelto** 

Valor `Double` aleatorio de 0 a 1. 

**Ejemplo** 

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>ROUND (numeric_expression, longitud [, función])

Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas. 

**Argumentos** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, ,`Int64` O`Decimal`. `Double` 
|`length`| Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`. Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`. Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.|
|`function` | Opcional. `Int32` Que representa el tipo de operación que se va a realizar. Cuando se omite la función o tiene un valor de 0 (valor predeterminado `numeric_expression` ), se redondea. Cuando se especifica un valor distinto de 0, `numeric_expression` se trunca. |

**Valor devuelto** 

Valor de la `numeric_expression` especificada a la `power_expression` especificada.

**Ejemplo** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>SIGN (expresión) 

Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada. 

**Argumentos** 

`expression`: `Int32`, `Int64`, `Double` o `Decimal` 

**Valor devuelto** 

`Int32`, ,`Int64` O`Decimal`. `Double` 

**Ejemplo** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN (expresión)

Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** de`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT (expresión)

Devuelve la raíz cuadrada de la expresión especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** de`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>SQUARE (expresión)

Devuelve la raíz cuadrada de la expresión especificada. 

**Argumentos** 

`expression`: OBJETO `Double`. 

**Valor devuelto** 

Objeto `Double`. 

**Ejemplo** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN (expresión)

Calcula la tangente de una expresión especificada.

**Argumentos** 

`expression`: `Double` 

**Valor devuelto** 

`Double` 

**Ejemplo** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Vea también

Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:

- **SQL Server 2005:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))
- **SQL Server 2008:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))
- **SQL Server 2012 y versiones posteriores:** [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)

- [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)
