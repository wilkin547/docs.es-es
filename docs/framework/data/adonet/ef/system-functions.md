---
title: Funciones del sistema
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 9b5455d63dca40834515b14bae2f35d3b54d2aee
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452440"
---
# <a name="system-functions"></a>Funciones del sistema
El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona las funciones del sistema siguientes:  
  
|Función|Descripción|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Devuelve el valor de suma. `CHECKSUM` se ha pensado para utilizarlo en la compilación de índices hash.<br /><br /> **Argumentos**<br /><br /> `value`: un `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`o `Guid`. Puede especificar uno, dos o tres valores.<br /><br /> **Valor devuelto**<br /><br /> Valor absoluto de la expresión especificada.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Genera la fecha actual y la hora en el formato interno de SQL Server para los valores `DateTime` con una precisión de 7 en SQL Server 2008 y una precisión de 3 en SQL Server 2005.<br /><br /> **Valor devuelto**<br /><br /> La fecha y la hora actuales del sistema como un `DateTime`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Devuelve el nombre del usuario actual.<br /><br /> **Valor devuelto**<br /><br /> Valor de tipo `String` ASCII.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Devuelve el número de bytes utilizados para representar cualquier expresión.<br /><br /> **Argumentos**<br /><br /> `expression`: un `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valor devuelto**<br /><br /> Tamaño de las propiedades en forma de un valor `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Devuelve el nombre de la estación de trabajo.<br /><br /> **Valor devuelto**<br /><br /> Valor de tipo `String` Unicode.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Determina si una expresión de entrada es una fecha válida.<br /><br /> **Argumentos**<br /><br /> `expression`: un `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valor devuelto**<br /><br /> Un valor de tipo `Int32`. Uno (1) si la expresión de entrada es una fecha válida. De lo contrario, es cero (0).<br /><br /> **Ejemplo**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Determina si una expresión es un tipo numérico válido.<br /><br /> **Argumentos**<br /><br /> `expression`: un `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valor devuelto**<br /><br /> Un valor de tipo `Int32`. Uno (1) si la expresión de entrada es una fecha válida. De lo contrario, es cero (0).<br /><br /> **Ejemplo**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Crea un valor único de tipo Guid.<br /><br /> **Valor devuelto**<br /><br /> `Guid`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Devuelve un nombre de usuario de base de datos a partir de un número de identificación especificado.<br /><br /> **Argumentos**<br /><br /> `expression`: número de identificación `Int32` asociado al usuario de una base de datos.<br /><br /> **Valor devuelto**<br /><br /> Valor de tipo `String` Unicode.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Para obtener más información sobre las funciones de `String` que SqlClient admite, consulte [funciones de cadena (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).
  
## <a name="see-also"></a>Consulte también

- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
- [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)
