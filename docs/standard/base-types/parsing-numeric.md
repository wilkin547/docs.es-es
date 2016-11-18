---
title: "Analizar cadenas numéricas en .NET"
description: "Analizar cadenas numéricas en .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 209d24d32eb3b235ff2fde2ef11ffd0ee4e930cf

---

# <a name="parsing-numeric-strings-in-net"></a>Analizar cadenas numéricas en .NET

Todos los tipos numéricos tienen dos métodos de análisis estáticos, `Parse` y `TryParse`, que puede usar para convertir la representación de cadena de un número en un tipo numérico. Estos métodos permiten analizar cadenas generadas mediante el uso de las cadenas de formato que se documentan en [Cadenas con formato numérico estándar](standard-numeric.md) y [Cadenas con formato numérico personalizado](custom-numeric.md). De forma predeterminada, los métodos `Parse` y `TryParse` pueden convertir correctamente las cadenas que contienen dígitos decimales enteros solo en valores enteros. Pueden convertir correctamente las cadenas que contienen dígitos decimales enteros y fraccionarios, separadores de grupos y un separador decimal en valores de punto flotante. El método `Parse` produce una excepción si se produce un error en la operación, mientras que el método `TryParse` devuelve `false`.

## <a name="parsing-and-format-providers"></a>Análisis y proveedores de formato

Normalmente, las representaciones de cadena de valores numéricos se diferencian en la referencia cultural. Todos los elementos de las cadenas numéricas, como los símbolos de moneda, los separadores de grupo (o millares) y los separadores decimales, varían según la referencia cultural. Los métodos de análisis usan implícita o explícitamente un proveedor de formato que reconoce estas variaciones específicas de la referencia cultural. Si no se especifica ningún proveedor de formato en una llamada al método `Parse` o `TryParse`, se usa el proveedor de formato asociado a la referencia cultural del subproceso actual (el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) devuelto por la propiedad [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo)). 

Un proveedor de formato se representa mediante una implementación [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo). Esta interfaz tiene un solo miembro, el método [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)), cuyo único parámetro es un objeto [Type](xref:System.Type) que representa el tipo al que se va a dar formato. Este método devuelve el objeto que proporciona información de formato. .NET es compatible con las dos implementaciones [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) siguientes para analizar cadenas numéricas:

* Un objeto [CultureInfo](xref:System.Globalization.CultureInfo) cuyo método [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) devuelve un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que proporciona información de formato específica de la referencia cultural.

* Un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) cuyo método [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) se devuelve a sí mismo.

En el ejemplo siguiente se intenta convertir cada cadena de una matriz en un valor [Double](xref:System.Double). Primero se intenta analizar la cadena mediante un proveedor de formato que refleja las convenciones de la referencia cultural Inglés (Estados Unidos). Si esta operación produce una excepción [FormatException](xref:System.FormatException), se intenta analizar la cadena mediante un proveedor de formato que refleja las convenciones de la referencia cultural Francés (Francia).

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a>Análisis y valores NumberStyles

Los elementos de estilo (como espacio en blanco, separadores de grupos y separador decimal) que la operación de análisis puede controlar se definen mediante un valor de enumeración [NumberStyles](xref:System.Globalization.NumberStyles). De forma predeterminada, las cadenas que representan valores enteros se analizan mediante el valor [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer), que solo permite dígitos numéricos, espacio en blanco inicial y final, y un signo inicial. Las cadenas que representan valores de punto flotante se analizan mediante una combinación de valores [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) y [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands). Este estilo compuesto permite dígitos decimales junto con un espacio en blanco inicial y final, un signo inicial, un separador decimal, separador de grupos y un exponente. Al llamar a una sobrecarga del método `Parse` o `TryParse` que incluya un parámetro de tipo [NumberStyles](xref:System.Globalization.NumberStyles) y configurar una o más marcas [NumberStyles](xref:System.Globalization.NumberStyles), puede controlar los elementos de estilo que pueden estar presentes en la cadena para que la operación de análisis se realice correctamente. 

Por ejemplo, una cadena que contiene un separador de grupos no puede convertirse en un valor [Int32](xref:System.Int32) mediante el método [Int32.Parse(String)](xref:System.Int32.Parse(System.String)). Pero la conversión se realiza correctamente si usa la marca [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands), como se muestra en el ejemplo siguiente.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> **Advertencia**
>
> La operación de análisis siempre usa las convenciones de formato de una referencia cultural determinada. Si no pasa un objeto [CultureInfo](xref:System.Globalization.CultureInfo) o [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) para especificar una referencia cultural, se usa la referencia cultural asociada al subproceso actual.
 
En la tabla siguiente se enumeran los miembros de la enumeración [NumberStyles](xref:System.Globalization.NumberStyles) y se describe el efecto que tienen en la operación de análisis.

Valor NumberStyles | Efecto en la cadena que se va a analizar
------------------ | --------------------------------- 
[NumberStyles.None](xref:System.Globalization.NumberStyles.None) | Solo se permiten los dígitos numéricos.
[NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | Se permiten el separador decimal y los dígitos fraccionarios. En el caso de los valores enteros, solo se permite cero como dígito fraccionario. Los separadores decimales válidos vienen determinados por la propiedad [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) o [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator).
[NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) | Se puede usar el carácter "e" o "E" para indicar la notación exponencial.
[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | Se permite el espacio en blanco inicial.
[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | Se permite el espacio en blanco final.
[NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) | Un signo positivo o negativo puede preceder a los dígitos numéricos.
[NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign) | Un signo positivo o negativo puede seguir a los dígitos numéricos.
[NumberStyles.AllowParentheses](xref:System.Globalization.NumberStyles.AllowParentheses) | Se pueden usar paréntesis para indicar valores negativos.
[NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) | Se permite el separador de grupos. El carácter de separador de grupos se determina mediante la propiedad [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) o [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator).
[NumberStyles.AllowCurrencySymbol](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | Se permite el símbolo de moneda. El símbolo de moneda se define mediante la propiedad [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol).
[NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | La cadena que se va a analizar se interpreta como un número hexadecimal. Puede incluir los dígitos hexadecimales 0-9, A-F y a-f. Esta marca solo se puede usar para analizar valores enteros.
 
Además, la enumeración [NumberStyles](xref:System.Globalization.NumberStyles) proporciona los siguientes estilos compuestos, que incluyen varias marcas [NumberStyles](xref:System.Globalization.NumberStyles). 

Valor NumberStyles compuestos | Miembros que incluye
---------------------------- | ---------------- 
[NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) | Incluye los estilos [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) y [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign). Este es el estilo predeterminado que se usa para analizar valores enteros.
[NumberStyles.Number](xref:System.Globalization.NumberStyles.Number) | Incluye los estilos [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) y [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).
[NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) | Incluye los estilos [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) y [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).
[NumberStyles.Currency](xref:System.Globalization.NumberStyles.Currency) | Incluye todos los estilos excepto [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) y [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.Any](xref:System.Globalization.NumberStyles.Any) | Incluye todos los estilos excepto [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.HexNumber](xref:System.Globalization.NumberStyles.HexNumber) | Incluye los estilos [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) y [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
 
## <a name="parsing-and-unicode-digits"></a>Análisis y dígitos Unicode

El estándar Unicode define puntos de código para dígitos de diferentes sistemas de escritura. Por ejemplo, los puntos de código de U+0030 a U+0039 representan los dígitos latinos básicos del 0 al 9, los puntos de código de U+09E6 a U+09EF representan los dígitos de bangla del 0 al 9, y los puntos de código de U+FF10 a U+FF19 representan los dígitos de ancho completo del 0 al 9. Pero los únicos dígitos numéricos que reconocen los métodos de análisis son los dígitos latinos básicos del 0 al 9 con puntos de código de U+0030 a U+0039. Si se pasa a un método de análisis numérico una cadena que contenga cualquier otro dígito, el método producirá una excepción [FormatException](xref:System.FormatException).

En el ejemplo siguiente se usa el método [Int32.Parse](xref:System.Int32.Parse(System.String)) para analizar las cadenas que se componen de dígitos en sistemas de escritura diferentes. Como muestra la salida del ejemplo, el intento de analizar los dígitos latinos básicos se realiza correctamente, pero se produce un error en el intento de analizar los dígitos de ancho completo, árabe-hindús y de bangla.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a>Vea también

[System.Globalization.NumberStyles](xref:System.Globalization.NumberStyles)

[Analizar cadenas en .NET](parsing-strings.md)

[Aplicar formato a tipos en .NET](formatting-types.md)




<!--HONumber=Nov16_HO3-->


