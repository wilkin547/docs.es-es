---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251708"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funciones de agregado (SqlClient para Entity Framework)
El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado. Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.  
  
 A continuación se enumeran las funciones de agregado SqlClient.  

## <a name="avgexpression"></a>AVG (expresión)

Devuelve el promedio de los valores de una colección. Los valores Null se pasan por alto.

**Argumentos**

`Int32` ,`Int64`, Y .`Decimal` `Double`

**Valor devuelto**

Tipo de `expression`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (colección)
 
 Devuelve la suma de comprobación de los valores de una colección. Los valores Null se pasan por alto.
 
 **Argumentos**
 
 Colección (`Int32`).
 
 **Valor devuelto**
 
 Una clase `Int32`.
 
 **Ejemplo**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>COUNT (expresión)

Devuelve el número de elementos de una colección como un valor `Int32`.

**Argumentos**

Colección\<t >, donde t es uno de los tipos siguientes:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(no se devuelve en SQL Server 2000)|

**Valor devuelto**

Una clase `Int32`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[! code-SQL[DP EntityServices conceptos # SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="count_bigexpression"></a>COUNT_BIG (expresión)
 
 Devuelve el número de elementos de una colección como un valor `bigint`.
 
 **Argumentos**
 
 Colección (T), donde T es uno de los tipos siguientes:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(no se devuelve en SQL Server 2000)|

**Valor devuelto**

Una clase `Int64`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX (expresión)

Devuelve el valor máximo de la colección.

**Argumentos**

Colección (T), donde T es uno de los tipos siguientes: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valor devuelto**

Tipo de `expression`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN (expresión)

Devuelve el valor mínimo de una colección.

**Argumentos**

Colección (T), donde T es uno de los tipos siguientes: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valor devuelto**

Tipo de `expression`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV (expresión)

Devuelve la desviación estándar estadística de todos los valores de la expresión especificada.

**Argumentos**

Colección (`Double`).

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP (expresión)

Devuelve la desviación estándar estadística de la población para todos los valores de la expresión especificada.

**Argumentos**

Colección (`Double`).

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM (expresión)

Devuelve la suma de todos los valores de la colección.

**Argumentos**

Colección (T), donde T es uno de los tipos siguientes: `Int32`, `Int64`, `Double`, `Decimal`.

**Valor devuelto**

Tipo de `expression`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR (expresión)

Devuelve la varianza estadística de todos los valores de la expresión especificada.

**Argumentos**

Colección (`Double`).

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP (expresión)

Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.

**Argumentos**

Colección (`Double`).

**Valor devuelto**

Objeto `Double`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>Vea también

Para obtener más información sobre las funciones de agregado que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SQLCLIENT:

- **SQL Server 2005:** [Funciones de agregado (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))
- **SQL Server 2008 y versiones posteriores:** [Funciones de agregado (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)

- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
- [Funciones canónicas de agregado](./language-reference/aggregate-canonical-functions.md)
