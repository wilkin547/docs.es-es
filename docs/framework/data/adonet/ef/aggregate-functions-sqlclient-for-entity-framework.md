---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 558e9f8480dd69e2277603e9bb1013acfbc29467
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funciones de agregado (SqlClient para Entity Framework)
El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado. Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.  
  
 En la tabla siguiente se muestran las funciones de agregado de SqlClient.  
  
|Función|Descripción|  
|--------------|-----------------|  
|`AVG(` `expression` `)`|Devuelve el promedio de los valores de una colección.<br /><br /> Los valores Null se pasan por alto.<br /><br /> **Argumentos**<br /><br /> Un `Int32`, `Int64`, `Double`, y `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]|  
|`CHECKSUM_AGG(` `collection` `)`|Devuelve la suma de comprobación de los valores de una colección.<br /><br /> Los valores Null se pasan por alto.<br /><br /> **Argumentos**<br /><br /> Colección (`Int32`).<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]|  
|`COUNT(` `expression` `)`|Devuelve el número de elementos de una colección como un valor `Int32`.<br /><br /> **Argumentos**<br /><br /> Colección (T), donde T es uno de los tipos siguientes:<br /><br /> `Guid` (no se devuelve en SQL Server 2000),<br /><br /> `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` o `Binary`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]|  
|`COUNT_BIG(` `expression` `)`|Devuelve el número de elementos de una colección como un valor `bigint`.<br /><br /> **Argumentos**<br /><br /> Colección (T), donde T es uno de los tipos siguientes:<br /><br /> `Guid` (no se devuelve en SQL Server 2000), `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` o `Binary`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int64`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]|  
|`MAX(` `expression` `)`|Devuelve el valor máximo de la colección.<br /><br /> **Argumentos**<br /><br /> Colección (T), donde T es uno de los tipos siguientes:`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]|  
|`MIN(` `expression` `)`|Devuelve el valor mínimo de una colección.<br /><br /> **Argumentos**<br /><br /> Colección (T), donde T es uno de los tipos siguientes: `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`.<br /><br /> `Binary`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]|  
|`STDEV(` `expression` `)`|Devuelve la desviación estándar estadística de todos los valores de la expresión especificada.<br /><br /> **Argumentos**<br /><br /> Colección (`Double`).<br /><br /> **Valor devuelto**<br /><br /> Objeto `Double`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]|  
|`STDEVP(` `expression` `)`|Devuelve la desviación estándar estadística de la población para todos los valores de la expresión especificada.<br /><br /> **Argumentos**<br /><br /> Colección (`Double`).<br /><br /> **Valor devuelto**<br /><br /> Objeto `Double`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]|  
|`SUM(` `expression` `)`|Devuelve la suma de todos los valores de la colección.<br /><br /> **Argumentos**<br /><br /> Colección (T), donde T es uno de los tipos siguientes: `Int32`, `Int64`, `Double`, `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]|  
|`VAR(` `expression` `)`|Devuelve la varianza estadística de todos los valores de la expresión especificada.<br /><br /> **Argumentos**<br /><br /> Colección (`Double`).<br /><br /> **Valor devuelto**<br /><br /> Objeto `Double`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]|  
|`VARP(` `expression` `)`|Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.<br /><br /> **Argumentos**<br /><br /> Colección (`Double`).<br /><br /> **Valor devuelto**<br /><br /> Objeto `Double`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]|  
  
 Para obtener más información sobre las funciones de agregado que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SQLCLIENT:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Funciones de agregado (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115906)|[Funciones de agregado (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkID=115903)|[Funciones de agregado (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115907)|  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Funciones canónicas de agregado](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
