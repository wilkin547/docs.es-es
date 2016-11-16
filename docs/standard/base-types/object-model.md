---
title: "El modelo de objetos de expresión regular"
description: "El modelo de objetos de expresión regular"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a1e611ec-c6a2-48c6-9c52-0ed845787621
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: e4a5237fcb439999efe4454512b06444f129e7b4

---

# <a name="the-regular-expression-object-model"></a>El modelo de objetos de expresión regular

En este tema se describe el modelo de objetos usado para trabajar con expresiones regulares de .NET. Contiene las siguientes secciones:

* [Motor de expresiones regulares](#the-regular-expression-engine)

* [Objetos MatchCollection y Match](#the-matchcollection-and-match-objects)

* [Colección de grupos](#the-group-collection)

* [Grupo capturado](#the-captured-group)

* [Colección de capturas](#the-capture-collection)

* [Captura individual](#the-individual-capture)

## <a name="the-regular-expression-engine"></a>Motor de expresiones regulares

La clase [Regex](xref:System.Text.RegularExpressions.Regex) representa el motor de expresiones regulares de .NET. El motor de expresiones regulares es responsable de analizar y compilar una expresión regular y de realizar operaciones en las que coinciden el patrón de expresión regular con una cadena de entrada. El motor es el componente central del modelo de objetos de expresión regular de .NET.

Puede utilizar el motor de expresiones regulares en una de estas dos formas:

* Mediante la llamada a los métodos estáticos de la clase [Regex](xref:System.Text.RegularExpressions.Regex). Los parámetros de método incluyen la cadena de entrada y el patrón de expresión regular. El motor de expresiones regulares almacena en memoria caché las expresiones regulares que se utilizan en llamadas de métodos estáticos, por lo que las llamadas repetidas a métodos de expresiones regulares estáticos que usan la misma expresión regular ofrecen un rendimiento relativamente bueno.

* Mediante la creación de instancias de un objeto [Regex](xref:System.Text.RegularExpressions.Regex), al pasar una expresión regular al constructor de clase. En este caso, el objeto [Regex](xref:System.Text.RegularExpressions.Regex) es inmutable (de solo lectura) y representa un motor de expresiones regulares estrechamente vinculado a una expresión regular única. Dado que las expresiones regulares usadas por instancias Regex no están almacenadas en memoria caché, no debe crear varias veces instancias de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) con la misma expresión regular.

Puede llamar a los métodos de la clase [Regex](xref:System.Text.RegularExpressions.Regex) para realizar las operaciones siguientes: 

* Determinar si una cadena coincide con un patrón de expresión regular.

* Extraer una coincidencia única o la primera coincidencia.

* Extraer todas las coincidencias.

* Reemplazar una subcadena coincidente.

* Dividir una cadena única en una matriz de cadenas.

Estas operaciones se describen en las siguientes secciones.

### <a name="matching-a-regular-expression-pattern"></a>Buscar coincidencias con un patrón de expresión regular

El método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) devuelve `true` si la cadena coincide con el patrón o `false` en caso contrario. El método [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) se usa a menudo para validar una entrada de cadena. Por ejemplo, el siguiente código garantiza que una cadena coincide con un número válido de la seguridad social en los Estados Unidos.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] values = { "111-22-3333", "111-2-3333"};
      string pattern = @"^\d{3}-\d{2}-\d{4}$";
      foreach (string value in values) {
         if (Regex.IsMatch(value, pattern))
            Console.WriteLine("{0} is a valid SSN.", value);
         else   
            Console.WriteLine("{0}: Invalid", value);
      }
   }
}
// The example displays the following output:
//       111-22-3333 is a valid SSN.
//       111-2-3333: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim values() As String = { "111-22-3333", "111-2-3333"}
      Dim pattern As String = "^\d{3}-\d{2}-\d{4}$"
      For Each value As String In values
         If Regex.IsMatch(value, pattern) Then
            Console.WriteLine("{0} is a valid SSN.", value)
         Else   
            Console.WriteLine("{0}: Invalid", value)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       111-22-3333 is a valid SSN.
'       111-2-3333: Invalid
```

El patrón de la expresión regular `^\d{3}-\d{2}-\d{4}$` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Buscar coincidencias con el principio de la cadena de entrada.
`\d{3}` | Coincide con tres dígitos decimales.
`-` | Buscar coincidencias con un guion.
`\d{2}` | Coincide con dos dígitos decimales.
`-` | Buscar coincidencias con un guion.
`\d{4}` | Buscar coincidencias con cuatro dígitos decimales.
`$` | Coincide con el final de la cadena de entrada.
 
### <a name="extracting-a-single-match-or-the-first-match"></a>Extraer una coincidencia única o la primera coincidencia

El método [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) devuelve un objeto [Match](xref:System.Text.RegularExpressions.Match) que contiene información sobre la primera subcadena que coincida con un patrón de expresión regular. Si la propiedad `Match.Success` devuelve `true` (lo que indica que se encontró una coincidencia), puede recuperar información sobre las coincidencias subsiguientes mediante una llama al método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch). Estas llamadas a métodos pueden seguir hasta que la propiedad `Match.Success` devuelva `false`. Por ejemplo, el código siguiente usa el método [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)) para buscar la primera aparición de una palabra duplicada en una cadena. Después, llama al método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) para encontrar cualquier aparición adicional. El ejemplo examina la propiedad `Match.Success` después de cada llamada de método para determinar si la coincidencia actual ha sido correcta y si debe seguir una llamada al método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      Match match = Regex.Match(input, pattern);
      while (match.Success)
      {
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
         match = match.NextMatch();
      }                       
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      Dim match As Match = Regex.Match(input, pattern)
      Do While match.Success
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
         match = match.NextMatch()
      Loop                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

El patrón de la expresión regular `\b(\w+)\W+(\1)\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Comienza la búsqueda de coincidencias en un límite de palabras.
`(\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.
`\W+` | Coincide con uno o varios caracteres que no se usan para formar palabras.
`(\1)` | Buscar coincidencias con la primera cadena capturada. Este es el segundo grupo de captura. 
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
### <a name="extracting-all-matches"></a>Extraer todas las coincidencias

El método [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) devuelve un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) que contiene información sobre todas las coincidencias que el motor de expresiones regulares encontró en la cadena de entrada. Por ejemplo, se podría escribir de nuevo el ejemplo anterior para que llamara al método [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) en lugar de a los métodos [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) y [NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
      Next                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

### <a name="replacing-a-matched-substring"></a>Reemplazar una subcadena coincidente

El método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) reemplaza cada subcadena que hace coincidir el patrón de expresión regular con una cadena o patrón de expresión regular especificados, y devuelve la cadena de entrada completa con reemplazos. Por ejemplo, el código siguiente agrega un símbolo de la divisa de EE. UU. antes de un número decimal en una cadena.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+\.\d{2}\b";
      string replacement = "$$$&"; 
      string input = "Total Cost: 103.64";
      Console.WriteLine(Regex.Replace(input, pattern, replacement));     
   }
}
// The example displays the following output:
//       Total Cost: $103.64
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+\.\d{2}\b"
      Dim replacement As String = "$$$&" 
      Dim input As String = "Total Cost: 103.64"
      Console.WriteLine(Regex.Replace(input, pattern, replacement))     
   End Sub
End Module
' The example displays the following output:
'       Total Cost: $103.64
```

El patrón de la expresión regular `\b\d+\.\d{2}\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
`\.` | Coincide con un punto.
`\d{2}` | Coincide con dos dígitos decimales.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
El patrón de reemplazo `$$$&` se interpreta como se muestra en la siguiente tabla.

Modelo | Cadena de reemplazo
------- | ------------------ 
`$$` | El carácter del signo de dólar (**$**).
`$&` | La subcadena coincidente completa.
 
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Dividir una cadena única en una matriz de cadenas

El método [Regex.Split](xref:System.Text.RegularExpressions.Regex.Split(System.String)) divide la cadena de entrada en las posiciones definidas por una coincidencia de expresión regular. Por ejemplo, el siguiente código coloca los elementos de una lista numerada en una matriz de cadena.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea";
      string pattern = @"\b\d{1,2}\.\s";
      foreach (string item in Regex.Split(input, pattern))
      {
         if (! String.IsNullOrEmpty(item))
            Console.WriteLine(item);
      }      
   }
}
// The example displays the following output:
//       Eggs
//       Bread
//       Milk
//       Coffee
//       Tea
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea"
      Dim pattern As String = "\b\d{1,2}\.\s"
      For Each item As String In Regex.Split(input, pattern)
         If Not String.IsNullOrEmpty(item) Then
            Console.WriteLine(item)
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       Eggs
'       Bread
'       Milk
'       Coffee
'       Tea
```

El patrón de la expresión regular `\b\d{1,2}\.\s` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\d{1,2}` | Buscar coincidencias con uno o dos dígitos decimales.
`\.` | Coincide con un punto.
`\s` | Coincide con un carácter de espacio en blanco.
 
## <a name="the-matchcollection-and-match-objects"></a>Objetos MatchCollection y Match

Los métodos [Regex](xref:System.Text.RegularExpressions.Regex) devuelven dos objetos que forman parte del modelo de objetos de expresión regular: el objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) y el objeto [Match](xref:System.Text.RegularExpressions.Match). 

### <a name="the-match-collection"></a>Colección de coincidencias

El método [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) devuelve un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) que contiene objetos [Match](xref:System.Text.RegularExpressions.Match) que representan todas las coincidencias que encontró el motor de expresiones regulares, en el orden en el que aparecen en la cadena de entrada. Si no hay ninguna coincidencia, el método devuelve un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) que contiene un objeto [Match](xref:System.Text.RegularExpressions.Match) sin miembros. La propiedad [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item` proporciona acceso a miembros individuales de la colección por índice, desde cero hasta uno menos que el valor de la propiedad [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count). "Item" es el indizador de la colección (en C#) y la propiedad predeterminada (en Visual Basic).

De forma predeterminada, la llamada al método [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) usa la evaluación diferida para rellenar el objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection). El acceso a propiedades que requieren una colección totalmente rellenada, como las propiedades [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count) y `Item`, puede implicar una reducción del rendimiento. En consecuencia, recomendamos acceder a la colección mediante el objeto [IEnumerator](xref:System.Collections.IEnumerator) devuelto por el método [MatchCollection.GetEnumerator](xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator). Los lenguajes individuales proporcionan construcciones, como `foreach` en C# y "For Each" en Visual Basic, que encapsulan la interfaz IEnumerator](xref:System.Collections.IEnumerator) de la colección.

En el siguiente ejemplo se usa el método [Regex.Matches(String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) para rellenar un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) con todas las coincidencias encontradas en una cadena de entrada. El ejemplo enumera la colección, copia las coincidencias en una matriz de cadena y registra las posiciones de caracteres en una matriz entera.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
       MatchCollection matches;
       List<string> results = new List<string>();
       List<int> matchposition = new List<int>();

       // Create a new Regex object and define the regular expression.
       Regex r = new Regex("abc");
       // Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd");
       // Enumerate the collection to retrieve all matches and positions.
       foreach (Match match in matches)
       {
          // Add the match string to the string array.
           results.Add(match.Value);
           // Record the character position where the match was found.
           matchposition.Add(match.Index);
       }
       // List the results.
       for (int ctr = 0; ctr < results.Count; ctr++)
         Console.WriteLine("'{0}' found at position {1}.", 
                           results[ctr], matchposition[ctr]);  
   }
}
// The example displays the following output:
//       'abc' found at position 3.
//       'abc' found at position 7.
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
       Dim matches As MatchCollection
       Dim results As New List(Of String)
       Dim matchposition As New List(Of Integer)

       ' Create a new Regex object and define the regular expression.
       Dim r As New Regex("abc")
       ' Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd")
       ' Enumerate the collection to retrieve all matches and positions.
       For Each match As Match In matches
          ' Add the match string to the string array.
           results.Add(match.Value)
           ' Record the character position where the match was found.
           matchposition.Add(match.Index)
       Next
       ' List the results.
       For ctr As Integer = 0 To results.Count - 1
         Console.WriteLine("'{0}' found at position {1}.", _
                           results(ctr), matchposition(ctr))  
       Next
   End Sub
End Module
' The example displays the following output:
'       'abc' found at position 3.
'       'abc' found at position 7.
```

### <a name="the-match"></a>La coincidencia

La clase [Match](xref:System.Text.RegularExpressions.Match) representa el resultado de una coincidencia de expresión regular única. Puede acceder a los objetos [Match](xref:System.Text.RegularExpressions.Match) de dos formas:

* Mediante su recuperación del objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) devuelto por el método Regex.Matches. Para recuperar objetos [Match](xref:System.Text.RegularExpressions.Match) individuales, itere la colección mediante una construcción `foreach` (en C#) o `For Each...Next` (en Visual Basic), o bien use la propiedad [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item` para recuperar un determinado objeto [Match](xref:System.Text.RegularExpressions.Match) por índice o por nombre. También puede recuperar objetos [Match](xref:System.Text.RegularExpressions.Match) individuales de la colección mediante la iteración de la colección por índice, desde cero hasta uno menos que el número de objetos de la colección. Pero este método no saca partido de la evaluación diferida, ya que accede a la propiedad [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count). 

  En el siguiente ejemplo se recuperan objetos [Match](xref:System.Text.RegularExpressions.Match) individuales de un objeto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) mediante la iteración de la colección con el uso de la construcción `foreach`. La expresión regular simplemente coincide con la cadena "abc" de la cadena de entrada.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        foreach (Match match in Regex.Matches(input, pattern))
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
        Next                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

* Mediante una llamada al método [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)), que devuelve un objeto [Match](xref:System.Text.RegularExpressions.Match) que representa la primera coincidencia en una cadena o una parte de una cadena. Puede determinar si la coincidencia se ha encontrado recuperando el valor de la propiedad `Match.Success`. Para recuperar objetos [Match](xref:System.Text.RegularExpressions.Match) que representan las coincidencias subsiguientes, llame repetidamente al método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch), hasta que la propiedad `Success` del objeto [Match](xref:System.Text.RegularExpressions.Match) devuelto sea `false`. 

  En el siguiente ejemplo se usan los métodos [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)) y [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) para buscar coincidencias con la cadena "abc" en la cadena de entrada.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        Match match = Regex.Match(input, pattern);
        while (match.Success)
        {
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
           match = match.NextMatch();                  
        }                     
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        Dim match As Match = Regex.Match(input, pattern)
        Do While match.Success
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
           match = match.NextMatch()                  
        Loop                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

Dos propiedades de la clase [Match](xref:System.Text.RegularExpressions.Match) devuelven objetos de colección:

* La propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) devuelve un objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) que contiene información sobre las subcadenas que coinciden con grupos de capturas en el patrón de expresión regular. 

* La propiedad `Match.Captures` devuelve un objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) que es de uso limitado. La colección no se rellena para un objeto [Match](xref:System.Text.RegularExpressions.Match) cuya propiedad `Success` es `false`. De lo contrario, contiene un único objeto [Capture](xref:System.Text.RegularExpressions.Capture) que tiene la misma información que el objeto [Match](xref:System.Text.RegularExpressions.Match). 

Para obtener más información sobre estos objetos, consulte las secciones [Colección de grupos](#the-group-collection) y [Colección de capturas](#the-capture-collection) más adelante en este tema.

Dos propiedades adicionales de la clase [Match](xref:System.Text.RegularExpressions.Match) proporcionan información sobre la coincidencia. La propiedad `Match.Value` devuelve la subcadena en la cadena de entrada que coincide con el patrón de expresión regular. La propiedad `Match.Index` devuelve la posición inicial basada en cero de la cadena coincidente en la cadena de entrada.

La clase [Match](xref:System.Text.RegularExpressions.Match) también tiene dos métodos de coincidencia de patrones:

* El método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) encuentra la coincidencia según la coincidencia representada por el objeto [Match](xref:System.Text.RegularExpressions.Match) actual y devuelve un objeto [Match](xref:System.Text.RegularExpressions.Match) que representa esa coincidencia.

* El método [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch) realiza una operación de reemplazo especificada en la cadena coincidente y devuelve el resultado. 


En el siguiente ejemplo se usa el método [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch) para anteponer un símbolo **$** y un espacio antes de cada número que incluye dos dígitos fraccionarios. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+(,\d{3})*\.\d{2}\b";
      string input = "16.32\n194.03\n1,903,672.08"; 

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Result("$$ $&"));
   }
}
// The example displays the following output:
//       $ 16.32
//       $ 194.03
//       $ 1,903,672.08
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+(,\d{3})*\.\d{2}\b"
      Dim input As String = "16.32" + vbCrLf + "194.03" + vbCrLf + "1,903,672.08" 

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Result("$$ $&"))
      Next
   End Sub
End Module
' The example displays the following output:
'       $ 16.32
'       $ 194.03
'       $ 1,903,672.08
```

El patrón de expresión regular `\b\d+(,\d{3})*\.\d{2}\b` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
`(,\d{3})*` | Buscar coincidencias con cero o más apariciones de una coma seguida de tres dígitos decimales.
`\.` | Buscar coincidencias con el carácter de separador decimal.
`\d{2} | Coincide con dos dígitos decimales.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
El patrón de reemplazo **$$ $&** indica que la subcadena coincidente debe reemplazarse por un símbolo de signo de dólar (**$**) (el patrón `$$`), un espacio y el valor de la coincidencia (el patrón `$&`).

## <a name="the-group-collection"></a>Colección de grupos

La propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) devuelve un objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) que contiene objetos [Group](xref:System.Text.RegularExpressions.Group) que representan los grupos capturados en una coincidencia única. El primer objeto [Group](xref:System.Text.RegularExpressions.Group) de la colección (en el índice 0) representa la coincidencia completa. Cada objeto que sigue representa los resultados de un grupo de captura único. 

Puede recuperar objetos [Group](xref:System.Text.RegularExpressions.Group) individuales en la colección mediante la propiedad [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)). Puede recuperar los grupos sin nombre por su posición ordinal en la colección y recuperar grupos con nombre por nombre o por posición ordinal. Las capturas sin nombre aparecen primero en la colección y se indizan de izquierda a derecha en el orden en el que aparecen en el patrón de expresión regular. Las capturas con nombre se indizan después de las capturas sin nombre, de izquierda a derecha en el orden en el que aparecen en el patrón de expresión regular. Para determinar qué grupos numerados están disponibles en la colección devuelta para un determinado método de coincidencia de expresión regular, puede llamar al método [Regex.GetGroupNumbers](xref:System.Text.RegularExpressions.Regex.GetGroupNumbers) de instancia. Para determinar qué grupos con nombre están disponibles en la colección, puede llamar al método [Regex.GetGroupNames](xref:System.Text.RegularExpressions.Regex.GetGroupNames) de instancia. Ambos métodos son especialmente útiles en rutinas de uso general que analizan las coincidencias encontradas por cualquier expresión regular. 

La propiedad [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) es el indizador de la colección en C# y la propiedad predeterminada del objeto de la colección en Visual Basic. Esto significa que se puede obtener acceso a los objetos [Group](xref:System.Text.RegularExpressions.Group) individuales por índice (o por nombre, en el caso de grupos con nombre) del modo siguiente: 

```csharp
Group group = match.Groups[ctr];
```

```vb
Dim group As Group = match.Groups(ctr)
```

En el siguiente ejemplo se define una expresión regular que usa construcciones de agrupación para capturar el mes, día y año de una fecha. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s(\d{1,2}),\s(\d{4})\b";
      string input = "Born: July 28, 1989";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
         for (int ctr = 0; ctr <  match.Groups.Count; ctr++)
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups[ctr].Value);
    }
}
// The example displays the following output:
//       Group 0: July 28, 1989
//       Group 1: July
//       Group 2: 28
//       Group 3: 1989
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s(\d{1,2}),\s(\d{4})\b"
      Dim input As String = "Born: July 28, 1989"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         For ctr As Integer = 0 To match.Groups.Count - 1
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups(ctr).Value)
         Next      
      End If   
   End Sub
End Module
' The example displays the following output:
'       Group 0: July 28, 1989
'       Group 1: July
'       Group 2: 28
'       Group 3: 1989
```

El patrón de expresión regular `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`(\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.
`\s` | Coincide con un carácter de espacio en blanco.
`(\d{1,2})` | Buscar coincidencias con uno o dos dígitos decimales. Este es el segundo grupo de captura.
`,` | Coincide con una coma.
`\s` | Coincide con un carácter de espacio en blanco.
`(\d{4})` | Buscar coincidencias con cuatro dígitos decimales. Éste es el tercer grupo de captura.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
## <a name="the-captured-group"></a>Grupo capturado

La clase [Group](xref:System.Text.RegularExpressions.Group) representa el resultado de un único grupo de capturas. La propiedad [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) del objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) devuelto por la propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) devuelve objetos [Group](xref:System.Text.RegularExpressions.Group) que representan los grupos de capturas definidos en una expresión regular. La propiedad [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) es el indizador (en C#) y la propiedad predeterminada (en Visual Basic) de la clase [Group](xref:System.Text.RegularExpressions.Group). También puede recuperar miembros individuales iterando la colección mediante la construcción `foreach`. Para obtener un ejemplo, vea la sección anterior.

En el siguiente ejemplo se utilizan construcciones de agrupación anidadas para capturar subcadenas en grupos. El patrón de expresión regular `(a(b))c` coincide con la cadena "abc". Asigna la subcadena "ab" al primer grupo de captura y la subcadena "b" al segundo grupo de captura.

```csharp
List<int> matchposition = new List<int>();
List<string> results = new List<string>();
// Define substrings abc, ab, b.
Regex r = new Regex("(a(b))c"); 
Match m = r.Match("abdabc");
for (int i = 0; m.Groups[i].Value != ""; i++) 
{
   // Add groups to string array.
   results.Add(m.Groups[i].Value); 
   // Record character position.
   matchposition.Add(m.Groups[i].Index); 
}

// Display the capture groups.
for (int ctr = 0; ctr < results.Count; ctr++)
   Console.WriteLine("{0} at position {1}", 
                     results[ctr], matchposition[ctr]);
// The example displays the following output:
//       abc at position 3
//       ab at position 3
//       b at position 4
```

```vb
Dim matchposition As New List(Of Integer)
 Dim results As New List(Of String)
 ' Define substrings abc, ab, b.
 Dim r As New Regex("(a(b))c") 
 Dim m As Match = r.Match("abdabc")
 Dim i As Integer = 0
 While Not (m.Groups(i).Value = "")    
    ' Add groups to string array.
    results.Add(m.Groups(i).Value)     
    ' Record character position. 
    matchposition.Add(m.Groups(i).Index) 
     i += 1
 End While

 ' Display the capture groups.
 For ctr As Integer = 0 to results.Count - 1
    Console.WriteLine("{0} at position {1}", _ 
                      results(ctr), matchposition(ctr))
 Next                     
' The example displays the following output:
'       abc at position 3
'       ab at position 3
'       b at position 4
```

En el siguiente ejemplo se utilizan construcciones de agrupación con nombre para capturar subcadenas de una cadena que contiene datos en el formato "NOMBREDATOS:VALOR" que la expresión regular divide por el signo de dos puntos (:).

```csharp
Regex r = new Regex("^(?<name>\\w+):(?<value>\\w+)");
Match m = r.Match("Section1:119900");
Console.WriteLine(m.Groups["name"].Value);
Console.WriteLine(m.Groups["value"].Value);
// The example displays the following output:
//       Section1
//       119900
```

```vb
Dim r As New Regex("^(?<name>\w+):(?<value>\w+)")
Dim m As Match = r.Match("Section1:119900")
Console.WriteLine(m.Groups("name").Value)
Console.WriteLine(m.Groups("value").Value)
' The example displays the following output:
'       Section1
'       119900
```

El patrón de expresión regular `^(?<name>\w+):(?<value>\w+)` se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`^` | Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.
`(?<name>\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. El nombre de este grupo de capturas es name.
`:` | Buscar coincidencia con un signo de dos puntos.
`(?<value>\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. El nombre de este grupo de capturas es value.
 
Las propiedades de la clase [Group](xref:System.Text.RegularExpressions.Group) proporcionan información sobre el grupo capturado: la propiedad `Group.Value` contiene la subcadena capturada, la propiedad `Group.Index` indica la posición inicial del grupo capturado en el texto de entrada, la propiedad `Group.Length` contiene la longitud del texto capturado y la propiedad `Group.Success` indica si una subcadena coincidió con el patrón definido por el grupo de captura.

Al aplicar cuantificadores a un grupo (para obtener más información, consulte [Cuantificadores en expresiones regulares](quantifiers.md)), se modifica la relación de una captura por grupo de captura de dos maneras:

* Si el cuantificador __*__ o __*?__ (que especifica cero o más coincidencias) se aplica a un grupo, es posible que un grupo de captura no tenga una coincidencia en la cadena de entrada. Cuando no haya texto capturado, las propiedades del objeto [Group](xref:System.Text.RegularExpressions.Group) se establecen como se muestra en la siguiente tabla.

  Propiedades de grupo | Valor
  -------------- | ----- 
  `Success` | `false`
  `Value` | [String.Empty](xref:System.String.Empty) 
  `Length` | 0
 
  Esto se muestra en el ejemplo siguiente. En el patrón de expresión regular `aaa(bbb)*ccc`, se pueden buscar coincidencias para el primer grupo de captura (la subcadena "bbb") cero o varias veces. Dado que la cadena de entrada "aaaccc" coincide con el patrón, el grupo de captura no tiene una coincidencia.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "aaa(bbb)*ccc";
        string input = "aaaccc";
        Match match = Regex.Match(input, pattern);
        Console.WriteLine("Match value: {0}", match.Value);
        if (match.Groups[1].Success)
           Console.WriteLine("Group 1 value: {0}", match.Groups[1].Value);
        else
           Console.WriteLine("The first capturing group has no match.");
     }
  }
  // The example displays the following output:
  //       Match value: aaaccc
  //       The first capturing group has no match.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "aaa(bbb)*ccc"
        Dim input As String = "aaaccc"
        Dim match As Match = Regex.Match(input, pattern)
        Console.WriteLine("Match value: {0}", match.Value)
        If match.Groups(1).Success Then
           Console.WriteLine("Group 1 value: {0}", match.Groups(1).Value)
        Else
           Console.WriteLine("The first capturing group has no match.")
       End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match value: aaaccc
  '       The first capturing group has no match.
  ```

* Los cuantificadores pueden coincidir con varias apariciones de un patrón definido por un grupo de captura. En este caso, las propiedades `Value` y `Length` de un objeto [Group](xref:System.Text.RegularExpressions.Group) solo contienen información sobre la última subcadena capturada. Por ejemplo, la siguiente coincidencia de expresión regular coincide con una frase única que finaliza con un punto. Utiliza dos construcciones de agrupación: el primero captura palabras individuales junto con un carácter de espacio en blanco; el segundo captura palabras individuales. Como lo muestra el resultado del ejemplo, aunque la expresión regular logre capturar una frase completa, el segundo grupo de captura solo captura la última palabra.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = @"\b((\w+)\s?)+\.";
        string input = "This is a sentence. This is another sentence.";
        Match match = Regex.Match(input, pattern);
        if (match.Success)
        {
           Console.WriteLine("Match: " + match.Value);
           Console.WriteLine("Group 2: " + match.Groups[2].Value);
        }   
     }
  }
  // The example displays the following output:
  //       Match: This is a sentence.
  //       Group 2: sentence
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "\b((\w+)\s?)+\."
        Dim input As String = "This is a sentence. This is another sentence."
        Dim match As Match = Regex.Match(input, pattern)
        If match.Success Then
           Console.WriteLine("Match: " + match.Value)
           Console.WriteLine("Group 2: " + match.Groups(2).Value)
        End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match: This is a sentence.
  '       Group 2: sentence
  ```

## <a name="the-capture-collection"></a>Colección de capturas

El objeto [Group](xref:System.Text.RegularExpressions.Group) solo contiene información sobre la última captura. Pero el conjunto completo de capturas realizadas por un grupo de captura sigue aún disponible en el objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) devuelto por la propiedad [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures). Cada miembro de la colección es un objeto [Capture](xref:System.Text.RegularExpressions.Capture) que representa una captura realizada por este grupo de captura, en el orden en el que se capturaron (y, por consiguiente, en el orden en el que las cadenas capturadas coincidían de izquierda a derecha en la cadena de entrada). Puede recuperar objetos [Capture](xref:System.Text.RegularExpressions.Capture) individuales de la colección de estas dos formas: 

* Mediante la iteración de la colección con el uso de una construcción como `foreach` (en C#) o `For Each` (en Visual Basic).

* Mediante el uso de la propiedad [CaptureCollection.Item](xref:System.Text.RegularExpressions.CaptureCollection.Item(System.Int32)) para recuperar un objeto específico por índice. La propiedad Item es la propiedad predeterminada del objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) (en Visual Basic) o el indizador (en C#).


Si no se aplica un cuantificador a un grupo de captura, el objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) contiene un objeto [Capture](xref:System.Text.RegularExpressions.Capture) único que es de escaso interés, ya que proporciona información sobre la misma coincidencia que su objeto [Group](xref:System.Text.RegularExpressions.Group). Si se aplica un cuantificador a un grupo de captura, el objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) contiene todas las capturas realizadas por el grupo de captura, y el último miembro de la colección representa la misma captura que el objeto [Group](xref:System.Text.RegularExpressions.Group). 

Por ejemplo, si usa el patrón de expresión regular `((a(b))c)+` (donde el cuantificador `+` indica una o varias coincidencias) para capturar coincidencias de la cadena "abcabcabc", el objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) para cada objeto [Group](xref:System.Text.RegularExpressions.Group) contiene tres miembros.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "((a(b))c)+";
      string input = "abcabcabc";

      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Match: '{0}' at position {1}",  
                           match.Value, match.Index);
         GroupCollection groups = match.Groups;
         for (int ctr = 0; ctr < groups.Count; ctr++) {
            Console.WriteLine("   Group {0}: '{1}' at position {2}", 
                              ctr, groups[ctr].Value, groups[ctr].Index);
            CaptureCollection captures = groups[ctr].Captures;
            for (int ctr2 = 0; ctr2 < captures.Count; ctr2++) {
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", 
                                 ctr2, captures[ctr2].Value, captures[ctr2].Index);
            }                     
         }
      }
   }
}
// The example displays the following output:
//       Match: 'abcabcabc' at position 0
//          Group 0: 'abcabcabc' at position 0
//             Capture 0: 'abcabcabc' at position 0
//          Group 1: 'abc' at position 6
//             Capture 0: 'abc' at position 0
//             Capture 1: 'abc' at position 3
//             Capture 2: 'abc' at position 6
//          Group 2: 'ab' at position 6
//             Capture 0: 'ab' at position 0
//             Capture 1: 'ab' at position 3
//             Capture 2: 'ab' at position 6
//          Group 3: 'b' at position 7
//             Capture 0: 'b' at position 1
//             Capture 1: 'b' at position 4
//             Capture 2: 'b' at position 7
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example dosplays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

En el siguiente ejemplo se utiliza la expresión regular `(Abc)+` para buscar una o más ejecuciones consecutivas de la cadena "Abc" en la cadena "XYZAbcAbcAbcXYZAbcAb". El ejemplo ilustra la forma en que se usa la propiedad [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) para que devuelva varios grupos de subcadenas capturadas.

```csharp
{
   int counter;
   Match m;
   CaptureCollection cc;
   GroupCollection gc;

   // Look for groupings of "Abc".
   Regex r = new Regex("(Abc)+"); 
   // Define the string to search.
   m = r.Match("XYZAbcAbcAbcXYZAbcAb"); 
   gc = m.Groups;

   // Display the number of groups.
   Console.WriteLine("Captured groups = " + gc.Count.ToString());

   // Loop through each group.
   for (int i=0; i < gc.Count; i++) 
   {
      cc = gc[i].Captures;
      counter = cc.Count;

      // Display the number of captures in this group.
      Console.WriteLine("Captures count = " + counter.ToString());

      // Loop through each capture in the group.
      for (int ii = 0; ii < counter; ii++) 
      {
         // Display the capture and its position.
         Console.WriteLine(cc[ii] + "   Starts at character " + 
              cc[ii].Index);
      }
   }
}
// The example displays the following output:
//       Captured groups = 2
//       Captures count = 1
//       AbcAbcAbc   Starts at character 3
//       Captures count = 3
//       Abc   Starts at character 3
//       Abc   Starts at character 6
//       Abc   Starts at character 9  
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

## <a name="the-individual-capture"></a>Captura individual

La clase [Capture](xref:System.Text.RegularExpressions.Capture) contiene el resultado de una única captura de subexpresiones. La propiedad [Capture.Value](xref:System.Text.RegularExpressions.Capture.Value) contiene el texto coincidente y la propiedad [Capture.Index](xref:System.Text.RegularExpressions.Capture.Index) indica la posición basada en cero en la cadena de entrada en la que comienza la subcadena coincidente. 

En el siguiente ejemplo se analiza una cadena de entrada para la temperatura de las ciudades seleccionadas. Se utiliza una coma (",") para separar una ciudad y su temperatura, y un punto y coma (";"), para separar los datos de cada ciudad. La cadena de entrada completa representa una coincidencia única. En el patrón de expresión regular `((\w+(\s\w+)*),(\d+);)+`, que se utiliza para analizar la cadena, se asigna el nombre de la ciudad al segundo grupo de captura y la temperatura al cuarto grupo de captura.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;"; 
      string pattern = @"((\w+(\s\w+)*),(\d+);)+";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Current temperatures:");
         for (int ctr = 0; ctr < match.Groups[2].Captures.Count; ctr++)
            Console.WriteLine("{0,-20} {1,3}", match.Groups[2].Captures[ctr].Value, 
                              match.Groups[4].Captures[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Current temperatures:
//       Miami                 78
//       Chicago               62
//       New York              67
//       San Francisco         59
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;" 
      Dim pattern As String = "((\w+(\s\w+)*),(\d+);)+"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Current temperatures:")
         For ctr As Integer = 0 To match.Groups(2).Captures.Count - 1
            Console.WriteLine("{0,-20} {1,3}", match.Groups(2).Captures(ctr).Value, _
                              match.Groups(4).Captures(ctr).Value)
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Current temperatures:
'       Miami                 78
'       Chicago               62
'       New York              67
'       San Francisco         59
```

La expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\w+` | Buscar coincidencias con uno o más caracteres alfabéticos.
`(\s\w+)*` | Coincide con cero o más apariciones de un carácter de espacio en blanco seguido de uno o varios caracteres que se usan para formar palabras. Este patrón busca coincidencias con nombres de ciudades de múltiples palabras. Éste es el tercer grupo de captura.
`(\w+(\s\w+)*)` | Coincide con uno o varios caracteres que se usan para formar palabras seguidos de cero o más apariciones de un carácter de espacio en blanco seguidos de uno o varios caracteres que se usan para formar palabras. Este es el segundo grupo de captura.
`,` | Coincide con una coma.
`(\d+)` | Buscar coincidencias con uno o más dígitos. Este es el cuarto grupo de captura.
`;` | Buscar coincidencias con un signo de punto y coma.
`((\w+(\s\w+)*),(\d+);)+` | Buscar coincidencias con el patrón de una palabra seguido de cualquier palabra adicional seguida de una coma, uno o más dígitos y un punto y coma, una o más veces. Este es el primer grupo de captura. 
 
## <a name="see-also"></a>Vea también

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[Expresiones regulares de .NET](regular-expressions.md)

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)




<!--HONumber=Nov16_HO1-->


