---
title: Detalles del comportamiento de expresiones regulares
description: Detalles del comportamiento de expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6f11047f-45a4-4caf-a259-18abe08cc0d2
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: b217b59874ceafbb0e5e410878cc434974c5a863

---

# <a name="details-of-regular-expression-behavior"></a>Detalles del comportamiento de expresiones regulares


El motor de expresiones regulares de .NET es un buscador de coincidencias de expresiones regulares con retroceso que incorpora un motor NFA (autómata finito no determinista) tradicional, como el que usa Perl, Python, Emacs y Tcl. Esto lo distingue de los motores DFA (autómatas finitos deterministas) de expresiones regulares puras, más rápidos pero más limitados, como los de awk, egrep o lex. Esto también lo distingue de los NFA POSIX, estandarizados pero más lentos. En la sección siguiente se describen los tres tipos de motores de expresiones regulares y se explica por qué las expresiones regulares de .NET se implementan mediante un motor NFA tradicional.

## <a name="benefits-of-the-nfa-engine"></a>Ventajas del motor NFA

Cuando los motores DFA realizan una búsqueda de coincidencia de patrones, su orden de procesamiento está controlado por la cadena de entrada. El motor empieza al principio de la cadena de entrada y continúa de forma secuencial para determinar si el carácter siguiente coincide con el patrón de expresión regular. Pueden garantizar una coincidencia con la cadena más larga posible. Dado que nunca prueban el mismo carácter dos veces, los motores de búsqueda DFA no permiten el retroceso. Pero, como los motores de búsqueda DFA solo contienen estados finitos, no pueden coincidir con un patrón con referencias inversas y, como no crean una expansión explícita, no pueden capturar subexpresiones.

A diferencia de los motores DFA, cuando los motores NFA tradicionales realizan una búsqueda de coincidencia de patrones, su orden de procesamiento está controlado por el patrón de expresión regular. Al procesar un elemento del lenguaje determinado, el motor usa una búsqueda de coincidencia expansiva, es decir, coincide con la mayor parte posible de la cadena de entrada. Pero también guarda su estado después de encontrar una coincidencia correcta con una subexpresión. Si finalmente se produce un error en una coincidencia, el motor puede volver a un estado guardado para buscar otras coincidencias. Este proceso de abandonar una coincidencia de subexpresión correcta para que los elementos del lenguaje subsiguientes de la expresión regular también puedan coincidir se conoce como retroceso. Los motores NFA usan el retroceso para probar todas las expansiones posibles de una expresión regular en un orden específico y aceptan la primera coincidencia. Puesto que los motores NFA tradicionales construyen una expansión específica de la expresión regular para encontrar una coincidencia correcta, pueden capturar coincidencias de subexpresiones y referencias inversas coincidentes. Pero el hecho de que los motores NFA tradicionales puedan retroceder les permite visitar el mismo estado varias veces si llegan al estado a través de diferentes rutas de acceso. Como resultado, se pueden ejecutar de forma exponencialmente lenta en el peor de los casos. Dado que los motores NFA tradicionales aceptan la primera coincidencia que encuentran, puede darse que no descubran otras coincidencias (probablemente más largas).

Los motores NFA POSIX son como los motores NFA tradicionales, salvo que siguen retrocediendo hasta que puedan garantizar que han encontrado la coincidencia más larga posible. Como resultado, un motor NFA POSIX es más lento que un motor NFA tradicional, y cuando se usa un motor NFA POSIX, no se puede dar preferencia a una coincidencia más corta frente a una más larga cambiando el orden de la búsqueda hacia atrás. 

Los motores NFA tradicionales son muy populares entre los programadores porque ofrecen mayor control sobre la coincidencia de cadenas que los motores de búsqueda DFA o NFA POSIX. Aunque, en el peor de los casos, se pueden ejecutar con lentitud, se les puede dirigir para que busquen coincidencias en tiempo lineal o polinómico mediante patrones que reduzcan las ambigüedades y limiten el retroceso. En otras palabras, aunque los motores NFA sacrifican el rendimiento a favor de la eficacia y la flexibilidad, en la mayoría de los casos ofrecen un rendimiento aceptable si una expresión regular está escrita correctamente y evitan los casos en los que el retroceso degrada exponencialmente el rendimiento.

> [!NOTE]
> Para obtener información sobre la reducción del rendimiento que causa un retroceso excesivo y sobre las maneras de crear una expresión regular para solucionarlo, consulte [Backtracking in Regular Expressions](backtracking.md) (Retroceso en expresiones regulares).
 
## <a name="net-framework-engine-capabilities"></a>Funciones del motor de .NET Framework

Para aprovechar las ventajas de un motor NFA tradicional, el motor de expresiones regulares de .NET incluye un conjunto completo de construcciones que permiten a los programadores dirigir el motor de retroceso. Estas construcciones se pueden usar para buscar coincidencias con mayor rapidez o para dar preferencia a determinadas expansiones frente a otras.

Otras características del motor de expresiones regulares de .NET son las siguientes: 

### <a name="lazy-quantifiers"></a>Cuantificadores diferidos

Cuantificadores diferidos: **??**, __*?__, **+?**, **{**_n_**,**_m_**}?**. Estas construcciones le indican al motor de retroceso que busque primero el número mínimo de repeticiones. En cambio, los cuantificadores expansivos normales intentan buscar primero el número máximo de repeticiones. En el siguiente ejemplo se ilustra la diferencia entre ambos. Una expresión regular coincide con una oración que termina con un número, y hay un grupo de capturas diseñado para extraer ese número. La expresión regular `.+(\d+)\.` incluye el cuantificador expansivo `.+`, lo que hace que el motor de expresiones regulares capture solo el último dígito del número. En cambio, la expresión regular `.+?(\d+)\.` incluye el cuantificador diferido `.+?`, lo que hace que el motor de expresiones regulares capture el número entero.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string lazyPattern = @".+?(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
       // Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", lazyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (greedy): 5
//       Number at end of sentence (lazy): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim lazyPattern As String = ".+?(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", lazyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (greedy): 5
'       Number at end of sentence (lazy): 107325
```

Las versiones expansiva y diferida de esta expresión regular se definen como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`.+` (cuantificador expansivo) | Buscar al menos una repetición de cualquier carácter. Esto hace que el motor de expresiones regulares busque una coincidencia con la cadena completa y, después, retroceda según sea necesario para coincidir con el resto del patrón.
`.+?` (cuantificador diferido) | Coincide con al menos una repetición de cualquier carácter, pero el menor número posible.
`(\d+)` | Coincide con al menos un carácter numérico y lo asigna al primer grupo de capturas.
`\.` | Coincide con un punto.
 
Para obtener más información sobre los cuantificadores diferidos, consulte [Cuantificadores en expresiones regulares](quantifiers.md).

### <a name="positive-lookahead"></a>Búsqueda anticipada positiva

Búsqueda anticipada positiva: **(?**=_subexpresión_**)**. Esta característica permite que el motor de retroceso vuelva a la misma posición en el texto después de encontrar una coincidencia con una subexpresión. Es útil para buscar en todo el texto mediante la comprobación de varios patrones que empiezan en la misma posición. Además, permite al motor comprobar que una subcadena existe al final de la coincidencia sin incluir la subcadena en el texto coincidente. En el ejemplo siguiente se usa la búsqueda anticipada positiva para extraer las palabras de una oración que no van seguidas de símbolos de puntuación.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b[A-Z]+\b(?=\P{P})";
      string input = "If so, what comes next?";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       If
//       what
//       comes
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b[A-Z]+\b(?=\P{P})"
      Dim input As String = "If so, what comes next?"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next   
   End Sub
End Module
' The example displays the following output:
'       If
'       what
'       comes
```

La expresión regular `\b[A-Z]+\b(?=\P{P})` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`[A-Z]+` | Coincide con cualquier carácter alfabético una o más veces. Dado que se llama al método [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) con la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), la comparación no distingue mayúsculas de minúsculas. 
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
`(?=\P{P})` | Busca hacia delante para determinar si el siguiente carácter es un signo de puntuación. Si no es así, se produce la coincidencia.

Para obtener más información sobre las aserciones de búsqueda anticipada positiva, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

### <a name="negative-lookahead"></a>Búsqueda anticipada negativa

Búsqueda anticipada negativa: **(?!**_subexpresión_**)**. Esta característica permite coincidir con una expresión solo si no se produce una coincidencia con una subexpresión. Esto es especialmente eficaz para restringir una búsqueda, ya que a menudo resulta más sencillo proporcionar una expresión para un caso que se debe eliminar, en lugar de una expresión para los casos que se deben incluir. Por ejemplo, es difícil escribir una expresión para buscar palabras que no comienzan por "non". En el ejemplo siguiente se usa la búsqueda anticipada negativa para excluirlas.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?!non)\w+\b";
      string input = "Nonsense is not always non-functional.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       is
//       not
//       always
//       functional
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?!non)\w+\b"
      Dim input As String = "Nonsense is not always non-functional."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       is
'       not
'       always
'       functional
```

El patrón de expresión regular `\b(?!non)\w+\b` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`(?!non)` | Buscar hacia delante para asegurarse de que la cadena actual no empieza por "non". Si lo hace, se produce un error de coincidencia.
`(\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
Para obtener más información sobre las aserciones de búsqueda anticipada negativa, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

### <a name="conditional-evaluation"></a>Evaluación condicional

Evaluación condicional: **(?(**_expresión_**)**_sí_&#124;_no_**)** and**(?(**_nombre_**)**_sí_&#124;_no_**)**, donde *expresión* es una subexpresión que debe coincidir, *nombre* es el nombre de un grupo de capturas, *sí* es la cadena que debe coincidir si *expresión* coincide o *nombre* es un grupo capturado válido y no vacío, y *no* es la subexpresión que debe coincidir si *expresión* no coincide o si *nombre* no es un grupo capturado válido y no vacío. Esta característica permite al motor buscar mediante más de un patrón alternativo, según el resultado de una búsqueda de coincidencia de subexpresión anterior o el resultado de una aserción de ancho cero. Esto posibilita una forma más eficaz de referencia inversa que permite, por ejemplo, coincidir con una subexpresión en función de si se produjo una coincidiencia con una subexpresión anterior. La expresión regular del ejemplo siguiente coincide con párrafos que están pensados tanto para un uso público como interno. Los párrafos destinados únicamente al uso interno empiezan con una etiqueta `<PRIVATE>`. El patrón de expresión regular `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` usa la evaluación condicional para asignar el contenido de los párrafos pensados para el uso público y para el uso interno a grupos de capturas independientes. Después, estos párrafos se pueden tratar de forma diferente.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "<PRIVATE> This is not for public consumption." + Environment.NewLine + 
                     "But this is for public consumption." + Environment.NewLine + 
                     "<PRIVATE> Again, this is confidential.\n";  
      string pattern = @"^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$";
      string publicDocument = null, privateDocument = null;

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
      {
         if (match.Groups[1].Success) {
            privateDocument += match.Groups[1].Value + "\n";
         }
         else {
            publicDocument += match.Groups[3].Value + "\n";   
            privateDocument += match.Groups[3].Value + "\n";
         }  
      }

      Console.WriteLine("Private Document:");
      Console.WriteLine(privateDocument);
      Console.WriteLine("Public Document:");
      Console.WriteLine(publicDocument);
   }
}
// The example displays the following output:
//    Private Document:
//    This is not for public consumption.
//    But this is for public consumption.
//    Again, this is confidential.
//    
//    Public Document:
//    But this is for public consumption.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "<PRIVATE> This is not for public consumption." + vbCrLf + _
                            "But this is for public consumption." + vbCrLf + _
                            "<PRIVATE> Again, this is confidential." + vbCrLf
      Dim pattern As String = "^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$"
      Dim publicDocument As String = Nothing
      Dim privateDocument As String = Nothing

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         If match.Groups(1).Success Then
            privateDocument += match.Groups(1).Value + vbCrLf
         Else
            publicDocument += match.Groups(3).Value + vbCrLf   
            privateDocument += match.Groups(3).Value + vbCrLf
         End If  
      Next

      Console.WriteLine("Private Document:")
      Console.WriteLine(privateDocument)
      Console.WriteLine("Public Document:")
      Console.WriteLine(publicDocument)
   End Sub
End Module
' The example displays the following output:
'    Private Document:
'    This is not for public consumption.
'    But this is for public consumption.
'    Again, this is confidential.
'    
'    Public Document:
'    But this is for public consumption.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`^` | Inicia la búsqueda de coincidencias al principio de una línea.
`(?<Pvt>\<PRIVATE\>\s)?` | Coincide con cero o una repetición de la cadena `<PRIVATE>` seguida de un carácter de espacio en blanco. Asigna la coincidencia a un grupo de capturas denominado Pvt.
`(?(Pvt)((\w+\p{P}?\s)+)` | Si existe el grupo de capturas `Pvt`, coincide con una o más repeticiones de uno o más caracteres de palabra seguidos de cero o un separador de puntuación, seguido de un carácter de espacio en blanco. Asigna la subcadena al primer grupo de capturas.
`&#124;((\w+\p{P}?\s)+))` | Si no existe el grupo de capturas `Pvt`, coincide con una o más repeticiones de uno o más caracteres de palabra seguidos de cero o un separador de puntuación, seguido de un carácter de espacio en blanco. Asigna la subcadena al tercer grupo de capturas.
`\r?$` | Coincide con el final de una línea o con el final de la cadena.
 
Para obtener más información sobre la evaluación condicional, consulte [Construcciones de alternancia en expresiones regulares](alternation.md).

### <a name="balancing-group-definitions"></a>Definiciones de grupos de compensación

Definiciones de grupos de compensación: **(?<**_nombre1-nombre2_**>** _subexpresión_**)**. Esta característica permite al motor de expresiones regulares realizar un seguimiento de construcciones anidadas como paréntesis o corchetes de apertura y cierre. Para ver un ejemplo, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

### <a name="nonbacktracking-subexpressions"></a>Subexpresiones sin retroceso

Subexpresiones sin retroceso (denominadas también subexpresiones expansivas): **(?>**_subexpresión_**)**. Esta característica permite al motor de retroceso garantizar que una subexpresión coincida solo con la primera coincidencia encontrada para dicha subexpresión, como si la expresión se ejecutara independientemente de la expresión que la contiene. Si no usa esta construcción, el retroceso en las búsquedas en la expresión más grande puede cambiar el comportamiento de una subexpresión. Por ejemplo, la expresión regular `(a+)\w` coincide con uno o más caracteres "a", junto con un carácter de palabra que sigue a la secuencia de caracteres "a", y asigna la secuencia de caracteres "a" al primer grupo de capturas. Pero si el último carácter de la cadena de entrada es también una "a", coincide con el elemento del lenguaje `\w` y no se incluye en el grupo capturado.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string backtrackingPattern = @"(a+)\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, backtrackingPattern);
         Console.WriteLine("   Pattern: {0}", backtrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: (a+)\w
//             Match: aaaaa
//             Group 1: aaaa
//       Input: aaaaab
//          Pattern: (a+)\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim backtrackingPattern As String = "(a+)\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, backtrackingPattern)
         Console.WriteLine("   Pattern: {0}", backtrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: (a+)\w
'             Match: aaaaa
'             Group 1: aaaa
'       Input: aaaaab
'          Pattern: (a+)\w
'             Match: aaaaab
'             Group 1: aaaaa
```

La expresión regular `((?>a+))\w` impide este comportamiento. Dado que todos los caracteres "a" consecutivos se buscan sin retroceso, el primer grupo de capturas incluye todos los caracteres "a" consecutivos. Si los caracteres "a" no van seguidos de al menos otro carácter que no sea "a", se produce un error de coincidencia.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string nonbacktrackingPattern = @"((?>a+))\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, nonbacktrackingPattern);
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: ((?>a+))\w
//             Match failed.
//       Input: aaaaab
//          Pattern: ((?>a+))\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim nonbacktrackingPattern As String = "((?>a+))\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, nonbacktrackingPattern)
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: ((?>a+))\w
'             Match failed.
'       Input: aaaaab
'          Pattern: ((?>a+))\w
'             Match: aaaaab
'             Group 1: aaaaa
```

Para obtener más información sobre las subexpresiones sin retroceso, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

### <a name="righttoleft-matching"></a>Búsqueda de coincidencias de derecha a izquierda

La búsqueda de coincidencias de derecha a izquierda se especifica al proporcionar la opción [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) a un constructor de clase [Regex](xref:System.Text.RegularExpressions.Regex) o a un método coincidente de instancia estática. Esta característica es útil al realizar búsquedas de derecha a izquierda en lugar de izquierda a derecha, o en los casos en los que es más eficaz iniciar una búsqueda de coincidencias en la parte derecha del patrón, en lugar de la izquierda. Como se muestra en el ejemplo siguiente, el uso de la búsqueda de coincidencias de derecha a izquierda puede cambiar el comportamiento de los cuantificadores expansivos. En el ejemplo se realizan dos búsquedas de una oración que termina con un número. La búsqueda de izquierda a derecha que usa el cuantificador expansivo `+` coincide con uno de los seis dígitos de la oración, mientras que la búsqueda de derecha a izquierda coincide con los seis dígitos. Para obtener una descripción del patrón de expresión regular, consulte el ejemplo que ilustra los cuantificadores diferidos anteriormente en esta sección.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);

      // Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (left-to-right): 5
//       Number at end of sentence (right-to-left): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (left-to-right): 5
'       Number at end of sentence (right-to-left): 107325
```

Para obtener más información sobre la búsqueda de coincidencias de derecha a izquierda, consulte [Opciones de expresiones regulares](options.md).

### <a name="positive-and-negative-lookbehind"></a>Búsqueda tardía positiva y negativa

Búsqueda tardía positiva y negativa: **(?<**=_subexpresión_**)** para la búsqueda tardía positiva y **(?<!**_subexpresión_**)** para la búsqueda tardía negativa. Esta característica es parecida a la búsqueda anticipada, que se describe anteriormente en este tema. Dado que el motor de expresiones regulares permite una búsqueda de coincidencias completa de derecha a izquierda, las expresiones regulares permiten búsquedas tardías sin restricciones. La búsqueda tardía positiva y negativa también se puede usar para evitar anidar los cuantificadores cuando la subexpresión anidada es un superconjunto de una expresión exterior. Las expresiones regulares con cuantificadores anidados suelen ofrecer un rendimiento bajo. Por ejemplo, en el ejemplo siguiente se comprueba que una cadena empieza y acaba con un carácter alfanumérico y que cualquier otro carácter de la cadena es de un subconjunto más grande. Forma una parte de la expresión regular usada para validar direcciones de correo electrónico. Para obtener más información, consulte [How to: Verify that Strings Are in Valid Email Format](verify-format.md) (Cómo comprobar si las cadenas tienen un formato de correo electrónico válido).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                          "me.myself!" };
      string pattern = @"^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$";
      foreach (string input in inputs) {
         if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
            Console.WriteLine("{0}: Valid", input);
         else
            Console.WriteLine("{0}: Invalid", input);
      }
   }
}
// The example displays the following output:
//       jack.sprat: Valid
//       dog#: Invalid
//       dog#1: Valid
//       me.myself: Valid
//       me.myself!: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                                 "me.myself!" }
      Dim pattern As String = "^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$"
      For Each input As String In inputs
         If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
            Console.WriteLine("{0}: Valid", input)
         Else
            Console.WriteLine("{0}: Invalid", input)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       jack.sprat: Valid
'       dog#: Invalid
'       dog#1: Valid
'       me.myself: Valid
'       me.myself!: Invalid
```

La expresión regular `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Empieza la búsqueda de coincidencias en el principio de la cadena.
`[A-Z0-9]` | Coincide con cualquier carácter numérico o alfanumérico. (La comparación no distingue mayúsculas de minúsculas).
`([-!#$%&'.*+/=?^`{}&#124;~\w])*` | Coincide con cero o más repeticiones de cualquier carácter de palabra o de cualquiera de los caracteres siguientes: -, !, #, $, %, &, ', ., *, +, /, =, ?, ^, `, {, }, &#124; o ~.
`(?<=[A-Z0-9])` | Realiza una búsqueda tardía en el carácter anterior, que debe ser numérico o alfanumérico. (La comparación no distingue mayúsculas de minúsculas).
`$` | Finalizar la búsqueda al final de la cadena.
 
Para obtener más información sobre la búsqueda tardía positiva y negativa, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).


## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | ----------- 
[Retroceso](backtracking.md) | Proporciona información sobre la manera en que el retroceso de expresiones regulares se bifurca para buscar coincidencias alternativas.
[Compilar y reutilizar](compilation.md) | Proporciona información sobre cómo compilar y reutilizar expresiones regulares para aumentar el rendimiento.
[Seguridad para subprocesos](thread-safety.md) | Proporciona información sobre la seguridad para subprocesos de expresiones regulares y explica cuándo se debe sincronizar el acceso a objetos de expresión regular.
[Expresiones regulares de .NET](regular-expressions.md) | Proporciona información general sobre el aspecto del lenguaje de programación de expresiones regulares.
[Modelo de objetos de expresión regular](object-model.md) | Proporciona información y ejemplos de código que muestran cómo usar las clases de expresiones regulares.
[Ejemplos de expresiones regulares](regex-examples.md) | Contiene ejemplos de código que muestran el uso de expresiones regulares en aplicaciones comunes.
[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md) | Ofrece información sobre el conjunto de caracteres, operadores y construcciones que se pueden usar para definir expresiones regulares.
 
## <a name="reference"></a>Referencia

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)




<!--HONumber=Nov16_HO1-->


