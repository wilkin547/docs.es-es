---
title: "Conversión entre DateTime y DateTimeOffset"
description: "Conversión entre DateTime y DateTimeOffset"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fab3af5b-5d0f-4384-a40a-1b5d99b30dd1
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2ba70e9ea39148d040bdb46d5e00ea50dcbb8980
ms.lasthandoff: 03/02/2017

---

# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque la estructura [System.DateTimeOffset](xref:System.DateTimeOffset) proporciona un mayor grado de reconocimiento de la zona horaria que la estructura [System.DateTime](xref:System.DateTime), los parámetros [DateTime](xref:System.DateTime) se usan con más frecuencia en las llamadas a métodos. Por eso, la capacidad de convertir valores [DateTimeOffset](xref:System.DateTimeOffset) en valores [DateTime](xref:System.DateTime) y viceversa resulta especialmente importante. En este artículo se muestra cómo realizar estas conversiones de manera que se conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Los tipos [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) tienen algunas limitaciones para la representación de horas en zonas horarias. Con su propiedad [Kind](xref:System.DateTime.Kind), [DateTime](xref:System.DateTime) solo puede reflejar la hora universal coordinada (UTC) y la zona horaria local del sistema. [DateTimeOffset](xref:System.DateTimeOffset) refleja la diferencia horaria respecto de la hora UTC, pero no la zona horaria real a la que pertenece esa diferencia horaria. Para conocer detalles sobre los valores de hora y la compatibilidad con las zonas horarias, consulte [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

La estructura [DateTimeOffset](xref:System.DateTimeOffset) ofrece dos maneras equivalentes de realizar la conversión de [DateTime](xref:System.DateTime) a [DateTimeOffset](xref:System.DateTimeOffset) adecuadas para la mayoría de las conversiones:

* El constructor [DateTimeOffset(DateTime)](xref:System.DateTimeOffset), que crea un nuevo objeto [DateTimeOffset](xref:System.DateTimeOffset) basado en un valor [DateTime](xref:System.DateTime).

* El operador de conversión implícito, que permite asignar un valor [DateTime](xref:System.DateTime) a un objeto [DateTimeOffset](xref:System.DateTimeOffset).

En el caso de los valores [DateTime](xref:System.DateTime) UTC y local, la propiedad [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) del valor resultante [DateTimeOffset](xref:System.DateTimeOffset) refleja con exactitud la diferencia horaria de la zona horaria local o UTC. Por ejemplo, el código siguiente convierte una hora UTC a su valor [DateTimeOffset](xref:System.DateTimeOffset) equivalente. 

```csharp
DateTime utcTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
utcTime1 = DateTime.SpecifyKind(utcTime1, DateTimeKind.Utc);
DateTimeOffset utcTime2 = utcTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  utcTime1, 
                  utcTime1.Kind.ToString(), 
                  utcTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM +00:00
```

```vb
Dim utcTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, _
                                        DateTimeKind.Utc)
Dim utcTime2 As DateTimeOffset = utcTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  utcTime1, _
                  utcTime1.Kind.ToString(), _
                  utcTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM  +00:00
```

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. Del mismo modo, el código siguiente convierte una hora local a su valor [DateTimeOffset](xref:System.DateTimeOffset) equivalente.

```csharp
DateTime localTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
localTime1 = DateTime.SpecifyKind(localTime1, DateTimeKind.Local);
DateTimeOffset localTime2 = localTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  localTime1, 
                  localTime1.Kind.ToString(), 
                  localTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim localTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, DateTimeKind.Local)
Dim localTime2 As DateTimeOffset = localTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  localTime1, _
                  localTime1.Kind.ToString(), _
                  localTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

Pero en el caso de los valores [DateTime](xref:System.DateTime) cuya propiedad [Kind](xref:System.DateTime.Kind) es [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), estos dos métodos de conversión generan un valor [DateTimeOffset](xref:System.DateTimeOffset) cuya diferencia horaria es la de la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en los EE. UU. Zona horaria estándar del Pacífico.

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);  // Kind is DateTimeKind.Unspecified
DateTimeOffset time2 = time1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  time1, 
                  time1.Kind.ToString(), 
                  time2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Dim time2 As DateTimeOffset = time1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  time1, _
                  time1.Kind.ToString(), _
                  time2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

Si el valor [DateTime](xref:System.DateTime) refleja la fecha y la hora en algo distinto a la zona horaria local o UTC, puede convertirlo a un valor [DateTimeOffset](xref:System.DateTimeOffset) y conservar su información de zona horaria si llama al constructor sobrecargado [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset). Por ejemplo, en el ejemplo siguiente se crea una instancia del objeto [DateTimeOffset](xref:System.DateTimeOffset) que refleja la hora estándar central.

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);     // Kind is DateTimeKind.Unspecified
try
{
   DateTimeOffset time2 = new DateTimeOffset(time1, 
                  TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)); 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", 
                     time1, 
                     time1.Kind.ToString(), 
                     time2);
}
// Handle exception if time zone is not defined in registry
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to identify target time zone for conversion.");
}
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Try
   Dim time2 As New DateTimeOffset(time1, _
                    TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)) 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", _
                     time1, _
                     time1.Kind.ToString(), _
                     time2)
' Handle exception if time zone is not defined in registry
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to identify target time zone for conversion.")
End Try
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

Debería recuperarse el segundo parámetro de este constructor sobrecargado, un objeto [System.TimeSpan](xref:System.TimeSpan) que representa la diferencia horaria con respecto a UTC, mediante una llamada al método [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) de la zona horaria correspondiente a la hora. El parámetro único del método es el valor [DateTime](xref:System.DateTime) que representa la fecha y la hora que se van a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

La propiedad [DateTime](xref:System.DateTime) se usa normalmente para realizar conversiones de [DateTimeOffset](xref:System.DateTimeOffset) a [DateTime](xref:System.DateTime). Pero devuelve un valor [DateTime](xref:System.DateTime) cuya propiedad [Kind](xref:System.DateTime.Kind) es [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), como se muestra en el ejemplo siguiente. 

```csharp
DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset sourceTime;
DateTime targetTime;

// Convert UTC to DateTime value
sourceTime = new DateTimeOffset(baseTime, TimeSpan.Zero);
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert local time to DateTime value
sourceTime = new DateTimeOffset(baseTime, 
                                TimeZoneInfo.Local.GetUtcOffset(baseTime));
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert Central Standard Time to a DateTime value
try
{
   TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime);
   sourceTime = new DateTimeOffset(baseTime, offset);
   targetTime = sourceTime.DateTime;
   Console.WriteLine("{0} converts to {1} {2}", 
                     sourceTime, 
                     targetTime, 
                     targetTime.Kind.ToString());
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.");
} 
// This example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

```vb
Const baseTime As Date = #06/19/2008 7:00AM#
Dim sourceTime As DateTimeOffset
Dim targetTime As Date

' Convert UTC to DateTime value
sourceTime = New DateTimeOffset(baseTime, TimeSpan.Zero)
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert local time to DateTime value
sourceTime = New DateTimeOffset(baseTime, _
                                TimeZoneInfo.Local.GetUtcOffset(baseTime))
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert Central Standard Time to a DateTime value
Try
   Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime)
   sourceTime = New DateTimeOffset(baseTime, offset)
   targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.")
End Try 
' This example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

Esto significa que cualquier información sobre la relación del valor [DateTimeOffset](xref:System.DateTimeOffset) con UTC se pierde durante la conversión cuando se usa la propiedad [DateTime](xref:System.DateTime). Esto afecta a los valores [DateTimeOffset](xref:System.DateTimeOffset) que corresponden a la hora UTC o a la hora local del sistema, porque la estructura [DateTime](xref:System.DateTime) refleja únicamente esas dos zonas horarias en su propiedad [Kind](xref:System.DateTime.Kind).

Para conservar tanta información de zona horaria como sea posible al convertir un valor [DateTimeOffset](xref:System.DateTimeOffset) en [DateTime](xref:System.DateTime), puede usar las propiedades [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) y [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime). 

## <a name="converting-a-utc-time"></a>Conversión de una hora UTC

Para indicar que un valor [DateTime](xref:System.DateTime) convertido es la hora UTC, puede recuperar el valor de la propiedad [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime). Difiere de la propiedad [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) de dos maneras:

* Devuelve un valor [DateTime](xref:System.DateTime) cuya propiedad [Kind](xref:System.DateTime.Kind) es [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

* Si el valor de la propiedad [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) no es igual a [TimeSpan.Zero](xref:System.TimeSpan.Zero), convierte la hora a UTC.

> [!NOTE]
> Si la aplicación exige que los valores [DateTime](xref:System.DateTime) convertidos identifiquen inequívocamente un único punto en el tiempo, debería considerar el uso de la propiedad [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) para controlar todas las conversiones de [DateTimeOffset](xref:System.DateTimeOffset) a [DateTime](xref:System.DateTime).

El siguiente código usa la propiedad [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) para convertir un valor [DateTimeOffset](xref:System.DateTimeOffset) cuya diferencia horaria es igual a [TimeSpan.Zero](xref:System.TimeSpan.Zero) a un valor [DateTime](xref:System.DateTime).

```csharp
DateTimeOffset utcTime1 = new DateTimeOffset(2008, 6, 19, 7, 0, 0, TimeSpan.Zero);
DateTime utcTime2 = utcTime1.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

```vb
Dim utcTime1 As New DateTimeOffset(#06/19/2008 7:00AM#, TimeSpan.Zero)
Dim utcTime2 As Date = utcTime1.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

El código siguiente usa la propiedad UtcDateTime para realizar una conversión de zona horaria y una conversión de tipos en un valor [DateTimeOffset](xref:System.DateTimeOffset).

```csharp
DateTimeOffset originalTime = new DateTimeOffset(2008, 6, 19, 7, 0, 0, new TimeSpan(5, 0, 0));
DateTime utcTime = originalTime.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalTime, 
                  utcTime, 
                  utcTime.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

```vb
Dim originalTime As New DateTimeOffset(#6/19/2008 7:00AM#, _
                                       New TimeSpan(5, 0, 0))
Dim utcTime As Date = originalTime.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _ 
                  originalTime, _
                  utcTime, _
                  utcTime.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

## <a name="converting-a-local-time"></a>Conversión de una hora local

Para indicar que un valor [DateTimeOffset](xref:System.DateTimeOffset) representa la hora local, puede pasar el valor [DateTime](xref:System.DateTime) devuelto por la propiedad [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) al método estático [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)). El método devuelve la fecha y la hora que se le pasaron como su primer parámetro, pero establece la propiedad [Kind](xref:System.DateTime.Kind) en el valor especificado por su segundo parámetro. El siguiente código usa el método [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) al convertir un valor [DateTimeOffset](xref:System.DateTimeOffset) cuya diferencia horaria corresponde a la de la zona horaria local.

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset utcTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime utcTime2 = utcTime1.DateTime;
if (utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime))) 
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local);

Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim utcTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim utcTime2 As Date = utcTime1.DateTime
If utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime)) Then
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local)
End If   
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

También puede usar la propiedad [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) para convertir un valor [DateTimeOffset](xref:System.DateTimeOffset) a un valor local [DateTime](xref:System.DateTime). La propiedad [Kind](xref:System.DateTime.Kind) del valor [DateTime](xref:System.DateTime) devuelto es [DateTimeKind.Local](xref:System.DateTimeKind.Local). El siguiente código usa la propiedad [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) al convertir un valor [DateTimeOffset](xref:System.DateTimeOffset) cuya diferencia horaria corresponde a la de la zona horaria local.

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset localTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime localTime2 = localTime1.LocalDateTime;

Console.WriteLine("{0} converted to {1} {2}", 
                  localTime1, 
                  localTime2, 
                  localTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim localTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim localTime2 As Date = localTime1.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime1, _
                  localTime2, _
                  localTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local 
```

Cuando se recupera un valor [DateTime](xref:System.DateTime) mediante la propiedad [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime), el descriptor de acceso `get` de la propiedad primero convierte el valor [DateTimeOffset](xref:System.DateTimeOffset) a UTC y después lo convierte a la hora local mediante una llamada al método [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset). Esto significa que puede recuperar un valor desde la propiedad [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) para realizar una conversión de zona horaria al mismo tiempo que realiza una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. El código siguiente muestra el empleo de la propiedad [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) para realizar una conversión de zona horaria y de tipos.

```csharp
DateTimeOffset originalDate;
DateTime localDate;

// Convert time originating in a different time zone
originalDate = new DateTimeOffset(2008, 6, 18, 7, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// Convert time originating in a different time zone 
// so local time zone's adjustment rules are applied
originalDate = new DateTimeOffset(2007, 11, 4, 4, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
//       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

```vb
Dim originalDate As DateTimeOffset
Dim localDate As Date

' Convert time originating in a different time zone
originalDate = New DateTimeOffset(#06/19/2008 7:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' Convert time originating in a different time zone 
' so local time zone's adjustment rules are applied
originalDate = New DateTimeOffset(#11/04/2007 4:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
'       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

## <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

El ejemplo siguiente define un método denominado `ConvertFromDateTimeOffset` que convierte valores [DateTimeOffset](xref:System.DateTimeOffset) a valores [DateTime](xref:System.DateTime). En función de su diferencia horaria, determina si el valor [DateTimeOffset](xref:System.DateTimeOffset) es una hora UTC, una hora local o alguna otra y define la propiedad [Kind](xref:System.DateTime.Kind) del valor de fecha y hora devuelto en consecuencia. 

```csharp
static DateTime ConvertFromDateTimeOffset(DateTimeOffset dateTime)
{
   if (dateTime.Offset.Equals(TimeSpan.Zero))
      return dateTime.UtcDateTime;
   else if (dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime)))
      return DateTime.SpecifyKind(dateTime.DateTime, DateTimeKind.Local);
   else
      return dateTime.DateTime;   
}
```

```vb
Function ConvertFromDateTimeOffset(dateTime As DateTimeOffset) As Date
   If dateTime.Offset.Equals(TimeSpan.Zero) Then
      Return dateTime.UtcDateTime
   ElseIf dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime))
      Return Date.SpecifyKind(dateTime.DateTime, DateTimeKind.Local)
   Else
      Return dateTime.DateTime   
   End If
```

El ejemplo siguiente llama al método `ConvertFromDateTimeOffset` para convertir valores [DateTimeOffset](xref:System.DateTimeOffset) que representan una hora UTC, una hora local y una hora de los Estados Unidos. Zona horaria estándar central.

```csharp
DateTime timeComponent = new DateTime(2008, 6, 19, 7, 0, 0);
DateTime returnedDate; 

// Convert UTC time
DateTimeOffset utcTime = new DateTimeOffset(timeComponent, TimeSpan.Zero);
returnedDate = ConvertFromDateTimeOffset(utcTime); 
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert local time
DateTimeOffset localTime = new DateTimeOffset(timeComponent, 
                           TimeZoneInfo.Local.GetUtcOffset(timeComponent)); 
returnedDate = ConvertFromDateTimeOffset(localTime);                                          
Console.WriteLine("{0} converted to {1} {2}", 
                  localTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert Central Standard Time
DateTimeOffset cstTime = new DateTimeOffset(timeComponent, 
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent));
returnedDate = ConvertFromDateTimeOffset(cstTime);
Console.WriteLine("{0} converted to {1} {2}", 
                  cstTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());
// The example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
//    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
//    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

```vb
Dim timeComponent As Date = #06/19/2008 7:00AM#
Dim returnedDate As Date 

' Convert UTC time
Dim utcTime As New DateTimeOffset(timeComponent, TimeSpan.Zero)
returnedDate = ConvertFromDateTimeOffset(utcTime) 
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert local time
Dim localTime As New DateTimeOffset(timeComponent, _
                                    TimeZoneInfo.Local.GetUtcOffset(timeComponent)) 
returnedDate = ConvertFromDateTimeOffset(localTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert Central Standard Time
Dim cstTime As New DateTimeOffset(timeComponent, _
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent))
returnedDate = ConvertFromDateTimeOffset(cstTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  cstTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())
' The example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
'    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
'    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

* Supone que un valor de fecha y hora cuya diferencia horaria es [TimeSpan.Zero](xref:System.TimeSpan.Zero) representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Las zonas horarias también pueden tener una diferencia horaria de [cero](xref:System.TimeSpan.Zero).

* Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)





