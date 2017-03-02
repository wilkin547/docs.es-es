---
title: "Cómo: Mostrar milisegundos en los valores de fecha y hora"
description: "Cómo mostrar milisegundos en los valores de fecha y hora"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 78599e33-1c3f-4335-b320-751e35906338
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 7a110cf28ac8de558cd1460c61a650fc8a80e51a
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Cómo: Mostrar milisegundos en los valores de fecha y hora

Los métodos de formato de fecha y hora predeterminados, como [DateTime.ToString()](xref:System.DateTime.ToString), incluyen las horas, los minutos y los segundos de un valor de tiempo, pero excluyen el componente de milisegundos. En este tema se muestra cómo se incluye un componente de milisegundos de un valor de fecha y hora en cadenas de fecha y hora con formato.

## <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Para mostrar el componente de milisegundos de un valor DateTime

1. Si está trabajando con la representación de cadena de una fecha, conviértala a un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) con el método estático [DateTime.Parse(String)](xref:System.DateTime.Parse(System.String)) o [DateTimeOffset.Parse(String)](xref:System.DateTimeOffset.Parse(System.String)).

2. Para extraer la representación de cadena del componente de milisegundos de una hora, llame al método [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) o [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String)) del valor de fecha y hora y pase el modelo de formato personalizado `fff` o `FFF` en solitario o junto a otros especificadores de formato personalizado como el parámetro de formato.

## <a name="example"></a>Ejemplo

En el ejemplo se muestra el componente de milisegundos de un valor [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) en la consola en su presentación en solitario e incluido en una cadena de fecha y hora más larga. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class MillisecondDisplay
{
   public static void Main()
   {
      string dateString = "7/16/2008 8:32:45.126 AM";

      try
      {
         DateTime dateValue = DateTime.Parse(dateString);
         DateTimeOffset dateOffsetValue = DateTimeOffset.Parse(dateString);

         // Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", 
                           dateValue.ToString("fff"));
         Console.WriteLine("Millisecond component only: {0}", 
                           dateOffsetValue.ToString("fff"));

         // Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));

         // Append millisecond pattern to current culture's full date time pattern
         string fullPattern = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern;
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff");

         // Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", 
                           dateValue.ToString(fullPattern));
         Console.WriteLine("Modified full date time pattern: {0}",
                           dateOffsetValue.ToString(fullPattern));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output if the current culture is en-US:
//    Millisecond component only: 126
//    Millisecond component only: 126
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

```vb
Imports System.Globalization
Imports System.Text.REgularExpressions

Module MillisecondDisplay
   Public Sub Main()

      Dim dateString As String = "7/16/2008 8:32:45.126 AM"

      Try
         Dim dateValue As Date = Date.Parse(dateString)
         Dim dateOffsetValue As DateTimeOffset = DateTimeOffset.Parse(dateString)

         ' Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", _
                           dateValue.ToString("fff"))
         Console.WriteLine("Millisecond component only: {0}", _
                           dateOffsetValue.ToString("fff"))

         ' Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))

         ' Append millisecond pattern to current culture's full date time pattern
         Dim fullPattern As String = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff")

         ' Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateValue.ToString(fullPattern))                        
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateOffsetValue.ToString(fullPattern))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)      
      End Try
   End Sub
End Module
' The example displays the following output if the current culture is en-US:
'    Millisecond component only: 126
'    Millisecond component only: 126
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

El modelo de formato `fff` incluye todos los ceros finales en el valor de milisegundos. El modelo de formato `FFF` suprime todos estos ceros. En el siguiente ejemplo se ilustra la diferencia.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine(dateValue.ToString("fff"));    
Console.WriteLine(dateValue.ToString("FFF"));
// The example displays the following output to the console:
//    180
//    18 
```

```vb
Dim dateValue As New Date(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLIne(dateValue.ToString("fff"))    
Console.WriteLine(dateValue.ToString("FFF"))
' The example displays the following output to the console:
'    180
'    18
```

Un problema que surge al definir un especificador de formato personalizado completo que incluya el componente de milisegundos de un valor de fecha y hora es que éste establece un formato codificado de forma rígida que es posible que no se corresponda con la organización de elementos horarios de la referencia cultural actual de la aplicación. Una alternativa más conveniente consiste en recuperar uno de los modelos de presentación de fecha y hora definidos por el objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) de la referencia cultural actual y modificarlo para incluir los milisegundos. En el ejemplo se muestra también este enfoque. Se recupera el modelo completo de fecha y hora de la referencia cultural actual de la propiedad [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) y luego se inserta el modelo personalizado `.ffff` tras el modelo de segundos. Observe que en el ejemplo se utiliza una expresión regular para realizar esta operación en una única llamada al método.

También puede utilizar un especificador de formato personalizado para mostrar una fracción de segundo distinta de los milisegundos. Por ejemplo, el especificador de formato personalizado `f` o `F` muestra las décimas de segundo, el especificador de formato personalizado `ff` o `FF` muestra las centésimas de segundo y el especificador de formato personalizado `ffff` o `FFFF` muestra las diezmilésimas de segundo. Las fracciones de milisegundo se truncan en lugar de redondearse en la cadena devuelta. Estos especificadores de formato se utilizan en el ejemplo siguiente.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"));
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"));      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"));
// The example displays the following output to the console:
//    45.1 seconds
//    45.18 seconds
//    45.1800 seconds
```

```vb
Dim dateValue As New DateTime(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"))
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"))      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"))
' The example displays the following output to the console:
'    45.1 seconds
'    45.18 seconds
'    45.1800 seconds
```

> [!NOTE]
> Es posible mostrar unidades fraccionarias de segundo muy pequeñas, como diezmilésimas o cienmilésimas de segundo. Sin embargo, estos valores no suelen ser significativos. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.

## <a name="see-also"></a>Vea también

[System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)

[Cadenas con formato de fecha y hora personalizado](custom-datetime.md)


