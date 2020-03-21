---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149770"
---
# <a name="mathematical-functions"></a>Funciones matemáticas

El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones. En la tabla siguiente se describen las funciones matemáticas SqlClient.  
  
## <a name="absexpression"></a>ABS (expresión)

Lleva a cabo la función que devuelve el valor absoluto.

**Argumentos**

`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.

**Valor de devolución**

Valor absoluto de la expresión especificada.

**Ejemplo**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(expresión)

Devuelve el valor del arcocoseno de la expresión especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(expresión)

Devuelve el valor del arcoseno de la expresión especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(expresión)

Devuelve el valor del arcotangente de la expresión numérica especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(expresión, expresión)

Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a>CEILING(expresión)

Convierte la expresión especificada al número entero más pequeño mayor o igual que él.

**Argumentos**

`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.

**Valor de devolución**

Un `Int32` `Int64`, `Double`, `Decimal`, o .

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(expresión)

Calcula el coseno trigonométrico del ángulo especificado, en radianes.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(expresión)

Calcula la cotangente trigonométrica del ángulo especificado, en radianes.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES(radianes)

Devuelve el ángulo correspondiente en grados.

**Argumentos**

`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.

**Valor de devolución**

Un `Int32` `Int64`, `Double`, `Decimal`, o .

**Ejemplo**

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(expresión)

Calcula el valor exponencial de la expresión numérica especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**`SqlServer.EXP(1)`

## <a name="floorexpression"></a>PLANTA(expresión)

Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(expresión)

Calcula el logaritmo natural de la expresión `float` especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(expresión)

Devuelve el logaritmo en base 10 de la expresión `Double` especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI()

Devuelve el valor constante de Pi como un `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a>POTENCIA(numeric_expression, power_expression)

Calcula el valor de la expresión especificada elevada a la potencia indicada.

**Argumentos**

|  |  |
|--|--|
|`numeric_expression`| Un `Int32` `Int64`, `Double`, `Decimal`, o .|
|`power_expression`| A `Double` que representa el poder al `numeric_expression`que elevar el archivo .|

**Valor de devolución**

Valor de la `numeric_expression` especificada a la `power_expression` especificada.

**Ejemplo**

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(expresión)

Convierte los grados en radianes.

**Argumentos**

`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.

**Valor de devolución**

Un `Int32` `Int64`, `Double`, `Decimal`, o .

**Ejemplo**

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([semilla])

Devuelve un valor aleatorio de 0 a 1.

**Argumentos**

El valor de `Int32`semilla como un archivo . Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria. Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.

**Valor de devolución**

Valor `Double` aleatorio de 0 a 1.

**Ejemplo**

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>ROUND(numeric_expression, length[,function])

Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.

**Argumentos**

|  |  |
|--|--|
|`numeric_expression`| Un `Int32` `Int64`, `Double`, `Decimal`, o .
|`length`| Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`. Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`. Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.|
|`function` | Opcional. Un `Int32` que representa el tipo de operación que se va a realizar. Cuando se omite la función o tiene `numeric_expression` un valor de 0 (predeterminado), se redondea. Cuando se especifica un valor `numeric_expression` distinto de 0, se trunca. |

**Valor de devolución**

Valor de la `numeric_expression` especificada a la `power_expression` especificada.

**Ejemplo**

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>SIGN(expresión)

Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.

**Argumentos**

`expression`: `Int32`, `Int64`, `Double` o `Decimal`

**Valor de devolución**

Un `Int32` `Int64`, `Double`, `Decimal`, o .

**Ejemplo**

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(expresión)

Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT(expresión)

Devuelve la raíz cuadrada de la expresión especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>SQUARE(expresión)

Devuelve la raíz cuadrada de la expresión especificada.

**Argumentos**

`expression`: un valor `Double`.

**Valor de devolución**

`Double`.

**Ejemplo**

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(expresión)

Calcula la tangente de una expresión especificada.

**Argumentos**

`expression`: `Double`

**Valor de devolución**

`Double`

**Ejemplo**

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Consulte también

- [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)
