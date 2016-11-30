---
title: Opciones de expresiones regulares
description: Opciones de expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2db2c3e6-953e-4913-8168-d707c437f2df
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: a2a9fe356a0b2e9cf9415714bc01b77ea86229fc

---

# <a name="regular-expression-options"></a>Opciones de expresiones regulares

De forma predeterminada, al comparar una cadena de entrada con los caracteres literales de un patrón de expresión regular, se distinguen mayúsculas de minúsculas, los espacios en blanco del patrón de expresión regular se interpretan como caracteres de espacio en blanco literales, y los grupos de captura de la expresión regular se denominan tanto implícita como explícitamente. Estos y otros aspectos del comportamiento predeterminado de la expresión regular se pueden modificar mediante la especificación de las opciones de la expresión regular. Estas opciones, que aparecen enumeradas en la tabla siguiente, se pueden insertar como parte del patrón de expresión regular, o se pueden suministrar a un constructor de clase [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) o a un método estático de coincidencia de patrones como valor de enumeración [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). 

Miembro RegexOptions | Carácter insertado | Efecto
------------------- | ---------------- | ------ 
[Ninguno](xref:System.Text.RegularExpressions.RegexOptions.None) | No disponible | Usar el comportamiento predeterminado. Para obtener más información, consulte [Opciones predeterminadas](#default-options).
[IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) | **i** | Usa la coincidencia sin distinción entre mayúsculas y minúsculas. Para obtener más información, consulte la sección [Coincidencia sin distinción entre mayúsculas y minúsculas](#case-insensitive-matching).
[Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) | **m** | Usa el modo multilínea, donde **^** y **$** coinciden con el principio y el final de cada línea (en lugar del principio y el final de la cadena de entrada). Para obtener más información, consulte la sección [Modo multilínea](#multiline-mode).
[Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) | **s** | Usa el modo de una sola línea, donde el punto (**.**) coincide con todos los caracteres (en lugar de todos los caracteres excepto **\n**). Para obtener más información, consulte la sección [Modo de una sola línea](#single-line-mode).
[ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) | **n** | No se capturan grupos sin nombre. Las únicas capturas válidas son grupos con nombre explícito o numerados con el formato **(?<**_nombre_**>** _subexpresión_**)**. Para obtener más información, consulte la sección [Solo capturas explícitas](#explicit-captures-only).
[Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) | No disponible | Compilar la expresión regular en un ensamblado. Para obtener más información, consulte [Expresiones regulares compiladas](#compiled-regular-expressions).
[IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) | **x** | Excluye del patrón el espacio en blanco sin escape y habilita los comentarios tras un signo de número (**#**). Para obtener más información, consulte la sección [Ignorar el espacio en blanco](#ignore-white-space).
[RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) | No disponible | Cambiar la dirección de búsqueda. La búsqueda se mueve de derecha a izquierda en vez de de izquierda a derecha. Para obtener más información, consulte la sección [Modo de derecha a izquierda](#right-to-left-mode).
[ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) | No disponible | Habilitar un comportamiento conforme a ECMAScript para la expresión. Para obtener más información, consulte la sección [Comportamiento de búsqueda de coincidencias de ECMAScript](#ecmascript-matching-behavior).
[CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) | No disponible | Ignorar las diferencias culturales de idioma. Para obtener más información, consulte la sección [Comparación con la referencia cultural de todos los idiomas](#comparison-using-the-invariant-culture).
 
## <a name="specifying-the-options"></a>Especificación de opciones

Las opciones de las expresiones regulares se pueden especificar de tres modos:

* En el parámetro *options* de un constructor de clase [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) como [Regex.Regex(String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions)) o un método estático (en Visual Basic, compartido) de coincidencia de patrones, como [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). El parámetro *options* es una combinación OR bit a bit de valores enumerados [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). 

  Cuando se proporcionan opciones a una instancia [Regex](xref:System.Text.RegularExpressions.Regex) mediante el parámetro *options* de un constructor de clase, las opciones se asignan a la propiedad [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). Pero la propiedad [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) no refleja las opciones insertadas en el mismo patrón de expresión regular. 

  Esto se muestra en el ejemplo siguiente. Usa el parámetro *options* del método [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra "d".

  ```csharp
  string pattern = @"d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  RegexOptions options = RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace;
  
  foreach (Match match in Regex.Matches(input, pattern, options))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."
  Dim options As RegexOptions = RegexOptions.IgnoreCase Or RegexOptions.IgnorePatternWhitespace

  For Each match As Match In Regex.Matches(input, pattern, options)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Con la aplicación de las opciones insertadas en un patrón de expresión regular con la sintaxis **(?imnsx-imnsx)**. La opción se aplica al patrón a partir del punto en que la opción se define hasta el final del patrón o hasta el punto en que otra opción insertada deja a la opción sin definir. Tenga en cuenta que la propiedad [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) de una instancia [Regex](xref:System.Text.RegularExpressions.Regex) no refleja estas opciones insertadas. Para obtener más información, consulte el tema [Construcciones misceláneas en expresiones regulares](miscellaneous.md).

  Esto se muestra en el ejemplo siguiente. Usa opciones insertadas para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra “d”.

  ```csharp
  string pattern = @"(?ix) d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix) d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Con la aplicación de opciones insertadas en una construcción de agrupamiento de un patrón de expresión regular con la sintaxis **(?imnsx-imnsx:**_subexpresión_**)**. El conjunto de opciones se activa si no va precedido por un signo y se desactiva si va precedido por un signo menos. (**?** es una parte fija de la sintaxis del constructor de lenguaje que se necesita si las opciones están habilitadas o deshabilitadas). La opción solo se aplica a ese grupo. Para obtener más información, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

  Esto se muestra en el ejemplo siguiente. Usa opciones insertadas en una construcción de agrupamiento para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra “d”.

  ```csharp
  string pattern = @"\b(?ix: d \w+)\s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix: d \w+)\s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9. 
  ```


Si las opciones están insertadas, un signo menos (-) antes de una opción o conjunto de opciones desactiva dichas opciones. Por ejemplo, la construcción insertada **(?ix-ms)** activa las opciones [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) y [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) y desactiva las opciones [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) y [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Todas las opciones de expresión regular están desactivadas de forma predeterminada.

> [!NOTE]
> Si las opciones de expresión regular especificadas en el parámetro options de un constructor o llamada de método están en conflicto con las opciones insertadas en un patrón de expresión regular, se usan las opciones insertadas.
 

Las cinco opciones siguientes de expresión regular se pueden establecer con el parámetro *options* y mediante inserción:

* [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)

* [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)

* [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline)

* [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)

* [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace)

Las cinco opciones siguientes de expresión regular se pueden establecer con el parámetro *options*, pero no mediante inserción:

* [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None)

* [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)

* [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)

* [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant)

* [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript)

## <a name="determining-the-options"></a>Determinación de opciones

Se pueden determinar las opciones que se proporcionaron a un objeto [Regex](xref:System.Text.RegularExpressions.Regex) al crearse su instancia. Para ello, recupere el valor de la propiedad [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options) de solo lectura.

Para probar la presencia de cualquier opción, excepto [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), realice una operación AND con el valor de la propiedad [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options) y el valor de [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) en el que esté interesado. Después, pruebe si el resultado es igual a ese valor [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). En el ejemplo siguiente se prueba si se ha establecido la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). 

```csharp
if ((rgx.Options & RegexOptions.IgnoreCase) == RegexOptions.IgnoreCase)
   Console.WriteLine("Case-insensitive pattern comparison.");
else
   Console.WriteLine("Case-sensitive pattern comparison.");
```

```vb
If (rgx.Options And RegexOptions.IgnoreCase) = RegexOptions.IgnoreCase Then
   Console.WriteLine("Case-insensitive pattern comparison.")
Else
   Console.WriteLine("Case-sensitive pattern comparison.")
End If 
```

Para probar [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), determine si el valor de la propiedad [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) es igual a [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), tal como se muestra en el ejemplo siguiente. 

```csharp
if (rgx.Options == RegexOptions.None)
   Console.WriteLine("No options have been set.");
```

```vb
If rgx.Options = RegexOptions.None Then
   Console.WriteLine("No options have been set.")
End If
```

En las secciones siguientes se enumeran las opciones admitidas en una expresión regular de .NET. 

## <a name="default-options"></a>Opciones predeterminadas

La opción [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) indica que no se ha especificado ninguna opción y que el motor de expresiones regulares sigue su comportamiento predeterminado. Entre estas estructuras se incluyen las siguientes:

* El patrón se interpreta como un canónico en vez de como una expresión regular ECMAScript.

* El patrón de expresión regular se compara con la cadena de entrada de izquierda a derecha.

* Las comparaciones distinguen entre mayúsculas y minúsculas.

* Los elementos de lenguaje **^** y **$** coinciden con el principio y el final de la cadena de entrada.

* El elemento de lenguaje **.** coincide con todos los caracteres excepto **\n**.

* Un espacio en blanco en un patrón de expresión regular se interpreta como un carácter de espacio literal.

* Las convenciones de la referencia cultural actual se usan al comparar el patrón con la cadena de entrada. 

* Los grupos de captura del patrón de expresión regular son implícitos y explícitos. 

> [!NOTE]
> La opción [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) no tiene ningún equivalente de inserción. Cuando las opciones de expresión regular se aplican mediante inserción, el comportamiento predeterminado se restaura opción por opción, mediante la desactivación de una opción concreta.  Por ejemplo, `(?i)` activa la comparación sin distinción entre mayúsculas y minúsculas, y `(?-i)` restaura la comparación con distinción entre mayúsculas y minúsculas.
 
Debido a que la opción [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) representa el comportamiento predeterminado del motor de expresiones regulares, casi nunca se especifica de forma explícita en una llamada de método. En su lugar, se llama a un constructor o método estático de coincidencia de patrones sin un parámetro options.

## <a name="case-insensitive-matching"></a>Coincidencia sin distinción entre mayúsculas y minúsculas

La opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), o la opción insertada **i**, proporciona coincidencia sin distinción entre mayúsculas y minúsculas. De forma predeterminada, se usan las convenciones sobre el uso de mayúsculas de la referencia cultural actual.

En el ejemplo siguiente se define un patrón de expresión regular, `\bthe\w*\b`, por el que coinciden todas las palabras que empiezan por “the”. Debido a que la primera llamada al método Match usa la comparación predeterminada con distinción entre mayúsculas y minúsculas, el resultado indica que no hay coincidencia con la cadena "The" del inicio de la oración. Hay coincidencia cuando se llama al método [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) con las opciones establecidas en [IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bthe\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bthe\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern, _
                                               RegexOptions.IgnoreCase)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

En el ejemplo siguiente se modifica el patrón de expresión regular del ejemplo anterior a fin de usar las opciones insertadas en vez del parámetro *options* para realizar la comparación sin distinción entre mayúsculas y minúsculas. El primer parámetro define la opción sin distinción entre mayúsculas y minúsculas en una construcción de agrupamiento que se aplica solo a la letra “t” de la cadena “the”. Como la construcción de opciones ocurre al principio del patrón, el segundo patrón aplica la opción sin distinción entre mayúsculas y minúsculas a toda la expresión regular.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?i:t)he\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      pattern = @"(?i)\bthe\w*\b";
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?i:t)he\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      pattern = "(?i)\bthe\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

## <a name="multiline-mode"></a>Modo multilínea

La opción [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline), o la opción insertada **m**, permite que el motor de expresiones regulares controle una cadena de entrada que consta de varias líneas. Cambia la interpretación de los elementos de lenguaje **^** y **$** de modo que coincidan con el inicio y el final de una línea, en vez de con el inicio y el final de la cadena de entrada. 

De forma predeterminada, **$** coincide solo con el final de la cadena de entrada. Si se especifica la opción [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline), coincide con el carácter de nueva línea **(\n)** o con el final de la cadena de entrada. Sin embargo, no coincide con la combinación de caracteres de retorno de carro y salto de línea. Para que coincida correctamente, use la subexpresión **\r?$** en vez de simplemente **$**. 

En el ejemplo siguiente se extraen los nombres y las puntuaciones de los jugadores de bolos y se agregan a una colección [SortedList&lt;TKey, TValue&gt;](xref:System.Collections.Generic.SortedList%602) que los ordena en sentido descendente. Se realizan dos llamadas al método [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)). En la primera llamada a método, la expresión regular es `^(\w+)\s(\d+)$` y no se establece ninguna opción. Como muestra el resultado, no se encuentran coincidencias, ya que el motor de expresiones regulares no puede hacer coincidir el patrón de entrada junto con el principio y el final de la cadena de entrada. En la segunda llamada a método, la expresión regular se cambia a `^(\w+)\s(\d+)\r?$` y las opciones se establecen en [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). Como muestra el resultado, los nombres y las puntuaciones coinciden correctamente, y las puntuaciones aparecen en orden descendente.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" + 
                     "Sam 208\n" + 
                     "Allison 211\n" + 
                     "Gwen 171\n"; 
      string pattern = @"^(\w+)\s(\d+)$";
      bool matched = false;

      Console.WriteLine("Without Multiline option:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);
         matched = true;
      }
      if (! matched)
         Console.WriteLine("   No matches.");
      Console.WriteLine();

      // Redefine pattern to handle multiple lines.
      pattern = @"^(\w+)\s(\d+)\r*$";
      Console.WriteLine("With multiline option:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y)
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//   Without Multiline option:
//      No matches.
//   
//   With multiline option:
//   Allison: 211
//   Sam: 208
//   Gwen: 171
//   Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "^(\w+)\s(\d+)$"
      Dim matched As Boolean = False

      Console.WriteLine("Without Multiline option:")
      For Each match As Match In Regex.Matches(input, pattern)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
         matched = True
      Next
      If Not matched Then Console.WriteLine("   No matches.")
      Console.WriteLine()

      ' Redefine pattern to handle multiple lines.
      pattern = "^(\w+)\s(\d+)\r*$"
      Console.WriteLine("With multiline option:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Without Multiline option:
'       No matches.
'    
'    With multiline option:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

El patrón de expresión regular `^(\w+)\s(\d+)\r*$` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Comienza al principio de la línea.
`(\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.
`\s` | Coincide con un carácter de espacio en blanco.
`(\d+)` | Buscar coincidencias con uno o más dígitos decimales. Este es el segundo grupo de captura.
`\r?` | Coincidencia con cero o con un carácter de retorno de carro.
`$` | Finaliza al final de la línea.
 
El ejemplo siguiente es equivalente al anterior, a excepción de que usa la opción insertada **(?m)** para establecer la opción multilínea.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" +  
                     "Sam 208\n" +  
                     "Allison 211\n" +  
                     "Gwen 171\n"; 
      string pattern = @"(?m)^(\w+)\s(\d+)\r*$";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Convert.ToInt32(match.Groups[2].Value), match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y) 
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//    Allison: 211
//    Sam: 208
//    Gwen: 171
//    Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "(?m)^(\w+)\s(\d+)\r*$"

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

## <a name="single-line-mode"></a>Modo de una sola línea

La opción [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline), o la opción insertada s, hace que el motor de expresiones regulares trate la cadena de entrada como si constase de una única línea. Para ello, se cambia el comportamiento del elemento de lenguaje punto (**.**) para que coincida con todos los caracteres, en vez de coincidir con todos los caracteres excepto con el de nueva línea **\n** o \u000A.

En el ejemplo siguiente se muestra cómo cambia el comportamiento del elemento de lenguaje . cuando se usa la opción [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). La expresión regular `^.+` comienza en el principio de la cadena y coincide con todos los caracteres. De forma predeterminada, la coincidencia termina al final de la primera línea. El patrón de la expresión regular coincide con el carácter de retorno de carro, **\r** o \u000D, pero no coincide con **\n**. Dado que la opción [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) interpreta la cadena de entrada completa como una sola línea, coincide con cada carácter de la cadena de entrada, incluido **\n**.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Singleline))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r
//       
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^.+"
      Dim input As String = "This is one line and" + vbCrLf + "this is the second."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.SingleLine)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
   End Sub
End Module
' The example displays the following output:
'       This\ is\ one\ line\ and\r
'       
'       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

El ejemplo siguiente es equivalente al anterior, a excepción de que usa la opción insertada **(?s)** para habilitar el modo de una sola línea. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {      
      string pattern = "(?s)^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?s)^.+"
      Dim input As String = "This is one line and" + vbCrLf + "this is the second."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
   End Sub
End Module
' The example displays the following output:
'       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

## <a name="explicit-captures-only"></a>Solo capturas explícitas

De forma predeterminada, los grupos de captura se definen con el uso de paréntesis en el patrón de expresión regular. A los grupos con nombre se les asigna un nombre o un número con la opción de lenguaje **(?<**_nombre_**>** _subexpresión_**)**, mientras que a los grupos sin nombre se accede mediante el índice. En el objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), los grupos sin nombre preceden a los grupos con nombre. 

A menudo, los constructores de agrupamiento se usan únicamente para aplicar cuantificadores a varios elementos de lenguaje, y las subcadenas capturadas carecen de interés. Por ejemplo, en la expresión regular siguiente:

```
\b\(?((\w+),?\s?)+[\.!?]\)?
```

Su única finalidad es extraer de un documento las oraciones que finalizan con un punto, signo de exclamación o signo de interrogación, y solo la oración resultante (representada mediante el objeto [Match](xref:System.Text.RegularExpressions.Match)) es de interés. En cambio, las palabras individuales de la colección no son de interés. 

Los grupos de captura que no se usan posteriormente pueden ser costosos, ya que el motor de expresiones regulares debe rellenar los objetos de colección [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) y [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection). Como alternativa, se puede usar la opción [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) o la opción insertada **n** para especificar que las únicas capturas válidas son grupos con nombre o número explícitos que se designan mediante el constructor **(?<**_nombre_**>** _subexpresión_**)**. 

En el ejemplo siguiente se muestra información sobre las coincidencias devueltas por el patrón de expresión regular `\b\(?((\w+),?\s?)+[\.!?]\)?` cuando se llama al método [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32)) con y sin la opción [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture). Tal como muestra el resultado de la primera llamada de método, el motor de expresiones regulares rellena totalmente los objetos de colección [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) y [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) con información sobre las subcadenas capturadas. Dado que el segundo método se llama con options establecido en [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture), no se captura información en grupos.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";
      Console.WriteLine("With implicit captures:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
      Console.WriteLine();
      Console.WriteLine("With explicit captures only:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.ExplicitCapture))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//    With implicit captures:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//       Group 1: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//       Group 2: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//       Group 1: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//       Group 2: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//       Group 1: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//       Group 2: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
//       Group 1: paragraph
//          Capture 0: Instead,
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//       Group 2: paragraph
//          Capture 0: Instead
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//    
//    With explicit captures only:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?((?>\w+),?\s?)+[\.!?]\)?"
      Console.WriteLine("With implicit captures:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
      Console.WriteLine()
      Console.WriteLine("With explicit captures only:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.ExplicitCapture)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'    With implicit captures:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'       Group 1: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'       Group 2: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'       Group 1: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'       Group 2: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'       Group 1: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'       Group 2: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
'       Group 1: paragraph
'          Capture 0: Instead,
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'       Group 2: paragraph
'          Capture 0: Instead
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'    
'    With explicit captures only:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
```

El patrón de expresión regular `\b\(?((?>\w+),?\s?)+[\.!?]\)?` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`\(?` | Busca una coincidencia con cero o con una aparición de los paréntesis de apertura ("(").
`(?>\w+),?` | Busca una coincidencia con uno o más caracteres alfabéticos seguidos de cero o una coma. No hay retroceso al coincidir con caracteres alfabéticos.
`\s?` | Busca una coincidencia con cero o un carácter de espacio en blanco.
`((\w+),?\s?)+` | Busca una coincidencia con la combinación de uno o varios caracteres de palabra, cero o una coma, y cero o un carácter de espacio en blanco una o varias veces.
`[\.!?]\)?` | Busca una coincidencia con cualquiera de los tres símbolos de puntuación, seguidos de cero o un paréntesis de cierre (")").
 
También se puede usar el elemento insertado **(?n)** para suprimir las capturas automáticas. En el ejemplo siguiente se modifica el patrón de expresión regular anterior para usar el elemento insertado **(?n)** en vez de la opción [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

Finalmente, se puede usar el elemento de grupo insertado **(?n:)** para suprimir las capturas automáticas grupo a grupo. En el ejemplo siguiente se modifica el patrón anterior para suprimir las capturas sin nombre en el grupo externo, `((?>\w+),?\s?)`. Observe que, de este modo, también se suprimen las capturas sin nombre en el grupo interno.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas

Las expresiones de .NET se interpretan de forma predeterminada. Cuando se crea una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) o se llama a un método [Regex](xref:System.Text.RegularExpressions.Regex) estático, el patrón de expresión regular se analiza en un conjunto de códigos de operación personalizados y un intérprete usa dichos códigos para ejecutar la expresión regular. Esto implica una contrapartida: el coste de inicializar el motor de expresiones regulares se minimiza a costa del rendimiento en tiempo de ejecución.

Si quiere usar expresiones regulares compiladas en vez de interpretadas, use la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled). En este caso, cuando un patrón se pasa al motor de expresiones regulares, se analiza en un conjunto de códigos de operación y luego se convierte en Lenguaje intermedio de Microsoft (MSIL, por sus siglas en inglés), que puede pasarse directamente a Common Language Runtime. Las expresiones regulares compiladas maximizan el rendimiento en tiempo de ejecución a costa del tiempo de inicialización.

> [!NOTE]
> Una expresión regular solo se puede compilar si se suministra el valor [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) al parámetro options de un constructor de clases [Regex](xref:System.Text.RegularExpressions.Regex) o de un método estático de coincidencia de patrones. No está disponible como opción insertada. 
 

Las expresiones regulares compiladas se pueden usar en llamadas a expresiones regulares estáticas y de instancias. En expresiones regulares estáticas, la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) se pasa al parámetro options del método de coincidencia de patrones de expresión regular. En expresiones regulares de instancia, se pasa al parámetro options del constructor de clases [Regex](xref:System.Text.RegularExpressions.Regex). En ambos casos, tiene como resultado una mejora en el rendimiento. 

No obstante, esta mejora en el rendimiento solo se produce bajo las condiciones siguientes:

* Un objeto [Regex](xref:System.Text.RegularExpressions.Regex) que representa una expresión regular concreta se usa en varias llamadas a métodos de coincidencia de patrones de expresión regular.

* El objeto [Regex](xref:System.Text.RegularExpressions.Regex) no puede estar fuera del ámbito y, por tanto, se puede volver a usar.

* Una expresión regular estática se usa en varias llamadas a métodos de coincidencia de patrones de expresión regular. (La mejora de rendimiento es posible porque el motor de expresiones regulares almacena en la caché las expresiones regulares que se usan en llamadas de métodos estáticos). 

## <a name="ignore-white-space"></a>Ignorar el espacio en blanco

De forma predeterminada, el espacio en blanco de un patrón de expresión regular es significativo; fuerza al motor de expresiones regulares a buscar un carácter de espacio en blanco en la cadena de entrada. Debido a ello, las expresiones regulares `"\b\w+\s"` y `"\b\w+ "` son, en líneas generales, expresiones regulares equivalentes. Además, cuando el signo de número (**#**) se detecta en un patrón de expresión regular, se interpreta como un carácter literal para el que se deben buscar coincidencias.

La opción [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace), o la opción insertada **x**, cambia su comportamiento predeterminado del modo siguiente:

* El espacio en blanco sin escape del patrón de expresión regular se ignora. Para formar parte de un patrón de expresión regular, los caracteres de espacio en blanco se deben incluir en secuencias de escape (por ejemplo, como **\s** o "**\** ").

* El signo de número (**#**) se interpreta como el inicio de un comentario, en vez de como carácter literal. Todo el texto del patrón de expresión regular comprendido entre el carácter **#** y el final de la cadena se interpreta como un comentario.

Pero en los casos siguientes, los caracteres de espacio en blanco de una expresión regular no se ignoran, aunque se use la opción [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace): 

* Un espacio en blanco dentro de una clase de caracteres se interpreta siempre de forma literal. Por ejemplo, el patrón de expresión regular `[ .,;:]` coincide con cualquier carácter de espacio en blanco, punto, coma, punto y coma o dos puntos. 

* Los cuantificadores entre corchetes, por ejemplo, **{**_n_**}**, **{**_n_**,}** y **{**_n_**,**_m_**}**, no admiten espacio en blanco. Por ejemplo, el patrón de expresión regular **\d{1. 3}** no encontrará ninguna secuencia de entre uno y tres dígitos porque contiene un carácter de espacio en blanco. 

* No se admiten espacios en blanco en una secuencia de caracteres que presenta un elemento de lenguaje. Por ejemplo: 

    * El elemento de lenguaje **(?:**_subexpresión_**)** representa un grupo sin captura, y la parte **(?:** del elemento no puede tener espacios insertados. El patrón **(? :**_subexpresión_**)** produce una excepción [ArgumentException](xref:System.ArgumentException) en tiempo de ejecución porque el motor de expresiones regulares no puede analizar el patrón, y el patrón **(? :**_subexpresión_**)** no coincide con *subexpresión*.

    * El elemento de lenguaje **\p{**_nombre_**}**, que representa una categoría Unicode o bloque con nombre, no puede incluir espacios insertados en la parte **\p{** del elemento. Si se incluye un espacio en blanco, el elemento produce una excepción [ArgumentException](xref:System.ArgumentException) en tiempo de ejecución. 

Esta opción sirve para simplificar las expresiones regulares que a menudo resultan difíciles de analizar y entender. Además, mejora la legibilidad y posibilita la documentación de una expresión regular. 

Este ejemplo define el siguiente patrón de expresión regular:

`\b \(? ( (?>\w+) ,?\s? )+ [\.!?] \)? # Matches an entire sentence`.

El patrón es similar al patrón definido en la sección [Solo capturas explícitas](#explicit-captures-only), a excepción de que usa la opción [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) para ignorar el espacio en blanco del patrón.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

En el ejemplo siguiente se usa la opción insertada **(?x)** para ignorar el espacio en blanco del patrón.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

## <a name="right-to-left-mode"></a>Modo de derecha a izquierda

De forma predeterminada, el motor de expresiones regulares realiza las búsquedas de izquierda a derecha. Para invertir la dirección de búsqueda, se puede usar la opción [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft). De este modo, la búsqueda empieza automáticamente en la posición del último carácter de la cadena. En los métodos de coincidencia de patrones que incluyen un parámetro de posición inicial, como [Regex.Match(String, Int32)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32)), la posición inicial es el índice del carácter situado más a la derecha en el que debe empezar la búsqueda. 

> [!NOTE]
> El modo de patrón de derecha a izquierda solo está disponible si se suministra el valor [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) al parámetro options de un constructor de clase [Regex](xref:System.Text.RegularExpressions.Regex) o de un método estático de coincidencia de patrones. No está disponible como opción insertada. 
 

La opción [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) únicamente cambia la dirección de búsqueda, no interpreta el patrón de expresión regular de derecha a izquierda. Por ejemplo, la expresión regular `\bb\w+\s` coincide con las palabras que empiezan por la letra “b” y van seguidas por un carácter de espacio en blanco. En el ejemplo siguiente, la cadena de entrada consta de tres palabras que incluyen uno o varios caracteres “b”. La primera palabra empieza por “b”, la segunda finaliza en “b” y la tercera incluye dos caracteres “b” en el medio de la palabra. Tal como muestra el resultado del ejemplo, solo la primera palabra coincide con el patrón de expresión regular. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bb\w+\s";
      string input = "builder rob rabble";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.RightToLeft))
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);     
   }
}
// The example displays the following output:
//       'builder ' found at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bb\w+\s"
      Dim input As String = "builder rob rabble"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.RightToLeft)
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)     
      Next
   End Sub
End Module
' The example displays the following output:
'       'builder ' found at position 0.
```

Observe también que la aserción de búsqueda anticipada (el elemento de lenguaje **(?**=_subexpresión_**)**) y la aserción de búsqueda tardía (el elemento de lenguaje **(?<**=_subexpresión_**)**) no cambian de dirección. Las aserciones de búsqueda anticipada miran hacia la derecha, mientras que las de búsqueda tardía lo hacen hacia la izquierda. Por ejemplo, la expresión regular `(?<=\d{1,2}\s)\w+,?\s\d{4}` usa la aserción de búsqueda tardía para probar una fecha que precede al nombre de un mes. Después, la expresión regular busca coincidencias con el mes y el año. Para obtener información sobre aserciones de búsqueda anticipada y tardía, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "1 May 1917", "June 16, 2003" };
      string pattern = @"(?<=\d{1,2}\s)\w+,?\s\d{4}";

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern, RegexOptions.RightToLeft);
         if (match.Success)
            Console.WriteLine("The date occurs in {0}.", match.Value);
         else
            Console.WriteLine("{0} does not match.", input);
      }
   }
}
// The example displays the following output:
//       The date occurs in May 1917.
//       June 16, 2003 does not match.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "1 May 1917", "June 16, 2003" }
      Dim pattern As String = "(?<=\d{1,2}\s)\w+,?\s\d{4}"

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern, RegexOptions.RightToLeft)
         If match.Success Then
            Console.WriteLine("The date occurs in {0}.", match.Value)
         Else
            Console.WriteLine("{0} does not match.", input)
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       The date occurs in May 1917.
'       June 16, 2003 does not match.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`(?<=\d{1,2}\s)` | El inicio de la coincidencia debe estar precedido por uno o dos dígitos decimales seguidos de un espacio.
`\w+` | Buscar coincidencias con uno o más caracteres alfabéticos.
`,?` | Buscar coincidencias con cero o un carácter de coma.
`\s` | Coincide con un carácter de espacio en blanco.
`\d{4}` | Buscar coincidencias con cuatro dígitos decimales.
 
## <a name="ecmascript-matching-behavior"></a>Comportamiento de búsqueda de coincidencias de ECMAScript

De forma predeterminada, el motor de expresiones regulares usa un comportamiento canónico al buscar coincidencias entre un patrón de expresiones regulares y el texto de entrada. Pero se puede especificar la opción [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) para hacer que el motor de expresiones regulares use el comportamiento de búsqueda de coincidencias de ECMAScript. 

> [!NOTE]
> El comportamiento conforme a ECMAScript solo está disponible si se suministra el valor [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) al parámetro options de un constructor de clase [Regex](xref:System.Text.RegularExpressions.Regex) o de un método estático de coincidencia de patrones. No está disponible como opción insertada. 
 
La opción [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) únicamente se puede combinar con las opciones [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) y [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). El uso de cualquier otra opción en una expresión regular produce una excepción [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException).

El comportamiento de las expresiones regulares canónicas y ECMAScript se diferencia en tres aspectos: sintaxis de la clase de caracteres, grupos de captura con autorreferencia e interpretación de referencia inversa frente a octal. 

* Sintaxis de la clase de caracteres. Debido a que las expresiones regulares canónicas admiten Unicode y ECMAScript no, las clases de caracteres de ECMAScript tienen una sintaxis más limitada y algunos elementos de lenguaje de clases de caracteres tienen un significado diferente. Por ejemplo, ECMAScript no admite elementos de lenguaje como la categoría Unicode ni elementos de bloque como *\p* y **\P**. De igual modo, el elemento **\w**, que coincide con un carácter de palabra, es equivalente a la clase de caracteres **[a-zA-Z_0-9]** al usar ECMAScript y a **[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]** al usar un comportamiento canónico. Para obtener más información, consulte [Clases de carácter en expresiones regulares](classes.md).

  En el ejemplo siguiente se muestra la diferencia entre la búsqueda de coincidencias canónica y la de ECMAScript. Se define una expresión regular, `\b(\w+\s*)+`, que busca coincidencias con palabras seguidas de caracteres de espacio en blanco. La entrada consta de dos cadenas: una que usa el conjunto de caracteres latinos y otra que usa el conjunto de caracteres del cirílico. Tal como muestra el resultado, la llamada al método [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) que usa la búsqueda de coincidencias de ECMAScript no encuentra coincidencias con las palabras del cirílico, mientras que la llamada de método que usa la búsqueda de coincidencias canónica sí encuentra coincidencias con estas palabras. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;
  
  public class Example
  {
     public static void Main()
     {
        string[] values = { "целый мир", "the whole world" };
        string pattern = @"\b(\w+\s*)+";
        foreach (var value in values)
        {
           Console.Write("Canonical matching: ");
           if (Regex.IsMatch(value, pattern))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
  
           Console.Write("ECMAScript matching: ");
           if (Regex.IsMatch(value, pattern, RegexOptions.ECMAScript))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
           Console.WriteLine();
        }
     }
  }
  // The example displays the following output:
  //       Canonical matching: 'целый мир' matches the pattern.
  //       ECMAScript matching: целый мир does not match the pattern.
  //       
  //       Canonical matching: 'the whole world' matches the pattern.
  //       ECMAScript matching: 'the whole world' matches the pattern.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim values() As String = { "целый мир", "the whole world" }
        Dim pattern As String = "\b(\w+\s*)+"
        For Each value In values
           Console.Write("Canonical matching: ")
           If Regex.IsMatch(value, pattern)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If

           Console.Write("ECMAScript matching: ")
           If Regex.IsMatch(value, pattern, RegexOptions.ECMAScript)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If
           Console.WriteLine()
        Next
     End Sub
  End Module
  ' The example displays the following output:
  '       Canonical matching: 'целый мир' matches the pattern.
  '       ECMAScript matching: целый мир does not match the pattern.
  '       
  '       Canonical matching: 'the whole world' matches the pattern.
  '       ECMAScript matching: 'the whole world' matches the pattern.
  ```

* Grupos de captura con autorreferencia. Una clase de captura de expresión regular con una referencia inversa a sí misma debe actualizarse con cada iteración de captura. Como se muestra en el ejemplo siguiente, esta característica permite a la expresión regular `((a+)(\1) ?)+` coincidir con la cadena “ aa aaaa aaaaaa ” si se usa ECMAScript, pero no si se usa la búsqueda de coincidencias canónica. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     static string pattern;
  
     public static void Main()
     {
        string input = "aa aaaa aaaaaa "; 
        pattern = @"((a+)(\1) ?)+";
  
        // Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern));

        // Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript));
     }   

     private static void AnalyzeMatch(Match m)
     {
        if (m.Success)
        {
           Console.WriteLine("'{0}' matches {1} at position {2}.",  
                             pattern, m.Value, m.Index);
           int grpCtr = 0;
           foreach (Group grp in m.Groups)
           {
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value);
              grpCtr++;
              int capCtr = 0;
              foreach (Capture cap in grp.Captures)
              {
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value);
                 capCtr++;
              }
           }
        }
        else
        {
           Console.WriteLine("No match found.");
        }   
        Console.WriteLine();
     }
  }
  // The example displays the following output:
  //    No match found.
  //    
  //    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  //       0: 'aa aaaa aaaaaa '
  //          0: 'aa aaaa aaaaaa '
  //       1: 'aaaaaa '
  //          0: 'aa '
  //          1: 'aaaa '
  //          2: 'aaaaaa '
  //       2: 'aa'
  //          0: 'aa'
  //          1: 'aa'
  //          2: 'aa'
  //       3: 'aaaa '
  //          0: ''
  //          1: 'aa '
  //          2: 'aaaa '
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Dim pattern As String

     Public Sub Main()
        Dim input As String = "aa aaaa aaaaaa " 
        pattern = "((a+)(\1) ?)+"
  
        ' Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern))

        ' Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript))
     End Sub   

     Private Sub AnalyzeMatch(m As Match)
        If m.Success
           Console.WriteLine("'{0}' matches {1} at position {2}.", _ 
                             pattern, m.Value, m.Index)
           Dim grpCtr As Integer = 0
           For Each grp As Group In m.Groups
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value)
              grpCtr += 1
              Dim capCtr As Integer = 0
              For Each cap As Capture In grp.Captures
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value)
                 capCtr += 1
              Next
           Next
        Else
           Console.WriteLine("No match found.")
        End If   
        Console.WriteLine()
     End Sub
  End Module
  ' The example displays the following output:
  '    No match found.
  '    
  '    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  '       0: 'aa aaaa aaaaaa '
  '          0: 'aa aaaa aaaaaa '
  '       1: 'aaaaaa '
  '          0: 'aa '
  '          1: 'aaaa '  
  '          2: 'aaaaaa '
  '       2: 'aa'
  '          0: 'aa'
  '          1: 'aa'
  '          2: 'aa'
  '       3: 'aaaa '
  '          0: ''
  '          1: 'aa '
  '          2: 'aaaa '
  ``

  The regular expression is defined as shown in the following table.

Pattern | Description
------- | ----------- 
`(a+)` | Match the letter "a" one or more times. This is the second capturing group.
`(\1)` | Match the substring captured by the first capturing group. This is the third capturing group.
`?` | Match zero or one space characters.
`((a+)(\1) ?)+` | Match the pattern of one or more "a" characters followed by a string that matches the first capturing group followed by zero or one space characters one or more times. This is the first capturing group.
  
* Resolution of ambiguities between octal escapes and backreferences. The following table summarizes the differences in octal versus backreference interpretation by canonical and ECMAScript regular expressions.

Regular expression | Canonical behavior | ECMAScript behavior
------------------ | ------------------ | ------------------- 
`\0` followed by 0 to 2 octal digits | Interpret as an octal. For example, `\044` is always interpreted as an octal value and means "**$**". | Same behavior.
**\** followed by a digit from 1 to 9, followed by no additional decimal digits | Interpret as a backreference. For example, \9 always means backreference 9, even if a ninth capturing group does not exist. If the capturing group does not exist, the regular expression parser throws an [ArgumentException](xref:System.ArgumentException). | If a single decimal digit capturing group exists, backreference to that digit. Otherwise, interpret the value as a literal.
**\** followed by a digit from 1 to 9, followed by additional decimal digits | Interpret the digits as a decimal value. If that capturing group exists, interpret the expression as a backreference. Otherwise, interpret the leading octal digits up to octal 377; that is, consider only the low 8 bits of the value. Interpret the remaining digits as literals. For example, in the expression `\3000`, if capturing group 300 exists, interpret as backreference 300; if capturing group 300 does not exist, interpret as octal 300 followed by 0. | Interpret as a backreference by converting as many digits as possible to a decimal value that can refer to a capture. If no digits can be converted, interpret as an octal by using the leading octal digits up to octal 377; interpret the remaining digits as literals.
 
## Comparison using the invariant culture

By default, when the regular expression engine performs case-insensitive comparisons, it uses the casing conventions of the current culture to determine equivalent uppercase and lowercase characters. 

However, this behavior is undesirable for some types of comparisons, particularly when comparing user input to the names of system resources, such as passwords, files, or URLs. The following example illustrates such as scenario. The code is intended to block access to any resource whose URL is prefaced with **FILE://**. The regular expression attempts a case-insensitive match with the string by using the regular expression `$FILE://`. However, when the current system culture is tr-TR (Turkish-Turkey), "I" is not the uppercase equivalent of "i". As a result, the call to the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method returns `false`, and access to the file is allowed. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-sensitive matching ({0} culture)...", 
                  Thread.CurrentThread.CurrentCulture.Name);
if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("URLs that access files are not allowed.");      
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-sensitive matching (tr-TR culture)...
//       Access to file://c:/Documents.MyReport.doc is allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-sensitive matching ({0} culture)...", _
                  Thread.CurrentThread.CurrentCulture.Name)
If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If

Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'       Culture-sensitive matching (tr-TR culture)...
'       Access to file://c:/Documents.MyReport.doc is allowed.
```

> [!NOTE]
>   Para obtener más información sobre la comparación de cadenas con distinción entre mayúsculas y minúsculas, y con la referencia cultural de todos los idiomas, consulte [Procedimientos recomendados para el uso de cadenas](best-practices.md).
 
En vez de usar comparaciones sin distinción entre mayúsculas y minúsculas de la referencia cultural actual, se puede especificar la opción [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) para ignorar las diferencias culturales de idioma y usar las convenciones de la referencia cultural de todos los idiomas.

> [!NOTE]
> La comparación con la referencia cultural de todos los idiomas solo está disponible si se suministra el valor [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) al parámetro options de un constructor de clase [Regex](xref:System.Text.RegularExpressions.Regex) o de un método estático de coincidencia de patrones. No está disponible como opción insertada. 
 
El ejemplo siguiente es idéntico al anterior, excepto que se llama al método [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) estático con opciones que incluyen [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant). A pesar de que la referencia cultural actual está establecida en turco (Turquía), el motor de expresiones regulares es capaz de encontrar coincidencias con “FILE” y “file” y bloquear el acceso al recurso de archivo. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-insensitive matching...");
if (Regex.IsMatch(input, pattern, 
                  RegexOptions.IgnoreCase | RegexOptions.CultureInvariant)) 
   Console.WriteLine("URLs that access files are not allowed.");
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-insensitive matching...
//       URLs that access files are not allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-insensitive matching...")
If Regex.IsMatch(input, pattern, _
               RegexOptions.IgnoreCase Or RegexOptions.CultureInvariant) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If
Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'        Culture-insensitive matching...
'        URLs that access files are not allowed.
```

## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)




<!--HONumber=Nov16_HO3-->


