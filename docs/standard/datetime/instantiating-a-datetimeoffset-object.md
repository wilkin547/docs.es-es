---
title: Crear instancias de un objeto DateTimeOffset
description: Crear instancias de un objeto DateTimeOffset
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 3b6e2cc973b9587cc9950ecd6898b8a321a01036

---

# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

La estructura [System.DateTimeOffset](xref:System.DateTimeOffset) ofrece varias maneras de crear nuevos valores [DateTimeOffset](xref:System.DateTimeOffset). Muchos de ellos se corresponden directamente con los métodos disponibles para crear instancias de nuevos valores [System.DateTime](xref:System.DateTime), con mejoras que le permiten especificar el desplazamiento del valor de fecha y hora de la hora universal coordinada (UTC). En concreto, puede crear instancias de un valor [DateTimeOffset](xref:System.DateTimeOffset) de las siguientes maneras:

* Mediante la llamada a un constructor [DateTimeOffset](xref:System.DateTimeOffset).

* Mediante la conversión implícita de un valor en [DateTimeOffset](xref:System.DateTimeOffset).

* Mediante el análisis de la representación de una cadena de una fecha y hora.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

Para los lenguajes que lo admiten, una de las maneras más comunes de crear instancias de un valor [DateTime](xref:System.DateTime) es proporcionar la fecha y la hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea un objeto [DateTime](xref:System.DateTime) cuyo valor es el 1 de enero de 2008, a las 10:00 AM.

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

Los valores [DateTimeOffset](xref:System.DateTimeOffset) también se pueden inicializar mediante literales de fecha y hora cuando se usan lenguajes que admiten literales de [DateTime](xref:System.DateTime). Por ejemplo, el siguiente código de Visual Basic crea un objeto [DateTimeOffset](xref:System.DateTimeOffset).

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

Como se muestra en la salida de la consola, el valor [DateTimeOffset](xref:System.DateTimeOffset) creado de esta forma se asigna al desplazamiento de la zona horaria local. Esto significa que un valor [DateTimeOffset](xref:System.DateTimeOffset) asignado mediante un literal de carácter no identifica un punto temporal único si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores de DateTimeOffset

El tipo [System.DateTimeOffset](xref:System.DateTimeOffset) define cinco constructores. Tres de ellos se corresponden directamente con constructores de [DateTime](xref:System.DateTime) con un parámetro adicional del tipo [System.TimeSpan](xref:System.TimeSpan) que define el desplazamiento de la fecha y la hora con respecto a UTC. Estos le permiten definir un valor [DateTimeOffset](xref:System.DateTimeOffset) basándose en el valor de sus componentes individuales de fecha y hora. Por ejemplo, el código siguiente usa estos tres constructores para crear instancias de objetos [DateTimeOffset](xref:System.DateTimeOffset) con valores idénticos de 1/7/2008 12:05 AM + 01:00.

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

Tenga en cuenta que, cuando el valor del objeto [DateTimeOffset](xref:System.DateTimeOffset) crea una instancia mediante un objeto [PersianCalendar](xref:System.Globalization.PersianCalendar) como uno de los argumentos de su constructor se muestra en la consola, y se expresa como una fecha en el calendario gregoriano en lugar de en el calendario persa. 

Los otros dos constructores crean un objeto [DateTimeOffset](xref:System.DateTimeOffset) de un valor DateTime. El primero de ellos tiene un único parámetro, el valor [DateTime](xref:System.DateTime) para la conversión a un valor [DateTimeOffset](xref:System.DateTimeOffset). El desplazamiento del valor resultante [DateTimeOffset](xref:System.DateTimeOffset) depende de la propiedad [Kind](xref:System.DateTime.Kind) del parámetro único del constructor [DateTime](xref:System.DateTime). Si su valor es [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), el desplazamiento se establece igual que [TimeSpan.Zero](xref:System.TimeSpan.Zero). De lo contrario, su desplazamiento se establece igual al de la zona horaria local. En el ejemplo siguiente se muestra el uso de este constructor para crear una instancia de objetos [DateTimeOffset](xref:System.DateTimeOffset) que representan la hora UTC y la zona horaria local:

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> Llamar a la sobrecarga del constructor [DateTimeOffset](xref:System.DateTimeOffset) que tiene un único parámetro [DateTime](xref:System.DateTime) es equivalente a realizar una conversión implícita de un valor [DateTime](xref:System.DateTime) a un valor [DateTimeOffset](xref:System.DateTimeOffset).

El segundo constructor que crea un objeto [DateTimeOffset](xref:System.DateTimeOffset) a partir de un valor [DateTime](xref:System.DateTime) tiene dos parámetros: el valor [DateTime](xref:System.DateTime) que se va a convertir y un valor [TimeSpan](xref:System.TimeSpan) que representa el desplazamiento de la fecha y la hora con respecto a UTC. Este valor de desplazamiento debe corresponder a la propiedad [Kind](xref:System.DateTime.Kind) del primer parámetro del constructor o se iniciará [System.ArgumentException](xref:System.ArgumentException). Si la propiedad [Kind](xref:System.DateTime.Kind) del primer parámetro es [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), el valor del segundo parámetro debe ser [TimeSpan.Zero](xref:System.TimeSpan.Zero). Si la propiedad [Kind](xref:System.DateTime.Kind) del primer parámetro es [DateTimeKind.Local](xref:System.DateTimeKind.Local), el valor del segundo parámetro debe ser el desplazamiento de la zona horaria del sistema local. Si la propiedad [Kind](xref:System.DateTime.Kind) del primer parámetro es [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), el desplazamiento puede ser cualquier valor válido. El código siguiente muestra las llamadas a este constructor para convertir los valores [DateTime](xref:System.DateTime) en valores [DateTimeOffset](xref:System.DateTimeOffset).

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a>Conversión de tipos implícita
 
El tipo [System.DateTimeOffset](xref:System.DateTimeOffset) admite una conversión de tipos implícita: de un valor [System.DateTime](xref:System.DateTime) a un valor [DateTimeOffset](xref:System.DateTimeOffset). (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

El desplazamiento del valor resultante [DateTimeOffset](xref:System.DateTimeOffset) depende del valor de la propiedad DateTime.Kind](xref:System.DateTime.Kind). Si su valor es [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), el desplazamiento se establece igual que [TimeSpan.Zero](xref:System.TimeSpan.Zero). Si su valor es [DateTimeKind.Local](xref:System.DateTimeKind.Local) o [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), el ajuste se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Análisis de la representación de una cadena de una fecha y hora

El tipo [System.DateTimeOffset](xref:System.DateTimeOffset) admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un valor [DateTimeOffset](xref:System.DateTimeOffset):

* [Parse](xref:System.DateTimeOffset.Parse(System.String)), que intenta convertir la representación de la cadena de una fecha y hora en un valor [DateTimeOffset](xref:System.DateTimeOffset) e inicia una excepción si se produce un error en la conversión.

* [TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), que intenta convertir la representación de la cadena de una fecha y hora en un valor [DateTimeOffset](xref:System.DateTimeOffset) y devuelve `false` si se produce un error en la conversión.

* [ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), que intenta convertir la representación de la cadena de una fecha y hora en un formato especificado para un valor [DateTimeOffset](xref:System.DateTimeOffset). El método inicia una excepción si se produce un error en la conversión.

* [TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), que intenta convertir la representación de la cadena de una fecha y hora en un formato especificado para un valor [DateTimeOffset](xref:System.DateTimeOffset). El método devuelve `false` si se produce un error de conversión.

En el ejemplo siguiente se muestran llamadas a cada uno de estos cuatro métodos de conversión de cadena para crear instancias de un valor [DateTimeOffset](xref:System.DateTimeOffset).

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)




<!--HONumber=Nov16_HO3-->


