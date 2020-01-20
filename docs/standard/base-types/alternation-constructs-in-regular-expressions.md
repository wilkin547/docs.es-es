---
title: Construcciones de alternancia en expresiones regulares de .NET
description: Obtenga información sobre cómo usar construcciones de alternancia para la coincidencia condicional en expresiones regulares.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET Framework regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
ms.openlocfilehash: 8db9ef72415f148aca2c975fc4e8b70421e3adc3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711563"
---
# <a name="alternation-constructs-in-regular-expressions"></a>Construcciones de alternancia en expresiones regulares

Las construcciones de alternancia modifican una expresión regular para habilitar la coincidencia condicional o “either/or”. .NET admite tres construcciones de alternancia:

- [Coincidencia de patrones con &#124;](#Either_Or)
- [Coincidencia condicional con (?(expresión)sí&#124;no)](#Conditional_Expr)
- [Coincidencia condicional basada en un grupo capturado válido](#Conditional_Group)

<a name="Either_Or"></a>
## <a name="pattern-matching-with-124"></a>Coincidencia de patrones con &#124;

Puede usar el carácter de barra vertical (`|`) para hacer coincidir un elemento de una serie de patrones, donde el carácter `|` separa cada patrón.

Como sucede con la clase de caracteres positivos, el carácter `|` puede utilizarse para hacer coincidir un elemento de una serie de caracteres individuales. En el ejemplo siguiente se utiliza una clase de caracteres positivos y un patrón either/or que coincide con el carácter `|` para buscar apariciones de las palabras "gray" o "grey" en una cadena. En este caso, el carácter `|` produce una expresión regular que es más detallada.

[!code-csharp[RegularExpressions.Language.Alternation#1](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
[!code-vb[RegularExpressions.Language.Alternation#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]

La expresión regular que usa el carácter `|`, `\bgr(a|e)y\b`, se interpreta como se muestra en la tabla siguiente:

|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`gr`|Coincide con los caracteres "gr".|  
|<code>(a&#124;e)</code>|Coincide con una "a" o una "e".|  
|`y\b`|Coincide con una "y" en un límite de palabras.|  

El carácter `|` también se puede usar para realizar una coincidencia either/or con varios caracteres o subexpresiones, que pueden incluir cualquier combinación de literales de carácter y elementos de lenguaje de expresión regular. (La clase de caracteres no proporciona esta funcionalidad). En el ejemplo siguiente, se usa el carácter `|` para extraer un número de la seguridad social (SSN) de EE. UU., de nueve dígitos y en formato *ddd*-*dd*-*dddd*, o un número de identificación de empleador (EIN), de nueve dígitos y en formato *dd*-*ddddddd*.

[!code-csharp[RegularExpressions.Language.Alternation#2](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
[!code-vb[RegularExpressions.Language.Alternation#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  

La expresión regular `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|Coincide con cualquiera de las siguientes opciones: dos dígitos decimales seguidos de un guión seguido de siete dígitos decimales; o tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.|  
|`\d`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
<a name="Conditional_Expr"></a>   
## <a name="conditional-matching-with-an-expression"></a>Coincidencia condicional con una expresión

Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si puede coincidir con un patrón inicial. Su sintaxis es:  

`(?(` *expresión* `)` *sí* `|` *no* `)`

donde *expresión* es el patrón inicial de coincidencia, *sí* es el patrón de coincidencia si se encuentra una coincidencia para *expresión* y *no* es el patrón opcional de coincidencia si no se encuentra ninguna coincidencia para *expresión* . El motor de expresiones regulares trata a la *expresión* como una aserción de ancho cero; es decir, el motor de expresiones regulares no avanza en el flujo de entrada después de evaluar la *expresión*. Por tanto, esta construcción es equivalente a la siguiente:

`(?(?=` *expresión* `)` *sí* `|` *no* `)`

donde `(?=`*expresión*`)` es una construcción de aserción de ancho cero. Para más información, consulte la sección sobre [Construcciones de agrupamiento en expresiones regulares](grouping-constructs-in-regular-expressions.md). Como el motor de expresiones regulares interpreta la *expresión* como un delimitador (una aserción de ancho cero), la *expresión* debe ser una aserción de ancho cero (para más información, consulte [Delimitadores en expresiones regulares](anchors-in-regular-expressions.md)) o una subexpresión que también esté incluida en *sí*. De lo contrario, no se pueden encontrar coincidencias para el patrón *sí* .  
  
> [!NOTE]
> Si *expresión* es un grupo de captura con nombre o con numeración, la construcción de alternancia se interpreta como una prueba de captura; para obtener más información, consulte la sección siguiente, [Coincidencia condicional basada en un grupo capturado válido](#Conditional_Group). En otras palabras, el motor de expresiones regulares no intenta coincidir con la subcadena capturada, sino que, en vez de eso, comprueba la presencia o la ausencia del grupo.  
  
El siguiente ejemplo es una variación del que aparece en la sección [Coincidencia de patrones either/or con &#124;](#Either_Or). En él se usa la coincidencia condicional para determinar si los tres primeros caracteres después de un límite de palabra son dos dígitos seguidos por un guión. Si es así, intenta buscar un número de identificación de empleador (EIN) de EE. UU. Si no, intenta buscar un número de la seguridad social (SSN) de EE.UU.

[!code-csharp[RegularExpressions.Language.Alternation#3](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
[!code-vb[RegularExpressions.Language.Alternation#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]

El patrón de la expresión regular `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:

|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(?(\d{2}-)`|Determina si los tres caracteres siguientes están compuestos de dos dígitos seguidos de un guión.|  
|`\d{2}-\d{7}`|Si el patrón anterior coincide, coincide con dos dígitos seguidos de un guión seguido de siete dígitos.|  
|`\d{3}-\d{2}-\d{4}`|Si el patrón anterior no coincide, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.|  
|`\b`|Coincide con un límite de palabras.|  

<a name="Conditional_Group"></a>
## <a name="conditional-matching-based-on-a-valid-captured-group"></a>Coincidencia condicional basada en un grupo capturado válido

Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si coincidió con un grupo de captura especificado. Su sintaxis es:

`(?(` *nombre* `)` *sí* `|` *no* `)`

o

`(?(` *número* `)` *sí* `|` *no* `)`

donde *nombre* es el nombre y *número* es el número de un grupo de captura, *sí* es la expresión que debe coincidir si *nombre* o *número* tienen una coincidencia, y *no* es la expresión opcional que debe coincidir si no la tienen.

Si *nombre* no se corresponde con el nombre de un grupo de captura que se usa en el patrón de expresión regular, la construcción de alternancia se interpreta como una prueba de expresión, tal como se explica en la sección anterior. Normalmente, esto significa que *expresión* se evalúa como `false`. Si *número* no se corresponde con un grupo de captura numerado que se usa en el patrón de expresión regular, el motor de expresiones regulares genera una excepción <xref:System.ArgumentException>.

El siguiente ejemplo es una variación del que aparece en la sección [Coincidencia de patrones either/or con &#124;](#Either_Or). En él se usa un grupo de captura denominado `n2` que consta de dos dígitos seguidos por un guión. La construcción de alternancia prueba si este grupo de captura ha coincidido en la cadena de entrada. En caso afirmativo, la construcción de alternancia intenta hacer coincidir los últimos siete dígitos de un número de identificación de empleador de identificación de empleador (EIN) de EE. UU. En caso negativo, intenta coincidir con un número de la seguridad social (SSN) de EE.UU.

[!code-csharp[RegularExpressions.Language.Alternation#4](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
[!code-vb[RegularExpressions.Language.Alternation#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]

El patrón de la expresión regular `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:

|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(?<n2>\d{2}-)?`|Coincide con cero o con dos dígitos seguidos por un guión. Este grupo de captura se denomina `n2`.|  
|`(?(n2)`|Prueba si `n2` coincidió con la cadena de entrada.|  
|`\d{7}`|Si `n2` coincidió, coincide con siete dígitos decimales.|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|Si `n2` no coincidió, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.|  
|`\b`|Coincide con un límite de palabras.|  

En el ejemplo siguiente se muestra una variación de este ejemplo, pero con un grupo numerado en lugar de un grupo con nombre. Su patrón de expresión regular es `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.

[!code-csharp[RegularExpressions.Language.Alternation#5](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
[!code-vb[RegularExpressions.Language.Alternation#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]

## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
