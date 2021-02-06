---
description: 'Más información sobre: funciones de fecha y hora'
title: Funciones de fecha y hora
ms.date: 03/30/2017
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
ms.openlocfilehash: d8172a3b69f36c183d5288740d4a11e008a97428
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651033"
---
# <a name="date-and-time-functions"></a>Funciones de fecha y hora

El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de fecha y hora que realizan operaciones en un valor de entrada `System.DateTime` y devuelven un resultado `string`, numérico o `System.DateTime`. Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient. La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones. En la tabla siguiente se muestran las funciones de fecha y hora SqlClient.  
  
|Función|Descripción|  
|--------------|-----------------|  
|`DATEADD(datepart, number, date)`|Devuelve un valor `DateTime` nuevo que se basa en sumar un intervalo a la fecha especificada.<br /><br /> **Argumentos**<br /><br /> `datepart`: valor de tipo `String` que representa qué parte de la fecha se devuelve como el valor nuevo.<br /><br /> `number`: valor de tipo `Int32`, `Int64`, `Decimal` o `Double` que se usa para incrementar el valor de `datepart`.<br /><br /> `date:` Expresión que devuelve un `DateTime` , o `DateTimeOffset` , o `Time` con precisión = [0-7], o una cadena de caracteres en un formato de fecha.<br /><br /> **Valor devuelto**<br /><br /> Valor de tipo `DateTime`, `DateTimeOffset` o `Time` nuevo con precisión = [0-7].<br /><br /> **Ejemplo**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(datepart,startdate,enddate)`|Devuelve el número de límites de fecha y hora entre dos fechas especificadas.<br /><br /> **Argumentos**<br /><br /> `datepart`: `String` que representa la parte de la fecha para calcular la diferencia.<br /><br /> `startdate`: la fecha de comienzo para el cálculo es una expresión que devuelve un valor de tipo `DateTime`, `DateTimeOffset` o `Time` con precisión = [0-7], o una cadena de caracteres en formato de fecha.<br /><br /> `enddate:` Una fecha de finalización para el cálculo es una expresión que devuelve un `DateTime` valor de tipo, o `DateTimeOffset` `Time` con precisión = [0-7], o una cadena de caracteres en formato de fecha.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(datepart, date)`|Devuelve una cadena de caracteres que representa el datepart especificado de la fecha especificada.<br /><br /> **Argumentos**<br /><br /> `datepart`: valor de tipo `String` que representa qué parte de la fecha se devuelve como el valor nuevo.<br /><br /> `date`: expresión que devuelve un valor de tipo `DateTime,``DateTimeOffset` o `Time` con precisión = [0-7], o una cadena de caracteres en un formato de fecha.<br /><br /> **Valor devuelto**<br /><br /> La cadena de caracteres que representa el datepart especificado de la fecha especificada.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(datepart, date)`|Devuelve un número entero que representa el Datepart especificado de la fecha dada.<br /><br /> **Argumentos**<br /><br /> `datepart`: valor de tipo `String` que representa qué parte de la fecha se devuelve como el valor nuevo.<br /><br /> `date`: expresión que devuelve un valor de tipo `DateTime,``DateTimeOffset,` o `Time` con precisión = [0-7], o una cadena de caracteres en un formato de fecha.<br /><br /> **Valor devuelto**<br /><br /> El datepart especificado de la fecha especificada como un valor de tipo `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(date)`|Devuelve el día de la fecha especificada como un entero.<br /><br /> **Argumentos**<br /><br /> `date`: Una expresión de tipo `DateTime` o `DateTimeOffset` con precisión = 0-7.<br /><br /> **Valor devuelto**<br /><br /> Día de la fecha especificada como un valor de tipo `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Genera la fecha y hora actuales en el formato interno de SQL Server para los valores datetime.<br /><br /> **Valor devuelto**<br /><br /> La fecha y hora actuales del sistema como `DateTime` con una precisión de 3.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Devuelve el valor datetime en formato de hora universal coordinada (UTC) o del meridiano de Greenwich.<br /><br /> **Valor devuelto**<br /><br /> El valor `DateTime` con una precisión de 3 en formato UTC.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(date)`|Devuelve el mes de la fecha especificada como un número entero.<br /><br /> **Argumentos**<br /><br /> `date`: Una expresión de tipo `DateTime` o `DateTimeOffset` con precisión = 0-7.<br /><br /> **Valor devuelto**<br /><br /> Mes de la fecha especificada como un `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(date)`|Devuelve el año de la fecha especificada como un número entero.<br /><br /> **Argumentos**<br /><br /> `date`: Una expresión de tipo `DateTime` o `DateTimeOffset` con precisión = 0-7.<br /><br /> **Valor devuelto**<br /><br /> Año de la fecha especificada como un valor de tipo `Int32`.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Devuelve un valor `DateTime` con una precisión de 7.<br /><br /> **Valor devuelto**<br /><br /> Valor `DateTime` con una precisión de 7.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Devuelve el valor datetime en formato de hora universal coordinada (UTC) o del meridiano de Greenwich.<br /><br /> **Valor devuelto**<br /><br /> Valor `DateTime` con una precisión = 7 en formato UTC.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Devuelve un valor `DateTimeOffset` con una precisión de 7.<br /><br /> **Valor devuelto**<br /><br /> Valor `DateTimeOffset` con una precisión de 7 en formato UTC.<br /><br /> **Ejemplo**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Para obtener más información sobre las funciones de fecha y hora que SqlClient admite, vea [tipos de datos y funciones de fecha y hora (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).
  
## <a name="see-also"></a>Vea también

- [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)
