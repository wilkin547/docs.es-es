---
title: Cuantificadores en expresiones regulares
description: Cuantificadores en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8e5124c4-20b5-4c57-ab68-301d1d7311c4
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cd47cc351fb926bcf444bdcbd12f3cd61d9fb327
ms.lasthandoff: 03/02/2017

---

# <a name="quantifiers-in-regular-expressions"></a>Cuantificadores en expresiones regulares

Los cuantificadores especifican cuántas instancias de un carácter, grupo o clase de caracteres deben estar presentes en la entrada para que se encuentre una coincidencia. En la tabla siguiente se indican los cuantificadores compatibles con .NET.

Cuantificador expansivo | Cuantificador diferido | Descripción
----------------- | --------------- | ----------- 
**\*** | **\*?** | Coincide cero o más veces.
**+** | **+?** | Coincide una o más veces.
**?** | **??** | Coincide cero o una vez.
**{**_n_**}** | **{**_n_**}?** | Coincide exactamente n veces.
**{**_n_**,}** | **{**_n_**,}?** | Coincide al menos n veces.
**{**_n_**,**_m_**}** | **{**_n_**,**_m_**}?** | Coincide de n a m veces.
 
Las cantidades *n* y *m* son constantes de tipo entero. Normalmente, los cuantificadores son expansivos, ya que hacen que el motor de expresiones regulares busque el mayor número posible de repeticiones de patrones concretos. Si se anexa el carácter `?` a un cuantificador se convierte en diferido, ya que hace que el motor de expresiones regulares busque el menor número posible de repeticiones. Para obtener una descripción completa de la diferencia entre los cuantificadores expansivos y diferidos, consulte la sección [Cuantificadores expansivos y diferidos](#greedy-and-lazy-quantifiers) más adelante en este tema.

> [!IMPORTANT]
> El anidamiento de cuantificadores (por ejemplo, como hace el patrón de expresión regular `(a*)*`) puede aumentar el número de comparaciones que debe realizar el motor de expresiones regulares, como una función exponencial del número de caracteres de la cadena de entrada. Para obtener más información sobre este comportamiento y sus soluciones alternativas, consulte [Retroceso en expresiones regulares](backtracking.md).

## <a name="regular-expression-quantifiers"></a>Cuantificadores de expresiones regulares

En las secciones siguientes se enumeran los cuantificadores admitidos en expresiones regulares de .NET. 

> [!NOTE]
> Si los caracteres \*, +, ?, { y } se encuentran en un patrón de expresión regular, el motor de expresiones regulares los interpreta como cuantificadores o como parte de construcciones de cuantificador, a menos que se incluyan en una [clase de caracteres](classes.md). Para interpretarlos como caracteres literales fuera de una clase de caracteres, debe anteponerles una barra diagonal inversa para indicar su secuencia de escape. Por ejemplo, la cadena `\*` en un patrón de expresión regular se interpreta como un carácter de asterisco literal ("*").

### <a name="match-zero-or-more-times-"></a>Coincidir cero o más veces: \*

El cuantificador \* coincide con el elemento anterior cero o más veces. Equivale al cuantificador **{0,}**. **\*** es un cuantificador expansivo cuyo equivalente diferido es **\*?**.

En el ejemplo siguiente se muestra esta expresión regular. De los nueve dígitos de la cadena de entrada, cinco coinciden con el patrón y cuatro (`95`, `929`, `9129` y `9919`) no coinciden.

```csharp
string pattern = @"\b91*9*\b";   
string input = "99 95 919 929 9119 9219 999 9919 91119";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       '99' found at position 0.
//       '919' found at position 6.
//       '9119' found at position 14.
//       '999' found at position 24.
//       '91119' found at position 33.
```

```vb
Dim pattern As String = "\b91*9*\b"   
Dim input As String = "99 95 919 929 9119 9219 999 9919 91119"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '99' found at position 0.
'       '919' found at position 6.
'       '9119' found at position 14.
'       '999' found at position 24.
'       '91119' found at position 33.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`91*` | Coincide con un "9" seguido de cero o más caracteres "1".
`9*` | Coincide con cero o más caracteres "9".
`\b` | Finaliza en un límite de palabras.
 
### <a name="match-one-or-more-times-"></a>Coincidir una o más veces: +

El cuantificador **+** coincide con el elemento anterior una o más veces. Equivale a **{1,}**. **+** es un cuantificador expansivo cuyo equivalente diferido es **+?**.

Por ejemplo, la expresión regular `\ban+\w*?\b` intenta coincidir con palabras completas que empiezan por la letra `a` seguida de una o más instancias de la letra `n`. En el ejemplo siguiente se muestra esta expresión regular. La expresión regular coincide con las palabras `an`, `annual`, `announcement` y `antique`, y no coincide con `autumn` y `all`.

```csharp
string pattern = @"\ban+\w*?\b";

string input = "Autumn is a great time for an annual announcement to all antique collectors.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       'an' found at position 27.
//       'annual' found at position 30.
//       'announcement' found at position 37.
//       'antique' found at position 57.      
```

```vb
Dim pattern As String = "\ban+\w*?\b"

Dim input As String = "Autumn is a great time for an annual announcement to all antique collectors."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next   
' The example displays the following output:   
'       'an' found at position 27.
'       'annual' found at position 30.
'       'announcement' found at position 37.
'       'antique' found at position 57. 
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`an+` | Coincide con una "a" seguida de uno o más caracteres "n". 
`\w*?` | Coincide con un carácter de palabra cero o más veces, pero el menor número de veces que sea posible.
`\b` | Finaliza en un límite de palabras.
 
### <a name="match-zero-or-one-time-"></a>Coincidir cero o una vez: ?

El cuantificador **?** coincide con el elemento anterior cero o una vez. Equivale a **{0,1,}**. **?** es un cuantificador expansivo cuyo equivalente diferido es **??**.

Por ejemplo, la expresión regular `\ban?\b` intenta coincidir con palabras completas que empiezan por la letra `a` seguida de cero o una instancia de la letra `n`. En otras palabras, intenta coincidir con las palabras `a` y `an`. En el ejemplo siguiente se muestra esta expresión regular.

```csharp
string pattern = @"\ban?\b";
string input = "An amiable animal with a large snount and an animated nose.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//        'An' found at position 0.
//        'a' found at position 23.
//        'an' found at position 42.
```

```vb
Dim pattern As String = "\ban?\b"
Dim input As String = "An amiable animal with a large snount and an animated nose."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next  
' The example displays the following output:   
'       'An' found at position 0.
'       'a' found at position 23.
'       'an' found at position 42.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`an?` | Coincide con una "a" seguida de cero o un carácter "n". 
`\b` | Finaliza en un límite de palabras.
 
### <a name="match-exactly-n-times-n"></a>Coincidir exactamente n veces: {n}

El cuantificador **{**_n_**}** coincide con el elemento anterior exactamente *n* veces, donde *n* es un entero. **{**_n_**}** es un cuantificador expansivo cuyo equivalente diferido es **{**_n_**}?**.

Por ejemplo, la expresión regular `\b\d+\,\d{3}\b` intenta coincidir con un límite de palabra seguido de uno o más dígitos decimales, seguidos de tres dígitos decimales, seguidos de un límite de palabra. En el ejemplo siguiente se muestra esta expresión regular. 

```csharp
string pattern = @"\b\d+\,\d{3}\b";
string input = "Sales totaled 103,524 million in January, " + 
                      "106,971 million in February, but only " + 
                      "943 million in March.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:   
//        '103,524' found at position 14.
//        '106,971' found at position 45.
```

```vb
Dim pattern As String = "\b\d+\,\d{3}\b"
Dim input As String = "Sales totaled 103,524 million in January, " + _
                      "106,971 million in February, but only " + _
                      "943 million in March."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '103,524' found at position 14.
'       '106,971' found at position 45.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`\d+` | Buscar coincidencias con uno o más dígitos decimales. 
`\,` | Coincide con un carácter de coma.
`\d{3}` | Coincide con tres dígitos decimales.
`\b` | Finaliza en un límite de palabras.
 
### <a name="match-at-least-n-times-n"></a>Coincidir al menos n veces: {n,}

El cuantificador **{**_n_**,}** coincide con el elemento anterior al menos *n* veces, donde *n* es un entero. **{**_n_**,}** es un cuantificador expansivo cuyo equivalente diferido es **{**_n_**}?**.

Por ejemplo, la expresión regular `\b\d{2,}\b\D+` intenta coincidir con un límite de palabra seguido de por lo menos dos dígitos, seguidos de un límite de palabra y de un carácter que no sea un dígito. En el ejemplo siguiente se muestra esta expresión regular. La expresión regular no coincide con la frase "7 days" porque solo contiene un dígito decimal, pero coincide correctamente con las frases "10 weeks and 300 years".

```csharp
string pattern = @"\b\d{2,}\b\D+";   
string input = "7 days, 10 weeks, 300 years";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '10 weeks, ' found at position 8.
// 
``` 

```vb
Dim pattern As String = "\b\d{2,}\b\D+"  
 Dim input As String = "7 days, 10 weeks, 300 years"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '10 weeks, ' found at position 8.
'       '300 years' found at position 18.
      '300 years' found at position 18.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`\d{2,}` | Coincide con al menos dos dígitos decimales. 
`\b` | Coincide con un límite de palabras.
`\D+` | Coincide con al menos un carácter de dígito no decimal.
 
### <a name="match-between-n-and-m-times-nm"></a>Coincidir de n a m veces: {n,m}

El cuantificador **{**_n_**,**_m_**}** coincide con el elemento anterior al menos *n* veces, pero no más de *m* veces, donde *n* y *m* son enteros. **{**_n_**,**_m_**}** es un cuantificador expansivo cuyo equivalente diferido es **{**_n_**,**_m_**}?**.

En el ejemplo siguiente, la expresión regular `(00\s){2,4}` intenta coincidir con dos ceros seguidos de un espacio que se repitan de dos a cuatro veces. Observe que la parte final de la cadena de entrada incluye este patrón cinco veces en lugar del máximo de cuatro. Pero solo la parte inicial de esta subcadena (hasta el espacio y el quinto par de ceros) coincide con el patrón de la expresión regular.

```csharp
string pattern = @"(00\s){2,4}";
string input = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '00 00 ' found at position 8.
//        '00 00 00 ' found at position 23.
//        '00 00 00 00 ' found at position 35.
```

```vb
Dim pattern As String = "(00\s){2,4}"
Dim input As String = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '00 00 ' found at position 8.
'       '00 00 00 ' found at position 23.
'       '00 00 00 00 ' found at position 35.
```

### <a name="match-zero-or-more-times-lazy-match-"></a>Coincidir cero o más veces (coincidencia diferida): \*?

El cuantificador **\*?** coincide con el elemento anterior cero o más veces, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo **\***.

En el ejemplo siguiente, la expresión regular `\b\w*?oo\w*?\b` coincide con todas las palabras que contienen la cadena `oo`. 

```csharp
 string pattern = @"\b\w*?oo\w*?\b";
 string input = "woof root root rob oof woo woe";
 foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

 //  The example displays the following output:
//        'woof' found at position 0.
//        'root' found at position 5.
//        'root' found at position 10.
//        'oof' found at position 19.
//        'woo' found at position 23.
```

```vb
Dim pattern As String = "\b\w*?oo\w*?\b"
 Dim input As String = "woof root root rob oof woo woe"
 For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
 Next 
 ' The example displays the following output:
'       'woof' found at position 0.
'       'root' found at position 5.
'       'root' found at position 10.
'       'oof' found at position 19.
'       'woo' found at position 23.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Empieza en un límite de palabras.
`\w*?` | Coincide con cero o más caracteres de palabra, pero con el menor número de caracteres posible. 
`oo` | Coincide con la cadena "oo".
`\w*?` | Coincide con cero o más caracteres de palabra, pero con el menor número de caracteres posible.
`\b` | Finaliza en un límite de palabras.
 
### <a name="match-one-or-more-times-lazy-match-"></a>Coincidir una o más veces (coincidencia diferida): +?

El cuantificador **+?** coincide con el elemento anterior una o más veces, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo **+**.

Por ejemplo, la expresión regular `\b\w+?\b` coincide con uno o más caracteres separados por límites de palabra. En el ejemplo siguiente se muestra esta expresión regular.

```csharp
string pattern = @"\b\w+?\b";
string input = "Aa Bb Cc Dd Ee Ff";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Aa' found at position 0.
//        'Bb' found at position 3.
//        'Cc' found at position 6.
//        'Dd' found at position 9.
//        'Ee' found at position 12.
//        'Ff' found at position 15.
```

```vb
Dim pattern As String = "\b\w+?\b"
 Dim input As String = "Aa Bb Cc Dd Ee Ff"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Aa' found at position 0.
'       'Bb' found at position 3.
'       'Cc' found at position 6.
'       'Dd' found at position 9.
'       'Ee' found at position 12.
'       'Ff' found at position 15.
```

### <a name="match-zero-or-one-time-lazy-match-"></a>Coincidir cero o una vez (coincidencia diferida): ??

El cuantificador **??** coincide con el elemento anterior cero o una vez, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo **?**.

Por ejemplo, la expresión regular `^\s*(System.)??Console.Write(Line)??\(??` intenta coincidir con las cadenas "Console.Write" o "Console.WriteLine". La cadena también puede incluir "System." antes de "Console", y puede ir seguida de un paréntesis de apertura. La cadena debe estar al principio de una línea, aunque puede ir precedida de un espacio en blanco. En el ejemplo siguiente se muestra esta expresión regular.

```csharp
string pattern = @"^\s*(System.)??Console.Write(Line)??\(??";
string input = "System.Console.WriteLine(\"Hello!\")\n" + 
                      "Console.Write(\"Hello!\")\n" + 
                      "Console.WriteLine(\"Hello!\")\n" + 
                      "Console.ReadLine()\n" + 
                      "   Console.WriteLine";
foreach (Match match in Regex.Matches(input, pattern, 
                                      RegexOptions.IgnorePatternWhitespace | 
                                      RegexOptions.IgnoreCase | 
                                      RegexOptions.Multiline))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'System.Console.Write' found at position 0.
//        'Console.Write' found at position 36.
//        'Console.Write' found at position 61.
//        '   Console.Write' found at position 110.
```

```vb
Dim pattern As String = "^\s*(System.)??Console.Write(Line)??\(??"
Dim input As String = "System.Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.Write(""Hello!"")" + vbCrLf + _
                      "Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.ReadLine()" + vbCrLf + _
                      "   Console.WriteLine"
For Each match As Match In Regex.Matches(input, pattern, _
                                         RegexOptions.IgnorePatternWhitespace Or RegexOptions.IgnoreCase Or RegexOptions.MultiLine)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'System.Console.Write' found at position 0.
'       'Console.Write' found at position 36.
'       'Console.Write' found at position 61.
'       '   Console.Write' found at position 110.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Coincide con el inicio del flujo de entrada.
`\s*` | Busca coincidencias con cero o más caracteres de espacio en blanco.
`(System.)??` | Coincide con cero o una repetición de la cadena "System.".
`Console.Write` | Coincide con la cadena "Console.Write".
`(Line)??` | Coincide con cero o una repetición de la cadena "Line".
`\(??` | Coincide con cero o con una repetición del paréntesis de apertura.
 
### <a name="match-exactly-n-times-lazy-match-n"></a>Coincidir exactamente n veces (coincidencia diferida): {n}?

El cuantificador **{**_n_**}?** coincide con el elemento anterior exactamente *n* veces, donde *n* es un entero. Es el equivalente diferido del cuantificador expansivo **{**_n_**}+**.

En el ejemplo siguiente, la expresión regular `\b(\w{3,}?\.){2}?\w{3,}?\b` se usa para identificar la dirección de un sitio web. Observe que coincide con "www.microsoft.com" y con "msdn.microsoft.com", pero no coincide con "mywebsite" ni con "mycompany.com".

```csharp
string pattern = @"\b(\w{3,}?\.){2}?\w{3,}?\b";
string input = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'www.microsoft.com' found at position 0.
//        'msdn.microsoft.com' found at position 18.
```

```vb
Dim pattern As String = "\b(\w{3,}?\.){2}?\w{3,}?\b"
 Dim input As String = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:
'       'www.microsoft.com' found at position 0.
'       'msdn.microsoft.com' found at position 18.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`(\w{3,}?\.)` | Coincide con al menos 3 caracteres de palabra, pero con el menor número de caracteres posible, seguidos de un carácter de punto. Este es el primer grupo de captura.
`(\w{3,}?\.){2}?` | Coincide con el patrón del primer grupo dos veces, pero el menor número de veces posible.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
### <a name="match-at-least-n-times-lazy-match-n"></a>Coincidir al menos n veces (coincidencia diferida): {n,}?

El cuantificador **{**_n_**,}?** coincide con el elemento anterior al menos *n* veces, donde *n* es un entero, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo **{**_n_**,}**.

Consulte el ejemplo del cuantificador **{**_n_**}?** en la sección anterior para obtener más detalles. La expresión regular de ese ejemplo usa el cuantificador **{**_n_**,}** para coincidir con una cadena que tenga al menos tres caracteres seguidos de un punto.

### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Coincidir de n a m veces (coincidencia diferida): {n,m}?

El cuantificador **{**_n_**,**_m_**}?** coincide con el elemento anterior de *n* a *m* veces, donde *n* y *m* son enteros, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo **{**_n_**,**_m_**}**.

En el ejemplo siguiente, la expresión regular `\b[A-Z](\w*\s+){1,10}?[.!?]` coincide con las frases que contengan de una a diez palabras. Coincidencia con todas las frases de la cadena de entrada, excepto con una frase que contiene 18 palabras.

```csharp
string pattern = @"\b[A-Z](\w*?\s*?){1,10}[.!?]";
string input = "Hi. I am writing a short note. Its purpose is " + 
                      "to test a regular expression that attempts to find " + 
                      "sentences with ten or fewer words. Most sentences " + 
                      "in this note are short.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Hi.' found at position 0.
//        'I am writing a short note.' found at position 4.
//        'Most sentences in this note are short.' found at position 132.
```

```vb
Dim pattern As String = "\b[A-Z](\w*\s?){1,10}?[.!?]"
Dim input As String = "Hi. I am writing a short note. Its purpose is " + _
                      "to test a regular expression that attempts to find " + _
                      "sentences with ten or fewer words. Most sentences " + _
                      "in this note are short."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Hi.' found at position 0.
'       'I am writing a short note.' found at position 4.
'       'Most sentences in this note are short.' found at position 132.
```

El patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Empieza en un límite de palabras.
`[A-Z]` | Coincide con cualquier letra mayúscula de la A a la Z.
`(\w*\s+)` | Coincide con cero o más caracteres de palabra, seguidos de uno o más caracteres de espacio en blanco. Este es el primer grupo de capturas.
`{1,10}?` | Coincide con el patrón anterior entre una y diez veces, pero el menor número de veces que sea posible.
`[.!?]` | Coincide con cualquiera de los caracteres de puntuación ".", "!" o "?".
 
## <a name="greedy-and-lazy-quantifiers"></a>Cuantificadores expansivos y diferidos

Varios cuantificadores tienen dos versiones: 

* Una versión expansiva. 

  Un cuantificador expansivo intenta coincidir con un elemento tantas veces como sea posible. 


* •Una versión no expansiva (o diferida). 

 Un cuantificador no expansivo intenta coincidir con un elemento el menor número de veces que sea posible. Para convertir un cuantificador expansivo en un cuantificador diferido, simplemente agregue el signo **?**.

Considere una expresión regular simple diseñada para extraer los cuatro últimos dígitos de una cadena de números, como un número de tarjeta de crédito. La versión de la expresión regular que usa el cuantificador expansivo **\*** es `\b.*([0-9]{4})\b`. Pero si una cadena contiene dos números, esta expresión regular coincide con los cuatro últimos dígitos del segundo número, como se muestra en el ejemplo siguiente.

```csharp
string greedyPattern = @"\b.*([0-9]{4})\b";
string input1 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input1, greedyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******1999.
```

```vb
Dim greedyPattern As String = "\b.*([0-9]{4})\b"
Dim input1 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input1, greedypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next
' The example displays the following output:
'       Account ending in ******1999.
```

La expresión regular no coincide con el primer número porque el cuantificador **\*** intenta coincidir con el elemento anterior tantas veces como sea posible en toda la cadena y, por tanto, encuentra una coincidencia al final de la cadena.

Este no es el comportamiento deseado. En su lugar, puede usar el cuantificador diferido **\*?** para extraer los dígitos de ambos números, tal como se muestra en el ejemplo siguiente.

```csharp
string lazyPattern = @"\b.*?([0-9]{4})\b";
string input2 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input2, lazyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******3333.
//       Account ending in ******1999.
```

```vb
Dim lazyPattern As String = "\b.*?([0-9]{4})\b"
Dim input2 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input2, lazypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next     
' The example displays the following output:
'       Account ending in ******3333.
'       Account ending in ******1999.
```

En la mayoría de los casos, las expresiones regulares con cuantificadores expansivos y diferidos devuelven las mismas coincidencias. Suelen devolver resultados diferentes cuando se usan con el metacarácter comodín (**.**), que coincide con cualquier carácter. 

## <a name="quantifiers-and-empty-matches"></a>Cuantificadores y coincidencias vacías

Los cuantificadores **\***, **+** y **{**_n_**,**_m_**}** y sus equivalentes diferidos nunca se repiten tras una coincidencia vacía cuando no se ha encontrado el número mínimo de capturas. Esta regla impide que los cuantificadores entren en bucles infinitos en coincidencias de subexpresiones vacías cuando el número máximo de posibles capturas de grupo es infinito o cerca de infinito.

Por ejemplo, en el código siguiente se muestra el resultado de una llamada al método [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) con el patrón de expresión regular `(a?)*,` que coincide cero o más veces con cero o un carácter "a". Observe que el único grupo de captura realiza una captura de todos los caracteres "a", así como de [String.Empty](xref:System.String.Empty), pero no hay una segunda coincidencia vacía, ya que la primera coincidencia vacía hace que el cuantificador deje de repetirse.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(a?)*";
      string input = "aaabbb";
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         GroupCollection groups = match.Groups;
         for (int grpCtr = 1; grpCtr <= groups.Count - 1; grpCtr++) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups[grpCtr].Value,
                              groups[grpCtr].Index);
            int captureCtr = 0;
            foreach (Capture capture in groups[grpCtr].Captures) {
               captureCtr++;
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index);
            }
         } 
      }   
   }
}
// The example displays the following output:
//       Match: 'aaa' at index 0
//          Group 1: '' at index 3
//             Capture 1: 'a' at index 0
//             Capture 2: 'a' at index 1
//             Capture 3: 'a' at index 2
//             Capture 4: '' at index 3
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(a?)*"
      Dim input As String = "aaabbb"
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         Dim groups As GroupCollection = match.Groups
         For grpCtr As Integer = 1 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups(grpCtr).Value,
                              groups(grpCtr).Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In groups(grpCtr).Captures
               captureCtr += 1
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index)
            Next
         Next 
      End If   
   End Sub
End Module
' The example displays the following output:
'       Match: 'aaa' at index 0
'          Group 1: '' at index 3
'             Capture 1: 'a' at index 0
'             Capture 2: 'a' at index 1
'             Capture 3: 'a' at index 2
'             Capture 4: '' at index 3
```

Para ver la diferencia práctica entre un grupo de captura que define un número mínimo y máximo de capturas y otro que define un número fijo de capturas, tenga en cuenta los patrones de expresiones regulares `(a\1|(?(1)\1)){0,2}` y `(a\1|(?(1)\1)){2}`. Ambas expresiones regulares constan de un único grupo de captura, que se define como se muestra en la tabla siguiente. 

Modelo | Descripción
------- | -----------
`(a\1` | Coincide con "a", junto con el valor del primer grupo capturado...
`&#124;(?(1)` | … o bien, prueba si se ha definido el primer grupo capturado. (Tenga en cuenta que la construcción **(?(1)** no define un grupo de captura).
`\1))` | Si el primer grupo capturado existe, coincide con su valor. Si el grupo no existe, el grupo coincidirá con [String.Empty](xref:System.String.Empty). 
 
La primera expresión regular intenta coincidir con este patrón de cero a dos veces; el segundo, exactamente dos veces. Dado que el primer patrón alcanza el número mínimo de capturas con su primera captura de [String.Empty](xref:System.String.Empty), nunca se repite para intentar coincidir con `a\1;` el cuantificador `{0,2}` solo permite las coincidencias vacías en la última iteración. En cambio, la segunda expresión regular coincide con "a" porque evalúa `a\1` una segunda vez. El número mínimo de iteraciones (dos) obliga al motor a repetirse tras una coincidencia vacía.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern, input;

      pattern = @"(a\1|(?(1)\1)){0,2}";
      input = "aaabbb"; 

      Console.WriteLine("Regex pattern: {0}", pattern);
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
      Console.WriteLine();

      pattern = @"(a\1|(?(1)\1)){2}";
      Console.WriteLine("Regex pattern: {0}", pattern);
      match = Regex.Match(input, pattern);
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
   }
}
// The example displays the following output:
//       Regex pattern: (a\1|(?(1)\1)){0,2}
//       Match: '' at position 0.
//          Group: 1: '' at position 0.
//             Capture: 1: '' at position 0.
//       
//       Regex pattern: (a\1|(?(1)\1)){2}
//       Matched 'a' at position 0.
//          Group: 1: 'a' at position 0.
//             Capture: 1: '' at position 0.
//             Capture: 2: 'a' at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern, input As String

      pattern = "(a\1|(?(1)\1)){0,2}"
      input = "aaabbb" 

      Console.WriteLine("Regex pattern: {0}", pattern)
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
      Console.WriteLine()

      pattern = "(a\1|(?(1)\1)){2}"
      Console.WriteLine("Regex pattern: {0}", pattern)
      match = Regex.Match(input, pattern)
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Regex pattern: (a\1|(?(1)\1)){0,2}
'       Match: '' at position 0.
'          Group: 1: '' at position 0.
'             Capture: 1: '' at position 0.
'       
'       Regex pattern: (a\1|(?(1)\1)){2}
'       Matched 'a' at position 0.
'          Group: 1: 'a' at position 0.
'             Capture: 1: '' at position 0.
'             Capture: 2: 'a' at position 0.
```

## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)

[Retroceso en expresiones regulares](backtracking.md)


