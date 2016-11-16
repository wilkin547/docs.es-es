---
title: "Cómo: Extraer el día de la semana de una fecha concreta"
description: "Cómo extraer el día de la semana de una fecha concreta"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 88a8f8b9-f5c9-4503-b968-84468b52bb8e
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: f7ae17ac6dbc23e18d18561d5e5ae7efc037c63e

---

# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a>Cómo: Extraer el día de la semana de una fecha concreta

.NET permite determinar fácilmente el número de día de la semana correspondiente a una fecha concreta, así como mostrar el nombre localizado del día de la semana para una fecha en particular. Las propiedades [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) o [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) proporcionan un valor enumerado que indica el día de la semana correspondiente a una fecha concreta. Por el contrario, la recuperación del nombre del día de la semana es una operación de formato que puede realizarse con una llamada a un método de formato como, por ejemplo, un método `ToString` de un valor de fecha y hora o un método [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). En este tema se muestra cómo realizar estas operaciones de formato.

## <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a>Para obtener un número que indique el día de la semana a partir de una fecha específica

1. Si está trabajando con la representación de la cadena de una fecha, conviértala a un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) usando el método estático [DateTime.Parse](xref:System.DateTime.Parse(System.String)) o [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Use la propiedad [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) o [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) para recuperar un valor [DayOfWeek](xref:System.DayOfWeek) que indica el día de la semana.

3. Si es necesario, convierta el valor [DayOfWeek](xref:System.DayOfWeek) en un entero. 

En el ejemplo siguiente se muestra un entero que representa el día de la semana de una fecha concreta. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      DateTime dateValue = new DateTime(2008, 6, 11);
      Console.WriteLine((int) dateValue.DayOfWeek);      
   }
}
// The example displays the following output:
//       3
```

```vb
Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.DayOfWeek)           
   End Sub
End Module
' The example displays the following output:
'    3
```

## <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a>Para obtener el nombre abreviado del día de la semana a partir de una fecha específica

1. Si está trabajando con la representación de la cadena de una fecha, conviértala a un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) usando el método estático [DateTime.Parse](xref:System.DateTime.Parse(System.String)) o [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Puede obtener el nombre abreviado de un día de la semana de la referencia cultural actual o de una referencia cultural específica:

    a. Para extraer el nombre del día laborable abreviado de la referencia cultural actual, llame al método de instancia [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String) o [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) del valor de fecha y hora, y pase la cadena "ddd" como el parámetro *format*. En el ejemplo siguiente se muestra la llamada al método `ToString(String)`.
    
    ```csharp
    using System;

    public class Example
    {
       public static void Main()
       {
          DateTime dateValue = new DateTime(2008, 6, 11);
          Console.WriteLine(dateValue.ToString("ddd"));   
       }
    }
    // The example displays the following output:
    //       Wed
    ```

    ```vb
    Module Example
       Public Sub Main()
          Dim dateValue As Date = #6/11/2008#
          Console.WriteLine(dateValue.ToString("ddd"))    
       End Sub
    End Module
    ' The example displays the following output:
    '       Wed
    ```
    
    b. Para extraer el nombre del día laborable abreviado para una referencia cultural concreta, llame al método de instancia [DateTime.ToString (String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) o [DateTimeOffset.ToString (String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) del valor de fecha y hora. Pase la cadena "ddd" como parámetro *format*. Pase un objeto [CultureInfo](xref:System.Globalization.CultureInfo) o [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que represente la referencia cultural cuyo nombre del día laborable desee recuperar como parámetro *provider*. En el código siguiente se muestra una llamada al método [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) con un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural fr-FR.
    
    ```csharp
    using System;
    using System.Globalization;

    public class Example
    {
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("ddd", 
                            new CultureInfo("fr-FR")));    
    }
    }
    // The example displays the following output:
    //       mer. 
    ```

    ```vb
    Imports System.Globalization

    Module Example
       Public Sub Main()
          Dim dateValue As Date = #6/11/2008#
          Console.WriteLine(dateValue.ToString("ddd", 
                            New CultureInfo("fr-FR")))    
       End Sub
    End Module
    ' The example displays the following output:
    '       mer.
    ```
    
## <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a>Para obtener el nombre completo del día de la semana a partir de una fecha específica

1. Si está trabajando con la representación de la cadena de una fecha, conviértala a un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) usando el método estático [DateTime.Parse](xref:System.DateTime.Parse(System.String)) o [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Puede obtener el nombre abreviado de un día de la semana de la referencia cultural actual o de una referencia cultural específica:

    a. Para extraer el nombre del día laborable abreviado de la referencia cultural actual, llame al método de instancia [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String) o [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) del valor de fecha y hora, y pase la cadena "dddd" como el parámetro *format*. En el ejemplo siguiente se muestra la llamada al método `ToString(String)`.
    
    ```csharp
    using System;

    public class Example
    {
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd"));    
    }
    }
    // The example displays the following output:
    //       Wednesday
    ```

    ```vb
    Module Example
       Public Sub Main()
          Dim dateValue As Date = #6/11/2008#
          Console.WriteLine(dateValue.ToString("dddd"))
       End Sub
    End Module
    ' The example displays the following output:
    '       Wednesday
    ```
    
    b. Para extraer el nombre del día laborable para una referencia cultural concreta, llame al método de instancia [DateTime.ToString (String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) o [DateTimeOffset.ToString (String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) del valor de fecha y hora. Pase la cadena "dddd" como parámetro *format*. Pase un objeto [CultureInfo](xref:System.Globalization.CultureInfo) o [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que represente la referencia cultural cuyo nombre del día laborable desee recuperar como parámetro *provider*. En el código siguiente se muestra una llamada al método [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) con un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural es-ES.
    
    ```csharp
    using System;
    using System.Globalization;

    public class Example
    {
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd", 
                            new CultureInfo("es-ES")));    
    }
    }
    // The example displays the following output:
    //       miércoles.
    ```

    ```vb
    Imports System.Globalization

    Module Example
       Public Sub Main()
          Dim dateValue As Date = #6/11/2008#
          Console.WriteLine(dateValue.ToString("dddd", _
                            New CultureInfo("es-ES")))     
       End Sub
    End Module
    ' The example displays the following output:
    '       miércoles.
    ```
    
## <a name="example"></a>Ejemplo

En el ejemplo se muestran las llamadas a las propiedades [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) y [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) y los métodos [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String) o [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) para recuperar el número que representa el día de la semana, el nombre abreviado del día laborable y el nombre del día laborable completo de una fecha concreta. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string dateString = "6/11/2007";
      DateTime dateValue;
      DateTimeOffset dateOffsetValue;

      try
      {
         DateTimeFormatInfo dateTimeFormats;
         // Convert date representation to a date value
         dateValue = DateTime.Parse(dateString, CultureInfo.InvariantCulture);
         dateOffsetValue = new DateTimeOffset(dateValue, 
                                      TimeZoneInfo.Local.GetUtcOffset(dateValue));         

         // Convert date representation to a number indicating the day of week
         Console.WriteLine((int) dateValue.DayOfWeek);
         Console.WriteLine((int) dateOffsetValue.DayOfWeek);

         // Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"));
         Console.WriteLine(dateOffsetValue.ToString("ddd"));

         // Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"));
         Console.WriteLine(dateOffsetValue.ToString("dddd"));

         // Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("de-DE")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                     new CultureInfo("de-DE")));

         // Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("de-DE").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats));

         // Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("fr-FR")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                    new CultureInfo("fr-FR")));

         // Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("fr-FR").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output:
//       1
//       1
//       Mon
//       Mon
//       Monday
//       Monday
//       Mo
//       Mo
//       Mo
//       Mo
//       lun.
//       lun.
//       lundi
//       lundi
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

Puede haber lenguajes que ofrezcan una funcionalidad que duplique o complemente a la proporcionada por .NET. Por ejemplo, Visual Basic incluye dos funciones así:

* `Weekday`, que devuelve un número que indica el día de la semana a partir de una fecha específica. Considera que el valor ordinal del primer día de la semana es uno, mientras que la propiedad [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) considera que es cero.

* `WeekdayName`, que devuelve el nombre de la semana en la referencia cultural actual que corresponde a un número concreto del día de la semana.

En el ejemplo siguiente se demuestra el uso de las funciones `Weekday` y `WeekdayName`.

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#

      ' Get weekday number using Visual Basic Weekday function
      Console.WriteLine(Weekday(dateValue))                 ' Displays 4
      ' Compare with .NET DateTime.DayOfWeek property
      Console.WriteLine(dateValue.DayOfWeek)                ' Displays 3

      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))    ' Displays Wednesday

      ' Change culture to de-DE
      Dim originalCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
      Thread.CurrentThread.CurrentCulture = New CultureInfo("de-DE")
      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))   ' Displays Donnerstag

      ' Restore original culture
      Thread.CurrentThread.CurrentCulture = originalCulture   
   End Sub
End Module
``` 

También se puede usar el valor devuelto por la propiedad [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) para recuperar el nombre del día de la semana de una fecha en particular. Para ello, solo se necesita hacer una llamada al método [Enum.ToString](xref:System.Enum.ToString(System.String)) en el valor [DayOfWeek](xref:System.DayOfWeek) devuelto por la propiedad. Sin embargo, esta técnica no produce el nombre localizado de un día de la semana para la referencia cultural actual, tal como se muestra en el ejemplo siguiente. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      // Change current culture to fr-FR
      CultureInfo originalCulture = Thread.CurrentThread.CurrentCulture;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");

      DateTime dateValue = new DateTime(2008, 6, 11);
      // Display the DayOfWeek string representation
      Console.WriteLine(dateValue.DayOfWeek.ToString());   
      // Restore original current culture
      Thread.CurrentThread.CurrentCulture = originalCulture;
   }
}
// The example displays the following output:
//       Wednesday
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

## <a name="see-also"></a>Vea también

[Efectuar operaciones de formato](performing-formatting-operations.md)

[Cadenas con formato de fecha y hora estándar](standard-datetime.md)

[Cadenas con formato de fecha y hora personalizado](custom-datetime.md)
    



<!--HONumber=Nov16_HO1-->


