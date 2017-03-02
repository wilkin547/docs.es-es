---
title: "Construcciones misceláneas en expresiones regulares"
description: "Construcciones misceláneas en expresiones regulares"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 478901dc-db6c-4d90-9d3b-f5cfdca2cbf5
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6b8e39902dc735cac72864024033fe5cc14fb55a
ms.lasthandoff: 03/02/2017

---

# <a name="miscellaneous-constructs-in-regular-expressions"></a>Construcciones misceláneas en expresiones regulares


Las expresiones regulares en .NET incluyen tres construcciones de lenguaje misceláneas. Una permite habilitar o deshabilitar opciones de coincidencia determinadas en medio de un patrón de expresión regular. Las otras dos permiten incluir comentarios en una expresión regular.

## <a name="inline-options"></a>Opciones insertadas

Puede establecer o deshabilitar opciones de coincidencia de patrones específicas para una parte de una expresión regular mediante la sintaxis

```
(?imnsx-imnsx)
```

Indique las opciones que quiere habilitar después del signo de interrogación y las opciones que quiere deshabilitar después del signo menos. En la siguiente tabla se describe cada una de las opciones. Para obtener más información sobre cada opción, consulte [Opciones de expresiones regulares](options.md).

Opción | Descripción
------ | ----------- 
**i** | Coincidencia sin distinción entre mayúsculas y minúsculas.
**m** | Modo multilínea.
**n** | Solo capturas explícitas. (Los paréntesis no actúan como grupos de capturas).
**s** | Modo de una sola línea.
**x** | Se omite el espacio en blanco sin escape y se permiten los comentarios en modo X. 
 
Cualquier cambio en las opciones de expresión regular definido mediante la construcción **(?imnsx-imnsx)** permanece en vigor hasta el final del grupo envolvente.

> [!NOTE]
> La construcción de agrupamiento **(?imnsx-imnsx**:_subexpresión_**)** proporciona una funcionalidad idéntica para una subexpresión. Para obtener más información, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).
 
En el ejemplo siguiente se usan las opciones **i**, **n** y **x** para habilitar las capturas explícitas y la opción que no hace distinción entre mayúsculas y minúsculas, y para omitir el espacio en blanco del patrón de expresión regular en medio de una expresión regular. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern; 
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      pattern = @"\b(D\w+)\s(d\w+)\b";
      // Match pattern using default options.
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
      }
      Console.WriteLine();

      // Change regular expression pattern to include options.
      pattern = @"\b(D\w+)(?ixn) \s (d\w+) \b";
      // Match new pattern with options. 
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Drooling dog
//          Group 1: Drooling
//          Group 2: dog
//       
//       Drooling dog
//          Group 1: 'Drooling'
//       Dreaded Deep
//          Group 1: 'Dreaded'
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String 
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      pattern = "\b(D\w+)\s(d\w+)\b"
      ' Match pattern using default options.
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
      Console.WriteLine()

      ' Change regular expression pattern to include options.
      pattern = "\b(D\w+)(?ixn) \s (d\w+) \b"
      ' Match new pattern with options. 
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       Drooling dog
'          Group 1: Drooling
'          Group 2: dog
'       
'       Drooling dog
'          Group 1: 'Drooling'
'       Dreaded Deep
'          Group 1: 'Dreaded'
```

En el ejemplo se definen dos expresiones regulares. La primera, `\b(D\w+)\s(d\w+)\b`, coincide con dos palabras consecutivas que empiezan con una "D" mayúscula y una "d" minúscula. La segunda expresión regular, `\b(D\w+)(?ixn) \s (d\w+) \b`, usa opciones insertadas para modificar este patrón, como se describe en la tabla siguiente. Una comparación de los resultados confirma los efectos de la construcción `(?ixn)`.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`(D\w+)` | Coincide con una "D" mayúscula seguida de uno o más caracteres de palabra. Este es el primer grupo de capturas.
`(?ixn)` | A partir de este punto, hace comparaciones sin distinción entre mayúsculas y minúsculas, solo hace capturas explícitas y omite el espacio en blanco del patrón de expresión regular.
`\s` | Coincide con un carácter de espacio en blanco.
`(d\w+)` | Coincide con una "d" mayúscula o minúscula seguida de uno o más caracteres de palabra. Este grupo no se captura porque se ha habilitado la opción n (captura explícita).
`\b` | Coincide con un límite de palabras.
 
## <a name="inline-comment"></a>Comentario alineado

La construcción **(?#** _comentario_**)** permite incluir un comentario alineado en una expresión regular. El motor de expresiones regulares no usa ninguna parte del comentario en la coincidencia de patrones, aunque el comentario se incluye en la cadena devuelta por el método [Regex.ToString](xref:System.Text.RegularExpressions.Regex.Unescape(System.String)). El comentario termina en el primer paréntesis de cierre.

En el ejemplo siguiente se repite el primer patrón de expresión regular del ejemplo de la sección anterior. Se agregan dos comentarios alineados en la expresión regular para indicar si la comparación distingue entre mayúsculas y minúsculas. El patrón de expresión regular, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, se define como se indica a continuación.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`(?# case-sensitive comparison)` | Comentario. No afecta al comportamiento de la coincidencia de patrones.
`(D\w+)` | Coincide con una "D" mayúscula seguida de uno o más caracteres de palabra. Este es el primer grupo de captura.
`\s` | Coincide con un carácter de espacio en blanco.
`(?ixn)` |A partir de este punto, hace comparaciones sin distinción entre mayúsculas y minúsculas, solo hace capturas explícitas y omite el espacio en blanco del patrón de expresión regular.
`(?#case-insensitive comparison)` | Comentario. No afecta al comportamiento de la coincidencia de patrones. 
`(d\w+)` | Coincide con una "d" mayúscula o minúscula seguida de uno o más caracteres de palabra. Este es el segundo grupo de capturas.
`\b` | Coincide con un límite de palabras.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b";
      Regex rgx = new Regex(pattern);
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      Console.WriteLine("Pattern: " + pattern.ToString());
      // Match pattern using default options.
      foreach (Match match in rgx.Matches(input))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
         {
            for (int ctr = 1; ctr <match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
         }
      }
   }
}
// The example displays the following output:
//    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
//    arison)d\w+)\b
//    Drooling dog
//       Group 1: Drooling
//    Dreaded Deep
//       Group 1: Dreaded
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b"
      Dim rgx As New Regex(pattern)
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      Console.WriteLine("Pattern: " + pattern.ToString())
      ' Match pattern using default options.
      For Each match As Match In rgx.Matches(input)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
'    arison)d\w+)\b
'    Drooling dog
'       Group 1: Drooling
'    Dreaded Deep
'       Group 1: Dreaded
```

## <a name="end-of-line-comment"></a>Comentario de final de línea

Un signo de número (**#**) marca un comentario en modo X, que empieza en el carácter # sin escape al final del patrón de expresión regular y continúa hasta el final de la línea. Para usar esta construcción, debe habilitar la opción **x** (mediante opciones insertadas) o proporcionar el valor [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) al parámetro *option* al crear una instancia del objeto [Regex](xref:System.Text.RegularExpressions.Regex) o al llamar al método [Regex](xref:System.Text.RegularExpressions.Regex) estático. 

En el ejemplo siguiente se muestra la construcción de comentario de final de línea. Determina si una cadena es una cadena de formato compuesto que incluye al menos un elemento de formato. En la tabla siguiente se describe la construcción en el patrón de expresión regular: 

`\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item`. 

Modelo | Descripción
------- | ----------- 
`\{` | Coincide con una llave de apertura.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
`(,-*\d+)*` | Coincide con cero o una aparición de una coma seguida de un signo menos opcional, seguido de uno o más dígitos decimales.
`(\:\w{1,4}?)*` | Coincide con cero o una aparición de un signo de dos puntos seguido de uno a cuatro caracteres de espacio en blanco, pero el menor número posible.
`(?#case insensitive comparison)` | Comentario alineado. No tiene ningún efecto en el comportamiento de la coincidencia de patrones.
`\}` | Coincide con una llave de cierre.
`(?x)` | Habilita la opción de ignorar el espacio en blanco del patrón para que se reconozca el comentario de final de línea.
`# Looks for a composite format item.` | Comentario de final de línea.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.";
      string input = "{0,-3:F}";
      Console.WriteLine("'{0}':", input);
      if (Regex.IsMatch(input, pattern))
         Console.WriteLine("   contains a composite format item.");
      else
         Console.WriteLine("   does not contain a composite format item.");
   }
}
// The example displays the following output:
//       '{0,-3:F}':
//          contains a composite format item.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item."
      Dim input As String = "{0,-3:F}"
      Console.WriteLine("'{0}':", input)
      If Regex.IsMatch(input, pattern) Then
         Console.WriteLine("   contains a composite format item.")
      Else
         Console.WriteLine("   does not contain a composite format item.")
      End If
   End Sub
End Module
' The example displays the following output:
'       '{0,-3:F}':
'          contains a composite format item.
```

Tenga en cuenta que, en lugar de proporcionar la construcción `(?x)` en la expresión regular, el comentario también podía haberse reconocido llamando al método [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) y pasando el valor de enumeración [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace).

## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)


