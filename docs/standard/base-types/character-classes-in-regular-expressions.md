---
title: Clases de carácter en expresiones regulares de .NET
description: Obtenga información sobre cómo usar las clases de carácter para representar un conjunto de caracteres en expresiones regulares de .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- character classes
- regular expressions, character classes
- characters, matching syntax
- .NET Framework regular expressions, character classes
ms.assetid: 0f8bffab-ee0d-4e0e-9a96-2b4a252bb7e4
ms.openlocfilehash: cd9d3f69f8135b608ced91c34f747600352bafe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711459"
---
# <a name="character-classes-in-regular-expressions"></a>Clases de caracteres en expresiones regulares

Una clase de caracteres define un conjunto de caracteres, cualquiera de los cuales puede estar en una cadena de entrada para que se produzca una coincidencia. El lenguaje de expresiones regulares de .NET admite las siguientes clases de caracteres:  
  
- Grupos de caracteres positivos. Un carácter de la cadena de entrada debe coincidir con uno de los caracteres del conjunto especificado. Para obtener más información, consulte [Grupo de caracteres positivos](#PositiveGroup).  
  
- Grupos de caracteres negativos. Ningún carácter de la cadena de entrada debe coincidir con ninguno de los caracteres del conjunto especificado. Para obtener más información, consulte [Grupo de caracteres negativos](#NegativeGroup).  
  
- Cualquier carácter. El carácter `.` (punto) en una expresión regular es un carácter comodín que coincide con cualquier carácter excepto con `\n`. Para obtener más información, consulte [Cualquier carácter](#AnyCharacter).  
  
- Una categoría general o un bloque con nombre Unicode. Para que se produzca una coincidencia, un carácter de la cadena de entrada debe ser miembro de una categoría Unicode determinada o debe estar dentro de un intervalo contiguo de caracteres Unicode. Para obtener más información, consulte [Categoría Unicode o bloque Unicode](#CategoryOrBlock).  
  
- Un bloque con nombre o una categoría general negativa Unicode. Para que se produzca una coincidencia, un carácter de la cadena de entrada no debe ser miembro de una categoría Unicode determinada o no debe estar dentro de un intervalo contiguo de caracteres Unicode. Para obtener más información, consulte [Categoría Unicode o bloque Unicode negativo](#NegativeCategoryOrBlock).  
  
- Un carácter de palabra. Un carácter de la cadena de entrada puede pertenecer a cualquiera de las categorías Unicode que son adecuadas para los caracteres que se usan para formar palabras. Para obtener más información, consulte [Carácter de palabra](#WordCharacter).  
  
- Un carácter que no se usa en las palabras. Un carácter de la cadena de entrada puede pertenecer a cualquier categoría Unicode que no se usa para formar palabras. Para obtener más información, consulte [Carácter que no se usa en las palabras](#NonWordCharacter).  
  
- Un carácter de espacio en blanco. Un carácter de la cadena de entrada puede ser cualquiera de los caracteres separadores Unicode, así como cualquiera de los caracteres de una serie de caracteres de control. Para obtener más información, consulte [Carácter de espacio en blanco](#WhitespaceCharacter).  
  
- Un carácter que no sea un espacio en blanco. Un carácter de la cadena de entrada puede ser cualquier carácter que no sea un espacio en blanco. Para obtener más información, consulte [Carácter que no sea un espacio en blanco](#NonWhitespaceCharacter).  
  
- Un dígito decimal. Un carácter de la cadena de entrada puede ser cualquiera de los caracteres clasificados como dígitos decimales de Unicode. Para obtener más información, consulte [Carácter de dígito decimal](#DigitCharacter).  
  
- Un carácter que no sea un dígito decimal. Un carácter de la cadena de entrada puede ser cualquier carácter que no sea un dígito decimal de Unicode. Para obtener más información, consulte [Carácter de dígito decimal](#NonDigitCharacter).  
  
 .NET admite expresiones de sustracción de clases de caracteres, que permiten definir un conjunto de caracteres como el resultado de excluir una clase de caracteres de otra clase de caracteres. Para obtener más información, consulte [Sustracción de clases de caracteres](#CharacterClassSubtraction).  
  
> [!NOTE]
> Las clases que coinciden con los caracteres por categoría, como [\w](#WordCharacter) para que coincidan con caracteres alfabéticos o [\p{}](#CategoryOrBlock) para que coincidan con una categoría Unicode, que se basan en la clase <xref:System.Globalization.CharUnicodeInfo> para proporcionar información sobre las categorías de caracteres.  A partir de .NET Framework 4.6.2, las categorías de caracteres se basan en [el estándar Unicode, versión 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/). Desde .NET Framework 4 hasta .NET Framework 4.6.1, se basan en el [estándar Unicode, versión 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a>Grupo de caracteres positivos: [ ]  
 Un grupo de caracteres positivos especifica una lista de caracteres cualquiera de los cuales puede aparecer en una cadena de entrada para que se produzca una coincidencia. Los caracteres de la lista se pueden especificar individualmente, como un intervalo o de ambas formas.  
  
 La sintaxis para especificar la lista de caracteres individuales es la siguiente:  

`[*character_group*]`

 donde *grupo_caracteres* es una lista de cada uno de los caracteres que pueden aparecer en la cadena de entrada para que se produzca una coincidencia. *grupo_caracteres* puede estar formado por cualquier combinación de uno o varios caracteres literales, [caracteres de escape](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) o clases de caracteres.  
  
 La sintaxis para especificar un intervalo de caracteres es la siguiente:  
  
`[firstCharacter-lastCharacter]`  
  
 donde *firstCharacter* es el carácter que comienza el intervalo y *lastCharacter* es el carácter final del intervalo. Un intervalo de caracteres es una serie contigua de caracteres que se define especificando el primer carácter de la serie, un guion (-) y, a continuación, el último carácter de la serie. Dos caracteres son contiguos si tienen puntos de código Unicode adyacentes. *firstCharacter* debe ser el carácter con el punto de código inferior y *lastCharacter* debe ser el carácter con el punto de código superior.

> [!NOTE]
> Dado que un grupo de caracteres positivos puede incluir un conjunto de caracteres y un rango de caracteres, un carácter de guión (`-`) siempre se interpreta como el separador de rango, a menos que sea el primer carácter del grupo o el último.

En la tabla siguiente se recogen algunos de los patrones de expresiones regulares comunes que contienen clases de caracteres positivos.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`[aeiou]`|Coincide con todas las vocales.|  
|`[\p{P}\d]`|Coincide con todos los caracteres de puntuación y de dígitos decimales.|  
|`[\s\p{P}]`|Coincide con todos los caracteres de espacio en blanco y de puntuación.|  
  
 En el ejemplo siguiente se define un grupo de caracteres positivos que contiene los caracteres "a" y "e" de manera que la cadena de entrada deba contener las palabras "grey" o "gray" seguidas de cualquier otra palabra para que se produzca una coincidencia.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 La expresión regular `gr[ae]y\s\S+?[\s|\p{P}]` se define de la siguiente manera:  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`gr`|Coincide con los caracteres literales "gr".|  
|`[ae]`|Coincide con una "a" o una "e".|  
|`y\s`|Coincide con el carácter literal "y" seguido de un carácter de espacio en blanco.|  
|`\S+?`|Coincide con uno o varios caracteres que no sean un espacio en blanco, pero con la menor cantidad posible de caracteres.|  
|`[\s\p{P}]`|Coincide con un carácter de espacio en blanco o un signo de puntuación.|  
  
 En el ejemplo siguiente se buscan palabras que comienzan por cualquier letra mayúscula. Utiliza la subexpresión `[A-Z]` para representar el intervalo de letras mayúsculas de la A a la Z.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 La expresión regular `\b[A-Z]\w*\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`[A-Z]`|Coincide con cualquier letra mayúscula de la A a la Z.|  
|`\w*`|Buscar una coincidencia con cero o más caracteres alfabéticos.|  
|`\b`|Coincide con un límite de palabras.|  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a>Grupo de caracteres negativos: [^]  
 Un grupo de caracteres negativos especifica una lista de caracteres que no deben aparecer en una cadena de entrada para que se produzca una coincidencia. Los caracteres de la lista se pueden especificar individualmente, como un intervalo o de ambas formas.  
  
La sintaxis para especificar la lista de caracteres individuales es la siguiente:  

`[*^character_group*]`

 donde *grupo_caracteres* es una lista de cada uno de los caracteres que no pueden aparecer en la cadena de entrada para que se produzca una coincidencia. *grupo_caracteres* puede estar formado por cualquier combinación de uno o varios caracteres literales, [caracteres de escape](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) o clases de caracteres.  
  
 La sintaxis para especificar un intervalo de caracteres es la siguiente:  

`[^*firstCharacter*-*lastCharacter*]`

donde *firstCharacter* es el carácter que comienza el intervalo y *lastCharacter* es el carácter final del intervalo. Un intervalo de caracteres es una serie contigua de caracteres que se define especificando el primer carácter de la serie, un guion (-) y, a continuación, el último carácter de la serie. Dos caracteres son contiguos si tienen puntos de código Unicode adyacentes. *firstCharacter* debe ser el carácter con el punto de código inferior y *lastCharacter* debe ser el carácter con el punto de código superior.

> [!NOTE]
> Dado que un grupo de caracteres negativos puede incluir un conjunto de caracteres y un rango de caracteres, un carácter de guión (`-`) siempre se interpreta como el separador de rango, a menos que sea el primer carácter del grupo o el último.
  
 Es posible concatenar dos o más intervalos de caracteres. Por ejemplo, para especificar el intervalo de dígitos decimales del "0" al "9", el intervalo de letras minúsculas de la "a" a la "f" y el intervalo de letras mayúsculas de la "A" a la "F", utilice `[0-9a-fA-F]`.  
  
 El carácter inicial de acento circunflejo (`^`) de un grupo de caracteres negativos es obligatorio e indica que el grupo de caracteres es un grupo de caracteres negativos en lugar de un grupo de caracteres positivos.  
  
> [!IMPORTANT]
> Un grupo de caracteres negativos dentro de un patrón de expresión regular más grande no es una aserción de ancho cero. Es decir, después de evaluar el grupo de caracteres negativos, el motor de expresiones regulares avanza un carácter en la cadena de entrada.  
  
 En la tabla siguiente se recogen algunos de los patrones de expresiones regulares comunes que contienen grupos de caracteres negativos.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`[^aeiou]`|Coincide con todos los caracteres excepto las vocales.|  
|`[^\p{P}\d]`|Coincide con todos los caracteres excepto los caracteres de puntuación y de dígitos decimales.|  
  
 En el ejemplo siguiente se busca cualquier palabra que comience por los caracteres "th" y no vaya seguida de una "o".  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 La expresión regular `\bth[^o]\w+\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`th`|Coincide con los caracteres literales "th".|  
|`[^o]`|Coincide con cualquier carácter que no sea una "o".|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`\b`|Finaliza en un límite de palabras.|  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a>Cualquier carácter: .  
 El carácter de punto (.) coincide con cualquier carácter excepto con `\n` (carácter de nueva línea, \u000A), con los dos requisitos siguientes:  
  
- Si la opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> modifica un patrón de expresión regular o si la opción `.` modifica la parte del patrón que contiene la clase de caracteres `s`, `.` coincide con cualquier carácter. Para obtener más información, consulte [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
     El ejemplo siguiente muestra el comportamiento predeterminado de la clase de caracteres `.` y con la opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. La expresión regular `^.+` comienza en el principio de la cadena y coincide con todos los caracteres. De forma predeterminada, la coincidencia termina al final de la primera línea; el patrón de la expresión regular coincide con el carácter de retorno de carro, `\r` o \u000D, pero no coincide con `\n`. Dado que la opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> interpreta la cadena de entrada completa como una sola línea, coincide con cada carácter de la cadena de entrada, incluido `\n`.  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
> Dado que coincide con cualquier carácter excepto con `\n`, la clase de caracteres `.` también coincide con `\r` (el carácter de retorno de carro, \u000D).  
  
- En un grupo de caracteres positivos o negativos, un punto se considera un carácter de punto literal, no una clase de caracteres. Para más información, consulte las secciones [Grupo de caracteres positivos](#PositiveGroup) y [Grupo de caracteres negativos](#NegativeGroup) anteriormente en este tema. En el ejemplo siguiente se define una expresión regular que incluye el carácter de punto (`.`) como una clase de caracteres y como un miembro de un grupo de caracteres positivos. La expresión regular `\b.*[.?!;:](\s|\z)` comienza en un límite de palabras, coincide con cualquier carácter hasta que encuentra uno de cinco signos de puntuación, incluido el punto, y después coincide con un carácter de espacio en blanco o con el final de la cadena.  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
> Dado que coincide con cualquier carácter, el elemento del lenguaje `.` se utiliza a menudo con un cuantificador no expansivo si un patrón de expresión regular intenta coincidir varias veces con cualquier carácter. Para obtener más información, consulte [Cuantificadores](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a>Categoría Unicode o bloque Unicode: \p{}  
 El estándar Unicode asigna una categoría general a cada carácter. Por ejemplo, un carácter concreto puede ser una letra mayúscula (representada por la categoría `Lu`), un dígito decimal (categoría `Nd`), un símbolo matemático (categoría `Sm`) o un separador de párrafos (categoría `Zl`). Determinados juegos de caracteres del estándar Unicode también ocupan un intervalo o bloque específico de puntos de código consecutivos. Por ejemplo, el juego de caracteres latinos básico se encuentra desde \u0000 hasta \u007F, mientras que el juego de caracteres árabes se encuentra desde \u0600 hasta \u06FF.  
  
 La construcción de expresión regular  
  
 `\p{`*nombre* `}`  
  
 coincide con cualquier carácter que pertenezca a una categoría general o bloque con nombre de Unicode, donde *nombre* es la abreviatura de la categoría o el nombre del bloque con nombre. Para obtener una lista de abreviaturas de categorías, consulte la sección [Categorías generales Unicode compatibles](#SupportedUnicodeGeneralCategories) más adelante en este tema. Para obtener una lista de bloques con nombre, consulte la sección [Bloques con nombre compatibles](#SupportedNamedBlocks) más adelante en este tema.  
  
 En el ejemplo siguiente se usa la construcción `\p{`*nombre*`}` para buscar coincidencias con una categoría general de Unicode (en este caso, `Pd` o Punctuation, Dash) y un bloque con nombre (los bloques con nombre `IsGreek` e `IsBasicLatin`).  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 La expresión regular `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\p{IsGreek}+`|Coincide con uno o varios caracteres griegos.|  
|`(\s)?`|Busca coincidencias con cero o un carácter de espacio en blanco.|  
|`(\p{IsGreek}+(\s)?)+`|Coincide una o varias veces con el patrón de uno o varios caracteres griegos seguidos de cero o un carácter de espacio en blanco.|  
|`\p{Pd}`|Coincide con un carácter de puntuación, guion.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`\p{IsBasicLatin}+`|Coincide con uno o varios caracteres latinos básicos.|  
|`(\s)?`|Busca coincidencias con cero o un carácter de espacio en blanco.|  
|`(\p{IsBasicLatin}+(\s)?)+`|Coincide una o varias veces con el patrón de uno varios caracteres latinos básicos seguidos de cero o un carácter de espacio en blanco.|  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a>Categoría Unicode o bloque Unicode negativo: \P{}  
 El estándar Unicode asigna una categoría general a cada carácter. Por ejemplo, un carácter concreto puede ser una letra mayúscula (representada por la categoría `Lu`), un dígito decimal (categoría `Nd`), un símbolo matemático (categoría `Sm`) o un separador de párrafos (categoría `Zl`). Determinados juegos de caracteres del estándar Unicode también ocupan un intervalo o bloque específico de puntos de código consecutivos. Por ejemplo, el juego de caracteres latinos básico se encuentra desde \u0000 hasta \u007F, mientras que el juego de caracteres árabes se encuentra desde \u0600 hasta \u06FF.  
  
 La construcción de expresión regular  
  
 `\P{` *nombre* `}`  
  
 coincide con cualquier carácter que no pertenezca a una categoría general o bloque con nombre de Unicode, donde *nombre* es la abreviatura de la categoría o el nombre del bloque con nombre. Para obtener una lista de abreviaturas de categorías, consulte la sección [Categorías generales Unicode compatibles](#SupportedUnicodeGeneralCategories) más adelante en este tema. Para obtener una lista de bloques con nombre, consulte la sección [Bloques con nombre compatibles](#SupportedNamedBlocks) más adelante en este tema.  
  
 En el siguiente ejemplo se usa la construcción `\P{`*nombre*`}` para quitar cualquier símbolo de divisa (en este caso, la categoría `Sc`, o Symbol, Currency) de las cadenas numéricas.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 El patrón de expresión regular `(\P{Sc})+` coincide con uno o varios caracteres que no son símbolos de divisa; quita eficazmente cualquier símbolo de divisa de la cadena de resultado.  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a>Carácter de palabra: \w  
 `\w` coincide con cualquier carácter de palabra. Un carácter de palabra es un miembro de alguna de las categorías Unicode enumeradas en la tabla siguiente.  
  
|Categoría|Descripción|  
|--------------|-----------------|  
|Ll|Letra, minúscula|  
|Lu|Letra, mayúscula|  
|Lt|Letra, inicial en mayúscula|  
|Lo|Letra, otra|  
|Lm|Letra, modificador|  
|Mn|Marca, sin espacios|  
|Nd|Número, dígito decimal|  
|Pc|Puntuación, Conector Esta categoría incluye diez caracteres, el más usado de los cuales es el carácter LOWLINE (_), u+005F.|  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\w` es equivalente a `[a-zA-Z_0-9]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Dado que coincide con cualquier carácter de palabra, el elemento del lenguaje `\w` se suele usar con un cuantificador diferido si un patrón de expresión regular intenta coincidir varias veces con cualquier carácter de palabra, seguido de un carácter de palabra específico. Para obtener más información, consulte [Cuantificadores](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
 En el ejemplo siguiente se usa el elemento del lenguaje `\w` para buscar coincidencias de caracteres duplicados en una palabra. El ejemplo define un patrón de expresión regular, `(\w)\1`, que se puede interpretar de la siguiente manera.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|(\w)|Coincide con un carácter de palabra. Este es el primer grupo de captura.|  
|\1|Coincide con el valor de la primera captura.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a>Carácter que no se usa para formar palabras: \W  
 `\W` coincide con cualquier carácter que no sea de palabra. El elemento del lenguaje \W es equivalente a la clase de caracteres siguiente:  
  
`[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]`  
  
 En otras palabras, coincide con cualquier carácter excepto con los que figuran en las categorías Unicode de la tabla siguiente.  
  
|Categoría|Descripción|  
|--------------|-----------------|  
|Ll|Letra, minúscula|  
|Lu|Letra, mayúscula|  
|Lt|Letra, inicial en mayúscula|  
|Lo|Letra, otra|  
|Lm|Letra, modificador|  
|Mn|Marca, sin espacios|  
|Nd|Número, dígito decimal|  
|Pc|Puntuación, Conector Esta categoría incluye diez caracteres, el más usado de los cuales es el carácter LOWLINE (_), u+005F.|  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\W` es equivalente a `[^a-zA-Z_0-9]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Dado que coincide con cualquier carácter que no sea de palabra, el elemento del lenguaje `\W` se suele usar con un cuantificador diferido si un patrón de expresión regular intenta coincidir varias veces con cualquier carácter que no sea de palabra, seguido de un carácter que no sea de palabra específico. Para obtener más información, consulte [Cuantificadores](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
 En el ejemplo siguiente se ilustra la clase de caracteres `\W`.  Define un patrón de expresión regular, `\b(\w+)(\W){1,2}`, que coincide con una palabra seguida de uno o dos caracteres que no son de palabra, como un espacio en blanco o un signo de puntuación. La expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\b|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|(\w+)|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|  
|(\W){1,2}|Coincide una o dos veces con un carácter que no se usa para formar palabras. Este es el segundo grupo de captura.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 Dado que el objeto <xref:System.Text.RegularExpressions.Group> del segundo grupo de captura contiene solo un carácter que no se usa para formar palabras, el ejemplo recupera todos los caracteres que no se usan para formar palabras capturados del objeto <xref:System.Text.RegularExpressions.CaptureCollection> que devuelve la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>.  
  
<a name="WhitespaceCharacter"></a>   
## <a name="whitespace-character-s"></a>Carácter de espacio en blanco: \s  
 `\s` coincide con cualquier carácter de espacio en blanco. Equivale a las secuencias de escape y las categorías Unicode que figuran en la tabla siguiente.  
  
|Categoría|Descripción|  
|--------------|-----------------|  
|`\f`|El carácter de avance de página, \u000C.|  
|`\n`|El carácter de nueva línea, \u000A.|  
|`\r`|El carácter de retorno de carro, \u000D.|  
|`\t`|El carácter de tabulación, \u0009.|  
|`\v`|El carácter de tabulación vertical, \u000B.|  
|`\x85`|Los puntos suspensivos o el carácter de LÍNEA SIGUIENTE (…), \u0085.|  
|`\p{Z}`|Coincide con cualquier carácter separador.|  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\s` es equivalente a `[ \f\n\r\t\v]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
 En el ejemplo siguiente se ilustra la clase de caracteres `\s`. Define un patrón de expresión regular, `\b\w+(e)?s(\s|$)`, que coincide con una palabra que termina por "s" o "es" seguida de un carácter de espacio en blanco o el final de la cadena de entrada. La expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\b|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|\w+|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|(e)?|Coincide cero o una vez con una "e".|  
|s|Coincide con una "s".|  
|(\s&#124;$)|Coincide con un carácter de espacio en blanco o el final de la cadena de entrada.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-whitespace-character-s"></a>Carácter que no sea un espacio en blanco: \S  
 `\S` coincide con cualquier carácter que no sea un espacio en blanco. Equivale al patrón de expresión regular `[^\f\n\r\t\v\x85\p{Z}]` o es lo contrario del patrón de expresión regular equivalente a `\s`, que coincide con los caracteres de espacio en blanco. Para más información, consulte [Carácter de espacio en blanco: \s](#WhitespaceCharacter).  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\S` es equivalente a `[^ \f\n\r\t\v]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
 En el ejemplo siguiente se ilustra el elemento del lenguaje `\S`. El patrón de expresión regular `\b(\S+)\s?` coincide con cadenas delimitadas por caracteres de espacio en blanco. El segundo elemento del objeto <xref:System.Text.RegularExpressions.GroupCollection> de la coincidencia contiene la cadena coincidente. La expresión regular puede interpretarse como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(\S+)`|Coincide con caracteres que no son espacio en blanco. Este es el primer grupo de captura.|  
|`\s?`|Busca coincidencias con cero o un carácter de espacio en blanco.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a>Carácter de dígito decimal: \d  
 `\d` coincide con cualquier dígito decimal. Equivale al patrón de expresión regular `\p{Nd}`, que incluye los dígitos decimales estándar 0-9 así como los dígitos decimales de varios juegos de caracteres.  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\d` es equivalente a `[0-9]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
 En el ejemplo siguiente se ilustra el elemento del lenguaje `\d`. Comprueba si una cadena de entrada representa un número de teléfono válido de los Estados Unidos y Canadá. El patrón de expresión regular `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` se define como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`^`|Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.|  
|`\(?`|Coincide con cero o un carácter "(" literal.|  
|`\d{3}`|Coincide con tres dígitos decimales.|  
|`\)?`|Coincide con cero o un carácter ")" literal.|  
|`[\s-]`|Coincide con un guion o un carácter de espacio en blanco.|  
|`(\(?\d{3}\)?[\s-])?`|Coincide cero o una vez con un paréntesis de apertura opcional seguido de tres dígitos decimales, un paréntesis de cierre opcional y un carácter de espacio en blanco o un guion. Este es el primer grupo de captura.|  
|`\d{3}-\d{4}`|Coincide con tres dígitos decimales seguidos de un guion y otros cuatro dígitos decimales.|  
|`$`|Coincide con el final de la cadena de entrada.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a>Carácter que no sea un dígito: \D  
 `\D` coincide con cualquier carácter que no sea un dígito. Equivale al patrón de expresión regular `\P{Nd}`.  
  
 Si se especifica un comportamiento conforme a ECMAScript, `\D` es equivalente a `[^0-9]`. Para obtener información sobre las expresiones regulares ECMAScript, consulte la sección "Comportamiento de la búsqueda de coincidencias de ECMAScript" en [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
 En el ejemplo siguiente se muestra el elemento del lenguaje \D. Comprueba si una cadena, como un número de pieza, consta de la combinación adecuada de caracteres decimales y no decimales. El patrón de expresión regular `^\D\d{1,5}\D*$` se define como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`^`|Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.|  
|`\D`|Coincide con un carácter que no sea un dígito.|  
|`\d{1,5}`|Coincide con entre uno y cinco dígitos decimales.|  
|`\D*`|Coincide con cero, uno o más caracteres no decimales.|  
|`$`|Coincide con el final de la cadena de entrada.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a>Categorías generales Unicode compatibles  
 Unicode define las categorías generales que se muestran en la tabla siguiente. Para obtener más información, consulte las secciones sobre el "formato de archivo UCD" y los "valores de categorías generales" en la [base de datos de caracteres Unicode](https://www.unicode.org/reports/tr44/).  
  
|Categoría|Descripción|  
|--------------|-----------------|  
|`Lu`|Letra, mayúscula|  
|`Ll`|Letra, minúscula|  
|`Lt`|Letra, inicial en mayúscula|  
|`Lm`|Letra, modificador|  
|`Lo`|Letra, otra|  
|`L`|Todos los caracteres de letras. Esto incluye los caracteres `Lu`, `Ll`, `Lt`, `Lm` y `Lo`.|  
|`Mn`|Marca, sin espacios|  
|`Mc`|Marca, con espacios y combinación|  
|`Me`|Marca, inclusión|  
|`M`|Todas las marcas diacríticas. Esto incluye las categorías `Mn`, `Mc` y `Me`.|  
|`Nd`|Número, dígito decimal|  
|`Nl`|Número, letra|  
|`No`|Número, otro|  
|`N`|Todos los números. Esto incluye las categorías `Nd`, `Nl` y `No`.|  
|`Pc`|Puntuación, conector|  
|`Pd`|Puntuación, raya|  
|`Ps`|Puntuación, abrir|  
|`Pe`|Puntuación, cerrar|  
|`Pi`|Puntuación, comilla de apertura (puede comportarse como Ps o Pe, en función del uso)|  
|`Pf`|Puntuación, comilla de cierre (puede comportarse como Ps o Pe, en función del uso)|  
|`Po`|Puntuación, otro|  
|`P`|Todos los signos de puntuación. Esto incluye las categorías `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf` y `Po`.|  
|`Sm`|Símbolo, matemático|  
|`Sc`|Símbolo, divisa|  
|`Sk`|Símbolo, modificador|  
|`So`|Símbolo, otro|  
|`S`|Todos los símbolos. Esto incluye las categorías `Sm`, `Sc`, `Sk` y `So`.|  
|`Zs`|Separador, espacio|  
|`Zl`|Separador, línea|  
|`Zp`|Separador, párrafo|  
|`Z`|Todos los caracteres separadores. Esto incluye las categorías `Zs`, `Zl` y `Zp`.|  
|`Cc`|Otro, control|  
|`Cf`|Otro, formato|  
|`Cs`|Otro, suplente|  
|`Co`|Otro, uso privado|  
|`Cn`|Otro, no asignado (ningún carácter tiene esta propiedad)|  
|`C`|Todos los caracteres de control. Esto incluye las categorías `Cc`, `Cf`, `Cs`, `Co` y `Cn`.|  
  
 Puede determinar la categoría Unicode de cualquier carácter concreto pasando dicho carácter al método <xref:System.Char.GetUnicodeCategory%2A>. En el ejemplo siguiente se utiliza el método <xref:System.Char.GetUnicodeCategory%2A> para determinar la categoría de cada elemento de una matriz que contiene determinados caracteres latinos.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a>Bloques con nombre compatibles

.NET proporciona los bloques con nombre que se muestran en la tabla siguiente. El conjunto de bloques con nombre compatibles está basado en Unicode 4.0 y Perl 5.6. Para una expresión regular que utiliza bloques con nombre, consulte la sección [Categoría Unicode o bloque Unicode: \\p{}](#unicode-category-or-unicode-block-p).  
  
|Intervalo de puntos de código|Nombre del bloque|  
|----------------------|----------------|  
|0000 - 007F|`IsBasicLatin`|  
|0080 - 00FF|`IsLatin-1Supplement`|  
|0100 - 017F|`IsLatinExtended-A`|  
|0180 - 024F|`IsLatinExtended-B`|  
|0250 - 02AF|`IsIPAExtensions`|  
|02B0 - 02FF|`IsSpacingModifierLetters`|  
|0300 - 036F|`IsCombiningDiacriticalMarks`|  
|0370 - 03FF|`IsGreek`<br /><br /> o bien<br /><br /> `IsGreekandCoptic`|  
|0400 - 04FF|`IsCyrillic`|  
|0500 - 052F|`IsCyrillicSupplement`|  
|0530 - 058F|`IsArmenian`|  
|0590 - 05FF|`IsHebrew`|  
|0600 - 06FF|`IsArabic`|  
|0700 - 074F|`IsSyriac`|  
|0780 - 07BF|`IsThaana`|  
|0900 - 097F|`IsDevanagari`|  
|0980 - 09FF|`IsBengali`|  
|0A00 - 0A7F|`IsGurmukhi`|  
|0A80 - 0AFF|`IsGujarati`|  
|0B00 - 0B7F|`IsOriya`|  
|0B80 - 0BFF|`IsTamil`|  
|0C00 - 0C7F|`IsTelugu`|  
|0C80 - 0CFF|`IsKannada`|  
|0D00 - 0D7F|`IsMalayalam`|  
|0D80 - 0DFF|`IsSinhala`|  
|0E00 - 0E7F|`IsThai`|  
|0E80 - 0EFF|`IsLao`|  
|0F00 - 0FFF|`IsTibetan`|  
|1000 - 109F|`IsMyanmar`|  
|10A0 - 10FF|`IsGeorgian`|  
|1100 - 11FF|`IsHangulJamo`|  
|1200 - 137F|`IsEthiopic`|  
|13A0 - 13FF|`IsCherokee`|  
|1400 - 167F|`IsUnifiedCanadianAboriginalSyllabics`|  
|1680 - 169F|`IsOgham`|  
|16A0 - 16FF|`IsRunic`|  
|1700 - 171F|`IsTagalog`|  
|1720 - 173F|`IsHanunoo`|  
|1740 - 175F|`IsBuhid`|  
|1760 - 177F|`IsTagbanwa`|  
|1780 - 17FF|`IsKhmer`|  
|1800 - 18AF|`IsMongolian`|  
|1900 - 194F|`IsLimbu`|  
|1950 - 197F|`IsTaiLe`|  
|19E0 - 19FF|`IsKhmerSymbols`|  
|1D00 - 1D7F|`IsPhoneticExtensions`|  
|1E00 - 1EFF|`IsLatinExtendedAdditional`|  
|1F00 - 1FFF|`IsGreekExtended`|  
|2000 - 206F|`IsGeneralPunctuation`|  
|2070 - 209F|`IsSuperscriptsandSubscripts`|  
|20A0 - 20CF|`IsCurrencySymbols`|  
|20D0 - 20FF|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> o bien<br /><br /> `IsCombiningMarksforSymbols`|  
|2100 - 214F|`IsLetterlikeSymbols`|  
|2150 - 218F|`IsNumberForms`|  
|2190 - 21FF|`IsArrows`|  
|2200 - 22FF|`IsMathematicalOperators`|  
|2300 - 23FF|`IsMiscellaneousTechnical`|  
|2400 - 243F|`IsControlPictures`|  
|2440 - 245F|`IsOpticalCharacterRecognition`|  
|2460 - 24FF|`IsEnclosedAlphanumerics`|  
|2500 - 257F|`IsBoxDrawing`|  
|2580 - 259F|`IsBlockElements`|  
|25A0 - 25FF|`IsGeometricShapes`|  
|2600 - 26FF|`IsMiscellaneousSymbols`|  
|2700 - 27BF|`IsDingbats`|  
|27C0 - 27EF|`IsMiscellaneousMathematicalSymbols-A`|  
|27F0 - 27FF|`IsSupplementalArrows-A`|  
|2800 - 28FF|`IsBraillePatterns`|  
|2900 - 297F|`IsSupplementalArrows-B`|  
|2980 - 29FF|`IsMiscellaneousMathematicalSymbols-B`|  
|2A00 - 2AFF|`IsSupplementalMathematicalOperators`|  
|2B00 - 2BFF|`IsMiscellaneousSymbolsandArrows`|  
|2E80 - 2EFF|`IsCJKRadicalsSupplement`|  
|2F00 - 2FDF|`IsKangxiRadicals`|  
|2FF0 - 2FFF|`IsIdeographicDescriptionCharacters`|  
|3000 - 303F|`IsCJKSymbolsandPunctuation`|  
|3040 - 309F|`IsHiragana`|  
|30A0 - 30FF|`IsKatakana`|  
|3100 - 312F|`IsBopomofo`|  
|3130 - 318F|`IsHangulCompatibilityJamo`|  
|3190 - 319F|`IsKanbun`|  
|31A0 - 31BF|`IsBopomofoExtended`|  
|31F0 - 31FF|`IsKatakanaPhoneticExtensions`|  
|3200 - 32FF|`IsEnclosedCJKLettersandMonths`|  
|3300 - 33FF|`IsCJKCompatibility`|  
|3400 - 4DBF|`IsCJKUnifiedIdeographsExtensionA`|  
|4DC0 - 4DFF|`IsYijingHexagramSymbols`|  
|4E00 - 9FFF|`IsCJKUnifiedIdeographs`|  
|A000 - A48F|`IsYiSyllables`|  
|A490 - A4CF|`IsYiRadicals`|  
|AC00 - D7AF|`IsHangulSyllables`|  
|D800 - DB7F|`IsHighSurrogates`|  
|DB80 - DBFF|`IsHighPrivateUseSurrogates`|  
|DC00 - DFFF|`IsLowSurrogates`|  
|E000 - F8FF|`IsPrivateUse` o `IsPrivateUseArea`|  
|F900 - FAFF|`IsCJKCompatibilityIdeographs`|  
|FB00 - FB4F|`IsAlphabeticPresentationForms`|  
|FB50 - FDFF|`IsArabicPresentationForms-A`|  
|FE00 - FE0F|`IsVariationSelectors`|  
|FE20 - FE2F|`IsCombiningHalfMarks`|  
|FE30 - FE4F|`IsCJKCompatibilityForms`|  
|FE50 - FE6F|`IsSmallFormVariants`|  
|FE70 - FEFF|`IsArabicPresentationForms-B`|  
|FF00 - FFEF|`IsHalfwidthandFullwidthForms`|  
|FFF0 - FFFF|`IsSpecials`|  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-base_group---excluded_group"></a>Sustracción de clases de caracteres: [grupo_base - [grupo_excluido]]  
 Una clase de caracteres define un conjunto de caracteres. La sustracción de clases de caracteres genera un conjunto de caracteres que es el resultado de excluir los caracteres de una clase de caracteres de otra clase de caracteres.  
  
 Una expresión de sustracción de clases de caracteres tiene el formato siguiente:  
  
 `[` *base_group* `-[` *excluded_group* `]]`  
  
 Los corchetes (`[]`) y el guion (`-`) son obligatorios. El *grupo_base* es un [grupo de caracteres positivos](#PositiveGroup) o un [grupo de caracteres negativos](#NegativeGroup). El componente *grupo_excluido* es otro grupo de caracteres positivos o negativos, u otra expresión de sustracción de clases de caracteres (es decir, pueden anidarse expresiones de sustracción de clases de caracteres).  
  
 Por ejemplo, supongamos que tiene un grupo base formado por el intervalo de caracteres de "a" a "z". Para definir el conjunto de caracteres formado por el grupo base, salvo el carácter "m", utilice `[a-z-[m]]`. Para definir el conjunto de caracteres formado por el grupo base, salvo el conjunto de caracteres "d", "j" y "p", utilice `[a-z-[djp]]`. Para definir el conjunto de caracteres formado por el grupo base, salvo el intervalo de caracteres de "m" a "p", utilice `[a-z-[m-p]]`.  
  
 Considere la expresión de sustracción de clases de caracteres anidada `[a-z-[d-w-[m-o]]]`. La expresión se evalúa desde el intervalo de caracteres más profundo hacia el exterior. Primero, el intervalo de caracteres de "m" a "o" se resta del intervalo de caracteres de "d" a "w", lo que da como resultado el conjunto de caracteres de "d" a "l" y de "p" a "w". A continuación, ese conjunto se resta del intervalo de caracteres de "a" a "z", lo que da lugar al conjunto de caracteres `[abcmnoxyz]`.  
  
 Puede utilizar cualquier clase de caracteres con la sustracción de clases de caracteres. Para definir el conjunto de caracteres formado por todos los caracteres Unicode desde \u0000 hasta \uFFFF, a excepción de los caracteres de espacio en blanco (`\s`), los caracteres de la categoría general de puntuación (`\p{P}`), los caracteres del bloque con nombre `IsGreek` (`\p{IsGreek}`) y el carácter de control Unicode NEXT LINE (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.  
  
 Elija las clases de caracteres para que una expresión de sustracción de clases de caracteres produzca resultados satisfactorios. Evite el uso de expresiones que produzcan un conjunto vacío de caracteres, que no coincidan con nada, o expresiones equivalentes al grupo base original. Por ejemplo, el conjunto vacío es el resultado de la expresión `[\p{IsBasicLatin}-[\x00-\x7F]]`, que resta todos los caracteres del intervalo de caracteres `IsBasicLatin` de la categoría general `IsBasicLatin`. Ocurre lo mismo con el grupo base original, que es el resultado de la expresión `[a-z-[0-9]]`.  Esto se debe a que el grupo base, que está formado por el intervalo de caracteres comprendido entre las letras de la "a" a la "z", no contiene ningún carácter del grupo excluido, que es el intervalo de caracteres formado por los dígitos decimales del "0" al "9".  
  
 En el ejemplo siguiente se define una expresión regular, `^[0-9-[2468]]+$`, que coincide con cero y con los dígitos impares de una cadena de entrada.  La expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|^|Comienza la búsqueda de coincidencias al principio de la cadena de entrada.|  
|`[0-9-[2468]]+`|Coincide con una o varias apariciones de cualquier carácter del 0 al 9, salvo con el 2, 4, 6 y 8. En otras palabras, busca una o varias coincidencias con cero o un dígito impar.|  
|$|Finalizar la búsqueda de coincidencias al final de la cadena de entrada.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Char.GetUnicodeCategory%2A>
- [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md)
