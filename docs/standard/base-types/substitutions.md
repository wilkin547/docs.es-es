---
title: Sustituciones en expresiones regulares
description: Sustituciones en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0fded615-1021-4468-a644-b491814305c6
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 4b2b547b6edd67590ad75851b8b287e55dc7d70c

---

# <a name="substitutions-in-regular-expressions"></a>Sustituciones en expresiones regulares

Las sustituciones son elementos del lenguaje que se reconocen solo dentro de patrones de reemplazo. Usan un patrón de expresión regular para definir todo o parte del texto que reemplazará el texto coincidente en la cadena de entrada. El patrón de reemplazo puede estar compuesto de una o más sustituciones junto con caracteres literales. Se proporcionan patrones de reemplazo a sobrecargas del método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) que tienen un parámetro *replacement* y al método [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)). Los métodos reemplazan el patrón que coincide con el patrón que define el parámetro *replacement*.

.NET define los elementos de sustitución que se enumeran en la siguiente tabla.

Sustitución | Descripción
------------ | ----------- 
**$**_número_ | Incluye la última subcadena coincidente con el grupo de captura que se identifica con *número* en la cadena de reemplazo, donde *número* es un valor decimal. Para obtener más información, consulte [Sustituir un grupo numerado](#substituting-a-numbered-group).
**${**_nombre_**}** | Incluye la última subcadena coincidente con el grupo con nombre, que se designa con **(?<**_nombre_**>)** en la cadena de reemplazo. Para obtener más información, consulte [Sustituir un grupo con nombre](#substituting-a-named-group).
**$$** | Incluye un literal "$" único en la cadena de reemplazo. Para obtener más información, consulte [Sustituir un carácter "$"](#substituting-a--character).
**$&** | Incluye una copia de la coincidencia completa en la cadena de reemplazo. Para obtener más información, consulte [Sustituir toda la coincidencia](#substituting-the-entire-match).
**$`** | Incluye todo el texto de la cadena de entrada delante de la coincidencia en la cadena de reemplazo. Para obtener más información, consulte [Sustituir el texto delante de la coincidencia](#substituting-the-text-before-the-match).
**$'** | Incluye todo el texto de la cadena de entrada detrás de la coincidencia en la cadena de reemplazo. Para obtener más información, consulte [Sustituir el texto detrás de la coincidencia](#substituting-the-text-after-the-match). 
**$+** | Incluye el último grupo capturado en la cadena de reemplazo. Para obtener más información, consulte [Sustituir el último grupo capturado](#substituting-the-last-captured-group).
**$_** | Incluye la cadena de entrada completa en la cadena de reemplazo. Para obtener más información, consulte [Sustituir toda la cadena de entrada](#substituting-the-entire-input-string).
 
## <a name="substitution-elements-and-replacement-patterns"></a>Elementos de sustitución y patrones de reemplazo

Las sustituciones son las únicas construcciones especiales reconocidas en un patrón de reemplazo. No se admiten otros elementos de lenguaje de expresiones regulares, como los escapes de caracteres y el punto (**.**), que coincide con cualquier carácter. De igual forma, los elementos de lenguaje de sustitución se reconocen únicamente en patrones de reemplazo y no son válidos en patrones de expresiones regulares. 

El único carácter que puede aparecer en un patrón de expresión regular o en una sustitución es el carácter **$**, aunque tiene un significado diferente en cada contexto. En un patrón de expresión regular, **$** es un delimitador que coincide con el final de la cadena. En un patrón de reemplazo, **$** indica el principio de una sustitución. 

> [!NOTE]
> Para obtener una funcionalidad similar a la de un patrón de reemplazo dentro de una expresión regular, use una referencia inversa. Para obtener más información acerca de las referencias inversas, consulte [Construcciones de referencia inversa](backreference.md).
 
## <a name="substituting-a-numbered-group"></a>Sustituir un grupo numerado

El elemento de lenguaje **$**_número_ incluye la última subcadena coincidente con el grupo de captura de ese número en la cadena de reemplazo, donde *número* es el índice del grupo de captura. Por ejemplo, el patrón de reemplazo `$1` indica que el primer grupo capturado reemplazará la subcadena coincidente. Para obtener más información acerca de los grupos de captura numerados, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

Todos los dígitos después del símbolo **$** se interpretan como pertenecientes al número del grupo. Si esto no es lo que pretende, puede sustituir un grupo con nombre en su lugar. Por ejemplo, puede usar la cadena de reemplazo **${1}1** en lugar de **$11** para definir la cadena de reemplazo como el valor del primer grupo capturado seguido del número "1". Para obtener más información, consulte [Sustituir un grupo con nombre](#substituting-a-named-group). 

Los grupos de captura que no tienen nombres asignados explícitamente mediante la sintaxis **(?<**_nombre_**>)** se numeran de izquierda a derecha a partir de uno. Los grupos con nombre también se numeran de izquierda a derecha, comenzando por uno mayor que el índice del último grupo sin nombre. Por ejemplo, en la expresión regular `(\w)(?<digit>\d)`, el índice del grupo con nombre `digit` es 2.

Si *número* no especifica ningún grupo de captura válido del patrón de expresión regular, **$**_número_ se interpreta como una secuencia de caracteres literales que se usa para reemplazar cada coincidencia.

En el ejemplo siguiente se usa la sustitución **$**_número_ para quitar el símbolo de divisa de un valor decimal. Quita los símbolos de divisa encontrados al principio o al final de un valor monetario y reconoce los dos separadores decimales más comunes ("." y ","). 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "$1";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "$1"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

El patrón de expresión regular `\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\p{Sc}*` | Busca una coincidencia con cero o más caracteres de símbolo de divisa.
`\s?` | Busca una coincidencia con cero o un carácter de espacio en blanco.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
`[.,]?` | Busca una coincidencia con cero o un punto o una coma.
`\d*` | Busca cero o más dígitos decimales.
`(\s?\d+[.,]?\d*)` | Busca un espacio en blanco seguido de uno o más dígitos decimales, seguido de cero o un punto o una coma, seguido de cero o más dígitos decimales. Este es el primer grupo de captura. Dado que el patrón de reemplazo es `$1`, la llamada al método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) reemplaza la subcadena coincidente completa por este grupo capturado. 
 
## <a name="substituting-a-named-group"></a>Sustituir un grupo con nombre

El elemento de lenguaje **${**_nombre_**}** sustituye la última subcadena coincidente con el grupo de captura *nombre*, donde *nombre* es el nombre del grupo de captura definido por el elemento de lenguaje **(?<**_nombre_**>)**. Para obtener más información acerca de los grupos de captura con nombre, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

Si *nombre* no especifica ningún grupo de captura con nombre válido en el patrón de expresión regular, pero consta de dígitos, **${**_nombre_**}** se interpreta como un grupo numerado. 

Si *nombre* no especifica ningún grupo de captura con nombre o grupo de captura numerado válido del patrón de expresión regular, **${**_nombre_**}** se interpreta como una secuencia de caracteres literales que se usa para reemplazar cada coincidencia.

En el ejemplo siguiente, se usa la sustitución **${**_nombre_**}** para quitar el símbolo de divisa de un valor decimal. Quita los símbolos de divisa encontrados al principio o al final de un valor monetario y reconoce los dos separadores decimales más comunes ("." y ",").

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "${amount}";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "${amount}"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

El patrón de expresión regular `\p{Sc}*(?<amount>\s?\d[.,]?\d*)\p{Sc}*` se define como se muestra en la tabla siguiente. 

Modelo | Descripción
------- | -----------
`\p{Sc}*` | Busca una coincidencia con cero o más caracteres de símbolo de divisa.
`\s?` | Busca una coincidencia con cero o un carácter de espacio en blanco.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
`[.,]?` | Busca una coincidencia con cero o un punto o una coma.
`\d*` | Busca cero o más dígitos decimales.
`(?<amount>\s?\d[.,]?\d*)` | Busca un espacio en blanco, seguido de uno o más dígitos decimales, seguido de cero o un punto o una coma, seguido de cero o más dígitos decimales. Este es el grupo de captura denominado amount. Dado que el patrón de reemplazo es `${amount}`, la llamada al método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) reemplaza la subcadena coincidente completa por este grupo capturado. 
 
## <a name="substituting-a-character"></a>Sustituir un carácter $

La sustitución **$$** inserta un carácter "$" literal en la cadena reemplazada. 

En el ejemplo siguiente, se usa el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) para determinar el símbolo de divisa de la referencia cultural actual y su posición en una cadena de divisa. A continuación, compila dinámicamente un patrón de expresión regular y un patrón de reemplazo. Si el ejemplo se ejecuta en un equipo cuya referencia cultural actual es en-US, genera el patrón de expresión regular `\b(\d+)(\.(\d+))?` y el patrón de reemplazo `$$ $1$2`. El patrón de reemplazo sustituye el texto coincidente por un símbolo de divisa y un espacio seguido del primer y del segundo grupo capturado.

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define array of decimal values.
      string[] values= { "16.35", "19.72", "1234", "0.99"};
      // Determine whether currency precedes (True) or follows (False) number.
      bool precedes = NumberFormatInfo.CurrentInfo.CurrencyPositivePattern % 2 == 0;
      // Get decimal separator.
      string cSeparator = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator;
      // Get currency symbol.
      string symbol = NumberFormatInfo.CurrentInfo.CurrencySymbol;
      // If symbol is a "$", add an extra "$".
      if (symbol == "$") symbol = "$$";

      // Define regular expression pattern and replacement string.
      string pattern = @"\b(\d+)(" + cSeparator + @"(\d+))?"; 
      string replacement = "$1$2";
      replacement = precedes ? symbol + " " + replacement : replacement + " " + symbol;
      foreach (string value in values)
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement));
   }
}
// The example displays the following output:
//       16.35 --> $ 16.35
//       19.72 --> $ 19.72
//       1234 --> $ 1234
//       0.99 --> $ 0.99
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Define array of decimal values.
      Dim values() As String = { "16.35", "19.72", "1234", "0.99"}
      ' Determine whether currency precedes (True) or follows (False) number.
      Dim precedes As Boolean = (NumberFormatInfo.CurrentInfo.CurrencyPositivePattern Mod 2 = 0)
      ' Get decimal separator.
      Dim cSeparator As String = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator
      ' Get currency symbol.
      Dim symbol As String = NumberFormatInfo.CurrentInfo.CurrencySymbol
      ' If symbol is a "$", add an extra "$".
      If symbol = "$" Then symbol = "$$"

      ' Define regular expression pattern and replacement string.
      Dim pattern As String = "\b(\d+)(" + cSeparator + "(\d+))?" 
      Dim replacement As String = "$1$2"
      replacement = If(precedes, symbol + " " + replacement, replacement + " " + symbol)
      For Each value In values
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement))
      Next
   End Sub
End Module
' The example displays the following output:
'       16.35 --> $ 16.35
'       19.72 --> $ 19.72
'       1234 --> $ 1234
'       0.99 --> $ 0.99
```

El patrón de expresión regular `\b(\d+)(\.(\d+))?` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Comenzar la búsqueda de coincidencias al principio de un límite de palabras.
`(\d+)` | Buscar coincidencias con uno o más dígitos decimales. Este es el primer grupo de captura.
`\.` | Buscar coincidencias con un punto (el separador decimal).
`(\d+)` | Buscar coincidencias con uno o más dígitos decimales. Éste es el tercer grupo de captura.
`(\.(\d+))?` | Buscar una coincidencia con cero o una aparición de un punto seguido de uno o más dígitos decimales. Este es el segundo grupo de captura.
 
## <a name="substituting-the-entire-match"></a>Sustituir toda la coincidencia

La sustitución **$&** incluye toda la coincidencia en la cadena de reemplazo. A menudo, se usa para agregar una subcadena al principio o final de la cadena coincidente. Por ejemplo, el patrón de reemplazo `($&)` agrega un paréntesis al principio y al final de cada coincidencia. Si no hay ninguna coincidencia, la sustitución **$&** no tiene ningún efecto.

En el ejemplo siguiente, se usa la sustitución **$&** para agregar comillas al principio y al final de los títulos de los libros almacenados en una matriz de cadena.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^(\w+\s?)+$";
      string[] titles = { "A Tale of Two Cities", 
                          "The Hound of the Baskervilles", 
                          "The Protestant Ethic and the Spirit of Capitalism", 
                          "The Origin of Species" };
      string replacement = "\"$&\"";
      foreach (string title in titles)
         Console.WriteLine(Regex.Replace(title, pattern, replacement));
   }
}
// The example displays the following output:
//       "A Tale of Two Cities"
//       "The Hound of the Baskervilles"
//       "The Protestant Ethic and the Spirit of Capitalism"
//       "The Origin of Species"
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(\w+\s?)+$"
      Dim titles() As String = { "A Tale of Two Cities", _
                                 "The Hound of the Baskervilles", _
                                 "The Protestant Ethic and the Spirit of Capitalism", _
                                 "The Origin of Species" }
      Dim replacement As String = """$&"""
      For Each title As String In titles
         Console.WriteLine(Regex.Replace(title, pattern, replacement))
      Next  
   End Sub
End Module
' The example displays the following output:
'       "A Tale of Two Cities"
'       "The Hound of the Baskervilles"
'       "The Protestant Ethic and the Spirit of Capitalism"
'       "The Origin of Species"
```

El patrón de expresión regular `^(\w+\s?)+$` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`^` | Comenzar la búsqueda de coincidencias al principio de la cadena de entrada.
`(\w+\s?)+` | Buscar coincidencias con el patrón de uno o varios caracteres de palabra seguidos de cero o un carácter de espacio en blanco una o varias veces. 
`$` | Coincide con el final de la cadena de entrada.

El patrón de reemplazo `"$&"` agrega una comilla literal al principio y al final de cada coincidencia.

## <a name="substituting-the-text-before-the-match"></a>Sustituir el texto delante de la coincidencia

La sustitución **$`** substitution replaces the matched string with the entire input string before the match. That is, it duplicates the input string up to the match while removing the matched text. Any text that follows the matched text is unchanged in the result string. If there are multiple matches in an input string, the replacement text is derived from the original input string, rather than from the string in which text has been replaced by earlier matches. (The example provides an illustration.) If there is no match, the **$`** no tiene ningún efecto.

En el ejemplo siguiente, se usa el patrón de expresión regular `\d+` para que coincida con una secuencia de uno o más dígitos decimales en la cadena de entrada. La cadena de reemplazo **$`** reemplaza estos dígitos por el texto que antecede a la coincidencia. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$`";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);

      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$`"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

En este ejemplo, la cadena de entrada `"aa1bb2cc3dd4ee5"` contiene cinco coincidencias. En la siguiente tabla se muestra cómo la sustitución $` hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna Cadena de resultado.

Coincidir con | Posición | Cadena antes de la coincidencia | Cadena de resultado
----- | -------- | ------------------- | -------------
1 | 2 | aa | aa**aa**bb2cc3dd4ee5
2 | 5 | aa1bb | aaaabb**aa1bb**cc3dd4ee5
3 | 8 | aa1bb2cc | aaaabbaa1bbcc**aa1bb2cc**dd4ee5
4 | 11 | aa1bb2cc3dd | aaaabbaa1bbccaa1bb2ccdd**aa1bb2cc3dd**ee5
5 | 14 | aa1bb2cc3dd4ee | aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddee **aa1bb2cc3dd4ee**
 
## <a name="substituting-the-text-after-the-match"></a>Sustituir el texto detrás de la coincidencia

La sustitución **$'** reemplaza la cadena coincidente por la cadena de entrada completa después de la coincidencia. Es decir, duplica la cadena de entrada después de la coincidencia quitando el texto coincidente. Cualquier texto que anteceda al texto coincidente no cambia en la cadena de resultado. Si no hay ninguna coincidencia, la sustitución **$'** no tiene ningún efecto.

En el ejemplo siguiente, se usa el patrón de expresión regular `\d+` para que coincida con una secuencia de uno o más dígitos decimales en la cadena de entrada. La cadena de reemplazo **$'** reemplaza estos dígitos por el texto que sigue a la coincidencia. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$'";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$'"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

En este ejemplo, la cadena de entrada `"aa1bb2cc3dd4ee5"` contiene cinco coincidencias. En la siguiente tabla se muestra cómo la sustitución **$'** hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna Cadena de resultado.

Coincidir con | Posición | Cadena antes de la coincidencia | Cadena de resultado
----- | -------- | ------------------- | -------------
1 | 2 | bb2cc3dd4ee5 | aa**bb2cc3dd4ee5**bb2cc3dd4ee5
2 | 5 | cc3dd4ee5 | aabb2cc3dd4ee5bb**cc3dd4ee5**cc3dd4ee5
3 | 8 | dd4ee5 | aabb2cc3dd4ee5bbcc3dd4ee5cc**dd4ee5**dd4ee5
4 | 11 | ee5 | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5dd**ee5**ee5
5 | 14 | [String.Empty](xref:System.String.Empty) | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5ddee5ee
 
## <a name="substituting-the-last-captured-group"></a>Sustituir el último grupo capturado

La sustitución **$+** reemplaza la cadena coincidente por el último grupo capturado. Si no hay ningún grupo capturado, o si el valor del último grupo capturado es [String.Empty](xref:System.String.Empty), la sustitución **$+** no tiene ningún efecto.

En el ejemplo siguiente se identifican las palabras duplicadas en una cadena y se usa la sustitución **$+** para reemplazarlas por una aparición única de la palabra. La opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) se usa para garantizar que palabras que difieren en el uso de mayúsculas y minúsculas, pero que de lo contrario son idénticas, se consideren duplicadas.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s\1\b";
      string substitution = "$+";
      string input = "The the dog jumped over the fence fence.";
      Console.WriteLine(Regex.Replace(input, pattern, substitution, 
                        RegexOptions.IgnoreCase));
   }
}
// The example displays the following output:
//      The dog jumped over the fence.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s\1\b"
      Dim substitution As String = "$+"
      Dim input As String = "The the dog jumped over the fence fence."
      Console.WriteLine(Regex.Replace(input, pattern, substitution, _
                                      RegexOptions.IgnoreCase))
   End Sub
End Module
' The example displays the following output:
'      The dog jumped over the fence.
```

El patrón de expresión regular `\b(\w+)\s\1\b` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`(\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.
`\s` | Coincide con un carácter de espacio en blanco.
`\1` | Buscar una coincidencia con el primer grupo capturado.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
## <a name="substituting-the-entire-input-string"></a>Sustituir toda la cadena de entrada

La sustitución **$_** reemplaza la cadena coincidente por la cadena de entrada completa. Es decir, quita el texto coincidente y lo reemplaza por la cadena completa, incluyendo el texto coincidente.

En el ejemplo siguiente se buscan coincidencias para uno o más dígitos decimales en la cadena de entrada. Se usa la sustitución **$_** para reemplazarlos por la cadena de entrada completa.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "ABC123DEF456";
      string pattern = @"\d+";
      string substitution = "$_";
      Console.WriteLine("Original string:          {0}", input);
      Console.WriteLine("String with substitution: {0}", 
                        Regex.Replace(input, pattern, substitution));      
   }
}
// The example displays the following output:
//       Original string:          ABC123DEF456
//       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "ABC123DEF456"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$_"
      Console.WriteLine("Original string:          {0}", input)
      Console.WriteLine("String with substitution: {0}", _
                        Regex.Replace(input, pattern, substitution))      
   End Sub
End Module
' The example displays the following output:
'       Original string:          ABC123DEF456
'       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

En este ejemplo, la cadena de entrada `"ABC123DEF456"` contiene dos coincidencias. En la siguiente tabla se muestra cómo la sustitución **$_** hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna Cadena de resultado.

Coincidir con | Posición | Cadena antes de la coincidencia | Cadena de resultado
----- | -------- | ------------------- | -------------
1 | 3 | 123 | ABC**ABC123DEF456**DEF456
2 | 5 | 456 | ABCABC123DEF456DEF**ABC123DEF456**
 
## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)




<!--HONumber=Nov16_HO3-->


