---
title: Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: 495a662cbab84c2686e4c31945c30d6f82d117cb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153123"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server

En este tema se describe cómo se asignan las funciones canónicas del modelo conceptual a las funciones de SQL Server correspondientes.  
  
## <a name="date-and-time-functions"></a>Funciones de fecha y hora  

 En la tabla siguiente se describe la asignación de funciones de fecha y hora:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[AddDays(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime(año, mes, día, hora, minuto, segundo)](./language-reference/date-and-time-canonical-functions.md)|En SQL Server 2000 y SQL Server 2005, se crea un valor con formato `datetime` en el servidor. En SQL Server 2008 y versiones posteriores, se crea un valor `datetime2` en el servidor.|  
|[CreateDateTimeOffset(año, mes, día, hora, minuto, segundo, tzoffset)](./language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `datetimeoffset` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CreateTime(hora, minuto, segundo)](./language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `time` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentDateTime ()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` en SQL Server 2008.<br /><br /> `GetDate()` en SQL Server 2000 y SQL Server 2005.|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` en SQL Server 2008.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentUtcDateTime()](./language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` en SQL Server 2008. `GetUtcDate()` en SQL Server 2000 y SQL Server 2005.|  
|[DayOfYear(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears(expresión_inicial, expresión_final)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hora(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expresión)](./language-reference/date-and-time-canonical-functions.md)|Por SQL Server 2000 y SQL Server 2005, `datetime` se crea un valor con formato truncado en el servidor. En SQL Server 2008 y versiones posteriores, `datetime2` se crea un valor o truncado `datetimeoffset` en el servidor.|  
|[Year(expresión)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Funciones de agregado  

 En la tabla siguiente se describe la asignación de funciones de agregado:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Avg(expresión)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expresión)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count (expresión)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min (expresión)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max (expresión)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expresión)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expresión)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[SUM (expresión)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expresión)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expresión)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Funciones matemáticas  

 En la tabla siguiente se describe la asignación de las funciones matemáticas:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Abs(valor)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(valor)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(valor)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(valor)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(valor)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncar](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Funciones de cadena  

 En la tabla siguiente se describe la asignación de las funciones de cadena:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Contains(cadena, destino)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat(cadena1, cadena2)](./language-reference/string-canonical-functions.md)|cadena1 + cadena2|  
|[EndsWith(cadena, destino)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Nota:** La `CHARINDEX` función devuelve `false` si el `string` está almacenado en una columna de cadena de longitud fija y `target` es una constante. En este caso, se buscará en toda la cadena, incluyendo los espacios finales de relleno que pueda haber. Una posible solución alternativa es recortar los datos de la cadena de longitud fija antes de pasar esta a la función `EndsWith`, como en el ejemplo siguiente: `EndsWith(TRIM(string), target)`|  
|[IndexOf(destino, cadena2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (cadena1, longitud)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (cadena)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(cadena)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (cadena1, longitud)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(cadena)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (cadena1, cadena2, cadena3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[REVERSE (cadena)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(cadena)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith(cadena, destino)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring(cadena, inicio, longitud)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(cadena)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(cadena)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Funciones bit a bit  

 En la tabla siguiente se describe la asignación de las funciones bit a bit:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[BitWiseAnd (valor1, valor2)](./language-reference/bitwise-canonical-functions.md)|valor1 & valor2|  
|[BitWiseNot (valor)](./language-reference/bitwise-canonical-functions.md)|~valor|  
|[BitWiseOr (valor1, valor2)](./language-reference/bitwise-canonical-functions.md)|valor1 &#124; valor2|  
|[BitWiseXor (valor1, valor2)](./language-reference/bitwise-canonical-functions.md)|valor1 ^ valor2|
