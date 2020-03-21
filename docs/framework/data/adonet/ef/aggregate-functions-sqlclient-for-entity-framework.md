---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150654"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funciones de agregado (SqlClient para Entity Framework)
El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado. Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.  
  
 A continuación se muestran las funciones de agregado SqlClient.  

## <a name="avgexpression"></a>AVG(expresión)

Devuelve el promedio de los valores de una colección. Se omiten los valores NULL.

**Argumentos**

Un `Int32` `Int64`, `Double`, `Decimal`, y .

**Valor de devolución**

Tipo de `expression`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (colección)

 Devuelve la suma de comprobación de los valores de una colección. Se omiten los valores NULL.

 **Argumentos**

 A Collection(`Int32`).

 **Valor de devolución**

 Un valor de tipo `Int32`.

 **Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a>COUNT(expresión)

Devuelve el número de elementos de una colección como un valor `Int32`.

**Argumentos**

Un\<T de colección>, donde T es uno de los siguientes tipos:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(no devuelto en SQL Server 2000)|

**Valor de devolución**

Un valor de tipo `Int32`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a>COUNT_BIG(expresión)

Devuelve el número de elementos de una colección como un valor `bigint`.

 **Argumentos**

 Una colección(T), donde T es uno de los siguientes tipos:

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(no devuelto en SQL Server 2000)|

**Valor de devolución**

Un valor de tipo `Int64`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX(expresión)

Devuelve el valor máximo de la colección.

**Argumentos**

Una colección(T), donde T es uno de los siguientes tipos:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valor de devolución**

Tipo de `expression`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN(expresión)

Devuelve el valor mínimo de una colección.

**Argumentos**

Una colección(T), donde T es uno de los siguientes tipos:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valor de devolución**

Tipo de `expression`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV(expresión)

Devuelve la desviación típica estadística de todos los valores de la expresión especificada.

**Argumentos**

A Collection(`Double`).

**Valor de devolución**

`Double`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP(expresión)

Devuelve la desviación estadística estándar para la población de todos los valores de la expresión especificada.

**Argumentos**

A Collection(`Double`).

**Valor de devolución**

`Double`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM(expresión)

Devuelve la suma de todos los valores de la colección.

**Argumentos**

Una colección(T) donde T es `Int32`uno `Int64` `Double`de `Decimal`los siguientes tipos: , , , .

**Valor de devolución**

Tipo de `expression`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR(expresión)

Devuelve la varianza estadística de todos los valores de la expresión especificada.

**Argumentos**

A Collection(`Double`).

**Valor de devolución**

`Double`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP(expresión)

Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.

**Argumentos**

A Collection(`Double`).

**Valor de devolución**

`Double`.

**Ejemplo**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a>Consulte también

- [Funciones de agregado (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
- [Funciones canónicas de agregado](./language-reference/aggregate-canonical-functions.md)
