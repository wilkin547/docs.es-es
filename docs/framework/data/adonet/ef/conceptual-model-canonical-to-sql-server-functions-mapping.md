---
title: "Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5c408b64beec87c62b2bb8274fe985187ba7e5e6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server
En este tema se describe cómo se asignan las funciones canónicas del modelo conceptual a las funciones de SQL Server correspondientes.  
  
## <a name="date-and-time-functions"></a>Funciones de fecha y hora  
 En la tabla siguiente se describe la asignación de funciones de fecha y hora:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[AddDays(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (año, mes, día, hora, minuto, segundo)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|En SQL Server 2000 y SQL Server 2005, se crea un valor con formato `datetime` en el servidor. En SQL Server 2008 y versiones posteriores, se crea un valor `datetime2` en el servidor.|  
|[CreateDateTimeOffset (año, mes, día, hora, minuto, segundo, tzoffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `datetimeoffset` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CreateTime (hora, minuto, segundo)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `time` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` en SQL Server 2008.<br /><br /> `GetDate()` en SQL Server 2000 y SQL Server 2005.|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` en SQL Server 2008.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` en SQL Server 2008. `GetUtcDate()` en SQL Server 2000 y SQL Server 2005.|  
|[DayOfYear(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays (Expresión_inicial, Expresión_final)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (Expresión_inicial, Expresión_final)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (Expresión_inicial, Expresión_final)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Para SQL Server 2000 y SQL Server 2005, un truncados `datetime` valor con formato se crea en el servidor. Para SQL Server 2008 y versiones posteriores, un truncados `datetime2` o `datetimeoffset` valor se crea en el servidor.|  
|[Year(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Funciones de agregado  
 En la tabla siguiente se describe la asignación de funciones de agregado:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Avg(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Funciones matemáticas  
 En la tabla siguiente se describe la asignación de las funciones matemáticas:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Abs(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Funciones de cadena  
 En la tabla siguiente se describe la asignación de las funciones de cadena:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[Contains(String, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (cadena1, cadena2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|cadena1 + cadena2|  
|[EndsWith (cadena, destino)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Tenga en cuenta** el `CHARINDEX` función devuelve `false` si la `string` se almacena en una columna de cadenas de longitud fija y `target` es una constante. En este caso, se buscará en toda la cadena, incluyendo los espacios finales de relleno que pueda haber. Una posible solución alternativa es recortar los datos de la cadena de longitud fija antes de pasar esta a la función `EndsWith`, como en el ejemplo siguiente: `EndsWith(TRIM(string), target)`|  
|[IndexOf (destino, cadena2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (cadena1, longitud)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (cadena)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (cadena1, longitud)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (cadena1, cadena2, cadena3)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (cadena)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith (cadena, destino)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (cadena, inicio, longitud)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Funciones bit a bit  
 En la tabla siguiente se describe la asignación de las funciones bit a bit:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|--------------------------|  
|[BitWiseAnd (valor1, valor2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot (value)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~valor|  
|[BitWiseOr (valor1, valor2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|valor1 &#124; valor2|  
|[BitWiseXor (valor1, valor2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|valor1 ^ valor2|
