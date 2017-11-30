---
title: "Construcciones misceláneas en expresiones regulares"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>Construcciones misceláneas en expresiones regulares
Las expresiones regulares en .NET incluyen tres construcciones de lenguaje misceláneas. Una permite habilitar o deshabilitar opciones de coincidencia determinadas en medio de un patrón de expresión regular. Las otras dos permiten incluir comentarios en una expresión regular.  
  
## <a name="inline-options"></a>Opciones insertadas  
 Puede establecer o deshabilitar opciones de coincidencia de patrones específicas para una parte de una expresión regular mediante la sintaxis  
  
```  
(?imnsx-imnsx)  
```  
  
 Indique las opciones que quiere habilitar después del signo de interrogación y las opciones que quiere deshabilitar después del signo menos. En la siguiente tabla se describe cada una de las opciones. Para obtener más información sobre cada opción, consulte [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
|Opción|Descripción|  
|------------|-----------------|  
|`i`|Coincidencia sin distinción entre mayúsculas y minúsculas.|  
|`m`|Modo multilínea.|  
|`n`|Solo capturas explícitas. (Los paréntesis no actúan como grupos de capturas).|  
|`s`|Modo de una sola línea.|  
|`x`|Se omite el espacio en blanco sin escape y se permiten los comentarios en modo X.|  
  
 Cualquier cambio en las opciones de expresión regular definidas por el `(?imnsx-imnsx)` construir permanece en vigor hasta el final del grupo envolvente.  
  
> [!NOTE]
>  El `(?imnsx-imnsx:` *subexpresión* `)` construcción de agrupamiento proporciona una funcionalidad idéntica para una subexpresión. Para más información, consulte [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 En el ejemplo siguiente se usa el `i`, `n`, y `x` opciones para habilitar distingue mayúsculas de minúsculas y las capturas explícitas y para omitir los espacios en blanco en el patrón de expresión regular en medio de una expresión regular.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 En el ejemplo se definen dos expresiones regulares. La primera, `\b(D\w+)\s(d\w+)\b`, coincide con dos palabras consecutivas que empiezan con una "D" mayúscula y una "d" minúscula. La segunda expresión regular, `\b(D\w+)(?ixn) \s (d\w+) \b`, usa opciones insertadas para modificar este patrón, como se describe en la tabla siguiente. Una comparación de los resultados confirma los efectos de la construcción `(?ixn)`.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(D\w+)`|Coincide con una "D" mayúscula seguida de uno o más caracteres de palabra. Este es el primer grupo de capturas.|  
|`(?ixn)`|A partir de este punto, hace comparaciones sin distinción entre mayúsculas y minúsculas, solo hace capturas explícitas y omite el espacio en blanco del patrón de expresión regular.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(d\w+)`|Coincide con una "d" mayúscula o minúscula seguida de uno o más caracteres de palabra. No se captura este grupo porque la `n` opción (captura explícita) estaba habilitada...|  
|`\b`|Coincide con un límite de palabras.|  
  
## <a name="inline-comment"></a>Comentario alineado  
 El `(?#` *comentario* `)` construcción permite incluir un comentario alineado en una expresión regular. El motor de expresiones regulares no utiliza ninguna parte del comentario en la coincidencia de patrones, aunque el comentario está incluido en la cadena devuelta por la <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> método. El comentario termina en el primer paréntesis de cierre.  
  
 En el ejemplo siguiente se repite el primer patrón de expresión regular del ejemplo de la sección anterior. Se agregan dos comentarios alineados en la expresión regular para indicar si la comparación distingue entre mayúsculas y minúsculas. El patrón de expresión regular, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, se define como se indica a continuación.  
  
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
 Un signo de número (`#`) marca un comentario en modo x, que comienza en el carácter de escape # al final del patrón de expresión regular y continúa hasta el final de la línea. Para utilizar esta construcción, debe bien habilitar el `x` opción (mediante opciones alineadas) o proporcionar el <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> valor para el `option` parámetro al crear una instancia el <xref:System.Text.RegularExpressions.Regex> objeto o una llamada a una variable static <xref:System.Text.RegularExpressions.Regex> método.  
  
 En el ejemplo siguiente se muestra la construcción de comentario de final de línea. Determina si una cadena es una cadena de formato compuesto que incluye al menos un elemento de formato. En la tabla siguiente se describe la construcción en el patrón de expresión regular:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\{`|Coincide con una llave de apertura.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`(,-*\d+)*`|Coincide con cero o una aparición de una coma seguida de un signo menos opcional, seguido de uno o más dígitos decimales.|  
|`(\:\w{1,4}?)*`|Coincide con cero o una aparición de un signo de dos puntos seguido de uno a cuatro caracteres de espacio en blanco, pero el menor número posible.|  
|`(?#case insensitive comparison)`|Comentario alineado. No tiene ningún efecto en el comportamiento de la coincidencia de patrones.|  
|`\}`|Coincide con una llave de cierre.|  
|`(?x)`|Habilita la opción de ignorar el espacio en blanco del patrón para que se reconozca el comentario de final de línea.|  
|`# Looks for a composite format item.`|Comentario de final de línea.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Tenga en cuenta que, en lugar de proporcionar el `(?x)` construir de la expresión regular, el comentario podría también reconoció mediante una llamada a la <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> método y pásele el <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> valor de enumeración.  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
