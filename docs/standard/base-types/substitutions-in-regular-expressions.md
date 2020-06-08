---
title: Sustituciones en expresiones regulares
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, substitutions
- replacement patterns
- metacharacters, substitutions
- .NET Framework regular expressions, substitutions
- constructs, substitutions
- substitutions
ms.assetid: d1f52431-1c7d-4dc6-8792-6b988256892e
ms.openlocfilehash: 6e5773c220dccd4d139b4f85e19b55048a64e7ef
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288009"
---
# <a name="substitutions-in-regular-expressions"></a>Sustituciones en expresiones regulares
Las sustituciones son elementos del lenguaje que se reconocen solo dentro de patrones de reemplazo. Usan un patrón de expresión regular para definir todo o parte del texto que reemplazará el texto coincidente en la cadena de entrada. El patrón de reemplazo puede estar compuesto de una o más sustituciones junto con caracteres literales. Los patrones de reemplazo se proporcionan a las sobrecargas del método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> que tiene un parámetro `replacement` y al método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> . Los métodos reemplazan el patrón que coincide con el patrón que define el parámetro `replacement` .  
  
 .NET Framework define los elementos de sustitución que se enumeran en la siguiente tabla.  
  
|Sustitución|Descripción|  
|------------------|-----------------|  
|$ *number*|Incluye la última subcadena coincidente por el grupo capturado que identifica *number*, donde *number* es un valor decimal, en la cadena de reemplazo. Para obtener más información, vea [Sustituir un grupo numerado](#substituting-a-numbered-group).|  
|${ *name* }|Incluye la última subcadena coincidente por el grupo con nombre que designa `(?<`*name*`> )` en la cadena de reemplazo. Para obtener más información, vea [Sustituir un grupo con nombre](#substituting-a-named-group).|  
|$$|Incluye un literal "$" único en la cadena de reemplazo. Para obtener más información, vea [Sustituir un símbolo "$"](#substituting-a--character).|  
|$&|Incluye una copia de la coincidencia completa en la cadena de reemplazo. Para obtener más información, vea [Sustituir toda la coincidencia](#substituting-the-entire-match).|  
|$\`|Incluye todo el texto de la cadena de entrada delante de la coincidencia en la cadena de reemplazo. Para obtener más información, vea [Sustituir el texto delante de la coincidencia](#substituting-the-text-before-the-match).|  
|$'|Incluye todo el texto de la cadena de entrada detrás de la coincidencia en la cadena de reemplazo. Para obtener más información, vea [Sustituir el texto detrás de la coincidencia](#substituting-the-text-after-the-match).|  
|$+|Incluye el último grupo capturado en la cadena de reemplazo. Para obtener más información, vea [Sustituir el último grupo capturado](#substituting-the-last-captured-group).|  
|$\_|Incluye la cadena de entrada completa en la cadena de reemplazo. Para obtener más información, vea [Sustituir toda la cadena de entrada](#substituting-the-entire-input-string).|  
  
## <a name="substitution-elements-and-replacement-patterns"></a>Elementos de sustitución y patrones de reemplazo  
 Las sustituciones son las únicas construcciones especiales reconocidas en un patrón de reemplazo. No se admiten otros elementos de lenguaje de expresiones regulares, incluidos los escapes de caracteres y el punto (`.`), que coincidan con cualquier carácter. De igual forma, los elementos de lenguaje de sustitución se reconocen únicamente en patrones de reemplazo y no son válidos en patrones de expresiones regulares.  
  
 El único carácter que puede aparecer en un patrón de expresión regular o en una sustitución es el carácter `$` , aunque tiene un significado diferente en cada contexto. En un patrón de expresión regular, `$` es un delimitador que coincide con el final de la cadena. En un patrón de reemplazo, `$` indica el principio de una sustitución.  
  
> [!NOTE]
> Para obtener una funcionalidad similar a la de un patrón de reemplazo dentro de una expresión regular, use una referencia inversa. Para obtener más información acerca de las referencias inversas, vea [Construcciones de referencia inversa](backreference-constructs-in-regular-expressions.md).  

## <a name="substituting-a-numbered-group"></a>Sustituir un grupo numerado  
 El elemento de lenguaje `$`*number* incluye la última subcadena coincidente por el grupo de captura *number* en la cadena de reemplazo, donde *number* es el índice del grupo de captura. Por ejemplo, el patrón de reemplazo `$1` indica que el primer grupo capturado reemplazará la subcadena coincidente. Para más información sobre los grupos de captura numerados, vea [Grouping Constructs](grouping-constructs-in-regular-expressions.md).  
  
 Todos los dígitos después del símbolo `$` se interpretan como que pertenecen al grupo *number* . Si esto no es lo que pretende, puede sustituir un grupo con nombre en su lugar. Por ejemplo, puede utilizar la cadena de reemplazo `${1}1` en lugar de `$11` para definir la cadena de reemplazo como el valor del primer grupo capturado junto con el número "1". Para obtener más información, vea [Sustituir un grupo con nombre](#substituting-a-named-group).  
  
 Los grupos de captura que no tienen nombres asignados explícitamente mediante la sintaxis `(?<`*name*`>)` se enumeran de izquierda a derecha a partir de uno. Los grupos con nombre también se numeran de izquierda a derecha, comenzando por uno mayor que el índice del último grupo sin nombre. Por ejemplo, en la expresión regular `(\w)(?<digit>\d)`, el índice del grupo con nombre `digit` es 2.  
  
 Si *number* no especifica ningún grupo de captura válido en el patrón de expresión regular, `$`*number* se interpreta como una secuencia de caracteres literales que se usa para reemplazar cada coincidencia.  
  
 En el ejemplo siguiente se usa la sustitución `$`*number* para quitar el símbolo de divisa de un valor decimal. Quita los símbolos de divisa encontrados al principio o al final de un valor monetario y reconoce los dos separadores decimales más comunes ("." y ",").  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/numberedgroup1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/numberedgroup1.vb#1)]  
  
 El patrón de expresión regular `\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\p{Sc}*`|Busca una coincidencia con cero o más caracteres de símbolo de divisa.|  
|`\s?`|Busca una coincidencia con cero o un carácter de espacio en blanco.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`[.,]?`|Busca una coincidencia con cero o un punto o una coma.|  
|`\d*`|Busca cero o más dígitos decimales.|  
|`(\s?\d+[.,]?\d*)`|Busca un espacio en blanco seguido de uno o más dígitos decimales, seguido de cero o un punto o una coma, seguido de cero o más dígitos decimales. Este es el primer grupo de captura. Dado que el patrón de reemplazo es `$1`, la llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> reemplaza la subcadena coincidente completa por este grupo capturado.|  

## <a name="substituting-a-named-group"></a>Sustituir un grupo con nombre  
 El elemento de lenguaje `${`*name*`}` sustituye a la última subcadena coincidente por el grupo de captura *name* , donde *name* es el nombre del grupo de captura definido por el elemento de lenguaje `(?<`*name*`>)` . Para más información sobre los grupos de captura con nombre, vea [Grouping Constructs](grouping-constructs-in-regular-expressions.md).  
  
 Si *name* no especifica ningún grupo de captura con nombre válido en el patrón de expresión regular pero consta de dígitos, `${`*name*`}` se interpreta como un grupo numerado.  
  
 Si *name* no especifica ningún grupo de captura con nombre o grupo de captura numerado válido en el patrón de expresión regular, `${`*name*`}` se interpreta como una secuencia de caracteres literales que se utiliza para reemplazar cada coincidencia.  
  
 En el ejemplo siguiente, se usa la sustitución `${`*name*`}` para quitar el símbolo de divisa de un valor decimal. Quita los símbolos de divisa encontrados al principio o al final de un valor monetario y reconoce los dos separadores decimales más comunes ("." y ",").  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/namedgroup1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/namedgroup1.vb#2)]  
  
 El patrón de expresión regular `\p{Sc}*(?<amount>\s?\d[.,]?\d*)\p{Sc}*` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\p{Sc}*`|Busca una coincidencia con cero o más caracteres de símbolo de divisa.|  
|`\s?`|Busca una coincidencia con cero o un carácter de espacio en blanco.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`[.,]?`|Busca una coincidencia con cero o un punto o una coma.|  
|`\d*`|Busca cero o más dígitos decimales.|  
|`(?<amount>\s?\d[.,]?\d*)`|Busca un espacio en blanco, seguido de uno o más dígitos decimales, seguido de cero o un punto o una coma, seguido de cero o más dígitos decimales. Este es el grupo de captura denominado `amount`. Dado que el patrón de reemplazo es `${amount}`, la llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> reemplaza la subcadena coincidente completa por este grupo capturado.|  

## <a name="substituting-a--character"></a>Sustituir un carácter "$"  
 La sustitución `$$` inserta un carácter "$" literal en la cadena reemplazada.  
  
 En el ejemplo siguiente, se usa el objeto <xref:System.Globalization.NumberFormatInfo> para determinar el símbolo de divisa de la referencia cultural actual y su posición en una cadena de divisa. A continuación, compila dinámicamente un patrón de expresión regular y un patrón de reemplazo. Si el ejemplo se ejecuta en un equipo cuya referencia cultural actual es en-US, genera el patrón de expresión regular `\b(\d+)(\.(\d+))?` y el patrón de reemplazo `$$ $1$2`. El patrón de reemplazo sustituye el texto coincidente por un símbolo de divisa y un espacio seguido del primer y del segundo grupo capturado.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/dollarsign1.cs#8)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/dollarsign1.vb#8)]  
  
 El patrón de expresión regular `\b(\d+)(\.(\d+))?` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Comenzar la búsqueda de coincidencias al principio de un límite de palabras.|  
|`(\d+)`|Buscar coincidencias con uno o más dígitos decimales. Este es el primer grupo de captura.|  
|`\.`|Buscar coincidencias con un punto (el separador decimal).|  
|`(\d+)`|Buscar coincidencias con uno o más dígitos decimales. Éste es el tercer grupo de captura.|  
|`(\.(\d+))?`|Buscar una coincidencia con cero o una aparición de un punto seguido de uno o más dígitos decimales. Este es el segundo grupo de captura.|  

## <a name="substituting-the-entire-match"></a>Sustituir toda la coincidencia  
 La sustitución `$&` incluye toda la coincidencia en la cadena de reemplazo. A menudo, se usa para agregar una subcadena al principio o final de la cadena coincidente. Por ejemplo, el patrón de reemplazo `($&)` agrega un paréntesis al principio y al final de cada coincidencia. Si no hay ninguna coincidencia, la sustitución `$&` no tiene ningún efecto.  
  
 En el ejemplo siguiente, se usa la sustitución `$&` para agregar comillas al principio y al final de los títulos de los libros almacenados en una matriz de cadena.  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/entirematch1.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/entirematch1.vb#3)]  
  
 El patrón de expresión regular `^(\w+\s?)+$` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`^`|Comenzar la búsqueda de coincidencias al principio de la cadena de entrada.|  
|`(\w+\s?)+`|Buscar coincidencias con el patrón de uno o varios caracteres de palabra seguidos de cero o un carácter de espacio en blanco una o varias veces.|  
|`$`|Coincide con el final de la cadena de entrada.|  
  
 El patrón de reemplazo `"$&"` agrega una comilla literal al principio y al final de cada coincidencia.  

## <a name="substituting-the-text-before-the-match"></a>Sustituir el texto delante de la coincidencia  
 La sustitución ``$` `` reemplaza la cadena coincidente por la cadena de entrada completa delante de la coincidencia. Es decir, duplica la cadena de entrada hasta la coincidencia quitando el texto coincidente. Cualquier texto que siga al texto coincidente no cambia en la cadena de resultado. Si hay varias coincidencias en una cadena de entrada, el texto de reemplazo se deriva de la cadena de entrada original, en lugar de la cadena en la que coincidencias anteriores han reemplazado el texto. \(En el ejemplo se ofrece una ilustración.\) Si no hay ninguna coincidencia, la sustitución ``$` `` no tiene ningún efecto.  
  
 En el ejemplo siguiente, se usa el patrón de expresión regular `\d+` para que coincida con una secuencia de uno o más dígitos decimales en la cadena de entrada. La cadena de reemplazo ``$` `` reemplaza estos dígitos por el texto que antecede a la coincidencia.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/before1.cs#4)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/before1.vb#4)]  
  
 En este ejemplo, la cadena de entrada `"aa1bb2cc3dd4ee5"` contiene cinco coincidencias. En la siguiente tabla se muestra cómo la sustitución ``$` `` hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna de resultados.  
  
|Coincidir con|Posición|Cadena antes de la coincidencia|Cadena de resultado|  
|-----------|--------------|-------------------------|-------------------|  
|1|2|aa|aa**aa**bb2cc3dd4ee5|  
|2|5|aa1bb|aaaabb**aa1bb**cc3dd4ee5|  
|3|8|aa1bb2cc|aaaabbaa1bbcc**aa1bb2cc**dd4ee5|  
|4|11|aa1bb2cc3dd|aaaabbaa1bbccaa1bb2ccdd**aa1bb2cc3dd**ee5|  
|5|14|aa1bb2cc3dd4ee|aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddee**aa1bb2cc3dd4ee**|

## <a name="substituting-the-text-after-the-match"></a>Sustituir el texto detrás de la coincidencia  
 La sustitución `$'` reemplaza la cadena coincidente por la cadena de entrada completa después de la coincidencia. Es decir, duplica la cadena de entrada después de la coincidencia quitando el texto coincidente. Cualquier texto que anteceda al texto coincidente no cambia en la cadena de resultado. Si no hay ninguna coincidencia, la sustitución  `$'` no tiene ningún efecto.  
  
 En el ejemplo siguiente, se usa el patrón de expresión regular `\d+` para que coincida con una secuencia de uno o más dígitos decimales en la cadena de entrada. La cadena de reemplazo `$'` reemplaza estos dígitos por el texto que sigue a la coincidencia.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/after1.cs#5)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/after1.vb#5)]  
  
 En este ejemplo, la cadena de entrada `"aa1bb2cc3dd4ee5"` contiene cinco coincidencias. En la siguiente tabla se muestra cómo la sustitución `$'` hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna de resultados.  
  
|Coincidir con|Posición|Cadena después de la coincidencia|Cadena de resultado|  
|-----------|--------------|------------------------|-------------------|  
|1|2|bb2cc3dd4ee5|aa**bb2cc3dd4ee5**bb2cc3dd4ee5|  
|2|5|cc3dd4ee5|aabb2cc3dd4ee5bb**cc3dd4ee5**cc3dd4ee5|  
|3|8|dd4ee5|aabb2cc3dd4ee5bbcc3dd4ee5cc**dd4ee5**dd4ee5|  
|4|11|ee5|aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5dd**ee5**ee5|  
|5|14|<xref:System.String.Empty?displayProperty=nameWithType>|aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5ddee5ee|  

## <a name="substituting-the-last-captured-group"></a>Sustituir el último grupo capturado  
 La sustitución `$+` reemplaza la cadena coincidente por el último grupo capturado. Si no hay ningún grupo capturado o si el valor del último grupo capturado es <xref:System.String.Empty?displayProperty=nameWithType>, la sustitución `$+` no tiene ningún efecto.  
  
 En el ejemplo siguiente se identifican las palabras duplicadas en una cadena y se usa la sustitución `$+` para reemplazarlas por una aparición única de la palabra. La opción <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> se usa para garantizar que palabras que difieren en el uso de mayúsculas y minúsculas, pero que de lo contrario son idénticas, se consideren duplicadas.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/lastmatch1.cs#6)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/lastmatch1.vb#6)]  
  
 El patrón de expresión regular `\b(\w+)\s\1\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`\1`|Buscar una coincidencia con el primer grupo capturado.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  

## <a name="substituting-the-entire-input-string"></a>Sustituir toda la cadena de entrada  
 La sustitución `$_` reemplaza la cadena coincidente por la cadena de entrada completa. Es decir, quita el texto coincidente y lo reemplaza por la cadena completa, incluyendo el texto coincidente.  
  
 En el ejemplo siguiente se buscan coincidencias para uno o más dígitos decimales en la cadena de entrada. Se usa la sustitución `$_` para reemplazarlos por la cadena de entrada completa.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/entire1.cs#7)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/entire1.vb#7)]  
  
 En este ejemplo, la cadena de entrada `"ABC123DEF456"` contiene dos coincidencias. En la siguiente tabla se muestra cómo la sustitución `$_` hace que el motor de expresiones regulares reemplace cada coincidencia en la cadena de entrada. El texto insertado se muestra en negrita en la columna de resultados.  
  
|Coincidir con|Posición|Coincidir con|Cadena de resultado|  
|-----------|--------------|-----------|-------------------|  
|1|3|123|ABC**ABC123DEF456**DEF456|  
|2|5|456|ABCABC123DEF456DEF**ABC123DEF456**|  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
