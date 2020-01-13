---
title: Delimitadores en expresiones regulares de .NET
description: Obtenga información sobre cómo usar delimitadores en patrones de expresiones regulares.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- atomic zero-width assertions
- regular expressions, anchors
- regular expressions, atomic zero-width assertions
- anchors, in regular expressions
- metacharacters, atomic zero-width assertions
- metacharacters, anchors
- .NET Framework regular expressions, anchors
- .NET Framework regular expressions, atomic zero-width assertions
ms.assetid: 336391f6-2614-499b-8b1b-07a6837108a7
ms.openlocfilehash: 319aa76754adc852528f35448d9906d4e903693b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711550"
---
# <a name="anchors-in-regular-expressions"></a>Delimitadores en expresiones regulares
Los delimitadores, o aserciones atómicas de ancho cero, especifican la posición de la cadena en que se debe producir una coincidencia. Cuando se usa un delimitador en una expresión de búsqueda, el motor de expresiones regulares no avanza por la cadena o ni consume caracteres, sino que solo busca una coincidencia en la posición especificada. Por ejemplo, `^` especifica que la coincidencia debe empezar al principio de una cadena o línea. Por consiguiente, la expresión regular `^http:` coincide con "http": solo cuando se encuentra al principio de una línea. En la tabla siguiente, se enumeran los delimitadores que admiten las expresiones regulares de .NET.  
  
|Delimitador|Descripción|  
|------------|-----------------|  
|`^`|De forma predeterminada, la coincidencia se debe producir al principio de la cadena. Por su parte, en el modo multilínea, se debe producir al principio de la línea. Para obtener más información, vea [Principio de cadena o línea](#start-of-string-or-line-).|  
|`$`|De forma predeterminada, la coincidencia se debe producir al final de la cadena o antes de `\n` al final de la cadena. Por su parte, en el modo multilínea, se debe producir al final de la línea o antes de `\n` al final de la línea. Para obtener más información, vea [Final de cadena o línea](#end-of-string-or-line-).|  
|`\A`|La coincidencia se debe producir solo al principio de la cadena (no se admiten varias líneas). Para obtener más información, vea [Principio de cadena solamente](#start-of-string-only-a).|  
|`\Z`|La coincidencia se debe producir al final de la cadena o antes de `\n` al final de la cadena. Para obtener más información, vea [Final de cadena o antes de nueva línea al final](#end-of-string-or-before-ending-newline-z).|  
|`\z`|La coincidencia se debe producir solo al final de la cadena. Para obtener más información, vea [Final de cadena solamente](#end-of-string-only-z).|  
|`\G`|La coincidencia se debe iniciar en la posición en que finalizó la coincidencia anterior. Para obtener más información, vea [Coincidencias contiguas](#contiguous-matches-g).|  
|`\b`|La coincidencia se debe producir en un límite de palabras. Para obtener más información, vea [Límite de palabras](#word-boundary-b).|  
|`\B`|La coincidencia no se debe producir en un límite de palabras. Para obtener más información, vea [Fuera de un límite de palabras](#non-word-boundary-b).|  

## <a name="start-of-string-or-line-"></a>Principio de cadena o línea: ^  
 De forma predeterminada, el delimitador `^` especifica que el patrón siguiente debe comenzar en la posición del primer carácter de la cadena. Si usa `^` con la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> (vea [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md)), la coincidencia se debe producir al principio de cada línea.  
  
 En el ejemplo siguiente se usa el delimitador `^` en una expresión regular que extrae información sobre los años durante los que existieron algunos equipos de béisbol profesionales. En el ejemplo se llama a dos sobrecargas del método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> :  
  
- La llamada a la sobrecarga <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29> encuentra solo la primera subcadena que coincide con el patrón de la expresión regular en la cadena de entrada.  
  
- La llamada a la sobrecarga <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29> con el parámetro `options` establecido en <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> encuentra las cinco subcadenas.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring1.vb#1)]  
  
 El patrón de expresión regular `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`^`|Comienza la búsqueda de coincidencias al principio de la cadena de entrada (o al principio de la línea si se llama al método con la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> ).|  
|`((\w+(\s?)){2,}`|Coincide con uno o varios caracteres que se usan para formar palabras seguidos de cero o un espacio, al menos dos veces. Este es el primer grupo de captura. Esta expresión también define un segundo y tercer grupo de captura: El segundo grupo está compuesto por la palabra capturada y el tercero consta de los espacios en blanco capturados.|  
|`,\s`|Coincide con una coma seguida de un carácter de espacio en blanco.|  
|`(\w+\s\w+)`|Coincide con uno o varios caracteres que se usan para formar palabras seguidos de un espacio, seguidos de uno o varios caracteres que se usan para formar palabras. Este es el cuarto grupo de captura.|  
|`,`|Coincide con una coma.|  
|`\s\d{4}`|Coincide con un espacio seguido de cuatro dígitos decimales.|  
|<code>(-(\d{4}&#124;present))?</code>|Coincide con cero o un guion seguido de cuatro dígitos decimales o de la cadena "present". Este es el sexto grupo de captura. También incluye un séptimo grupo de captura.|  
|`,?`|Coincide con una coma o ninguna.|  
|<code>(\s\d{4}(-(\d{4}&#124;present))?,?)+</code>|Coincide con una o más apariciones de lo siguiente: un espacio, cuatro dígitos decimales, cero o un guion seguido de cuatro dígitos decimales o de la cadena "present", y una coma o ninguna. Este es el quinto grupo de captura.| 

## <a name="end-of-string-or-line-"></a>Final de cadena o línea: $  
 El delimitador `$` especifica que el patrón que le precede debe aparecer al final de la cadena de entrada o antes de `\n` al final de la cadena de entrada.  
  
 Si usa `$` con la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , la coincidencia también se puede producir al final de una línea. Observe que `$` coincide con `\n` , pero no coincide con `\r\n` (la combinación de caracteres de retorno de carro y nueva línea, o CR/LF). Para buscar la combinación de caracteres CR/LF, incluya `\r?$` en el patrón de expresión regular.  
  
 En el ejemplo siguiente se agrega el delimitador `$` al patrón de expresión regular usado en el ejemplo de la sección [Principio de cadena o línea](#start-of-string-or-line-) . Cuando se usa con la cadena de entrada original, que incluye cinco líneas de texto, el método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> no puede encontrar una coincidencia, porque el final de la primera línea no coincide con el patrón `$` . Cuando la cadena de entrada original se divide en una matriz de cadenas, el método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> consigue encontrar coincidencias en cada una de las cinco líneas. Cuando se llama al método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> con el parámetro `options` establecido en <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, no se encuentra ninguna coincidencia porque el patrón de la expresión regular no tiene en cuenta el elemento de retorno de carro (\u+000D). Sin embargo, cuando el patrón de la expresión regular se modifica al remplazar `$` por `\r?$`, si se llama al método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> con el parámetro `options` establecido en <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , ahora encuentra cinco coincidencias.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring1.vb#2)]     

## <a name="start-of-string-only-a"></a>Principio de cadena solamente: \A  
 El delimitador `\A` especifica que debe producirse una coincidencia al principio de la cadena de entrada. Es idéntico al delimitador `^` , salvo en que `\A` omite la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Por consiguiente, solo puede coincidir con el principio de la primera línea en una cadena de entrada de varias líneas.  
  
 El ejemplo siguiente es similar a los ejemplos de los delimitadores `^` y `$` . Usa el delimitador `\A` en una expresión regular que extrae información sobre los años durante los que existieron algunos equipos de béisbol profesionales. La cadena de entrada incluye cinco líneas. La llamada al método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> encuentra solo la primera subcadena que coincide con el patrón de la expresión regular en la cadena de entrada. Como muestra el ejemplo, la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline> no tiene ningún efecto.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring2.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring2.vb#3)]     

## <a name="end-of-string-or-before-ending-newline-z"></a>Final de cadena o antes de nueva línea al final: \Z  
 El delimitador `\Z` especifica que se debe producir una coincidencia al final de la cadena de entrada o antes de `\n` al final de la cadena de entrada. Es idéntico al delimitador `$` , salvo en que `\Z` omite la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Por consiguiente, en una cadena de varias líneas, solo puede coincidir con el final de la última línea o la última línea antes de `\n`.  
  
 Observe que `\Z` coincide con `\n` , pero no coincide con `\r\n` (la combinación de caracteres de retorno de carro y nueva línea, o CR/LF). Para buscar CR/LF, incluya `\r?\Z` en el patrón de expresión regular.  
  
 En el ejemplo siguiente, se usa el delimitador `\Z` en una expresión regular que es similar al ejemplo de la sección [Principio de cadena o línea](#start-of-string-or-line-) , que extrae información sobre los años durante los que existieron algunos equipos del béisbol profesionales. La subexpresión `\r?\Z` de la expresión regular `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` coincide con el final de una cadena, y también coincide con una cadena que termina por `\n` o `\r\n`. Como resultado, cada elemento de la matriz coincide con el patrón de la expresión regular.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring2.cs#4)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring2.vb#4)]     

## <a name="end-of-string-only-z"></a>Final de cadena solamente: \z  
 El delimitador `\z` especifica que debe producirse una coincidencia al final de la cadena de entrada. Al igual que el elemento del lenguaje `$` , `\z` omite la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . A diferencia del elemento del lenguaje `\Z` , `\z` no coincide con un carácter `\n` al final de una cadena. Por consiguiente, solo puede coincidir con la última línea de la cadena de entrada.  
  
 En el ejemplo siguiente, se usa el delimitador `\z` en una expresión regular que por lo demás es idéntica al ejemplo de la sección anterior, que extrae información sobre los años durante los que existieron algunos equipos del béisbol profesionales. En el ejemplo, se intenta buscar coincidencias con cada uno de los cinco elementos de una matriz de cadenas con el patrón de expresión regular `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z`. Dos de las cadenas finalizan con caracteres de retorno de carro y salto de línea, una finaliza con un carácter de salto de línea, y dos no finalizan con un carácter de retorno de carro ni con un carácter de salto de línea. Como muestra la salida, solo coinciden con el patrón las cadenas sin un carácter de retorno de carro ni de salto de línea.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring3.cs#5)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring3.vb#5)]    

## <a name="contiguous-matches-g"></a>Coincidencias contiguas: \G  
 El delimitador `\G` especifica que debe producirse una coincidencia en el punto en el que finalizó la coincidencia anterior. El uso de este delimitador con el método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> permite asegurarse de que todas las coincidencias son contiguas.  
  
 En el ejemplo siguiente se usa una expresión regular para extraer los nombres de especies de roedores de una cadena delimitada por comas.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/contiguous1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/contiguous1.vb#6)]  
  
 La expresión regular `\G(\w+\s?\w*),?` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\G`|Comienza donde finalizó la última coincidencia.|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`\s?`|Coincide con cero o un espacio.|  
|`\w*`|Buscar una coincidencia con cero o más caracteres alfabéticos.|  
|`(\w+\s?\w*)`|Coincide con uno o varios caracteres que se usan para formar palabras seguidos de cero o un espacio, seguidos de cero o más caracteres que se usan para formar palabras. Este es el primer grupo de captura.|  
|`,?`|Coincide con cero o un carácter de coma literal.|     

## <a name="word-boundary-b"></a>Límite de palabras: \b  
 El delimitador `\b` especifica que la coincidencia se debe producir en un límite entre un carácter que se usa para formar palabras (el elemento del lenguaje `\w` ) y un carácter que no se usa para formar palabras (el elemento del lenguaje `\W` ). Los caracteres que se usan para formar palabras son los caracteres alfanuméricos y de subrayado; un carácter que no se usa para formar palabras es cualquier carácter que no es alfanumérico ni de subrayado. (Para más información, vea [Clases de carácter](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)). La coincidencia también se puede producir en un límite de palabras al principio o al final de la cadena.  
  
 El delimitador `\b` se usa con frecuencia para asegurarse de que una subexpresión coincide con una palabra completa en lugar de solo con el principio o el final de una palabra. La expresión regular `\bare\w*\b` del ejemplo siguiente muestra este uso. Coincide con cualquier palabra que comience por la subcadena "are". El resultado del ejemplo también muestra que `\b` coincide tanto con el principio como con el final de la cadena de entrada.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/word1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/word1.vb#7)]  
  
 El patrón de la expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`are`|Coincide con la subcadena "are".|  
|`\w*`|Buscar una coincidencia con cero o más caracteres alfabéticos.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  

## <a name="non-word-boundary-b"></a>Fuera de un límite de palabras: \B  
 El delimitador `\B` especifica que la coincidencia no se debe producir en un límite de palabras. Es lo contrario del delimitador `\b` .  
  
 En el ejemplo siguiente, se usa el delimitador `\B` para buscar apariciones de la subcadena "qu" en una palabra. El patrón de expresión regular `\Bqu\w+` coincide con una subcadena que comienza por "qu" que no está al principio de una palabra y que continúa hasta el final de la palabra.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/nonword1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/nonword1.vb#8)]  
  
 El patrón de la expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\B`|La búsqueda de coincidencias no comienza en un límite de palabras.|  
|`qu`|Coincide con la subcadena "qu".|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md)
