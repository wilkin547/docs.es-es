---
title: Analizar cadenas de fecha y hora en .NET
description: Analizar cadenas de fecha y hora en .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a>Analizar cadenas de fecha y hora en .NET

Los métodos de análisis convierten la representación de cadena de una fecha y hora en un objeto [DateTime](xref:System.DateTime) equivalente. Los métodos [Parse](xref:System.DateTime.Parse(System.String)) y [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) convierten varias representaciones comunes de fecha y hora. Los métodos [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) y [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) convierten una representación de cadena que se ajusta al patrón especificado por una cadena de formato de fecha y hora. (Consulte los temas sobre [cadenas con formato de fecha y hora estándar](standard-datetime.md) y [cadenas con formato de fecha y hora personalizado](custom-datetime.md)). 

El análisis se ve influido por las propiedades de un proveedor de formato que proporcione información, como las cadenas usadas para los separadores de fecha y hora, y los nombres de meses, días y eras. El proveedor de formato es el objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro [IFormatProvider](xref:System.IFormatProvider) de un método de análisis. Para el parámetro [IFormatProvider](xref:System.IFormatProvider), debe especificar un objeto [CultureInfo](xref:System.Globalization.CultureInfo), que representa una referencia cultural, o un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). 

La representación de cadena de una fecha que se vaya a analizar debe incluir el mes y, al menos, un día o año. La representación de cadena de una hora debe incluir la hora y, al menos, los minutos o el designador a. m./p. m. Pero, si es posible, el análisis proporciona valores predeterminados para los componentes omitidos. Si falta una fecha, se usa como valor predeterminado la fecha actual; si falta un año, se usa como valor predeterminado el año actual; si falta un día del mes, se usa como valor predeterminado el primer día del mes; y si falta una hora, se usa como valor predeterminado la medianoche. 

Si la representación de cadena solo especifica una hora, el análisis devuelve un objeto [DateTime](xref:System.DateTime) con sus propiedades [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month) y [Day](xref:System.DateTime.Day) establecidas en los valores correspondientes de la propiedad [Today](xref:System.DateTime.Today). Pero si se especifica la constante [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) en el método de análisis, las propiedades de año, mes y día resultantes se establecen en el valor 1.

Además de un componente de fecha y hora, la representación de cadena de una fecha y hora puede incluir una diferencia horaria que indica cuánto difiere la hora respecto de la hora universal coordinada (UTC). Por ejemplo, la cadena "14/2/2007 5:32:00 -7:00" define una hora que es siete horas anterior a la hora UTC. Si se omite la diferencia horaria de la representación de cadena de una hora, el análisis devuelve un objeto [DateTime](xref:System.DateTime) con su propiedad [Kind](xref:System.DateTime.Kind) establecida en [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified). Si se especifica la diferencia horaria, el análisis devuelve un objeto [DateTime](xref:System.DateTime) con su propiedad [Kind](xref:System.DateTime.Kind) establecida en [Local](xref:System.DateTimeKind.Local) y su valor ajustado a la zona horaria local del equipo. Puede modificar este comportamiento mediante el uso de una constante [DateTimeStyles](xref:System.Globalization.DateTimeStyles) con el método de análisis.

El proveedor de formato también se usa para interpretar una fecha numérica ambigua. Por ejemplo, no está claro qué componentes de la fecha representada por la cadena "02/03/04" son el mes, el día y el año. En este caso, los componentes se interpretan según el orden de formatos de fecha similares del proveedor de formato. 

## <a name="parse"></a>Parse

En el ejemplo de código siguiente se muestra el uso del método `Parse` para convertir una cadena en un valor `DateTime`. En este ejemplo se usa la referencia cultural asociada al subproceso actual para realizar el análisis. Si el objeto [CultureInfo](xref:System.Globalization.CultureInfo) asociado a la referencia cultural actual no puede analizar la cadena de entrada, se produce una excepción [FormatException](xref:System.FormatException).

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

También puede especificar un objeto `CultureInfo` establecido en una de las referencias culturales definidas por ese objeto, o puede especificar uno de los objetos [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) estándar devueltos por la propiedad [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). En el ejemplo de código siguiente se usa un proveedor de formato para analizar una cadena alemana en un valor `DateTime`. Se define un objeto `CultureInfo` que representa la referencia cultural de-DE y se pasa con la cadena que se está analizando para garantizar el análisis correcto de esta cadena concreta. Esto impide cualquier opción que se encuentre en `CurrentCulture` de `CurrentThread`.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

Pero, aunque puede usar sobrecargas del método [Parse](xref:System.DateTime.Parse(System.String)) para especificar proveedores de formato personalizados, el método no admite el uso de proveedores de formato no estándar. Para analizar una fecha y hora expresadas en un formato no estándar, use en su lugar el método [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)).

En el ejemplo de código siguiente se usa la enumeración [DateTimeStyles](xref:System.Globalization.DateTimeStyles) para especificar que la información de fecha y hora actual no se debe agregar al valor `DateTime` para los campos que la cadena no defina.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a>ParseExact

El método [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) convierte una cadena que se ajusta a un patrón de cadena especificado en un objeto `DateTime`. Cuando se pasa a este método una cadena que no tiene la forma especificada, se produce una excepción [FormatException](xref:System.FormatException). Puede especificar uno de los especificadores de formato de fecha y hora estándar o una combinación limitada de especificadores de formato de fecha y hora personalizados. Con el uso de especificadores de formato personalizados, es posible construir una cadena de reconocimiento personalizada. Para obtener una explicación de los especificadores, consulte los temas sobre [cadenas con formato de fecha y hora estándar](standard-datetime.md) y [cadenas con formato de fecha y hora personalizado](custom-datetime.md). 

Cada sobrecarga del método [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) también tiene un parámetro [IFormatProvider](xref:System.IFormatProvider) que normalmente proporciona información específica de la referencia cultural sobre el formato de la cadena. Normalmente, este objeto [IFormatProvider](xref:System.IFormatProvider) es un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa una referencia cultural estándar o un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) devuelto por la propiedad [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). Pero, a diferencia de otras funciones de análisis de fecha y hora, este método también admite un objeto [IFormatProvider](xref:System.IFormatProvider) que define un formato de fecha y hora no estándar. 

En el ejemplo de código siguiente, se pasa al método `ParseExact` un objeto de cadena para que lo analice, seguido de un especificador de formato, seguido de un objeto `CultureInfo`. Este método `ParseExact` solo puede analizar cadenas que muestren el patrón de fecha larga de la referencia cultural en-US.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a>Vea también

[Analizar cadenas en .NET](parsing-strings.md)

[Aplicar formato a tipos en .NET](formatting-types.md)

[Conversión de tipos en .NET](type-conversion.md)


