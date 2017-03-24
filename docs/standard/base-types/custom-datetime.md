---
title: Cadenas con formato de fecha y hora personalizado
description: Cadenas con formato de fecha y hora personalizado
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 45f286f5-92c9-4150-957c-fa6d394bc29b
translationtype: Human Translation
ms.sourcegitcommit: 28625def4199a660fe0ea04ab75f4f65d2e0c9c4
ms.openlocfilehash: 285e4bfd6a53d576ce4538b09a2561065c93e399
ms.lasthandoff: 02/23/2017

---

# <a name="custom-date-and-time-format-strings"></a>Cadenas con formato de fecha y hora personalizado

Una cadena con formato de fecha y hora define la representación de texto de un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) que es el resultado de una operación de formato. También puede definir la representación de un valor de fecha y hora que se necesite en una operación de análisis para convertir correctamente la cadena en una fecha y hora. Una cadena de formato personalizado consta de uno o varios especificadores de formato de fecha y hora personalizado. Una cadena que no sea una [cadena con formato de fecha y hora estándar](standard-datetime.md) se interpreta como una cadena con formato de fecha y hora personalizado. 

Las cadenas con formato de fecha y hora personalizado se pueden usar con valores [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset).

En operaciones de formato, las cadenas de formato de fecha y hora personalizado se pueden usar con el método `ToString` de una instancia de fecha y hora o con un método que admita formato compuesto. En el ejemplo siguiente se muestran ambos usos. 

```csharp
DateTime thisDate1 = new DateTime(2011, 6, 10);
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".");

DateTimeOffset thisDate2 = new DateTimeOffset(2011, 6, 10, 15, 24, 16, 
                                              TimeSpan.Zero);
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2); 
// The example displays the following output:
//    Today is June 10, 2011.
//    The current date and time: 06/10/11 15:24:16 +00:00
```

```vb
Dim thisDate1 As Date = #6/10/2011#
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".")

Dim thisDate2 As New DateTimeOffset(2011, 6, 10, 15, 24, 16, TimeSpan.Zero)
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2) 
' The example displays the following output:
'    Today is June 10, 2011.
'    The current date and time: 06/10/11 15:24:16 +00:00
```

En las operaciones de análisis, las cadenas con formato de fecha y hora personalizado se pueden usar con los métodos [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) y [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)). Estos métodos necesitan que una cadena de entrada se ajuste exactamente a un modelo determinado para que la operación de análisis se realice correctamente. En el ejemplo siguiente se muestra una llamada al método [DateTimeOffset.ParseExact(String, String, IFormatProvider)](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) para analizar una fecha que debe incluir un día, un mes y un año de dos dígitos.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] dateValues = { "30-12-2011", "12-30-2011", 
                              "30-12-11", "12-30-11" };
      string pattern = "MM-dd-yy";
      DateTime parsedDate;

      foreach (var dateValue in dateValues) {
         if (DateTime.TryParseExact(dateValue, pattern, null, 
                                   DateTimeStyles.None, out parsedDate))
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate);
         else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue);
      }
   }
}
// The example displays the following output:
//    Unable to convert '30-12-2011' to a date and time.
//    Unable to convert '12-30-2011' to a date and time.
//    Unable to convert '30-12-11' to a date and time.
//    Converted '12-30-11' to 12/30/2011.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValues() As String = { "30-12-2011", "12-30-2011", 
                                      "30-12-11", "12-30-11" }
      Dim pattern As String = "MM-dd-yy"
      Dim parsedDate As Date

      For Each dateValue As String In dateValues
         If DateTime.TryParseExact(dateValue, pattern, Nothing, 
                                   DateTimeStyles.None, parsedDate) Then
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate)
         Else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue)
         End If                                                         
      Next
   End Sub
End Module
' The example displays the following output:
'    Unable to convert '30-12-2011' to a date and time.
'    Unable to convert '12-30-2011' to a date and time.
'    Unable to convert '30-12-11' to a date and time.
'    Converted '12-30-11' to 12/30/2011.
```

En la tabla siguiente se describen los especificadores de formato de fecha y hora personalizados, y se muestra la cadena de resultado producida por cada especificador de formato. De forma predeterminada, las cadenas de resultado reflejan las convenciones de formato de la referencia cultural en-us. Si un especificador de formato determinado genera una cadena de resultado localizada, el ejemplo también indica la referencia cultural a la que se aplica dicha cadena. Vea la sección Notas para obtener información adicional sobre cómo usar cadenas de formato de fecha y hora personalizado.

Especificador de formato | Descripción | Ejemplos
---------------- | ----------- | --------
"d" | El día del mes, de 1 a 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"dd" | El día del mes, de 01 a 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"ddd" | El nombre abreviado del día de la semana. | `2019-06-15T13:45:30 -> Mon (en-US)`; `2019-06-15T13:45:30 -> Пн (ru-RU)`; `2019-06-15T13:45:30 -> lun. (fr-FR)`
"dddd" | El nombre completo del día de la semana. | `2019-06-15T13:45:30 -> Monday (en-US)`; `2019-06-15T13:45:30 -> понедельник (ru-RU)`; `2019-06-15T13:45:30 -> lundi (fr-FR)`
"f" | Las décimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.05 -> 0` 
"ff" | Las centésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> 00`
"fff" | Los milisegundos de un valor de fecha y hora. | `6/15/2019 13:45:30.617 -> 617`; `6/15/2019 13:45:30.0005 -> 000`
"ffff" | Las diezmilésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175000 -> 6175`; `2019-06-15T13:45:30.0000500 -> 0000`
"fffff" | Las cienmilésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175400 -> 61754`; `6/15/2019 13:45:30.000005 -> 00000`
"ffffff" | Las millonésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> 000000`
"fffffff" | Las diezmillonésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175425 -> 6175425`;`2019-06-15T13:45:30.0001150 -> 0001150`
"F" | Si es distinto de cero, las décimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.0500000 -> (no output)`
"FF" | Si es distinto de cero, las centésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> (no output)`
"FFF" | Si es distinto de cero, los milisegundos de un valor de fecha y hora. | `2019-06-15T13:45:30.6170000 -> 617`; `2019-06-15T13:45:30.0005000 -> (no output)`
"FFFF" | Si es distinto de cero, las diezmilésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.5275000 -> 5275`; `2019-06-15T13:45:30.0000500 -> (no output)`
"FFFFF" | Si es distinto de cero, las cienmilésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175400 -> 61754`; `2019-06-15T13:45:30.0000050 -> (no output)`
"FFFFFF" | Si es distinto de cero, las millonésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> (no output)`
"FFFFFFF" | Si es distinto de cero, las diezmillonésimas de segundo de un valor de fecha y hora. | `2019-06-15T13:45:30.6175425 -> 6175425`; `2019-06-15T13:45:30.0001150 -> 000115`
"g", "gg" | El período o la era. | `2019-06-15T13:45:30.6170000 -> A.D.`
"h" | La hora, usando un reloj de 12 horas de 1 a 12. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 1`
"hh" | La hora, usando un reloj de 12 horas de 01 a 12. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 01`
"H" | La hora, usando un reloj de 24 horas de 0 a 23. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 13`
"HH" | La hora, usando un reloj de 24 horas de 00 a 23. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 13`
"K" | Información de la zona horaria. | Con valores [DateTime](xref:System.DateTime): `2019-06-15T13:45:30, Kind Unspecified ->`; `2019-06-15T13:45:30, Kind Utc -> Z`; `2019-06-15T13:45:30, Kind Local -> -07:00 (depends on local computer settings)`; Con valores [DateTimeOffset](xref:System.DateTimeOffset): `2019-06-15T01:45:30-07:00 --> -07:00`; `2019-06-15T08:45:30+00:00 --> +00:00`
"m" | Minutos, de 0 a 59. | `2019-06-15T01:09:30 -> 9`; `2019-06-15T13:29:30 -> 29`
"mm" | El minuto, de 00 a 59. | `2019-06-15T01:09:30 -> 09`; `2019-06-15T01:45:30 -> 45`
"M" | El mes, de 1 a 12. | `2019-06-15T13:45:30 -> 6`
"MM" | El mes, de 01 a 12. | `2019-06-15T13:45:30 -> 06`
"MMM" | El nombre abreviado del mes. | `2019-06-15T13:45:30 -> Jun (en-US)`; `2019-06-15T13:45:30 -> juin (fr-FR)`; `2019-06-15T13:45:30 -> Jun (zu-ZA)`
"MMMM" | El nombre completo del mes. | `2019-06-15T13:45:30 -> June (en-US)`; `2019-06-15T13:45:30 -> juni (da-DK)`; `2019-06-15T13:45:30 -> uJuni (zu-ZA)`
"s" | El segundo, de 0 a 59. | `2019-06-15T13:45:09 -> 9`
"ss" | El segundo, de 00 a 59. | `2019-06-15T13:45:09 -> 09`
"t" | El primer carácter del designador AM/PM. | `2019-06-15T13:45:30 -> P (en-US)`; `2019-06-15T13:45:30 -> 午 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"tt" | El designador AM/PM. | `2019-06-15T13:45:30 -> PM (en-US)`; `2019-06-15T13:45:30 -> 午後 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"y" | El año, de 0 a 99. | `0001-01-01T00:00:00 -> 1`; `0900-01-01T00:00:00 -> 0`; `1900-01-01T00:00:00 -> 0`; `2019-06-15T13:45:30 -> 9`; `2019-06-15T13:45:30 -> 19`
"yy" | El año, de 00 a 99. | `0001-01-01T00:00:00 -> 01`; `0900-01-01T00:00:00 -> 00`; `1900-01-01T00:00:00 -> 00`; `2019-06-15T13:45:30 -> 19`
"yyy" | El año, con un mínimo de tres dígitos. | `0001-01-01T00:00:00 -> 001`; `0900-01-01T00:00:00 -> 900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyy" | El año como un número de cuatro dígitos. | `0001-01-01T00:00:00 -> 0001`; `0900-01-01T00:00:00 -> 0900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyyy" | El año como un número de cinco dígitos. | `0001-01-01T00:00:00 -> 00001`; `2019-06-15T13:45:30 -> 02019`
"z" | Desfase de horas con respecto a la hora UTC, sin ceros iniciales. | `2019-06-15T13:45:30-07:00 -> -7`
"zz" | Desfase de horas con respecto a la hora UTC, con un cero inicial para un valor de un solo dígito. | `2019-06-15T13:45:30-07:00 -> -07`
"zzz" | Desfase de horas y minutos con respecto a la hora UTC. | `2019-06-15T13:45:30-07:00 -> -07:00`
":" | El separador de hora. | `2019-06-15T13:45:30 -> : (en-US)`; `2019-06-15T13:45:30 -> . (it-IT)`; `2019-06-15T13:45:30 -> : (ja-JP)`
"/" | El separador de fecha. | `2019-06-15T13:45:30 -> / (en-US)`; `2019-06-15T13:45:30 -> - (ar-DZ)`; `2019-06-15T13:45:30 -> . (tr-TR)`
"string", 'string' | Delimitador de cadena literal. | `2019-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P`; `2019-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P`
% | Define el siguiente carácter como un especificador de formato personalizado. | `2019-06-15T13:45:30 (%h) -> 1`
\ | El carácter de escape. | `2019-06-15T13:45:30 (h \h) -> 1 h`
Cualquier otro carácter | El carácter se copia en la cadena de resultado sin modificar. | `2019-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A`

En las secciones siguientes se proporciona información adicional sobre cada especificador de formato de fecha y hora personalizado. A menos que se indique lo contrario, cada especificador genera una representación de cadena idéntica independientemente de que se use con un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset). 

## <a name="the-d-custom-format-specifier"></a>Especificador de formato personalizado "d"

El especificador de formato personalizado "d" representa el día del mes como un número de 1 a 31. Un día con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "d" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "d". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "d" en varias cadenas de formato. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15); 

Console.WriteLine(date1.ToString("d, M", 
                  CultureInfo.InvariantCulture)); 
// Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays 29 agosto  
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("d, M", _
                  CultureInfo.InvariantCulture)) 
' Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays 29 agosto 
```

## <a name="the-dd-custom-format-specifier"></a>Especificador de formato personalizado "dd"

La cadena de formato personalizado "dd" representa el día del mes como un número de 01 a 31. Un día con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "dd" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-ddd-custom-format-specifier"></a>Especificador de formato personalizado "ddd"

El especificador de formato personalizado "ddd" representa el nombre abreviado del día de la semana. El nombre abreviado adaptado del día de la semana se recupera de la propiedad [DateTimeFormatInfo.AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) de la referencia cultural actual o especificada. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "ddd" en una cadena de formato personalizado. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-dddd-custom-format-specifier"></a>Especificador de formato personalizado "dddd"

El especificador de formato personalizado "dddd" (más cualquier número de especificadores "d" adicionales) representa el nombre completo del día de la semana. El nombre adaptado del día de la semana se recupera de la propiedad [DateTimeFormatInfo.DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) de la referencia cultural actual o especificada. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "dddd" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto                                          
```

## <a name="the-f-custom-format-specifier"></a>Especificador de formato personalizado "f"

El especificador de formato personalizado "f" representa el dígito más significativo de la fracción de segundos; es decir, representa las décimas de segundo de un valor de fecha y hora.

Si el especificador de formato "f" se usa sin otros especificadores de formato, se interpreta como el especificador de formato de fecha y hora estándar "f". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

Cuando se usan especificadores de formato "f" como parte de una cadena de formato proporcionada a los métodos [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) o [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), el número de especificadores de formato "f" indica el número de dígitos más significativos de la fracción de segundos que debe haber presentes para analizar la cadena correctamente.

En el ejemplo siguiente se incluye el especificador de formato personalizado "f" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Especificador de formato personalizado "ff"

El especificador de formato personalizado "ff" representa los dos dígitos más significativos de la fracción de segundos; es decir, representa las centésimas de segundo de un valor de fecha y hora. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "ff" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Especificador de formato personalizado "fff"

El especificador de formato personalizado "fff" representa los tres dígitos más significativos de la fracción de segundos; es decir, representa los milisegundos de un valor de fecha y hora. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "fff" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Especificador de formato personalizado "ffff"

El especificador de formato personalizado "ffff" representa los cuatro dígitos más significativos de la fracción de segundos; es decir, representa las diezmilésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las diezmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="the-fffff-custom-format-specifier"></a>Especificador de formato personalizado "fffff"

El especificador de formato personalizado "fffff" representa los cinco dígitos más significativos de la fracción de segundo; es decir, representa las cienmilésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las cienmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. 

## <a name="the-ffffff-custom-format-specifier"></a>Especificador de formato personalizado "ffffff"

El especificador de formato personalizado "ffffff" representa los seis dígitos más significativos de la fracción de segundos; es decir, representa las millonésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las millonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. 

## <a name="the-fffffff-custom-format-specifier"></a>Especificador de formato personalizado "fffffff"

El especificador de formato personalizado "fffffff" representa los siete dígitos más significativos de la fracción de segundos; es decir, representa las diezmillonésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las diezmillonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. 

## <a name="the-f-custom-format-specifier"></a>Especificador de formato personalizado "F"

El especificador de formato personalizado "F" representa el dígito más significativo de la fracción de segundos; es decir, representa las décimas de segundo de un valor de fecha y hora. Si el dígito es cero, no se muestra nada. 

Si el especificador de formato "F" se usa sin otros especificadores de formato, se interpreta como el especificador de formato de fecha y hora estándar "F". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

El número de especificadores de formato "F" usado con los métodos [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) o [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) indica el número máximo de dígitos más significativos de la fracción de segundos que puede haber presentes para analizar la cadena correctamente.

En el ejemplo siguiente se incluye el especificador de formato personalizado "F" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Especificador de formato personalizado "FF"

El especificador de formato personalizado "FF" representa los dos dígitos más significativos de la fracción de segundos; es decir, representa las centésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de dos ceros. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "FF" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Especificador de formato personalizado "FFF"

El especificador de formato personalizado "FFF" representa los tres dígitos más significativos de la fracción de segundos; es decir, representa los milisegundos de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de tres ceros. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "FFF" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
````

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Especificador de formato personalizado "FFFF"

El especificador de formato personalizado "FFFF" representa los cuatro dígitos más significativos de la fracción de segundos; es decir, representa las diezmilésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de cuatro ceros.

Si bien se puede mostrar el componente correspondiente a las diezmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="the-fffff-custom-format-specifier"></a>Especificador de formato personalizado "FFFFF"

El especificador de formato personalizado "FFFFF" representa los cinco dígitos más significativos de la fracción de segundos; es decir, representa las cienmilésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de cinco ceros.

Si bien se puede mostrar el componente correspondiente a las cienmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="the-ffffff-custom-format-specifier"></a>Especificador de formato personalizado "FFFFFF"

El especificador de formato personalizado "FFFFFF" representa los seis dígitos más significativos de la fracción de segundos; es decir, representa las millonésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de seis ceros.

Si bien se puede mostrar el componente correspondiente a las millonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="the-fffffff-custom-format-specifier"></a>Especificador de formato personalizado "FFFFFFF"

El especificador de formato personalizado "FFFFFFF" representa los siete dígitos más significativos de la fracción de segundos; es decir, representa las diezmillonésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de siete ceros.

Si bien se puede mostrar el componente correspondiente a las diezmillonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="the-g-or-gg-custom-format-specifier"></a>Especificador de formato personalizado "g" o "gg"

Los especificadores de formato personalizado "g" o "gg" (más cualquier número de especificadores "g" adicionales) representan el período o la era, como d.C. La operación de formato hace caso omiso de este especificador si la fecha a la que se va a dar formato no tiene una cadena de período o de era asociada. 

Si el especificador de formato "g" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "g". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "g" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(70, 08, 04);

Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.InvariantCulture));
// Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));                         
// Displays 08/04/0070 ap. J.-C.
```

```vb
Dim date1 As Date = #08/04/0070#

Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.InvariantCulture))
' Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))                         
' Displays 08/04/0070 ap. J.-C.
```

## <a name="the-h-custom-format-specifier"></a>Especificador de formato personalizado "h"

El especificador de formato personalizado "h" representa la hora como un número del 1 al 12; es decir, la hora se representa como en un reloj de 12 horas que cuenta las horas enteras desde medianoche o mediodía. Una hora determinada después de la medianoche no se distingue de la misma hora después del mediodía. No se redondea la hora y las horas con un solo dígito no tienen un cero inicial. Por ejemplo, dada una hora de 5:43 de la mañana o de la tarde, este especificador de formato personalizado muestra "5". 

Si el especificador de formato "h" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "h" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-hh-custom-format-specifier"></a>Especificador de formato personalizado "hh"

El especificador de formato personalizado "hh" (más cualquier número de especificadores "h" adicionales) representa la hora como un número del 01 al 12; es decir, la hora se representa como en un reloj de 12 horas que cuenta las horas enteras desde medianoche o mediodía. Una hora determinada después de la medianoche no se distingue de la misma hora después del mediodía. No se redondea la hora y las horas con un solo dígito tienen un cero inicial. Por ejemplo, dada una hora de 5:43 de la mañana o de la tarde, este especificador de formato muestra "05".

En el ejemplo siguiente se incluye el especificador de formato personalizado "hh" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-h-custom-format-specifier"></a>Especificador de formato personalizado "H"

El especificador de formato personalizado "H" representa la hora como un número del 0 al 23; es decir, la hora se representa como en un reloj de 24 horas de base cero que cuenta las horas desde medianoche. Una hora con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "H" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "H" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("H:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 6:09:01 
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("H:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 6:09:01 
```

## <a name="the-hh-custom-format-specifier"></a>Especificador de formato personalizado "HH"

El especificador de formato personalizado "HH" (más cualquier número de especificadores "H" adicionales) representa la hora como un número del 00 al 23; es decir, la hora se representa como en un reloj de 24 horas de base cero que cuenta las horas desde medianoche. Una hora con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "HH" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("HH:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01                        
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("HH:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01
```

## <a name="the-k-custom-format-specifier"></a>Especificador de formato personalizado "K"

El especificador de formato personalizado "K" representa la información de zona horaria de un valor de fecha y hora. Cuando este especificador de formato se usa con valores [DateTime](xref:System.DateTime), el valor de la propiedad [DateTime.Kind](xref:System.DateTime.Kind) define la cadena de resultado: 
 
* En la zona horaria local (un valor de propiedad [DateTime.Kind](xref:System.DateTime.Kind) de [DateTimeKind.Local](xref:System.DateTimeKind.Local)), este especificador es equivalente al especificador "zzz" y genera una cadena de resultado que contiene la diferencia horaria local con respecto a la hora universal coordinada (UTC); por ejemplo, "-07:00". 

* En una hora UTC (un valor de propiedad [DateTime.Kind](xref:System.DateTime.Kind) de [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)), la cadena de resultado incluye un carácter "Z" para representar una fecha UTC. 

* En una hora de una zona horaria no especificada (una hora cuya propiedad [DateTime.Kind](xref:System.DateTime.Kind) es igual a [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)), el resultado es equivalente a [String.Empty](xref:System.String#System_String_Empty). 

En los valores [DateTimeOffset](xref:System.DateTimeOffset), el especificador de formato "K" es equivalente al especificador de formato "zz" y genera una cadena de resultado que contiene la diferencia horaria del valor [DateTimeOffset](xref:System.DateTimeOffset) con respecto a la hora UTC. 

Si el especificador de formato "K" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se muestra la cadena que se obtiene al usar el especificador de formato personalizado "K" con varios valores [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) en un sistema de la zona horaria del Pacífico. de EE. UU.

```csharp
Console.WriteLine(DateTime.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTime.UtcNow.ToString("%K"));
// Displays Z      
Console.WriteLine("'{0}'", 
                  DateTime.SpecifyKind(DateTime.Now, 
                       DateTimeKind.Unspecified).ToString("%K"));
// Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"));
// Displays +00:00
Console.WriteLine(new DateTimeOffset(2008, 5, 1, 6, 30, 0, 
                      new TimeSpan(5, 0, 0)).ToString("%K"));
// Displays +05:00  
```

```vb
Console.WriteLine(Date.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(Date.UtcNow.ToString("%K"))
' Displays Z      
Console.WriteLine("'{0}'", _
                  Date.SpecifyKind(Date.Now, _
                                   DateTimeKind.Unspecified). _
                  ToString("%K"))
' Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"))
' Displays +00:00
Console.WriteLine(New DateTimeOffset(2008, 5, 1, 6, 30, 0, _
                                     New TimeSpan(5, 0, 0)). _
                  ToString("%K"))
' Displays +05:00 
```

## <a name="the-m-custom-format-specifier"></a>Especificador de formato personalizado "m"

El especificador de formato personalizado "m" representa el minuto como un número de 0 a 59. El minuto representa los minutos enteros que han transcurrido desde la última hora. Un minuto con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "m" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "m". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "m" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-mm-custom-format-specifier"></a>Especificador de formato personalizado "mm"

El especificador de formato personalizado "mm" (más cualquier número de especificadores "m" adicionales) representa el minuto como un número de 00 a 59. El minuto representa los minutos enteros que han transcurrido desde la última hora. Un minuto con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "mm" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-m-custom-format-specifier"></a>Especificador de formato personalizado "M"

El especificador de formato personalizado "M" representa el mes como un número del 1 al 12 (o del 1 al 13 para los calendarios con 13 meses). Un mes con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "M" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "M". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "M" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 18);
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("nl-NL")));                       
// Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("lv-LV")));                        
// Displays (8) Aug, augusts
```

```vb
Dim date1 As Date = #8/18/2008#
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("nl-NL")))                        
' Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("lv-LV")))                        
' Displays (8) Aug, augusts 
```

## <a name="the-mm-custom-format-specifier"></a>Especificador de formato personalizado "MM"

El especificador de formato personalizado "MM" representa el mes como un número del 01 al 12 (o del 1 al 13 para los calendarios con 13 meses). Un mes con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "MM" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-mmm-custom-format-specifier"></a>Especificador de formato personalizado "MMM"

El especificador de formato personalizado "MMM" representa el nombre abreviado del mes. El nombre abreviado adaptado del mes se recupera de la propiedad [DateTimeFormatInfo.AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) de la referencia cultural actual o especificada.

En el ejemplo siguiente se incluye el especificador de formato personalizado "MMM" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-mmmm-custom-format-specifier"></a>Especificador de formato personalizado "MMMM"

El especificador de formato personalizado "MMMM" representa el nombre completo del mes. El nombre adaptado del mes se recupera de la propiedad [DateTimeFormatInfo.MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) de la referencia cultural actual o especificada. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "MMMM" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto 
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto  
```

## <a name="the-s-custom-format-specifier"></a>Especificador de formato personalizado "s"

El especificador de formato personalizado "s" representa los segundos como un número de 0 a 59. El resultado representa los segundos enteros que han transcurrido desde el último minuto. Un segundo con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "s" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "s". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "s" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-ss-custom-format-specifier"></a>Especificador de formato personalizado "ss"

El especificador de formato personalizado "ss" (más cualquier número de especificadores "s" adicionales) representa los segundos como un número de 00 a 59. El resultado representa los segundos enteros que han transcurrido desde el último minuto. Un segundo con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "ss" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-t-custom-format-specifier"></a>Especificador de formato personalizado "t"

El especificador de formato personalizado "t" representa el primer carácter del designador AM/PM. El designador adaptado adecuado se recupera de la propiedad [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) o [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) de la referencia cultural actual o especificada. El designador AM se usa para todas las horas de 0:00:00 (medianoche) a 11:59:59.999. El designador PM se usa para todas las horas de 12:00:00 (mediodía) a 23:59:59.999. 

Si el especificador de formato "t" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "t". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "t" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-tt-custom-format-specifier"></a>Especificador de formato personalizado "tt"

El especificador de formato personalizado "tt" (más cualquier número de especificadores "t" adicionales) representa designador AM/PM completo. El designador adaptado adecuado se recupera de la propiedad [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) o [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) de la referencia cultural actual o especificada. El designador AM se usa para todas las horas de 0:00:00 (medianoche) a 11:59:59.999. El designador PM se usa para todas las horas de 12:00:00 (mediodía) a 23:59:59.999.

Asegúrese de usar el especificador "tt" para aquellos idiomas en los que sea necesario mantener la distinción entre a.m. y p.m. Un ejemplo es el japonés, en el que los designadores de a.m. y p.m. se diferencian en el segundo carácter en vez de en el primero.

En el ejemplo siguiente se incluye el especificador de formato personalizado "tt" en una cadena de formato personalizado.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-y-custom-format-specifier"></a>Especificador de formato personalizado "y"

El especificador de formato personalizado "y" representa el año como un número de uno o dos dígitos. Si el año tiene más de dos dígitos, en el resultado sólo aparecen los dos dígitos de orden inferior. Si el primer dígito de un año de dos dígitos comienza con un cero (por ejemplo, 2008), se aplica formato al número sin el cero inicial. 

Si el especificador de formato "y" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "y". Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

En el ejemplo siguiente se incluye el especificador de formato personalizado "y" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yy-custom-format-specifier"></a>Especificador de formato personalizado "yy"

El especificador de formato personalizado "yy" representa el año como un número de dos dígitos. Si el año tiene más de dos dígitos, en el resultado sólo aparecen los dos dígitos de orden inferior. Si el año de dos dígitos tiene menos de dos dígitos significativos, el número se rellenará con ceros iniciales hasta obtener dos dígitos.

En una operación de análisis, un año de dos dígitos que se analiza mediante el especificador de formato personalizado “yy” se interpreta en función de la propiedad [Calendar.TwoDigitYearMax](xref:System.Globalization.Calendar.TwoDigitYearMax) del calendario actual del proveedor de formato. En el ejemplo siguiente se analiza la representación en forma de cadena de una fecha con un año de dos dígitos utilizando el calendario gregoriano predeterminado de la referencia cultural actual (en este caso, en-US). Luego cambia el objeto [CultureInfo](xref:System.Globalization.CultureInfo) de la referencia cultural actual para usar un objeto [GregorianCalendar](xref:System.Globalization.GregorianCalendar) cuya propiedad [TwoDigitYearMax](xref:System.Globalization.GregorianCalendar.TwoDigitYearMax) se ha modificado.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fmt = "dd-MMM-yy";
      string value = "24-Jan-49";

      Calendar cal = (Calendar) CultureInfo.CurrentCulture.Calendar.Clone();
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
      Console.WriteLine();

      cal.TwoDigitYearMax = 2099;
      CultureInfo culture = (CultureInfo) CultureInfo.CurrentCulture.Clone();
      culture.DateTimeFormat.Calendar = cal;
      Thread.CurrentThread.CurrentCulture = culture;

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
   }
}
// The example displays the following output:
//       Two Digit Year Range: 1930 - 2029
//       1/24/1949
//       
//       Two Digit Year Range: 2000 - 2099
//       1/24/2049
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fmt As String = "dd-MMM-yy"
      Dim value As String = "24-Jan-49"

      Dim cal As Calendar = CType(CultureInfo.CurrentCulture.Calendar.Clone(), Calendar)
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
      Console.WriteLine()

      cal.TwoDigitYearMax = 2099
      Dim culture As CultureInfo = CType(CultureInfo.CurrentCulture.Clone(), CultureInfo)
      culture.DateTimeFormat.Calendar = cal
      Thread.CurrentThread.CurrentCulture = culture

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Two Digit Year Range: 1930 - 2029
'       1/24/1949
'       
'       Two Digit Year Range: 2000 - 2099
'       1/24/2049
```

En el ejemplo siguiente se incluye el especificador de formato personalizado "yy" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyy-custom-format-specifier"></a>Especificador de formato personalizado "yyy"

El especificador de formato personalizado "yyy" representa el año con un mínimo de tres dígitos. Si el año tiene más de tres dígitos significativos, se incluyen en la cadena de resultado. Si el año tiene menos de tres dígitos, el número se rellenará con ceros iniciales hasta obtener tres dígitos.

> [!NOTE]
> Para el calendario budista tailandés, que puede tener años de cinco dígitos, este especificador de formato muestra todos los dígitos significativos.

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyy" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010      
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-yyyy-custom-format-specifier"></a>Especificador de formato personalizado "yyyy"

El especificador de formato personalizado "Yyyy" representa el año con un mínimo de cuatro dígitos. Si el año tiene más de cuatro dígitos significativos, se incluyen en la cadena resultante. Si el año tiene menos de cuatro dígitos, el número se completa con ceros iniciales hasta obtener cuatro dígitos.

> [!NOTE]
> Para el calendario budista tailandés, que puede tener años de cinco dígitos, este especificador de formato muestra todos los dígitos significativos.

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyyy" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyyyy-custom-format-specifier"></a>Especificador de formato personalizado "yyyyy"

El especificador de formato personalizado "yyyyy" (más cualquier número de especificadores "y" adicionales) representa el año con un mínimo de cinco dígitos. Si el año tiene más de cinco dígitos significativos, se incluyen en la cadena resultante. Si el año tiene menos de cinco dígitos, el número se rellenará con ceros iniciales hasta obtener cinco dígitos.

Si hay especificadores "y" adicionales, el número se rellenará con tantos ceros iniciales como sean necesarios para obtener el número de especificadores "y". 

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyyyy" en una cadena de formato personalizado.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-z-custom-format-specifier"></a>Especificador de formato personalizado "z"

Con valores [DateTime](xref:System.DateTime), el especificador de formato personalizado "z" representa la diferencia horaria con signo de la zona horaria del sistema operativo local con respecto a la hora universal coordinada (UTC), medida en horas. No refleja el valor de la propiedad [DateTime.Kind](xref:System.DateTime.Kind) de una instancia. Por esta razón, no se recomienda usar el especificador de formato "z" con valores [DateTime](xref:System.DateTime).

Con valores [DateTimeOffset](xref:System.DateTimeOffset), este especificador de formato representa la diferencia horaria en horas del valor [DateTimeOffset](xref:System.DateTimeOffset) con respecto a la hora UTC. 

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato sin un cero inicial. 

Si el especificador de formato "z" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "z" en una cadena de formato personalizado.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zz-custom-format-specifier"></a>Especificador de formato personalizado "zz"

Con valores [DateTime](xref:System.DateTime), el especificador de formato personalizado "zz" representa la diferencia horaria con signo de la zona horaria del sistema operativo local con respecto a la hora universal coordinada (UTC), medida en horas. No refleja el valor de la propiedad [DateTime.Kind](xref:System.DateTime.Kind) de una instancia. Por esta razón, no se recomienda usar el especificador de formato "zz" con valores [DateTime](xref:System.DateTime).

Con valores [DateTimeOffset](xref:System.DateTimeOffset), este especificador de formato representa la diferencia horaria en horas del valor [DateTimeOffset](xref:System.DateTimeOffset) con respecto a la hora UTC.

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "zz" en una cadena de formato personalizado.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zzz-custom-format-specifier"></a>Especificador de formato personalizado "zzz"

Con valores [DateTime](xref:System.DateTime), el especificador de formato personalizado "zzz" representa la diferencia horaria con signo de la zona horaria del sistema operativo local con respecto a la hora universal coordinada (UTC), medida en horas. No refleja el valor de la propiedad [DateTime.Kind](xref:System.DateTime.Kind) de una instancia. Por esta razón, no se recomienda usar el especificador de formato "zzz" con valores [DateTime](xref:System.DateTime).

Con valores [DateTimeOffset](xref:System.DateTimeOffset), este especificador de formato representa la diferencia horaria en horas del valor [DateTimeOffset](xref:System.DateTimeOffset) con respecto a la hora UTC.

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato con un cero inicial. 

En el ejemplo siguiente se incluye el especificador de formato personalizado "zzz" en una cadena de formato personalizado.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the--custom-format-specifier"></a>Especificador de formato personalizado ":"

El especificador de formato personalizado ":" representa el separador de hora, que se usa para diferenciar horas, minutos y segundos. 

Si el especificador de formato ":" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

## <a name="the--custom-format-specifier"></a>Especificador de formato personalizado "/"

El especificador de formato personalizado "/" representa el separador de fecha, que se usa para diferenciar años, meses y días. 

Si el especificador de formato "/" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar e iniciará una [FormatException](xref:System.FormatException). Para obtener más información sobre cómo usar un especificador de formato único, consulte [Usar especificadores de formato personalizado únicos](#using-single-custom-format-specifiers) más adelante en este tema.

## <a name="character-literals"></a>Literales de carácter

Los siguientes caracteres de una cadena de formato de fecha y hora personalizado están reservados y siempre se interpretan como caracteres de formato o, en el caso de ", ', / y \,, como caracteres especiales. 

  |   |   |   |      
- | - | - | - | -
F | H | K | M | d
f | e | h | m | s
s | s | z | % | :
/ | " | ' | \ |
  |   |   |   |
  
Todos los demás caracteres se interpretan siempre como literales de carácter y, en una operación de formato, se incluyen en la cadena de resultado sin modificar. En una operación de análisis, deben coincidir exactamente con los caracteres de la cadena de entrada; la comparación distingue entre mayúsculas y minúsculas. 

En el ejemplo siguiente se incluyen los caracteres literales "PST" (para hora estándar del Pacífico) y "PDT" (para horario de verano del Pacífico) para representar la zona horaria local en una cadena de formato. Tenga en cuenta que la cadena se incluye en la cadena de resultado y que una cadena que incluye la cadena de zona horaria local también se analiza correctamente. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String[] formats = { "dd MMM yyyy hh:mm tt PST", 
                           "dd MMM yyyy hh:mm tt PDT" };
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(formats[1]));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm PST";
      DateTime newDate;
      if (DateTime.TryParseExact(value, formats, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim formats() As String = { "dd MMM yyyy hh:mm tt PST", 
                                  "dd MMM yyyy hh:mm tt PDT" }
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(formats(1)))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm PST"
      Dim newDate As Date
      If Date.TryParseExact(value, formats, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM PDT
'       12/25/2016 12:00:00 PM
```

Hay dos formas de indicar que los caracteres se han de interpretar como caracteres literales y no como caracteres de reserva, para que se puedan incluir en una cadena de resultado o analizarse correctamente en una cadena de entrada:

* Al incluir un escape con cada carácter reservado. Para obtener más información, consulte [Usar el carácter de escape](#using-the-escape-character). 
  
  En el ejemplo siguiente se incluyen los caracteres literales "pst" (para hora estándar del Pacífico) para representar la zona horaria local en una cadena de formato. Como "s" y "t" son cadenas de formato personalizado, ambos caracteres deben incluir un escape para interpretarse como literales de carácter. 
  
```csharp
using System;
using System.Globalization;

public class Example
{
  public static void Main()
  {
      String format = "dd MMM yyyy hh:mm tt p\\s\\t";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                  DateTimeStyles.None, out newDate)) 
          Console.WriteLine(newDate);
      else
          Console.WriteLine("Unable to parse '{0}'", value);
  }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt p\s\t" 
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```
  
* Al incluir toda la cadena literal entre comillas o apóstrofes. El siguiente ejemplo es igual al anterior, excepto que "pst" se incluye entre comillas para indicar que toda la cadena delimitada debe interpretarse como literales de carácter. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String format = "dd MMM yyyy hh:mm tt \"pst\"";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt ""pst"""  
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```

## <a name="notes"></a>Notas


### <a name="using-single-custom-format-specifiers"></a>Usar especificadores de formato personalizado únicos

Una cadena con formato de fecha y hora personalizado se compone de dos o más caracteres. Los métodos de formato de fecha y hora interpretan cualquier cadena de un único carácter como una cadena de formato de fecha y hora estándar. Si no reconocen el carácter como un especificador de formato válido, inician una [FormatException](xref:System.FormatException). Por ejemplo, una cadena de formato que solo se compone del especificador "h" se interpreta como una cadena de formato de fecha y hora estándar. Pero en este caso concreto se inicia una excepción porque no existe ningún especificador de formato de fecha y hora estándar "h". 

Para usar cualquiera de los especificadores de formato de fecha y hora personalizado como el único especificador en una cadena de formato (es decir, usar el especificador de formato personalizado "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" o "/"), incluya un espacio delante o detrás del especificador, o incluya un especificador de formato de porcentaje ("%") delante del único especificador de fecha y hora personalizado.

Por ejemplo, "`%h`" se interpreta como una cadena de formato de fecha y hora personalizado que muestra la hora representada por el valor de fecha y hora actual. También puede usar la cadena de formato " h" o "h ", aunque esto incluye un espacio en la cadena de resultado junto con la hora. En el ejemplo siguiente se muestran estas tres cadenas de formato.


```csharp
DateTime dat1 = new DateTime(2009, 6, 15, 13, 45, 0);

Console.WriteLine("'{0:%h}'", dat1);
Console.WriteLine("'{0: h}'", dat1);
Console.WriteLine("'{0:h }'", dat1);
// The example displays the following output:
//       '1'
//       ' 1'
//       '1 '
```

```vb
Dim dat1 As Date = #6/15/2009 1:45PM#

Console.WriteLine("'{0:%h}'", dat1)
Console.WriteLine("'{0: h}'", dat1)
Console.WriteLine("'{0:h }'", dat1)
' The example displays the following output:
'       '1'
'       ' 1'
'       '1 '
```

### <a name="using-the-escape-character"></a>Usar el carácter de escape

Los caracteres "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" o "/" en una cadena de formato se interpretan como especificadores de formato personalizado en lugar de como caracteres literales. Para evitar que un carácter se interprete como un especificador de formato, puede precederlo de una barra diagonal inversa (\), que es el carácter de escape. El carácter de escape significa que el siguiente carácter es un carácter literal que se debe incluir en la cadena de resultado sin modificar.

Para incluir una barra diagonal inversa en una cadena de resultado, debe indicar su secuencia de escape con otra barra diagonal inversa (`\\`).

> [!NOTE]
> Algunos compiladores, como el compilador de C#, también pueden interpretar un único carácter de barra diagonal inversa como un carácter de escape. Para asegurarse de que una cadena se interpreta correctamente al darle formato, puede usar el carácter literal de cadena textual (el carácter @) antes de la cadena o puede agregar otro carácter de barra diagonal inversa delante de cada barra diagonal inversa. En el siguiente ejemplo de C# se muestran ambos enfoques.

En el ejemplo siguiente se usa el carácter de escape para evitar que la operación de formato interprete los caracteres "h" y "m" como especificadores de formato. 

```csharp
DateTime date = new DateTime(2009, 06, 15, 13, 45, 30, 90);
string fmt1 = "h \\h m \\m";
string fmt2 = @"h \h m \m";

Console.WriteLine("{0} ({1}) -> {2}", date, fmt1, date.ToString(fmt1));
Console.WriteLine("{0} ({1}) -> {2}", date, fmt2, date.ToString(fmt2));
// The example displays the following output:
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
```

```vb
Dim date1 As Date = #6/15/2009 13:45#
Dim fmt As String = "h \h m \m"

Console.WriteLine("{0} ({1}) -> {2}", date1, fmt, date1.ToString(fmt))
' The example displays the following output:
'       6/15/2009 1:45:00 PM (h \h m \m) -> 1 h 45 m 
```

### <a name="datetimeformatinfo-properties"></a>Propiedades de DateTimeFormatInfo

El formato se ve influenciado por las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro [IFormatProvider](xref:System.IFormatProvider) del método que invoca el formato. Para el parámetro [IFormatProvider](xref:System.IFormatProvider), debe especificar un objeto [CultureInfo](xref:System.Globalization.CultureInfo), que representa una referencia cultural, o un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). 

La cadena de resultado generada por muchos de los especificadores de formato de fecha y hora personalizado también depende de las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) actual. La aplicación puede modificar el resultado generado por algunos de los especificadores de formato de fecha y hora personalizado al cambiar la propiedad [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) correspondiente. Por ejemplo, el especificador de formato "ddd" agrega a la cadena de resultado el nombre abreviado de un día de la semana que se encuentra en la matriz de cadenas [AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames). De igual forma, el especificador de formato "MMMM" agrega a la cadena de resultado el nombre completo de un mes que se encuentra en la matriz de cadenas [MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames).

## <a name="see-also"></a>Vea también

[System.DateTime](xref:System.DateTime)

[System.IFormatProvider](xref:System.IFormatProvider)

[Aplicar formato a tipos](formatting-types.md)

[Cadenas con formato de fecha y hora estándar](standard-datetime.md)


