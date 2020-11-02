---
title: Construcciones misceláneas en expresiones regulares
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
ms.openlocfilehash: f7800dee67513f885339fad67c7a999cc06cca36
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889275"
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>Construcciones misceláneas en expresiones regulares
Las expresiones regulares en .NET incluyen tres construcciones de lenguaje misceláneas. Una permite habilitar o deshabilitar opciones de coincidencia determinadas en medio de un patrón de expresión regular. Las otras dos permiten incluir comentarios en una expresión regular.  
  
## <a name="inline-options"></a>Opciones insertadas  
 Puede establecer o deshabilitar opciones de coincidencia de patrones específicas para una parte de una expresión regular mediante la sintaxis  
  
`(?imnsx-imnsx)`  
  
 Indique las opciones que quiere habilitar después del signo de interrogación y las opciones que quiere deshabilitar después del signo menos. En la siguiente tabla se describe cada una de las opciones. Para obtener más información sobre cada opción, consulte [Opciones de expresiones regulares](regular-expression-options.md).  
  
|Opción|Descripción|  
|------------|-----------------|  
|`i`|Coincidencia sin distinción entre mayúsculas y minúsculas.|  
|`m`|Modo multilínea.|  
|`n`|Solo capturas explícitas. (Los paréntesis no actúan como grupos de capturas).|  
|`s`|Modo de una sola línea.|  
|`x`|Se omite el espacio en blanco sin escape y se permiten los comentarios en modo X.|  
  
 Cualquier cambio en las opciones de expresión regular definido mediante la construcción `(?imnsx-imnsx)` permanece en vigor hasta el final del grupo envolvente.  
  
> [!NOTE]
> La construcción de agrupamiento `(?imnsx-imnsx:`*subexpresión*`)` proporciona una funcionalidad idéntica para una subexpresión. Para obtener más información, consulte [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md).  
  
 En el ejemplo siguiente se usan las opciones `i`, `n` y `x` para habilitar las capturas explícitas y la opción que no hace distinción entre mayúsculas y minúsculas, y para omitir el espacio en blanco del patrón de expresión regular en medio de una expresión regular.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 En el ejemplo se definen dos expresiones regulares. La primera, `\b(D\w+)\s(d\w+)\b`, coincide con dos palabras consecutivas que empiezan con una "D" mayúscula y una "d" minúscula. La segunda expresión regular, `\b(D\w+)(?ixn) \s (d\w+) \b`, usa opciones insertadas para modificar este patrón, como se describe en la tabla siguiente. Una comparación de los resultados confirma los efectos de la construcción `(?ixn)`.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(D\w+)`|Coincide con una "D" mayúscula seguida de uno o más caracteres de palabra. Este es el primer grupo de capturas.|  
|`(?ixn)`|A partir de este punto, hace comparaciones sin distinción entre mayúsculas y minúsculas, solo hace capturas explícitas y omite el espacio en blanco del patrón de expresión regular.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(d\w+)`|Coincide con una "d" mayúscula o minúscula seguida de uno o más caracteres de palabra. Este grupo no se captura porque se ha habilitado la opción `n` (captura explícita).|  
|`\b`|Coincide con un límite de palabras.|  
  
## <a name="inline-comment"></a>Comentario alineado  
 La construcción `(?#` *comment*`)` permite incluir un comentario alineado en una expresión regular. El motor de expresiones regulares no usa ninguna parte del comentario en la coincidencia de patrones, aunque el comentario se incluye en la cadena devuelta por el método <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType>. El comentario termina en el primer paréntesis de cierre.  
  
 En el ejemplo siguiente se repite el primer patrón de expresión regular del ejemplo de la sección anterior. Se agregan dos comentarios alineados en la expresión regular para indicar si la comparación distingue entre mayúsculas y minúsculas. El patrón de expresión regular, `\b((?# case-sensitive comparison)D\w+)\s(?ixn)((?#case-insensitive comparison)d\w+)\b`, se define como se indica a continuación.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(?# case-sensitive comparison)`|Comentario. No afecta al comportamiento de la coincidencia de patrones.|  
|`(D\w+)`|Coincide con una "D" mayúscula seguida de uno o más caracteres de palabra. Este es el primer grupo de captura.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(?ixn)`|A partir de este punto, hace comparaciones sin distinción entre mayúsculas y minúsculas, solo hace capturas explícitas y omite el espacio en blanco del patrón de expresión regular.|  
|`(?#case-insensitive comparison)`|Comentario. No afecta al comportamiento de la coincidencia de patrones.|  
|`(d\w+)`|Coincide con una "d" mayúscula o minúscula seguida de uno o más caracteres de palabra. Este es el segundo grupo de capturas.|  
|`\b`|Coincide con un límite de palabras.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a>Comentario de final de línea  
 Un signo de número (`#`) marca un comentario en modo X, que empieza en el carácter # sin escape al final del patrón de expresión regular y continúa hasta el final de la línea. Para usar esta construcción, debe habilitar la opción `x` (mediante opciones insertadas) o proporcionar el valor <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> al parámetro `option` al crear una instancia del objeto <xref:System.Text.RegularExpressions.Regex> o al llamar al método <xref:System.Text.RegularExpressions.Regex> estático.  
  
 En el ejemplo siguiente se muestra la construcción de comentario de final de línea. Determina si una cadena es una cadena de formato compuesto que incluye al menos un elemento de formato. En la tabla siguiente se describe la construcción en el patrón de expresión regular:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\{`|Coincide con una llave de apertura.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`(,-*\d+)*`|Coincide con cero o una aparición de una coma seguida de un signo menos opcional, seguido de uno o más dígitos decimales.|  
|`(\:\w{1,4}?)*`|Coincide con cero o una aparición de un signo de dos puntos seguido de uno a cuatro caracteres de espacio en blanco, pero el menor número posible.|  
|`\}`|Coincide con una llave de cierre.|  
|`(?x)`|Habilita la opción de ignorar el espacio en blanco del patrón para que se reconozca el comentario de final de línea.|  
|`# Looks for a composite format item.`|Comentario de final de línea.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Tenga en cuenta que, en lugar de proporcionar la construcción `(?x)` en la expresión regular, el comentario también podía haberse reconocido llamando al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> y pasando el valor de enumeración <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
