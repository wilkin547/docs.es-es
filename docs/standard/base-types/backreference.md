---
title: Construcciones de referencia inversa en expresiones regulares
description: Construcciones de referencia inversa en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c453ed78-650f-4c3c-9ab4-9d89d250bf88
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: d6fdf23898cacc7ce569f868b3a31b71eff5c716
ms.lasthandoff: 03/02/2017

---

# <a name="backreference-constructs-in-regular-expressions"></a>Construcciones de referencia inversa en expresiones regulares

Las referencias inversas proporcionan una forma cómoda de identificar un carácter o subcadena repetidos dentro de una cadena. Por ejemplo, si la cadena de entrada contiene varias apariciones de una subcadena arbitraria, puede buscar una coincidencia con la primera aparición con un grupo de captura y después usar una referencia inversa para buscar una coincidencia con las siguientes apariciones de la subcadena. 

> [!NOTE]
> Se usa una sintaxis independiente para hacer referencia a los grupos de captura con numeración y con nombre de las cadenas de reemplazo. Para obtener más información, consulte [Sustituciones en expresiones regulares](substitutions.md).
 
.NET define elementos del lenguaje independientes para hacer referencia a los grupos de captura con numeración y con nombre. Para obtener más información sobre los grupos de captura, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

## <a name="numbered-backreferences"></a>Referencias inversas con numeración

Una referencia inversa con numeración usa la siguiente sintaxis:

**\**_número_

donde *número* es la posición ordinal del grupo de captura en la expresión regular. Por ejemplo, `\4` coincide con el contenido del cuarto grupo de captura. Si *número* no está definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una [ArgumentException](xref:System.ArgumentException). Por ejemplo, la expresión regular `\b(\w+)\s\1` es válida, porque `(\w+)` es el primer y único grupo de captura de la expresión. Por otro lado, `\b(\w+)\s\2` no es válida y produce una excepción de argumento porque no hay ningún grupo de captura con numeración `\2`.

Tenga en cuenta la ambigüedad entre los códigos de escape octales (como `\16`) y las referencias inversas **\**_número_ que usan la misma notación. Esta ambigüedad se resuelve de la siguiente forma:

* Las expresiones `\1` a `\9` siempre se interpretan como referencias inversas y no como códigos octales.

* Si el primer dígito de una expresión con varios dígitos es 8 o 9 (como `\80` o `\91`), la expresión se interpreta como un literal.

* Las expresiones a partir de `\10` y superiores se consideran referencias inversas si hay una referencia inversa que se corresponda con ese número; en caso contrario, se interpretan como códigos octales.

* Si una expresión regular contiene una referencia inversa a un número de grupo sin definir, se produce un error de análisis y el motor de expresiones regulares produce una [ArgumentException](xref:System.ArgumentException).

Si la ambigüedad constituye un problema, puede usar la notación **\k<**_nombre_**>**, que es inequívoca y no se puede confundir con códigos de caracteres octales. De forma similar, los códigos hexadecimales como `\xdd` son inequívocos y no se pueden confundir con las referencias inversas.

En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena. Define una expresión regular, `(\w)\1,` que consta de los siguientes elementos.

Elemento | Descripción
------- | -----------
`(\w)` | Coincide con un carácter que se usa para formar palabras y se lo asigna al primer grupo de captura.
`\1` | Coincide con el siguiente carácter que sea igual que el valor del primer grupo de captura.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w)\1";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w)\1"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="named-backreferences"></a>Referencias inversas con nombre

Una referencia inversa con nombre se define mediante la sintaxis siguiente:

**\k<**_nombre_**>**

O bien

**\k'**_nombre_**'**

donde *nombre* es el nombre de un grupo de captura definido en el patrón de expresión regular. Si *nombre* no está definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una excepción [ArgumentException](xref:System.ArgumentException).

En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena. Define una expresión regular, `(?<char>\w)\k<char>`, que consta de los siguientes elementos.

Elemento | Descripción
------- | -----------
`(?<char>\w)` | Coincide con un carácter que se usa para formar palabras y se lo asigna a un grupo de captura denominado char.
`\k<char>` | Coincide con el siguiente carácter que sea igual que el valor del grupo de captura char.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<char>\w)\k<char>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<char>\w)\k<char>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

Tenga en cuenta que *nombre* también puede ser la representación de cadena de un número. Por ejemplo, en el ejemplo siguiente, se usa la expresión regular `(?<2>\w)\k<2>` para buscar caracteres de palabra duplicados en una cadena.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<2>\w)\k<2>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<2>\w)\k<2>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="what-backreferences-match"></a>Con qué coinciden las referencias inversas

Una referencia inversa constituye la definición más reciente de un grupo (la definición más inmediatamente a la izquierda, al coincidir de izquierda a derecha). Cuando un grupo realiza varias capturas, una referencia inversa se refiere a la captura más reciente. 

En el ejemplo siguiente, se incluye un patrón de expresión regular, `(?<1>a)(?<1>\1b)*`, que redefine el grupo con nombre \1. En la tabla siguiente, se describe cada patrón de la expresión regular. 

Modelo | Descripción
------- | -----------
`(?<1>a)` | Coincide con el carácter "a" y asigna el resultado al grupo de captura denominado 1.
`(?<1>\1b)*` |Coincide con 0 o 1 apariciones del grupo denominado 1 junto con una "b" y asigna el resultado al grupo de captura denominado 1. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<1>a)(?<1>\1b)*";
      string input = "aababb";
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("Match: " + match.Value);
         foreach (Group group in match.Groups)
            Console.WriteLine("   Group: " + group.Value);
      }
   }
}
// The example displays the following output:
//          Group: aababb
//          Group: abb
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<1>a)(?<1>\1b)*"
      Dim input As String = "aababb"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: " + match.Value)
         For Each group As Group In match.Groups
            Console.WriteLIne("   Group: " + group.Value)
         Next
      Next
   End Sub
End Module
' The example display the following output:
'          Group: aababb
'          Group: abb
```

Al comparar la expresión regular con la cadena de entrada ("aababb"), el motor de expresiones regulares realiza las siguientes operaciones:

1. Comienza al principio de la cadena y hace que "a" coincida correctamente con la expresión `(?<1>a)`. Ahora, el valor del grupo 1 es "a".

2. Se desplaza hasta el segundo carácter y hace que la cadena "ab" coincida correctamente con la expresión `\1b`, o "ab". Después, asigna el resultado "ab" a `\1`.

3. Se desplaza hasta el cuarto carácter. La expresión `(?<1>\1b)` puede coincidir cero o más veces, así que la cadena "abb" coincide correctamente con la expresión `\1b`. Vuelve a asignar el resultado, "abb", a `\1`.

En este ejemplo, \* es un cuantificador de bucle: se evalúa repetidas veces hasta que el motor de expresiones regulares no puede coincidir con el patrón que define. Los cuantificadores de bucle no borran las definiciones de grupo.

Si un grupo no ha capturado ninguna subcadena, no se define una referencia inversa a ese grupo y no coincide nunca. Así lo ilustra el patrón de expresión regular `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b,` que se define de la siguiente forma:

Modelo | Descripción
------- | -----------
`\b` | Comienza la búsqueda de coincidencias en un límite de palabras.
`(\p{Lu}{2})` | Coincide con dos letras mayúsculas. Este es el primer grupo de captura.
`(\d{2})?` | Coincide con una o ninguna aparición de dos dígitos decimales. Este es el segundo grupo de captura.
`(\p{Lu}{2})` | Coincide con dos letras mayúsculas. Éste es el tercer grupo de captura.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.

Una cadena de entrada puede coincidir con esta expresión regular aunque no estén presentes los dos dígitos decimales que define el segundo grupo de captura. En el ejemplo siguiente, se muestra que, aunque la coincidencia es correcta, hay un grupo de captura vacío entre dos grupos de captura correctos.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b";
      string[] inputs = { "AA22ZZ", "AABB" };
      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
         {
            Console.WriteLine("Match in {0}: {1}", input, match.Value);
            if (match.Groups.Count > 1)
            {
               for (int ctr = 1; ctr <= match.Groups.Count - 1; ctr++)
               {
                  if (match.Groups[ctr].Success)
                     Console.WriteLine("Group {0}: {1}", 
                                       ctr, match.Groups[ctr].Value);
                  else
                     Console.WriteLine("Group {0}: <no match>", ctr);
               }
            }
         }
         Console.WriteLine();
      }      
   }
}
// The example displays the following output:
//       Match in AA22ZZ: AA22ZZ
//       Group 1: AA
//       Group 2: 22
//       Group 3: ZZ
//       
//       Match in AABB: AABB
//       Group 1: AA
//       Group 2: <no match>
//       Group 3: BB
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b"
      Dim inputs() As String = { "AA22ZZ", "AABB" }
      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("Match in {0}: {1}", input, match.Value)
            If match.Groups.Count > 1 Then
               For ctr As Integer = 1 To match.Groups.Count - 1
                  If match.Groups(ctr).Success Then
                     Console.WriteLine("Group {0}: {1}", _
                                       ctr, match.Groups(ctr).Value)
                  Else
                     Console.WriteLine("Group {0}: <no match>", ctr)
                  End If      
               Next
            End If
         End If
         Console.WriteLine()
      Next      
   End Sub
End Module
' The example displays the following output:
'       Match in AA22ZZ: AA22ZZ
'       Group 1: AA
'       Group 2: 22
'       Group 3: ZZ
'       
'       Match in AABB: AABB
'       Group 1: AA
'       Group 2: <no match>
'       Group 3: BB
```

## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)


