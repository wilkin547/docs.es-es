---
title: "Aplicación de formato a tipos"
description: "Aplicación de formato a tipos"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: dc0693c2e2c034c4c71b4270ef2812be4af72e72
ms.lasthandoff: 03/02/2017

---

# <a name="formatting-types"></a>Aplicación de formato a tipos

Aplicar formato es el proceso de convertir una instancia de una clase, una estructura o un valor de enumeración en su representación de cadena, a menudo para que la cadena resultante se pueda mostrar a los usuarios o deserializar para restaurar el tipo de datos original. Esta conversión puede plantear varios desafíos:

* La forma en que se almacenan internamente los valores no refleja necesariamente la manera en que los usuarios desean verlos. Por ejemplo, un número de teléfono podría almacenarse con el formato **8009999999**, que no es fácil de usar. Se debería mostrar en su lugar como **800-999-9999**. Consulte la sección [Cadenas de formato personalizado](#custom-format-strings) para obtener un ejemplo que da formato a un número de esta forma. 

* A veces, la conversión de un objeto en su representación de cadena no es intuitiva. Por ejemplo, no está claro cómo debe aparecer la representación de cadena de un objeto **Temperature** o un objeto **Person**. Para obtener un ejemplo en el que se da formato a un objeto **Temperature** de varias formas, consulte la sección [Cadenas de formato estándar](#standard-format-strings).

* A menudo, los valores requieren un formato dependiente de la referencia cultural. Por ejemplo, en una aplicación en la que se usan números para reflejar los valores monetarios, las cadenas numéricas deben incluir el símbolo de divisa, el separador de grupo (que en la mayoría de las referencias culturales es el separador de miles) y el símbolo decimal correspondientes a la referencia cultural actual. Para ver un ejemplo, consulte la sección [Formato que tiene en cuenta las referencias culturales con proveedores de formato y la interfaz IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface). 

* Puede que una aplicación muestre el mismo valor de diferentes maneras. Por ejemplo, es posible que una aplicación represente un miembro de enumeración mostrando una representación de cadena de su nombre o mostrando su valor subyacente. Para obtener un ejemplo en el que se da formato a un miembro de la enumeración [DayOfWeek](xref:System.DayOfWeek) de maneras diferentes, consulte la sección [Cadenas de formato estándar](#standard-format-strings).

.NET proporciona compatibilidad de formato enriquecida que permite a los desarrolladores hacer frente a estos requisitos. 

> [!NOTE]
> La aplicación de formato convierte el valor de un tipo en una representación de cadena. El análisis es lo contrario que la aplicación de formato. Una operación de análisis crea una instancia de un tipo de datos a partir de su representación de cadena. Para obtener información sobre cómo convertir cadenas en otros tipos de datos, consulte [Analizar cadenas](parsing-strings.md).

Esta información general contiene las siguientes secciones:

* [Formato en .NET](#formatting-in-net)

* [Formato predeterminado mediante el método ToString](#default-formatting-using-the-tostring-method)

* [Invalidación del método ToString](#overriding-the-tostring-method)

* [Método ToString y cadenas de formato](#the-tostring-method-and-format-strings)

    * [Cadenas de formato estándar](#standard-format-strings)
    
    * [Cadenas de formato personalizado](#custom-format-strings)
    
    * [Cadenas de formato y tipos de .NET](#format-strings-and-net-types)
    
* [Formato que tiene en cuenta las referencias culturales con proveedores de formato y la interfaz IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [Formato que tiene en cuenta las referencias culturales de valores numéricos](#culture-sensitive-formatting-of-numeric-values)
    
    * [Formato que tiene en cuenta las referencias culturales de valores de fecha y hora](#culture-sensitive-formatting-of-date-and-time-values)
    
* [Interfaz IFormattable](#the-iformattable-interface)

* [Formatos compuestos](#composite-formatting)

* [Formato personalizado con ICustomFormatter](#custom-formatting-with-icustomformatter)

* [Temas relacionados](#related-topics)

* [Referencia](#reference)

## <a name="formatting-in-net"></a>Formato en .NET

El mecanismo básico para aplicar formato es la implementación predeterminada del método [Object.ToString](xref:System.Object.ToString), que se explica en la sección [Formato predeterminado mediante el método ToString](#default-formatting-using-the-tostring-method) más adelante en este tema. Pero .NET proporciona varias formas de modificar y extender su compatibilidad de formato predeterminado. Entre ellas se incluyen las siguientes:

* Invalidar el método [Object.ToString](xref:System.Object.ToString) para definir una representación de cadena personalizada del valor de un objeto. Para obtener más información, consulte la sección [Invalidación del método ToString](#overriding-the-tostring-method) más adelante en este tema.

* Definir especificadores de formato que permitan que la representación de cadena del valor de un objeto adopte varios formatos. Por ejemplo, el especificador de formato "X" en la siguiente instrucción convierte un entero en la representación de cadena de un valor hexadecimal.

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  Para obtener más información sobre los especificadores de formato, consulte la sección [Método ToString y cadenas de formato](#the-tostring-method-and-format-strings).
  
* Usar proveedores de formato para aprovechar las convenciones de formato de una referencia cultural concreta. Por ejemplo, la instrucción siguiente muestra un valor de divisa usando las convenciones de formato de la referencia cultural en-US. 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  Para obtener más información sobre cómo aplicar formato con proveedores de formato, consulte la sección [Formato que tiene en cuenta las referencias culturales con proveedores de formato y la interfaz IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).  
  
* Implementar la interfaz [IFormattable](xref:System.IFormattable) para admitir tanto la conversión de cadenas con la clase [Convert](xref:System.Convert) como formatos compuestos. Para obtener más información, consulte la sección [Interfaz IFormattable](#the-iformattable-interface).

* Usar formatos compuestos para incrustar la representación de cadena de un valor en una cadena más larga. Para obtener más información, consulte la sección [Formatos compuestos](#composite-formatting).

* Implementar [ICustomFormatter](xref:System.ICustomFormatter) e [IFormatProvider](xref:System.IFormatProvider) para proporcionar una solución completa y personalizada de formato. Para obtener más información, consulte la sección [Formato personalizado con ICustomFormatter](#custom-formatting-with-icustomformatter).

En las secciones siguientes se examinan estos métodos para convertir un objeto en su representación de cadena.

## <a name="default-formatting-using-the-tostring-method"></a>Formato predeterminado mediante el método ToString

Cada tipo derivado de [System.Object](xref:System.Object) hereda automáticamente un método [ToString](xref:System.Object.ToString) sin parámetros, que devuelve el nombre del tipo de forma predeterminada. En el ejemplo siguiente se ilustra el método [ToString](xref:System.Object.ToString) predeterminado. Se define una clase denominada `Automobile` que no tiene ninguna implementación. Cuando se crea una instancia de la clase y se llama a su método [ToString](xref:System.Object.ToString), se muestra el nombre de su tipo. Observe que en el ejemplo no se llama explícitamente al método [ToString](xref:System.Object.ToString). El método [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) llama implícitamente al método [ToString](xref:System.Object.ToString) del objeto pasado como argumento. 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

Puesto que todos los tipos distintos de las interfaces se derivan de [Object](xref:System.Object), esta funcionalidad se proporciona automáticamente a sus clases o estructuras personalizadas. Pero la funcionalidad proporcionada por el método [ToString](xref:System.Object.ToString) predeterminado es limitada: aunque identifica el tipo, no proporciona ninguna información sobre una instancia del tipo. Para proporcionar una representación de cadena de un objeto que proporciona información sobre ese objeto, debe invalidar el método [ToString](xref:System.Object.ToString).

> [!NOTE]
> Las estructuras heredan de [ValueType](xref:System.ValueType), que a su vez se deriva de [Object](xref:System.Object). Aunque [ValueType](xref:System.ValueType) invalida [Object.ToString](xref:System.Object.ToString), su implementación es idéntica.

## <a name="overriding-the-tostring-method"></a>Invalidación del método ToString

La presentación del nombre de un tipo suele tener un uso limitado y no permite a los consumidores de sus tipos diferenciar una instancia de otra. Pero puede invalidar el método [ToString](xref:System.Object.ToString) para proporcionar una representación más útil del valor de un objeto. En el ejemplo siguiente se define un objeto `Temperature` y se invalida su método [ToString](xref:System.Object.ToString) para mostrar la temperatura en grados centígrados.

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

En .NET, el método [ToString](xref:System.Object.ToString) de cada tipo de valor primitivo se ha invalidado para que se muestre el valor del objeto en lugar de su nombre. En la tabla siguiente se muestra la invalidación para cada tipo primitivo. Observe que la mayoría de los métodos invalidados llaman a otra sobrecarga del método [ToString](xref:System.Object.ToString) y le pasan el especificador de formato "G", que define el formato general de su tipo, y un objeto [IFormatProvider](xref:System.IFormatProvider) que representa la referencia cultural actual.

Tipo | Invalidación de ToString
---- | -----------------
[Boolean](xref:System.Boolean) | Devuelve [Boolean.TrueString](xref:System.Boolean.TrueString) o [Boolean.FalseString](xref:System.Boolean.FalseString).
[Byte](xref:System.Byte) | Llama a `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Byte](xref:System.Byte) correspondiente a la referencia cultural actual.
[Char](xref:System.Char) | Devuelve el carácter como una cadena.
[DateTime](xref:System.DateTime) | Llama a `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` para dar formato al valor de fecha y hora correspondiente a la referencia cultural actual. 
[Decimal](xref:System.Decimal) | Llama a `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Decimal](xref:System.Decimal) correspondiente a la referencia cultural actual.
[Double](xref:System.Double) | Llama a `Double.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Double](xref:System.Double) correspondiente a la referencia cultural actual.
[Int16](xref:System.Int16) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Int16](xref:System.Int16) correspondiente a la referencia cultural actual.
[Int32](xref:System.Int32) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Int32](xref:System.Int32) correspondiente a la referencia cultural actual.
[Int64](xref:System.Int64) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Int64](xref:System.Int64) correspondiente a la referencia cultural actual.
[SByte](xref:System.SByte) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [SByte](xref:System.SByte) | correspondiente la referencia cultural actual.
[Single](xref:System.Single) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [Single](xref:System.Single) correspondiente a la referencia cultural actual.
[UInt32](xref:System.UInt32) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [UInt32](xref:System.UInt32) correspondiente a la referencia cultural actual.
[UInt32](xref:System.UInt32) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [UInt32](xref:System.UInt32) correspondiente a la referencia cultural actual.
[UInt64](xref:System.UInt64) | Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo [UInt64](xref:System.UInt64) correspondiente a la referencia cultural actual.

## <a name="the-tostring-method-and-format-strings"></a>Método ToString y cadenas de formato

Recurrir al método [ToString](xref:System.Object.ToString) predeterminado o invalidar [ToString](xref:System.Object.ToString) resulta apropiado cuando un objeto tiene una única representación de cadena. Sin embargo, el valor de un objeto tiene a menudo varias representaciones. Por ejemplo, una temperatura puede expresarse en grados Fahrenheit, grados centígrados o grados Kelvin. De manera similar, el valor entero 10 puede representarse de numerosas maneras; por ejemplo, 10, 10,0, 1,0e01 o $10,00.

Para que un valor pueda tener varias representaciones de cadena, .NET usa cadenas de formato. Una cadena de formato es una cadena que contiene uno o varios especificadores de formato predefinidos, que son caracteres individuales o grupos de caracteres que definen cómo el método [ToString](xref:System.Object.ToString) debe dar formato a su salida. Después, se pasa la cadena de formato como un parámetro al método [ToString](xref:System.Object.ToString) del objeto, por lo que determina cómo debe mostrarse la representación de cadena del valor de ese objeto.

Todos los tipos numéricos, de fecha y hora, y de enumeración de .NET admiten un conjunto predefinido de especificadores de formato. Las cadenas de formato también se pueden emplear para definir varias representaciones de cadena de los tipos de datos definidos por una aplicación.

### <a name="standard-format-strings"></a>Cadenas de formato estándar

Una cadena de formato estándar contiene un único especificador de formato, que es un carácter alfabético que define la representación de cadena del objeto al que se aplica, junto con un especificador de precisión opcional que afecta a cuántos dígitos se muestran en la cadena de resultado. Si el especificador de precisión se omite o no se admite, un especificador de formato estándar es equivalente a una cadena de formato estándar. 

.NET define un conjunto de especificadores de formato estándar para todos los tipos numéricos, de fecha y hora, y de enumeración. Por ejemplo, cada una de estas categorías admite un especificador de formato estándar "G", que define una representación de cadena general de un valor de ese tipo.

Las cadenas de formato estándar para los tipos de enumeración controlan directamente la representación de cadena de un valor. Las cadenas de formato que se pasan al método [ToString](xref:System.Object.ToString) de un valor de enumeración determinan si el valor se muestra con su nombre de cadena (especificadores de formato "G" y "F"), su valor integral subyacente (especificador de formato "D") o su valor hexadecimal (especificador de formato "X"). En el ejemplo siguiente se muestra el uso de cadenas de formato estándar para dar formato a un valor de enumeración [DayOfWeek](xref:System.DayOfWeek). 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

Para obtener información acerca de las cadenas de formato de enumeración, consulte [Cadenas de formato de enumeración](enumeration-format.md).

Las cadenas de formato estándar para tipos numéricos normalmente definen una cadena de resultado cuya apariencia exacta está controlada por uno o más valores de propiedad. Por ejemplo, el especificador de formato "C" da formato a un número como un valor de divisa. Al llamar al método [ToString](xref:System.Object.ToString) con el especificador de formato "C" como único parámetro, se usan los siguientes valores de propiedad del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) de la referencia cultural actual para definir la representación de cadena del valor numérico:

* La propiedad [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol), que especifica el símbolo de divisa de la referencia cultural actual.

* La propiedad [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) o [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern), que devuelve un entero que determina lo siguiente: 

    * La posición del símbolo de divisa.
    
    * Si los valores negativos se indican mediante un signo negativo inicial, un signo negativo final o paréntesis.
    
    * Si aparece un espacio entre el valor numérico y el símbolo de divisa.
    
* La propiedad [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits), que define el número de dígitos fraccionarios en la cadena de resultado.

* La propiedad [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator), que define el símbolo del separador decimal en la cadena de resultado.

* La propiedad [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator), que define el símbolo del separador de grupo.

* La propiedad [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes), que define el número de dígitos de cada grupo que hay a la izquierda del decimal.

* La propiedad [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign), que determina el signo negativo usado en la cadena de resultado si no se emplean paréntesis para indicar valores negativos.

Además, las cadenas de formato numérico pueden incluir un especificador de precisión. El significado de este especificador depende de la cadena de formato con la que se usa, pero suele indicar el número total de dígitos o el número de dígitos fraccionarios que deben aparecer en la cadena de resultado. Por ejemplo, en el ejemplo siguiente se usa la cadena numérica estándar "X4" y un especificador de precisión para crear un valor de cadena que tiene cuatro dígitos hexadecimales.

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

Para obtener más información acerca de las cadenas con formato numérico estándar, consulte [Cadenas con formato numérico estándar](standard-numeric.md). 

Las cadenas de formato estándar para valores de fecha y hora son alias de las cadenas de formato personalizado almacenadas por una clase [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) determinada. Por ejemplo, al llamar al método [ToString](xref:System.Object.ToString) de un valor de fecha y hora con el especificador de formato "D" se muestran la fecha y la hora usando la cadena de formato personalizado que está almacenada en la propiedad [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) de la referencia cultural actual. (Para obtener más información sobre las cadenas de formato personalizado, consulte la [próxima sección](#custom-format-strings).) En el ejemplo siguiente se ilustra esta relación.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

Para obtener más información acerca de las cadenas de formato de fecha y hora estándar, consulte [Cadenas de formato de fecha y hora estándar](standard-datetime.md).

También se pueden emplear las cadenas de formato estándar para definir la representación de cadena de un objeto definido por la aplicación generado por el método `ToString(String)` del objeto. Puede definir los especificadores de formato estándar concretos que su objeto admite y determinar si distinguen entre mayúsculas y minúsculas o no. Su implementación del método `ToString(String)` debe aceptar lo siguiente:

* Un especificador de formato "G" que representa un formato personalizado o común del objeto. La sobrecarga sin parámetros del método `ToString` del objeto debe llamar a su sobrecarga de `ToString(String)` y pasarle la cadena de formato estándar "G".

* Compatibilidad con un especificador de formato que sea igual a una referencia nula. Un especificador de formato que es igual a una referencia nula debe considerarse equivalente al especificador de formato "G".

Por ejemplo, una clase `Temperature` puede almacenar internamente la temperatura en grados centígrados y usar especificadores de formato para representar el valor del objeto `Temperature` en grados centígrados, grados Fahrenheit y grados Kelvin. Esto se muestra en el ejemplo siguiente.

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a>Cadenas de formato personalizado

Además de las cadenas de formato estándar, .NET define cadenas de formato personalizado tanto para los valores numéricos como para los valores de fecha y hora. Una cadena de formato personalizado se compone de uno o varios especificadores de formato personalizado que definen la representación de cadena de un valor. Por ejemplo, la cadena de formato personalizado de fecha y hora “yyyy/mm/dd hh:mm:ss.ffff t zzz” convierte una fecha en su representación de cadena con el formato "2008/11/15 07:45:00.0000 P -08:00" para la referencia cultural en-US. Del mismo modo, la cadena de formato personalizado “0000” convierte el valor entero 12 en “0012”. Para obtener una lista completa de las cadenas de formato personalizado, consulte [Cadenas de formato de fecha y hora personalizado](custom-datetime.md) y [Cadenas con formato numérico personalizado](custom-numeric.md).

Si una cadena de formato consta de un único especificador de formato personalizado, el especificador de formato debe ir precedido del símbolo de porcentaje (%) para evitar la confusión con un especificador de formato estándar. En el ejemplo siguiente, se usa el especificador de formato personalizado "M" para mostrar un número de un dígito o de dos dígitos del mes de una fecha determinada.

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

Muchas cadenas de formato estándar para valores de fecha y hora son alias para cadenas de formato personalizado definidas por propiedades del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Las cadenas de formato personalizado también ofrecen una gran flexibilidad a la hora de proporcionar formatos definidos por la aplicación para los valores numéricos o de fecha y hora. Puede definir sus propias cadenas de resultado personalizadas para los valores numéricos y de fecha y hora si combina varios especificadores de formato personalizados en una única cadena de formato personalizado. En el ejemplo siguiente se define una cadena de formato personalizado que muestra el día de la semana entre paréntesis después del nombre de mes, el día y el año.

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

En el ejemplo siguiente se define una cadena de formato personalizado que muestra un valor [Int64](xref:System.Int64) como un número de teléfono de Estados Unidos estándar de siete dígitos con el código de área. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

Aunque las cadenas de formato estándar pueden satisfacer generalmente la mayoría de las necesidades de formato para los tipos definidos por la aplicación, también puede definir especificadores de formato personalizados para dar formato a sus tipos. 

### <a name="format-strings-and-net-types"></a>Cadenas de formato y tipos de .NET

Todos los tipos numéricos (es decir, los tipos [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) y [BigInteger](xref:System.Numerics.BigInteger)), así como [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), y todos los tipos de enumeración, admiten aplicar formato con cadenas de formato. Para obtener información sobre las cadenas de formato específicas que admite cada tipo, consulte los temas siguientes: 

Título | Definición
----- | ----------
[Cadenas con formato numérico estándar](standard-numeric.md) | Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores numéricos. 
[Cadenas con formato numérico personalizado](custom-numeric.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores numéricos.
[Cadenas con formato de fecha y hora estándar](standard-datetime.md) | Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores [DateTime](xref:System.DateTime).
[Cadenas con formato de fecha y hora personalizado](custom-datetime.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores de [DateTime](xref:System.DateTime).
[Cadenas de formato TimeSpan estándar](standard-timespan.md) | Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de intervalos de tiempo.
[Cadenas de formato TimeSpan personalizado](custom-timespan.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para intervalos de tiempo.
[Cadenas de formato de enumeración](enumeration-format.md) | Describe cadenas de formato estándar que se usan para crear representaciones de cadena de valores de enumeración.
[Guid.ToString(String)](xref:System.Guid.ToString(System.String)) | Describe cadenas de formato estándar para los valores de [Guid](xref:System.Guid).

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a>Formato que tiene en cuenta las referencias culturales con proveedores de formato y la interfaz IFormatProvider

Si bien los especificadores de formato permiten personalizar el formato de los objetos, la generación de una representación de cadena significativa de los objetos requiere a menudo información de formato adicional. Por ejemplo, cuando se da formato a un número como un valor de divisa mediante la cadena de formato estándar "C" o la cadena de formato personalizado “$ #,#.00”, se necesita como mínimo información sobre el símbolo de divisa, el separador de grupos y el separador decimal correctos para incluirla en la cadena con formato. En .NET, esta información de formato adicional está disponible mediante la interfaz [IFormatProvider](xref:System.IFormatProvider), que se proporciona como un parámetro a una o más sobrecargas del método `ToString` de los tipos numéricos y de fecha y hora. Las implementaciones de [IFormatProvider](xref:System.IFormatProvider) se usan en .NET para admitir el formato específico de una referencia cultural. En el siguiente ejemplo se muestra cómo cambia la representación en forma de cadena de un objeto cuando se le da formato con tres objetos [IFormatProvider](xref:System.IFormatProvider) que representan referencias culturales diferentes.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

La interfaz [IFormatProvider](xref:System.IFormatProvider) incluye un método, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), que tiene un único parámetro que especifica el tipo de objeto que proporciona información de formato. Si el método puede proporcionar un objeto de ese tipo, lo devuelve. De lo contrario, devuelve una referencia nula.

[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) es un método de devolución de llamada. Cuando se llama a una sobrecarga de método `ToString` que incluye un parámetro [IFormatProvider](xref:System.IFormatProvider), llama al método [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) de ese objeto [IFormatProvider](xref:System.IFormatProvider). El método [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) devuelve un objeto que proporciona al método `ToString` la información de formato necesaria especificada por su parámetro *formatType*. 

Varios métodos de formato o de conversión de cadenas incluyen un parámetro de tipo [IFormatProvider](xref:System.IFormatProvider) pero, en muchos casos, se omite el valor del parámetro cuando se llama al método. En la tabla siguiente se muestran algunos métodos de formato que usan el parámetro y el tipo del objeto [Type](xref:System.Type) que pasan al método [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). 

Método | Tipo de parámetro *formatType*
------ | ------------------------------
Método `ToString` de tipos numéricos | [System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)
Método `ToString` de tipos de fecha y hora | [System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)
[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)

.NET proporciona tres clases que implementan [IFormatProvider](xref:System.IFormatProvider): 

* [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), una clase que proporciona información de formato para los valores de fecha y hora para una referencia cultural concreta. Su implementación [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) devuelve una instancia de sí mismo.

* [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), una clase que proporciona información de formato numérico para una referencia cultural concreta. Su implementación [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) devuelve una instancia de sí mismo.

* [CultureInfo](xref:System.Globalization.CultureInfo). Su implementación [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) puede devolver un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) para proporcionar información de formato numérico o un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) para proporcionar información de formato para los valores de fecha y hora. 

También se puede implementar un proveedor de formato propio para reemplazar cualquiera de estas clases. Sin embargo, el método `GetFormat` de la implementación debe devolver un objeto del tipo mostrado en la tabla anterior si debe proporcionar información de formato al método `ToString`.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Formato que tiene en cuenta las referencias culturales de valores numéricos

De forma predeterminada, el formato de los valores numéricos depende de la referencia cultural. Si no especifica una referencia cultural cuando llama a un método de formato, se utilizan las convenciones de formato de la referencia cultural del subproceso actual. Esto se muestra en el ejemplo siguiente, que cambia la referencia cultural del subproceso actual cuatro veces y después llama al método [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)). En cada caso, la cadena resultante refleja las convenciones de formato de la referencia cultural actual. Esto se debe a que los métodos `ToString` y `ToString(String)` incluyen llamadas a cada tipo numérico del método `ToString(String, IFormatProvider)`. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

También se puede dar formato a un valor numérico para una referencia cultural concreta llamando a una sobrecarga de `ToString` que tenga un parámetro *provider* y pasándole uno de los elementos siguientes: 

* Un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural cuyas convenciones de formato se van a usar. El método [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) devuelve el valor de la propiedad [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), que es el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que proporciona información sobre el formato de la referencia cultural para los valores numéricos.

* Un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que define las convenciones de formato de la referencia cultural que se van a usar. Su método [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) devuelve una instancia de sí mismo.

En el siguiente ejemplo se usan objetos [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que representan las referencias culturales de inglés (Estados Unidos) e inglés (Reino Unido), y las referencias culturales neutras de francés y ruso para dar formato a un número de punto flotante.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Formato que tiene en cuenta las referencias culturales de valores de fecha y hora

De forma predeterminada, el formato de los valores de fecha y hora tiene en cuenta las referencias culturales. Si no especifica una referencia cultural cuando llama a un método de formato, se utilizan las convenciones de formato de la referencia cultural del subproceso actual. Esto se muestra en el ejemplo siguiente, que cambia la referencia cultural del subproceso actual cuatro veces y después llama al método [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)). En cada caso, la cadena resultante refleja las convenciones de formato de la referencia cultural actual. Esto se debe a que los métodos [DateTime.ToString ()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) y [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) encapsulan llamadas a los métodos [DateTime.ToString (String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) y [DateTimeOffset.ToString (String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)).

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

También se puede dar formato a un valor de fecha y hora para una referencia cultural concreta llamando a una sobrecarga de [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) o [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) que tenga un parámetro provider y pasándole uno de los elementos siguientes: 

* Un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural cuyas convenciones de formato se van a usar. El método [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) devuelve el valor de la propiedad [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), que es el objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que proporciona información sobre el formato de la referencia cultural para los valores numéricos.

* Un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que define las convenciones de formato de la referencia cultural que se van a usar. Su método [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) devuelve una instancia de sí mismo.

En el siguiente ejemplo se usan objetos [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) que representan las referencias culturales de inglés (Estados Unidos) e inglés (Reino Unido), y las referencias culturales neutras de francés y ruso para dar formato a una fecha. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a>Interfaz IFormattable

Normalmente, los tipos que sobrecargan el método `ToString` con una cadena de formato y un parámetro [IFormatProvider](xref:System.IFormatProvider) también implementan la interfaz [IFormattable](xref:System.IFormattable). Esta interfaz tiene un solo miembro, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), que incluye una cadena de formato y un proveedor de formato como parámetros.

La implementación de la interfaz [IFormattable](xref:System.IFormattable) para su clase definida por la aplicación ofrece dos ventajas: 

* Compatibilidad con la conversión de cadenas por la clase [Convert](xref:System.Convert). Las llamadas a los métodos [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) y [Convert.ToString (Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) llaman a su implementación de [IFormattable](xref:System.IFormattable) automáticamente.

* Compatibilidad con formatos compuestos. Si se usa un elemento de formato que incluye una cadena de formato para dar formato a su tipo personalizado, Common Language Runtime llama automáticamente a su implementación de [IFormattable](xref:System.IFormattable) y le pasa la cadena de formato. Para obtener más información sobre los formatos compuestos con métodos como `String.Format` o `Console.WriteLine`, consulte la sección [Formatos compuestos](#composite-formatting).

En el ejemplo siguiente se define una clase `Temperature` que implementa la interfaz [IFormattable](xref:System.IFormattable). Admite los especificadores de formato "C" o "G" para mostrar la temperatura en grados centígrados, el especificador de formato "F" para mostrar la temperatura en grados Fahrenheit y el especificador de formato "K" para mostrar la temperatura en grados Kelvin.

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

En el ejemplo siguiente se crea una instancia de un objeto `Temperature`. Después llama al método [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) y usa varias cadenas de formato compuesto para obtener representaciones de cadena diferentes de un objeto `Temperature`. Cada una de estas llamadas al método, a su vez, llama a la implementación de [IFormattable](xref:System.IFormattable) de la clase `Temperature`.

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a>Formatos compuestos

Algunos métodos, como `String.Format` y `StringBuilder.AppendFormat`, admiten formatos compuestos. Una cadena de formato compuesto es un tipo de plantilla que devuelve una sola cadena que incorpora la representación de cadena de cero, uno o más objetos. Cada objeto se representa en la cadena de formato compuesto mediante un elemento de formato indizado. El índice del elemento de formato corresponde a la posición del objeto que representa en la lista de parámetros del método. Los índices son de base cero. Por ejemplo, en la siguiente llamada al método `String.Format`, el primer elemento de formato, `{0:D}` se reemplaza con la representación de cadena de `thatDate`; el segundo elemento de formato, `{1}`, se reemplaza con la representación de cadena de `item1` y el tercer elemento de formato, `{2:C2}`, se reemplaza con la representación de cadena de `item1.Value`.

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

Además de reemplazar un elemento de formato con la representación de cadena de su objeto correspondiente, los elementos de formato también permiten controlar lo siguiente: 

* La forma específica en que un objeto se representa como una cadena, si el objeto implementa la interfaz [IFormattable](xref:System.IFormattable) y admite cadenas de formato. Para ello, siga el índice del elemento de formato con un signo : (dos puntos) seguido de una cadena de formato válida. En el ejemplo anterior, esto se hacía dando formato a un valor de fecha con la cadena de formato "d" (patrón de fecha corta) (por ejemplo, `{0:d}`) y dando formato a un valor numérico con la cadena de formato "C2" (por ejemplo, `{2:C2}`) para representar el número como un valor de moneda con dos decimales fraccionarios. 

* El ancho del campo que contiene la representación de cadena del objeto y la alineación de la representación de cadena en ese campo. Para ello, escriba una coma (,) seguida del ancho del campo. La cadena se alinea a la derecha en el campo si el ancho del campo es un valor positivo, y se alinea a la izquierda si el ancho del campo es un valor negativo. En el ejemplo siguiente los valores de fecha se alinean a la izquierda en un campo de 20 caracteres y los valores decimales con un dígito fraccionario se alinean a la derecha en un campo de 11 caracteres. 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

Tenga en cuenta que, si están presentes tanto el componente de cadena de alineación como el componente de cadena de formato, el primero precede al último (por ejemplo, `{0,-20:g}`). 

Para obtener más información sobre los formatos compuestos, consulte [Formatos compuestos](composite-format.md).

## <a name="custom-formatting-with-icustomformatter"></a>Formato personalizado con ICustomFormatter

Dos métodos de formato compuesto, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) y [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), incluyen un parámetro de proveedor de formato que admite formatos personalizados. Cuando se llama a alguno de estos métodos de formato, se pasa un objeto [Type](xref:System.Type) que representa una interfaz [ICustomFormatter](xref:System.ICustomFormatter) al método `GetFormat` del proveedor de formato. Después, el método `GetFormat` devuelve la implementación de [ICustomFormatter](xref:System.ICustomFormatter) que proporciona el formato personalizado.

La interfaz [ICustomFormatter](xref:System.ICustomFormatter) tiene un único método, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), al que un método de formato compuesto llama automáticamente una vez para cada elemento de formato de una cadena de formato compuesto. El método [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) tiene tres parámetros: una cadena de formato, que representa el argumento *formatString* de un elemento de formato, un objeto para dar formato y un objeto [IFormatProvider](xref:System.IFormatProvider) que proporciona servicios de formato. Normalmente, la clase que implementa [ICustomFormatter](xref:System.ICustomFormatter) también implementa [IFormatProvider](xref:System.IFormatProvider), de modo que este último parámetro es una referencia a la propia clase de formato personalizado. El método devuelve una representación de cadena con formato personalizado del objeto al que se va a dar formato. Si el método no puede dar formato al objeto, debe devolver una referencia nula.

En el ejemplo siguiente se proporciona una implementación de [ICustomFormatter](xref:System.ICustomFormatter) denominada `ByteByByteFormatter` que muestra los valores enteros como una secuencia de valores hexadecimales de dos dígitos seguidos de un espacio.

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

En el ejemplo siguiente se usa la clase `ByteByByteFormatter` para dar formato a valores enteros. Observe que se llama al método [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) más de una vez en la segunda llamada al método [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) y que el proveedor [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) predeterminado se usa en la tercera llamada al método porque el método `.ByteByByteFormatter.Format` no reconoce la cadena de formato "N0" y devuelve una referencia nula.

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a>Temas relacionados

Título | Definición
----- | ----------
[Cadenas con formato numérico estándar](standard-numeric.md) | Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores numéricos. 
[Cadenas con formato numérico personalizado](custom-numeric.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores numéricos.
[Cadenas con formato de fecha y hora estándar](standard-datetime.md) |  Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores [DateTime](xref:System.DateTime).
[Cadenas con formato de fecha y hora personalizado](custom-datetime.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores de [DateTime](xref:System.DateTime).
[Cadenas de formato TimeSpan estándar](standard-timespan.md) | Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de intervalos de tiempo.
[Cadenas de formato TimeSpan personalizado](custom-timespan.md) | Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para intervalos de tiempo.
[Cadenas de formato de enumeración](enumeration-format.md) | Describe cadenas de formato estándar que se usan para crear representaciones de cadena de valores de enumeración.
[Formatos compuestos](composite-format.md) | Describe cómo incrustar uno o más valores con formato en una cadena. Posteriormente se puede mostrar la cadena en la consola o escrita en una secuencia.
[Efectuar operaciones de formato](performing-formatting-operations.md) | Muestra los temas en los que se proporcionan instrucciones paso a paso para realizar operaciones de formato concretas.
[Analizar cadenas](parsing-strings.md) | Describe cómo inicializar objetos en los valores descritos por representaciones de cadena de dichos objetos. El análisis es la operación inversa de la aplicación de formato.

## <a name="reference"></a>Referencia

[System.IFormattable](xref:System.IFormattable)

[System.IFormatProvider](xref:System.IFormatProvider)

[System.ICustomFormatter](xref:System.ICustomFormatter)

