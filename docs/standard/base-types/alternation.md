---
title: Construcciones de alternancia en expresiones regulares
description: Construcciones de alternancia en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 59ffac4d-fc6e-461f-8783-d9f8dc88ce2c
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 2c31622ff97f30e565ed2cd82128518d04d5d1dc

---

# <a name="alternation-constructs-in-regular-expressions"></a>Construcciones de alternancia en expresiones regulares

Las construcciones de alternancia modifican una expresión regular para habilitar la coincidencia condicional o “either/or”. .NET admite tres construcciones de alternancia:

* Coincidencia de patrones con **|**

* Coincidencia condicional con **(?(**_expresión_**)**_sí_**|**_no_**)**

* Coincidencia condicional basada en un grupo capturado válido

## <a name="pattern-matching-with-"></a>Coincidencia de patrones con |

Puede usar el carácter de barra vertical (|) para hacer coincidir un elemento de una serie de patrones, donde el carácter | separa cada patrón. 

Como sucede con la clase de caracteres positivos, el carácter | puede usarse para hacer coincidir un elemento de una serie de caracteres individuales. En el ejemplo siguiente, se usa una clase de caracteres positivos y/o la coincidencia de patrones con el carácter | para buscar apariciones de las palabras "gray" o "grey" en una cadena. En este caso, el carácter | produce una expresión regular que es más detallada. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Regular expression using character class.
      string pattern1 = @"\bgr[ae]y\b";
      // Regular expression using either/or.
      string pattern2 = @"\bgr(a|e)y\b";

      string input = "The gray wolf blended in among the grey rocks.";
      foreach (Match match in Regex.Matches(input, pattern1))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern2))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       'gray' found at position 4
//       'grey' found at position 35
//       
//       'gray' found at position 4
//       'grey' found at position 35           
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Regular expression using character class.
      Dim pattern1 As String = "\bgr[ae]y\b"
      ' Regular expression using either/or.
      Dim pattern2 As String = "\bgr(a|e)y\b"

      Dim input As String = "The gray wolf blended in among the grey rocks."
      For Each match As Match In Regex.Matches(input, pattern1)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern2)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
   End Sub
End Module
' The example displays the following output:
'       'gray' found at position 4
'       'grey' found at position 35
'       
'       'gray' found at position 4
'       'grey' found at position 35 
```

La expresión regular que usa el carácter |, `\bgr(a|e)y\b,` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`gr` | Coincide con los caracteres "gr".
`(a|e)` | Coincide con una "a" o una "e".
`y\b` | Coincide con una "y" en un límite de palabras.


El carácter | también se puede usar para realizar una coincidencia either/or con varios caracteres o subexpresiones, que pueden incluir cualquier combinación de literales de carácter y elementos de lenguaje de expresión regular. (La clase de caracteres no proporciona esta funcionalidad). En el ejemplo siguiente, se usa el carácter | para extraer un número de la seguridad social (SSN) de EE. UU., de nueve dígitos y en formato *ddd-dd-dddd*, o un número de identificación de empleador (EIN), de nueve dígitos y en formato *dd-ddddddd*.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

La expresión regular `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`(\d{2}-\d{7}|;\d{3}-\d{2}-\d{4})` | Coincide con cualquiera de las siguientes opciones: dos dígitos decimales seguidos de un guión seguido de siete dígitos decimales; o tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales. 
`\d` | Finalizar la búsqueda de coincidencias en un límite de palabras.
                                         
## <a name="conditional-matching-with-an-expression"></a>Coincidencia condicional con una expresión

Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si puede coincidir con un patrón inicial. Su sintaxis es:

**(?(**_expresión_**)**_sí_**|**_no_**)**

donde *expresión* es el patrón inicial de coincidencia, *sí* es el patrón de coincidencia si se encuentra una coincidencia para expresión y *no* es el patrón opcional de coincidencia si no se encuentra ninguna coincidencia para *expresión*. El motor de expresiones regulares trata a la *expresión* como una aserción de ancho cero; es decir, el motor de expresiones regulares no avanza en el flujo de entrada después de evaluar la *expresión*. Por tanto, esta construcción es equivalente a la siguiente:

**(?(?**=_expresión_**)**_sí_**|**_no_**)**

donde **(?**=_expresión_**)** es una construcción de aserción de ancho cero. (Para obtener más información, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md)). Dado que el motor de expresiones regulares interpreta la *expresión* como un delimitador (una aserción de ancho cero), la *expresión* debe ser una aserción de ancho cero (para obtener más información, consulte [Delimitadores en expresiones regulares](anchors.md)) o una subexpresión que también está incluida en *sí*. De lo contrario, no se pueden encontrar coincidencias para el patrón *sí*. 

> [!NOTE]
> Si *expresión* es un grupo de captura con nombre o con numeración, la construcción de alternancia se interpreta como una prueba de captura; para obtener más información, consulte la sección siguiente, [Coincidencia condicional basada en un grupo capturado válido](#conditional-matching-based-on-a-valid-captured-group). En otras palabras, el motor de expresiones regulares no intenta coincidir con la subcadena capturada, sino que, en vez de eso, comprueba la presencia o la ausencia del grupo.
 

El siguiente ejemplo es una variación del que aparece en la sección anterior. En él se usa la coincidencia condicional para determinar si los tres primeros caracteres después de un límite de palabra son dos dígitos seguidos por un guión. Si es así, intenta buscar un número de identificación de empleador (EIN) de EE. UU. Si no, intenta buscar un número de la seguridad social (SSN) de EE.UU.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

El patrón de la expresión regular `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`(?(\d{2}-)` | Determina si los tres caracteres siguientes están compuestos de dos dígitos seguidos de un guión.
`\d{2}-\d{7}` | Si el patrón anterior coincide, coincide con dos dígitos seguidos de un guión seguido de siete dígitos.
`\d{3}-\d{2}-\d{4}` | Si el patrón anterior no coincide, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales. 
`\b` | Coincide con un límite de palabras.
 
## <a name="conditional-matching-based-on-a-valid-captured-group"></a>Coincidencia condicional basada en un grupo capturado válido

Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si coincidió con un grupo de captura especificado. Su sintaxis es:

**(?(**_nombre_**)**_sí_**|**_no_**)**

o

**(?(**_número_**)**_sí_**|**_no_**)**

donde *nombre* es el nombre y *número* es el número de un grupo de captura, *sí* es la expresión que debe coincidir si nombre o número tienen una coincidencia, y *no* es la expresión opcional que debe coincidir si no la tienen.

Si *nombre* no se corresponde con el nombre de un grupo de captura que se usa en el patrón de expresión regular, la construcción de alternancia se interpreta como una prueba de expresión, tal y como se explica en la sección anterior. Normalmente, esto significa que expresión se evalúa como `false`. Si `number` no se corresponde con un grupo de captura con numeración que se usa en el patrón de expresión regular, el motor de expresiones regulares genera una [ArgumentException](xref:System.ArgumentException).

El siguiente ejemplo es una variación del que aparece en la sección anterior. En él se usa un grupo de captura denominado `n2` que consta de dos dígitos seguidos por un guión. La construcción de alternancia prueba si este grupo de captura ha coincidido en la cadena de entrada. En caso afirmativo, la construcción de alternancia intenta hacer coincidir los últimos siete dígitos de un número de identificación de empleador de identificación de empleador (EIN) de EE. UU. En caso negativo, intenta coincidir con un número de la seguridad social (SSN) de EE.UU.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
```

El patrón de la expresión regular `\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`(?<n2>\d{2}-)*` | Coincide con cero o con dos dígitos seguidos por un guión. Este grupo de captura se denomina `n2`.
`(?(n2)` | Prueba si `n2` coincidió con la cadena de entrada. 
`)\d{7}` | Si `n2` coincidió, coincide con siete dígitos decimales.
`|;\d{3}-\d{2}-\d{4}` | Si `n2` no coincidió, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales. 
`\b` | Coincide con un límite de palabras.
 
En el ejemplo siguiente se muestra una variación de este ejemplo, pero con un grupo numerado en lugar de un grupo con nombre. Su patrón de expresión regular es `\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example display the following output:
//       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)




<!--HONumber=Nov16_HO3-->


