---
title: "Cadenas con formato de fecha y hora estándar"
description: "Cadenas con formato de fecha y hora estándar"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: be239871-10cc-4949-b548-200bb260630a
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 56da9671a0849b0f0a94d8881cdc28e70bcf8549

---

# <a name="standard-date-and-time-format-strings"></a>Cadenas con formato de fecha y hora estándar

Una cadena de formato de fecha y hora estándar usa un único especificador de formato para definir la representación de texto de un valor de fecha y hora. Cualquier cadena con formato de fecha y hora que contenga más de un carácter, incluido un espacio en blanco, se interpreta como una cadena con formato de fecha y hora personalizado; para obtener más información, consulte [Cadenas con formato de fecha y hora personalizado](custom-datetime.md). Una cadena de formato estándar o personalizado se puede usar de dos maneras:

* Para definir la cadena resultante una operación de formato.

* Para definir la representación de texto de un valor de fecha y hora que se puede convertir en un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) mediante una operación de análisis.

Las cadenas con formato de fecha y hora estándar se pueden usar con valores tanto [DateTime](xref:System.DateTime) como [DateTimeOffset](xref:System.DateTimeOffset). 

En la tabla siguiente se describen los especificadores de formato de fecha y hora estándar. A menos que se indique lo contrario, un determinado especificador de formato de fecha y hora estándar genera una representación de cadena idéntica independientemente de que se use con un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset). Consulte la sección [Notas](#notes) para obtener información adicional sobre cómo usar cadenas de formato de fecha y hora estándar.

Especificador de formato | Descripción | Ejemplos
---------------- | ----------- | --------
"d" | Patrón de fecha corta. | `2009-06-15T13:45:30 -> 6/15/2009 (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)`; `2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)`
"D" | Patrón de fecha larga. | `2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)`; `2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)`; `2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)`
"f" | Patrón de fecha y hora completa (hora corta). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)`
"F" | Patrón de fecha y hora completa (hora larga). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)`
"g" | Patrón de fecha y hora general (hora corta). | `2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)`
"G" | Patrón de fecha y hora general (hora larga). | `2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)`
"M", "m' | Patrón de mes/día. | `2009-06-15T13:45:30 -> June 15 (en-US)`; `2009-06-15T13:45:30 -> 15. juni (da-DK)`; `2009-06-15T13:45:30 -> 15 Juni (id-ID)`
"O", "o" | Patrón de fecha y hora de ida y vuelta. | Valores [DateTime](xref:System.DateTime): `2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00`; `2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z`; `2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000`. Valores [DateTimeOffset](xref:System.DateTimeOffset): `2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00`
"R", "r" | Patrón RFC1123. | `2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT`
"s" | Patrón de fecha y hora que se puede ordenar. | `2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30`; `2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30`
"t" | Patrón de hora corta. | `2009-06-15T13:45:30 -> 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45 م (ar-EG)` 
"T" | Patrón de hora larga. | `2009-06-15T13:45:30 -> 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45:30 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)`
"u" | Patrón de fecha y hora universal que se puede ordenar. | Con un valor [DateTime](xref:System.DateTime): `2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z`. Con un valor [DateTimeOffset](xref:System.DateTimeOffset): `2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z`
"U" | Patrón de fecha y hora completa universal. | `2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)`
"Y", "y" | Patrón de mes y año. | `2009-06-15T13:45:30 -> June, 2009 (en-US)`; `2009-06-15T13:45:30 -> juni 2009 (da-DK)`; `2009-06-15T13:45:30 -> Juni 2009 (id-ID)`
Cualquier otro carácter único | Especificador desconocido. | Se produce una excepción [FormatException](xref:System.FormatException) de tiempo de ejecución.

## <a name="how-standard-format-strings-work"></a>Cómo funcionan las cadenas con formato estándar

En una operación de formato, una cadena de formato estándar es simplemente un alias de una cadena con formato personalizado. La ventaja de usar un alias para referirse a una cadena de formato personalizado es que, aunque el alias permanece invariable, la propia cadena de formato personalizado puede variar. Esto es importante, porque las representaciones de cadena de valores de fecha y hora suelen variar con las referencias culturales. Por ejemplo, la cadena de formato estándar "d" indica que un valor de fecha y hora se va a mostrar utilizando un patrón de fecha corta. En la referencia cultural de todos los idiomas, este patrón es "MM/dd/aaaa". En la referencia cultural fr-FR, es "dd/MM/aaaa". En la referencia cultural ja-JP, es "aaaa/MM/dd."

Si una cadena con formato estándar en una operación de formato se asigna a una cadena con formato personalizado de una referencia cultural específica, la aplicación puede definir la referencia cultural concreta cuyas cadenas con formato personalizado se usan de uno de los modos siguientes:

* Puede utilizar la referencia cultural predeterminada (o la actual). En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de la referencia cultural. En este caso, la referencia cultural actual es en-US. 

  ```csharp
  // Display using current (en-us) culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  Console.WriteLine(thisDate.ToString("d"));           // Displays 3/15/2008
  ```

  ```vb
  ' Display using current (en-us) culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Console.WriteLine(thisDate.ToString("d"))     ' Displays 3/15/2008
  ```
  
* Puede pasar un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que represente la referencia cultural cuyo formato se va a usar a un método que tenga un parámetro [IFormatProvider](xref:System.IFormatProvider). En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de la referencia cultural pt-BR.
  
  ```csharp
  // Display using pt-BR culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  CultureInfo culture = new CultureInfo("pt-BR");      
  Console.WriteLine(thisDate.ToString("d", culture));  // Displays 15/3/2008
  ```

  ```vb
  ' Display using pt-BR culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Dim culture As New CultureInfo("pt-BR")      
  Console.WriteLine(thisDate.ToString("d", culture))   ' Displays 15/3/2008
  ```
  
* Puede pasar un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que proporcione información de formato a un método que tenga un parámetro [IFormatProvider](xref:System.IFormatProvider). En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de un objeto DateTimeFormatInfo en la referencia cultural hr-HR.  

  ```csharp
  // Display using date format information from hr-HR culture
  DateTime thisDate = new DateTime(2008, 3, 15);
  DateTimeFormatInfo fmt = (new CultureInfo("hr-HR")).DateTimeFormat;
  Console.WriteLine(thisDate.ToString("d", fmt));      // Displays 15.3.2008
  ```

  ```vb
  ' Display using date format information from hr-HR culture
  Dim thisDate As Date = #03/15/2008#
  Dim fmt As DateTimeFormatInfo = (New CultureInfo("hr-HR")).DateTimeFormat
  Console.WriteLine(thisDate.ToString("d", fmt))   ' Displays 15.3.2008
  ```
  
En algunos casos, la cadena con formato estándar actúa como la abreviatura correspondiente de una cadena con formato personalizado más larga que es invariable. Hay cuatro cadenas de formato estándar que pertenecen a esta categoría: "O" (o "o"), "R" (o "r"), "s" y "u". Estas cadenas se corresponden con las cadenas de formato personalizado definidas en la referencia cultural de todos los idiomas. Generan representaciones de cadena de valores de fecha y hora que están pensados para que sean idénticos en todas las referencias culturales. En la tabla siguiente se proporciona información sobre estas cuatro cadenas de formato de fecha y hora estándar.

Cadena con formato estándar | Se define en la propiedad DateTimeFormatInfo.InvariantInfo | Cadena con formato personalizado
---------------------- | ---------------------------------------------------- | --------------------
"O" u "o" | Ninguna | yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzz
"R" o "r" | [RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
"s" | [SortableDateTime](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern) | yyyy'-'MM'-'dd'T'HH':'mm':'ss
"u" | [UniversalSortableDateTime](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern) | yyyy'-'MM'-'dd HH':'mm':'ss'Z'

Las secciones siguientes describen los especificadores de formato estándar para los valores [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset).

## <a name="the-short-date-d-format-specifier"></a>El especificador de formato de fecha corta ("d")

El especificador de formato estándar "d" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) de una referencia cultural concreta. Por ejemplo, la cadena de formato personalizado devuelta por la propiedad [ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) de la referencia cultural de todos los idiomas es "MM/dd/yyyy". 

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que controlan el formato de la cadena devuelta.
En el ejemplo siguiente se usa el especificador de formato "d" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008,4, 10);
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-NZ")));
// Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("de-DE")));
// Displays 10.04.2008 
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-NZ")))
' Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("de-DE")))
' Displays 10.04.2008 
```

## <a name="the-long-date-d-format-specifier"></a>El especificador de formato de fecha larga ("D")

El especificador de formato estándar "D" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "dddd, dd MMMM yyyy".

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad | Descripción
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Define el formato global de la cadena de resultado.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.

En el ejemplo siguiente se usa el especificador de formato "D" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10);
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("pt-BR")));
// Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays jueves, 10 de abril de 2008
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("pt-BR")))
' Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays jueves, 10 de abril de 2008
```

## <a name="the-full-date-short-time-f-format-specifier"></a>El especificador de formato de fecha completa y hora corta ("f")

El especificador de formato estándar "f" representa una combinación de los patrones de fecha larga ("D") y hora corta ("t"), separados por un espacio.

La información de formato de un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelven las propiedades [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) y [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Define el formato del componente de fecha de la cadena de resultado.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Define el formato del componente de hora de la cadena de resultado.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "f" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30 
```

## <a name="the-full-date-long-time-f-format-specifier"></a>El especificador de formato de fecha completa y hora larga ("F")

El especificador de formato estándar "F" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "dddd, dd MMMM yyyy HH:mm:ss".

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelve la propiedad [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Define el formato global de la cadena de resultado.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "F" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30:00 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30:00 
```

## <a name="the-general-date-short-time-g-format-specifier"></a>El especificador de formato de fecha general y hora corta ("g")

El especificador de formato estándar "g" representa una combinación de los patrones de fecha corta ("d") y hora corta ("t"), separados por un espacio.

La información de formato de un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelven las propiedades [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) y [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Define el formato del componente de fecha de la cadena de resultado.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Define el formato del componente de hora de la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "g" para mostrar un valor de fecha y hora. 

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("g", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("fr-BE")));
// Displays 10/04/2008 6:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("g", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("fr-BE")))
' Displays 10/04/2008 6:30  
```

## <a name="the-general-date-long-time-g-format-specifier"></a>El especificador de formato de fecha general y hora larga ("G")

El especificador de formato estándar "G" representa una combinación de los patrones de fecha corta ("d") y hora larga ("T"), separados por un espacio.

La información de formato de un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelven las propiedades [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) y [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Define el formato del componente de fecha de la cadena de resultado.
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Define el formato del componente de hora de la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "G" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("G", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("nl-BE")));
// Displays 10/04/2008 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("G", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("nl-BE")))
' Displays 10/04/2008 6:30:00                       
```

## <a name="the-month-m-m-format-specifier"></a>El especificador de formato de mes ("M", "m")

El especificador de formato estándar "M" o "m" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern) actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "MMMM dd".

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad | Descripción
-------- | -----------
[MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern) | Define el formato global de la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.

En el ejemplo siguiente se usa el especificador de formato "m" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays April 10                        
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("ms-MY")));
// Displays 10 April  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays April 10                        
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("ms-MY")))
' Displays 10 April
```

## <a name="the-round-trip-o-o-format-specifier"></a>El especificador de formato de operación de ida y vuelta ("O", "o")

El especificador de formato estándar "O" u "o" representa una cadena de formato de fecha y hora personalizado mediante un patrón que conserva la información de la zona horaria y emite una cadena de resultado que cumple con la norma ISO 8601. En los valores [DateTime](xref:System.DateTime), este especificador de formato está diseñado para conservar los valores de fecha y hora junto con la propiedad [DateTime.Kind](xref:System.DateTime.Kind) en el texto. Se puede analizar la cadena con formato usando el método [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) o el método [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) si se establece el parámetro de estilos en [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind). 

El especificador de formato estándar "O" u "o" corresponde a la cadena de formato personalizado "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK" para los valores DateTime y a la cadena de formato personalizado "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz" para los valores [DateTimeOffset](xref:System.DateTimeOffset). En esta cadena, los pares de comillas que delimitan los caracteres individuales (como guiones, signos de dos puntos y la letra "T") indican que el carácter individual es un literal que no se puede cambiar. Los apóstrofos no aparecen en la cadena de salida. 

El especificador de formato estándar "O" u "o" (y la cadena de formato personalizado "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK") aprovecha los tres modos en que se representa la información de zona horaria en ISO 8601 para conservar la propiedad [Kind](xref:System.DateTime.Kind) de valores [DateTime](xref:System.DateTime): 

* El componente de zona horaria de valores de fecha y hora [DateTimeKind.Local](xref:System.DateTimeKind.Local) es un desfase con respecto a la hora UTC (por ejemplo, +01:00, -07:00). Todos los valores DateTimeOffset también se representan en este formato. 

* El componente de zona horaria de valores de fecha y hora [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) usa "Z" (que es un desfase cero) para representar la hora UTC. 

* Los valores de fecha y hora [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) no tienen ninguna información de zona horaria. 

Dado que el especificador de formato estándar "O" u "o" conforma un estándar internacional, la operación de formato o análisis que utiliza el especificador siempre usa la referencia cultural de todos los idiomas y el calendario gregoriano. 

Las cadenas que se pasan a los métodos `Parse`, `TryParse`, `ParseExact` y `TryParseExact` de [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) se pueden analizar con el especificador de formato "O" u "o" si están en uno de estos formatos. En el caso de objetos [DateTime](xref:System.DateTime), la sobrecarga de análisis a la que se llama debe incluir también un parámetro de estilos con un valor de [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind). Observe que si llama a un método de análisis con la cadena de formato personalizado que se corresponde con el especificador de formato "O" u "o", no obtendrá los mismos resultados que "O" u "o". Esto se debe a que los métodos de análisis que usan una cadena de formato personalizado no pueden analizar la representación de cadena de aquellos valores de fecha y hora que carecen de un componente de zona horaria o que usan "Z" para indicar la hora UTC. 

En el ejemplo siguiente se usa el especificador de formato "o" para mostrar una serie de valores [DateTime](xref:System.DateTime) y un valor [DateTimeOffset](xref:System.DateTimeOffset) en un sistema de la zona horaria del Pacífico de EE. UU. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
       DateTime dat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                   DateTimeKind.Unspecified);
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind); 

       DateTime uDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Utc);
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind);

       DateTime lDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Local);
       Console.WriteLine("{0} ({1}) --> {0:O}\n", lDat, lDat.Kind);

       DateTimeOffset dto = new DateTimeOffset(lDat);
       Console.WriteLine("{0} --> {0:O}", dto);
   }
}
// The example displays the following output:
//    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
//    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
//    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
//    
//    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

```vb
Module Example
   Public Sub Main()
       Dim dat As New Date(2009, 6, 15, 13, 45, 30, 
                           DateTimeKind.Unspecified)
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind) 

       Dim uDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Utc)
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind)

       Dim lDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Local)
       Console.WriteLine("{0} ({1}) --> {0:O}", lDat, lDat.Kind)
       Console.WriteLine()

       Dim dto As New DateTimeOffset(lDat)
       Console.WriteLine("{0} --> {0:O}", dto)
   End Sub
End Module
' The example displays the following output:
'    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
'    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
'    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
'    
'    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

En el ejemplo siguiente se usa el especificador de formato "o" para crear una cadena con formato y, a continuación, se restaura el valor de fecha y hora original llamando a un método `Parse` de fecha y hora.

```csharp
// Round-trip DateTime values.
DateTime originalDate, newDate;
string dateString;
// Round-trip a local time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 10, 6, 30, 0), DateTimeKind.Local);
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip a UTC time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 12, 9, 30, 0), DateTimeKind.Utc);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip time in an unspecified time zone.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 13, 12, 30, 0), DateTimeKind.Unspecified);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);

// Round-trip a DateTimeOffset value.
DateTimeOffset originalDTO = new DateTimeOffset(2008, 4, 12, 9, 30, 0, new TimeSpan(-8, 0, 0));
dateString = originalDTO.ToString("o");
DateTimeOffset newDTO = DateTimeOffset.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO);
// The example displays the following output:
//    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
//    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
//    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
//    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

```vb
' Round-trip DateTime values.
Dim originalDate, newDate As Date
Dim dateString As String
' Round-trip a local time.
originalDate = Date.SpecifyKind(#4/10/2008 6:30AM#, DateTimeKind.Local)
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip a UTC time.
originalDate = Date.SpecifyKind(#4/12/2008 9:30AM#, DateTimeKind.Utc)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip time in an unspecified time zone.
originalDate = Date.SpecifyKind(#4/13/2008 12:30PM#, DateTimeKind.Unspecified)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)

' Round-trip a DateTimeOffset value.
Dim originalDTO As New DateTimeOffset(#4/12/2008 9:30AM#, New TimeSpan(-8, 0, 0))
dateString = originalDTO.ToString("o")
Dim newDTO As DateTimeOffset = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO)
' The example displays the following output:
'    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
'    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
'    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
'    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

## <a name="the-rfc1123-r-r-format-specifier"></a>El especificador de formato RFC1123 ("R", "r")

El especificador de formato estándar "R" o "r" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern). El patrón refleja una norma definida y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "ddd, dd MMM yyyy HH':'mm':'ss 'GMT'". Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas.

La cadena de resultado se ve afectada por las siguientes propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) devuelto por la propiedad [DateTimeFormatInfo.InvariantInfo](xref:System.Globalization.DateTimeFormatInfo.InvariantInfo) que representa la referencia cultural invariable.

Propiedad | Descripción
-------- | -----------
[RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | Define el formato de la cadena de resultado.
[AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) | Define los nombres de días abreviados que pueden aparecer en la cadena de resultado.
[AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) | Define los nombres de meses abreviados que pueden aparecer en la cadena de resultado.

Aunque la norma RFC 1123 expresa una hora según la hora universal coordinada (hora UTC), la operación de formato no modifica el valor del objeto [DateTime](xref:System.DateTime) al que se está dando formato. Por tanto, debe convertir el valor [DateTime](xref:System.DateTime) en una hora UTC llamando al método [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) antes de realizar la operación de formato. Por el contrario, los valores [DateTimeOffset](xref:System.DateTimeOffset) realizan esta conversión automáticamente; no es necesario llamar al método [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) antes de realizar la operación de formato. 

En el ejemplo siguiente se usa el especificador de formato "r" para mostrar un valor [DateTime](xref:System.DateTime) y un valor [DateTimeOffset](xref:System.DateTimeOffset) en un sistema de la zona horaria del Pacífico de EE. UU.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
DateTimeOffset dateOffset = new DateTimeOffset(date1, 
                            TimeZoneInfo.Local.GetUtcOffset(date1));
Console.WriteLine(date1.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Dim dateOffset As New DateTimeOffset(date1, TimeZoneInfo.Local.GetUtcOFfset(date1))
Console.WriteLine(date1.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT
```

## <a name="the-sortable-s-format-specifier"></a>El especificador de formato que se puede ordenar ("s")

El especificador de formato estándar "s" representa una cadena de formato de fecha y hora personalizado definida por la propiedad [DateTimeFormatInfo.SortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern). El patrón refleja una norma definida (ISO 8601) y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "yyyy'-'MM'-'dd'T'HH':'mm':'ss".

La finalidad del especificador de formato "s" es generar cadenas de resultado de forma coherente en orden ascendente o descendente según los valores de fecha y hora. Como resultado, aunque el especificador de formato estándar "s" representa un valor de fecha y hora en un formato coherente, la operación de formato no modifica el valor del objeto de fecha y hora al que se está dando formato para reflejar su propiedad [DateTime.Kind](xref:System.DateTime.Kind) o su valor [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset). Por ejemplo, las cadenas de resultado que se producen al dar formato a los valores de fecha y hora 2014-11-15T18:32:17+00:00 y 2014-11-15T18:32:17+08:00 son idénticas. 

Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas. 

En el ejemplo siguiente se usa el especificador de formato "s" para mostrar un valor [DateTime](xref:System.DateTime) y un valor [DateTimeOffset](xref:System.DateTimeOffset) en un sistema de la zona horaria del Pacífico de EE. UU.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("s"));
// Displays 2008-04-10T06:30:00
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("s"))
' Displays 2008-04-10T06:30:00 
```

## <a name="the-short-time-t-format-specifier"></a>El especificador de formato de hora corta ("t")

El especificador de formato estándar "t" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "HH:mm".

La información de formato de un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelve la propiedad [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Define el formato del componente de hora de la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "t" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30
```

## <a name="the-long-time-t-format-specifier"></a>El especificador de formato de hora larga ("T")

El especificador de formato estándar "T" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) de una referencia cultural concreta. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "HH:mm:ss".

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelve la propiedad [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Define el formato del componente de hora de la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

En el ejemplo siguiente se usa el especificador de formato "T" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30:00 
```

## <a name="the-universal-sortable-u-format-specifier"></a>El especificador de formato universal que se puede ordenar ("u")

El especificador de formato estándar "u" representa una cadena de formato de fecha y hora personalizado definida por la propiedad [DateTimeFormatInfo.UniversalSortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern). El patrón refleja una norma definida y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "yyyy'-'MM'-'dd HH':'mm':'ss'Z'". Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas. 

Aunque la cadena de resultado debe expresar una hora como una hora universal coordinada (hora UTC), no se realiza ninguna conversión del valor [DateTime](xref:System.DateTime) original durante la operación de formato. Por lo tanto, debe convertir los valores [DateTime](xref:System.DateTime) en hora UTC llamando al método [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) antes de realizar la operación de formato. Por el contrario, los valores [DateTimeOffset](xref:System.DateTimeOffset) realizan esta conversión automáticamente; no es necesario llamar al método [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) antes de realizar la operación de formato.   

En el ejemplo siguiente se usa el especificador de formato "u" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToUniversalTime().ToString("u"));
// Displays 2008-04-10 13:30:00Z
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToUniversalTime.ToString("u"))
' Displays 2008-04-10 13:30:00Z                       
```

## <a name="the-universal-full-u-format-specifier"></a>El especificador de formato completo universal ("U")

El especificador de formato estándar "U" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) de una referencia cultural especificada. El patrón es igual que el patrón de "F". Pero el valor [DateTime](xref:System.DateTime) se convierte automáticamente en una hora UTC antes de darle formato.

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado que devuelve la propiedad [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) de algunas referencias culturales podría no hacer uso de todas las propiedades.

Propiedad | Descripción
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Define el formato global de la cadena de resultado.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.

El especificador de formato "U" no es compatible con el tipo [DateTimeOffset](xref:System.DateTimeOffset) e inicia una excepción [FormatException](xref:System.FormatException) si se usa para dar formato a un valor [DateTimeOffset](xref:System.DateTimeOffset).

En el ejemplo siguiente se usa el especificador de formato "U" para mostrar un valor de fecha y hora.

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("sv-FI")));
// Displays den 10 april 2008 13:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("sv-FI")))
' Displays den 10 april 2008 13:30:00                       
```

## <a name="the-year-month-y-y-format-specifier"></a>El especificador de formato de mes y año ("Y", "y")

El especificador de formato estándar "Y" o "y" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad [DateTimeFormatInfo.YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern) de una referencia cultural especificada. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "yyyy MMMM".

En la tabla siguiente se enumeran las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad | Descripción
-------- | -----------
[YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern) | Define el formato global de la cadena de resultado.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.

En el ejemplo siguiente se usa el especificador de formato "y" para mostrar un valor de fecha y hora.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("Y", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays April, 2008                       
Console.WriteLine(date1.ToString("y", 
                  CultureInfo.CreateSpecificCulture("af-ZA")));
// Displays April 2008 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("Y", CultureInfo.CreateSpecificCulture("en-US")))
' Displays April, 2008                       
Console.WriteLine(date1.ToString("y", CultureInfo.CreateSpecificCulture("af-ZA")))
' Displays April 2008
```                       

## <a name="notes"></a>Notas

### <a name="datetimeformatinfo-properties"></a>Propiedades de DateTimeFormatInfo

El formato se ve influenciado por las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro [IFormatProvider](xref:System.IFormatProvider) del método que invoca el formato. En el parámetro [IFormatProvider](xref:System.IFormatProvider), la aplicación debe especificar un objeto [CultureInfo](xref:System.Globalization.CultureInfo), que representa una referencia cultural, o un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), que representa las convenciones de formato de fecha y hora de una determinada referencia cultural. Muchos de los especificadores de formato de fecha y hora estándar son alias de patrones de formato definidos en las propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) actual. La aplicación puede modificar el resultado generado por algunos especificadores de formato de fecha y hora estándar al cambiar los patrones de formato de fecha y hora correspondientes de la propiedad [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) apropiada.

## <a name="see-also"></a>Vea también

[Aplicar formato a tipos](formatting-types.md)

[Cadenas con formato de fecha y hora personalizado](custom-datetime.md)




<!--HONumber=Nov16_HO3-->


