---
title: "Asignaci&#243;n entre las funciones can&#243;nicas del modelo conceptual y las funciones de SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Asignaci&#243;n entre las funciones can&#243;nicas del modelo conceptual y las funciones de SQL Server
En este tema se describe cómo se asignan las funciones canónicas del modelo conceptual a las funciones de SQL Server correspondientes.  
  
## Funciones de fecha y hora  
 En la tabla siguiente se describe la asignación de funciones de fecha y hora:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|-----------------------------|  
|[AddDays\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime\(año, mes, día, hora, minuto, segundo\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|En SQL Server 2000 y SQL Server 2005, se crea un valor con formato `datetime` en el servidor.  En SQL Server 2008 y versiones posteriores, se crea un valor `datetime2` en el servidor.|  
|[CreateDateTimeOffset\(año, mes, día, hora, minuto, segundo, tzoffset\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `datetimeoffset` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CreateTime\(hora, minuto, segundo\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Se crea un valor con formato `time` en el servidor.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentDateTime\(\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` en SQL Server 2008.<br /><br /> `GetDate()` en SQL Server 2000 y SQL Server 2005.|  
|[CurrentDateTimeOffset\(\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` en SQL Server 2008.<br /><br /> No se admite en SQL Server 2000 ni en SQL Server 2005.|  
|[CurrentUtcDateTime\(\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` en SQL Server 2008.  `GetUtcDate()` en SQL Server 2000 y SQL Server 2005.|  
|[DayOfYear\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears\(expresión\_inicial, expresión\_final\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes\(DateTimeOffset\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hora\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|En SQL Server 2000 y SQL Server 2005, se crea un valor con formato `datetime` ``  truncado en el servidor.  En SQL Server 2008 y versiones posteriores, se crea un valor  `` `datetime2` o  `` `datetimeoffset` truncado en el servidor.|  
|[Year\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## Funciones de agregado  
 En la tabla siguiente se describe la asignación de funciones de agregado:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|-----------------------------|  
|[Avg\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP\(expresión\)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## Funciones matemáticas  
 En la tabla siguiente se describe la asignación de las funciones matemáticas:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|-----------------------------|  
|[Abs\(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling\(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor\(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power\(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round\(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## Funciones de cadena  
 En la tabla siguiente se describe la asignación de las funciones de cadena:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|-----------------------------|  
|[Contains\(cadena, destino\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat\(cadena1, cadena2\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|cadena1 \+ cadena2|  
|[EndsWith\(cadena, destino\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Nota** La función `CHARINDEX` devuelve `false` si el parámetro `string` está almacenado en una columna de cadena de longitud fija y `target` es una constante.  En este caso, se buscará en toda la cadena, incluyendo los espacios finales de relleno que pueda haber.  Una posible solución alternativa es recortar los datos de la cadena de longitud fija antes de pasar esta a la función `EndsWith`, como en el ejemplo siguiente: `EndsWith(TRIM(string), target)`|  
|[IndexOf\(destino, cadena2\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left \(cadena1, longitud\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length \(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim\(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right \(cadena1, longitud\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim\(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace \(cadena1, cadena2, cadena3\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse \(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim\(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith\(cadena, destino\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring\(cadena, inicio, longitud\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower\(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper\(cadena\)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## Funciones bit a bit  
 En la tabla siguiente se describe la asignación de las funciones bit a bit:  
  
|Funciones canónicas|Funciones de SQL Server|  
|-------------------------|-----------------------------|  
|[BitWiseAnd \(valor1, valor2\)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot \(valor\)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~valor|  
|[BitWiseOr \(valor1, valor2\)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|valor1 &#124; valor2|  
|[BitWiseXor \(valor1, valor2\)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|valor1 ^ valor2|