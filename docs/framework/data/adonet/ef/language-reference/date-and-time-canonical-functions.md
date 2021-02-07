---
description: 'Más información sobre: funciones canónicas de fecha y hora'
title: Funciones canónicas de fecha y hora
ms.date: 03/30/2017
ms.assetid: 9628b74f-1585-436a-b385-8b02ed0cdd63
ms.openlocfilehash: 3c57edc613e5ef871aa3359ef7609e6c0892efc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724796"
---
# <a name="date-and-time-canonical-functions"></a>Funciones canónicas de fecha y hora

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] incluye funciones canónicas de fecha y hora.  
  
## <a name="remarks"></a>Observaciones  

 En la tabla siguiente se muestran las funciones canónicas de fecha y hora [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . `datetime` es un <xref:System.DateTime> valor.  
  
|Función|Descripción|  
|--------------|-----------------|  
|`AddNanoseconds(expression,number)`|Agrega el `number` de nanosegundos especificado a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddMicroseconds(expression,number)`|Agrega el objeto especificado `number` de microsegundos a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddMilliseconds(expression,number)`|Agrega el objeto especificado `number` de milisegundos a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddSeconds(expression,number)`|Agrega el objeto especificado `number` de segundos a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddMinutes(expression,number)`|Agrega el objeto especificado `number` de minutos a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddHours(expression,number)`|Agrega el objeto especificado `number` de horas a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` o `Time`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddDays(expression,number)`|Agrega el objeto especificado `number` de días a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime` o `DateTimeOffset`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddMonths(expression,number)`|Agrega el objeto especificado `number` de meses a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime` o `DateTimeOffset`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`AddYears(expression,number)`|Agrega el objeto especificado `number` de años a `expression`.<br /><br /> **Argumentos**<br /><br /> `expression`: `DateTime` o `DateTimeOffset`.<br /><br /> `number`: `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`CreateDateTime(year,month,day,hour,minute,second)`|Devuelve un valor `DateTime` nuevo como fecha y hora actuales del servidor en la zona horaria del servidor.<br /><br /> **Argumentos**<br /><br /> `year`, `month`, `day`, `hour`, `minute`: `Int16` y `Int32`.<br /><br /> `second`: `Double`.<br /><br /> **Valor devuelto**<br /><br /> Objeto `DateTime`.|  
|`CreateDateTimeOffset(year,month,day,hour,minute,second,tzoffset)`|Devuelve un valor `DateTimeOffset` nuevo como una fecha y hora del servidor relativo a la hora universal coordinada (UTC).<br /><br /> **Argumentos**<br /><br /> `year`, `month`, `day`, `hour`, `minute`, `tzoffset`: `Int32`.<br /><br /> `second`: `Double`.<br /><br /> **Valor devuelto**<br /><br /> Objeto `DateTimeOffset`.|  
|`CreateTime(hour,minute,second)`|Devuelve un valor `Time` nuevo como la hora actual.<br /><br /> **Argumentos**<br /><br /> `hour` y `minute`: `Int32`.<br /><br /> `second`: `Double`.<br /><br /> **Valor devuelto**<br /><br /> Objeto `Time`.|  
|`CurrentDateTime()`|Devuelve un valor `DateTime` como fecha y hora actuales del servidor en la zona horaria del servidor.<br /><br /> **Valor devuelto**<br /><br /> Objeto `DateTime`.|  
|`CurrentDateTimeOffset()`|Devuelve la fecha, la hora y el desplazamiento actuales como un objeto `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Objeto `DateTimeOffset`.|  
|`CurrentUtcDateTime()`|Devuelve un valor <xref:System.DateTime> como fecha y hora actuales del servidor en la zona horaria UTS.<br /><br /> **Valor devuelto**<br /><br /> Objeto `DateTime`.|  
|`Day(expression)`|Devuelve la parte de día de `expression` como un valor `Int32` entre 1 y 31.<br /><br /> **Argumentos**<br /><br /> `DateTime` y `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 12.`<br /><br /> `Day(cast('03/12/1998' as DateTime))`|  
|`DayOfYear(expression)`|Devuelve la parte de día de `expression` como un objeto `Int32` entre 1 y 366, donde 366 corresponde al último día de un año bisiesto.<br /><br /> **Argumentos**<br /><br /> `DateTime` o `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffNanoseconds(startExpression,endExpression)`|Devuelve la diferencia, en nanosegundos, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffMilliseconds(startExpression,endExpression)`|Devuelve la diferencia, en milisegundos, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffMicroseconds(startExpression,endExpression)`|Devuelve la diferencia, en microsegundos, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffSeconds(startExpression,endExpression)`|Devuelve la diferencia, en segundos, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffMinutes(startExpression,endExpression)`|Devuelve la diferencia, en minutos, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffHours(startExpression,endExpression)`|Devuelve la diferencia, en horas, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` o `Time`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffDays(startExpression,endExpression)`|Devuelve la diferencia, en días, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime` o `DateTimeOffset`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffMonths(startExpression,endExpression)`|Devuelve la diferencia, en meses, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime` o `DateTimeOffset`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`DiffYears(startExpression,endExpression)`|Devuelve la diferencia, en años, entre `startExpression` y `endExpression`.<br /><br /> **Argumentos**<br /><br /> `startExpression`, `endExpression`: `DateTime` o `DateTimeOffset`. **Nota:** `startExpression` y `endExpression` deben ser del mismo tipo.   <br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`GetTotalOffsetMinutes(datetimeoffset)`|Devuelve el número de minutos que constituyen el desplazamiento de `datetimeoffset` con respecto a GMT. Este valor está comprendido generalmente entre +780 y -780 (+ o - 13 horas). **Nota:**  Esta función solo se admite en SQL Server 2008. <br /><br /> **Argumentos**<br /><br /> Objeto `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`Hour(expression)`|Devuelve la parte de hora de `expression` como un valor `Int32` entre 0 y 23.<br /><br /> **Argumentos**<br /><br /> `DateTime, Time` y `DateTimeOffset`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 22.`<br /><br /> `Hour(cast('22:35:5' as DateTime))`|  
|`Millisecond(expression)`|Devuelve la parte de milisegundos de `expression` como un valor `Int32` entre 0 y 999.<br /><br /> **Argumentos**<br /><br /> `DateTime, Time` y `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.|  
|`Minute(expression)`|Devuelve la parte de minutos de `expression` como un valor `Int32` entre 0 y 59.<br /><br /> **Argumentos**<br /><br /> `DateTime, Time` o `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 35`<br /><br /> `Minute(cast('22:35:5' as DateTime))`|  
|`Month(expression)`|Devuelve la parte de mes de `expression` como un valor `Int32` entre 1 y 12.<br /><br /> **Argumentos**<br /><br /> `DateTime` o `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 3.`<br /><br /> `Month(cast('03/12/1998' as DateTime))`|  
|`Second(expression)`|Devuelve la parte de segundos de `expression` como un valor `Int32` entre 0 y 59.<br /><br /> **Argumentos**<br /><br /> `DateTime, Time` y `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 5`<br /><br /> `Second(cast('22:35:5' as DateTime))`|  
|`TruncateTime(expression)`|Devuelve `expression`, con los valores de tiempo truncados.<br /><br /> **Argumentos**<br /><br /> `DateTime` o `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `expression`.|  
|`Year(expression)`|Devuelve la parte del año de `expression` como un `Int32` `YYYY` .<br /><br /> **Argumentos**<br /><br /> `DateTime` y `DateTimeOffset`.<br /><br /> **Valor devuelto**<br /><br /> Una clase `Int32`.<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 1998.`<br /><br /> `Year(cast('03/12/1998' as DateTime))`|  
  
 Estas funciones devolverán `null` si se proporciona la entrada `null`.  
  
 La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client. Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones canónicas](canonical-functions.md)
