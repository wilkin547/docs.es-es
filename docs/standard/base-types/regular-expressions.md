---
title: Expresiones regulares en .NET
description: Expresiones regulares en .NET
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: e9ae9cb47955fb926507be32afb875efd3260ce3

---

# <a name="regular-expressions-in-net"></a>Expresiones regulares en .NET

Las expresiones regulares proporcionan un método eficaz y flexible para procesar texto. La notación extensiva de búsqueda de patrones coincidentes de las expresiones regulares permite analizar rápidamente grandes cantidades de texto para buscar patrones de caracteres específicos; para validar un texto con el fin de asegurar que se corresponde con un patrón predefinido (por ejemplo, una dirección de correo electrónico); para extraer, editar, reemplazar o eliminar subcadenas de texto; y para agregar las cadenas extraídas a una colección con el fin de generar un informe. Para muchas aplicaciones que usan cadenas o analizan grandes bloques de texto, las expresiones regulares son una herramienta indispensable.

## <a name="how-regular-expressions-work"></a>Funcionamiento de las expresiones regulares

El eje del procesamiento de texto mediante expresiones regulares es el motor de expresiones regulares, que viene representado por el objeto [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) en .NET. Como mínimo, el procesamiento de texto mediante expresiones regulares necesita que el motor de expresiones regulares disponga de los dos elementos de información siguientes:

* El patrón de expresión regular que se debe identificar en el texto. 
  
  En .NET, los patrones de expresiones regulares se definen mediante una sintaxis o un lenguaje especial, que es compatible con las expresiones regulares de Perl 5 y agrega algunas características adicionales, como búsquedas de coincidencias de derecha a izquierda. Para obtener más información, consulte [Lenguaje de expresiones regulares: Referencia rápida](quick-ref.md).
  
* El texto que se debe analizar para el patrón de expresión regular.

Los métodos de la clase [Regex](xref:System.Text.RegularExpressions.Regex) permiten realizar las operaciones siguientes:

* Determinar si el patrón de expresión regular se produce en el texto de entrada llamando al método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)). Para obtener un ejemplo que usa el método [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) para validar texto, consulte [Cómo comprobar si las cadenas tienen un formato de correo electrónico válido](verify-format.md).

* Recuperar una o todas las apariciones del texto que coincide con el patrón de expresión regular llamando al método [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) o [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)). El primer método devuelve un objeto [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) que proporciona información sobre el texto coincidente. El segundo método devuelve un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) que contiene un objeto [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) por cada coincidencia encontrada en el texto analizado. 

* Reemplazar el texto que coincide con el patrón de expresión regular llamando al método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)). Para obtener ejemplos en los que se usa el método [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) para cambiar los formatos de fecha y quitar los caracteres no válidos de una cadena, consulte [Cómo quitar caracteres no válidos de una cadena](strip-characters.md) y [Ejemplo de expresiones regulares: Cambio de formatos de fecha](changing-formats.md).

Para obtener información general acerca del modelo de objetos de expresiones regulares, consulte [El modelo de objetos de expresión regular](object-model.md).

Para obtener más información sobre el lenguaje de expresiones regulares, consulte [Lenguaje de expresiones regulares: Referencia rápida](quick-ref.md).

## <a name="regular-expression-examples"></a>Ejemplos de expresiones regulares

La clase [String](xref:System.String) incluye varios métodos de búsqueda y reemplazo de cadenas que puede usar cuando quiera buscar cadenas literales en una cadena mayor. Las expresiones regulares son muy útiles cuando se desea buscar una de varias subcadenas en una cadena mayor o cuando se desea identificar patrones en una cadena, como se muestra en los ejemplos siguientes. 

### <a name="example-1-replacing-substrings"></a>Ejemplo 1: reemplazar subcadenas

Suponga que una lista de distribución de correo contiene nombres que a veces incluyen un tratamiento (Sr., Sra. o Srta.) junto con un nombre y un apellido. Si no desea incluir los tratamientos al generar las etiquetas de los sobres a partir de la lista, puede usar una expresión regular para quitarlos, como se muestra en el ejemplo siguiente.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

El patrón de expresión regular `(Mr\.? |Mrs\.? |Miss |Ms\.? )` busca coincidencias con cualquier aparición de "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms " o "Ms. ". La llamada al método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) reemplaza la cadena coincidente con [String.Empty](xref:System.String.Empty); es decir, la quita de la cadena original.

### <a name="example-2-identifying-duplicated-words"></a>Ejemplo 2: identificar palabras duplicadas

Duplicar palabras accidentalmente es un error frecuente que cometen los escritores. Se puede usar una expresión regular para identificar palabras duplicadas, como se muestra en el ejemplo siguiente.

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

El patrón de expresión regular `\b(\w+?)\s\1\b` se puede interpretar de la manera siguiente:

Sintaxis | Significado
------ | -------
`\b` | Empieza en un límite de palabras.
`(\w+?)` | Coincide con uno o más caracteres de palabra, pero con el menor número de caracteres posible. Juntos, forman un grupo al que se puede hacer referencia como `\1`.
`\s` | Coincide con un carácter de espacio en blanco.
`\1` | Coincide con la subcadena que es igual al grupo denominado `\1`.
`\b` | Coincide con un límite de palabras.

El método [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) se invoca con las opciones de expresiones regulares establecidas en [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). Por tanto, la operación de coincidencia no distingue mayúsculas de minúsculas y el ejemplo identifica la subcadena "Esto esto" como una duplicación.

Observe que la cadena de entrada incluye la subcadena "this? This". Sin embargo, debido al signo de puntuación intermedio, no se identifica como una duplicación.

### <a name="example-3-dynamically-building-a-culturesensitive-regular-expression"></a>Ejemplo 3: crear dinámicamente una expresión regular dependiente de la referencia cultural

En el ejemplo siguiente se muestra la eficacia de las expresiones regulares, además de la flexibilidad que ofrecen las características de globalización de .NET. Se usa el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) para determinar el formato de los valores de divisa en la referencia cultural actual del sistema. A continuación, se usa dicha información para construir dinámicamente una expresión regular que extrae los valores de divisa del texto. Para cada coincidencia, se extrae el subgrupo que solo contiene la cadena numérica, se convierte el subgrupo en un valor [Decimal](xref:System.Decimal) y se calcula un total acumulativo. 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

En un equipo cuya referencia cultural actual sea Inglés - Estados Unidos (en-US), el ejemplo crea dinámicamente la expresión regular `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`. Este patrón de expresión regular se puede interpretar de la manera siguiente:

Sintaxis | Significado
------ | -------
`\$` | Buscar una sola aparición del símbolo de dólar ($) en la cadena de entrada. La cadena del patrón de expresión regular incluye una barra diagonal inversa para indicar que el símbolo de dólar debe interpretarse literalmente en lugar de interpretarse como un delimitador de la expresión regular. (Si solo apareciese el símbolo $, esto indicaría que el motor de expresiones regulares debe intentar comenzar su búsqueda de coincidencias al final de una cadena.) Para asegurarse de que el símbolo de divisa de la referencia cultural actual no se interpreta erróneamente como un símbolo de la expresión regular, en el ejemplo se llama al método [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) para marcar el carácter como carácter de escape.
`\s*` | Buscar cero o más apariciones de un carácter de espacio en blanco.
`[-+]?` | Buscar cero o una aparición de un signo positivo o un signo negativo.
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | Los paréntesis externos alrededor de esta expresión la definen como un grupo de captura o una subexpresión. Si se encuentra una coincidencia, la información sobre esta parte de la cadena coincidente se puede recuperar del segundo objeto [Group](xref:System.Text.RegularExpressions.Group) en el objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) devuelto por la propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups). (El primer elemento de la colección representa la coincidencia completa.)
`[0-9]{0,3}` | Buscar de cero a tres apariciones de los dígitos decimales comprendidos entre 0 y 9.
`(,[0-9]{3})*` | Buscar cero o más apariciones de un separador de grupos seguido de tres dígitos decimales.
`\.` | Buscar una única aparición del separador decimal.
`[0-9]+` | Buscar uno o más dígitos decimales.
`(\.[0-9]+)?` | Buscar cero o una aparición del separador decimal seguido de al menos un dígito decimal.

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | -----------
[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md) | Ofrece información sobre el conjunto de caracteres, operadores y construcciones que se pueden utilizar para definir expresiones regulares.
[El modelo de objetos de expresión regular](object-model.md) | Proporciona información y ejemplos de código que muestran cómo usar las clases de expresiones regulares.
[Detalles del comportamiento de expresiones regulares](regex-behavior.md) | Proporciona información sobre las características y el comportamiento de las expresiones regulares de .NET.
[Ejemplos de expresiones regulares](regex-examples.md) | Proporciona ejemplos de código que muestran los usos habituales de las expresiones regulares.


## <a name="reference"></a>Referencia

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)




<!--HONumber=Nov16_HO1-->


