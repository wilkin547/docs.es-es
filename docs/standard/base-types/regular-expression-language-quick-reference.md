---
title: Lenguaje de expresiones regulares - Referencia rápida
ms.date: 03/30/2017
ms.technology: dotnet-standard
f1_keywords:
- VS.RegularExpressionBuilder
helpviewer_keywords:
- regex cheat sheet
- parsing text with regular expressions, language elements
- searching with regular expressions, language elements
- pattern-matching with regular expressions, language elements
- regular expressions, language elements
- regular expressions [.NET Framework]
- cheat sheet
- .NET Framework regular expressions, language elements
ms.assetid: 930653a6-95d2-4697-9d5a-52d11bb6fd4c
ms.openlocfilehash: 0b553f44ebc512ffd1194254fe8ebc90bcb2f763
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523904"
---
# <a name="regular-expression-language---quick-reference"></a>Lenguaje de expresiones regulares - Referencia rápida

Una expresión regular es un modelo con el que el motor de expresiones regulares intenta buscar una coincidencia en el texto de entrada. Un modelo consta de uno o más literales de carácter, operadores o estructuras. Para obtener una breve introducción, consulte [Expresiones regulares de .NET](regular-expressions.md).

Cada sección de esta referencia rápida enumera una categoría determinada de caracteres, operadores y construcciones que puede usar para definir expresiones regulares.

Esta información también se proporciona en dos formatos que se pueden descargar e imprimir para facilitar su consulta:

- [Descargar en formato Word (.docx)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)
- [Descarga en formato PDF (.pdf)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)

## <a name="character-escapes"></a>Escapes de carácter

El carácter de barra diagonal inversa (\\) en una expresión regular indica que el carácter que le sigue es un carácter especial (como se muestra en la tabla siguiente) o que se debe interpretar literalmente. Para más información, consulte [Escapes de carácter](character-escapes-in-regular-expressions.md).

|Carácter de escape|Descripción|Modelo|Coincidencias|
|-----------------------|-----------------|-------------|-------------|
|`\a`|Coincide con un carácter de campana, \u0007.|`\a`|`"\u0007"` en `"Error!" + '\u0007'`|
|`\b`|En una clase de caracteres, coincide con un retroceso, \u0008.|`[\b]{3,}`|`"\b\b\b\b"` en `"\b\b\b\b"`|
|`\t`|Coincide con una tabulación, \u0009.|`(\w+)\t`|`"item1\t"`, `"item2\t"` en `"item1\titem2\t"`|
|`\r`|Coincide con un retorno de carro, \u000D. (`\r` no es equivalente al carácter de nueva línea, `\n`).|`\r\n(\w+)`|`"\r\nThese"` en `"\r\nThese are\ntwo lines."`|
|`\v`|Coincide con una tabulación vertical, \u000B.|`[\v]{2,}`|`"\v\v\v"` en `"\v\v\v"`|
|`\f`|Coincide con un avance de página, \u000C.|`[\f]{2,}`|`"\f\f\f"` en `"\f\f\f"`|
|`\n`|Coincide con una nueva línea, \u000A.|`\r\n(\w+)`|`"\r\nThese"` en `"\r\nThese are\ntwo lines."`|
|`\e`|Coincide con un escape, \u001B.|`\e`|`"\x001B"` en `"\x001B"`|
|`\` *nnn*|Usa la representación octal para especificar un carácter (*nnn* consta de dos o tres dígitos).|`\w\040\w`|`"a b"`, `"c d"` en `"a bc d"`|
|`\x` *nn*|Usa la representación hexadecimal para especificar un carácter (*nn* consta de exactamente dos dígitos).|`\w\x20\w`|`"a b"`, `"c d"` en `"a bc d"`|
|`\c` *X*<br /><br /> `\c` *x*|Coincide con el carácter de control ASCII especificado por *X* o *x*, donde *X* o *x* es la letra del carácter de control.|`\cC`|`"\x0003"` en `"\x0003"` (Ctrl-C)|
|`\u` *nnnn*|Coincide con un carácter Unicode usando la representación hexadecimal (exactamente cuatro dígitos, según representa *nnnn*).|`\w\u0020\w`|`"a b"`, `"c d"` en `"a bc d"`|
|`\`|Cuando va seguido de un carácter que no se reconoce como un carácter de escape en esta y otras tablas de este tema, coincide con ese carácter. Por ejemplo, `\*` es igual que `\x2A`y `\.` es igual que `\x2E`. Esto permite que el motor de expresiones regulares elimine la ambigüedad de los elementos del lenguaje (como \* o ?) y los literales de carácter (representados por `\*` o `\?`).|`\d+[\+-x\*]\d+`|`"2+2"` y `"3*9"` en `"(2+2) * 3*9"`|

## <a name="character-classes"></a>Clases de caracteres

Una clase de caracteres coincide con cualquiera de un juego de caracteres. Las clases de caracteres incluyen los elementos del lenguaje enumerados en la tabla siguiente. Para más información, consulte [Clases de caracteres](character-classes-in-regular-expressions.md).

|Clase de carácter|Descripción|Modelo|Coincidencias|
|---------------------|-----------------|-------------|-------------|
|`[` *grupo_caracteres* `]`|Coincide con cualquier carácter individual de *grupo_caracteres*. De forma predeterminada, la coincidencia distingue entre mayúsculas y minúsculas.|`[ae]`|`"a"` en `"gray"`<br /><br /> `"a"`, `"e"` en `"lane"`|
|`[^` *grupo_caracteres* `]`|Negativo: coincide con cualquier carácter individual que no esté en *grupo_caracteres*. De forma predeterminada, los caracteres de *grupo_caracteres* distinguen entre mayúsculas y minúsculas.|`[^aei]`|`"r"`, `"g"`, `"n"` en `"reign"`|
|`[` *primero* `-` *último* `]`|Rango de caracteres: coincide con cualquier carácter individual en el intervalo de *primero* a *último*.|`[A-Z]`|`"A"`, `"B"` en `"AB123"`|
|`.`|Carácter comodín: coincide con cualquier carácter excepto con \n.<br /><br /> Para coincidir con un carácter de punto literal (. o `\u002E`), debe anteponerle el carácter de escape (`\.`).|`a.e`|`"ave"` en `"nave"`<br /><br /> `"ate"` en `"water"`|
|`\p{` *nombre* `}`|Coincide con cualquier carácter individual que pertenezca a la categoría general Unicode o al bloque con nombre especificado por *nombre*.|`\p{Lu}`<br /><br /> `\p{IsCyrillic}`|`"C"`, `"L"` en `"City Lights"`<br /><br /> `"Д"`, `"Ж"` en `"ДЖem"`|
|`\P{` *nombre* `}`|Coincide con cualquier carácter individual que no pertenezca a la categoría general Unicode o al bloque con nombre especificado por *nombre*.|`\P{Lu}`<br /><br /> `\P{IsCyrillic}`|`"i"`, `"t"`, `"y"` en `"City"`<br /><br /> `"e"`, `"m"` en `"ДЖem"`|
|`\w`|Coincide con cualquier carácter de una palabra.|`\w`|`"I"`, `"D"`, `"A"`, `"1"`, `"3"` en `"ID A1.3"`|
|`\W`|Coincide con cualquier carácter que no pertenezca a una palabra.|`\W`|`" "`, `"."` en `"ID A1.3"`|
|`\s`|Coincide con cualquier carácter que sea un espacio en blanco.|`\w\s`|`"D "` en `"ID A1.3"`|
|`\S`|Coincide con cualquier carácter que no sea un espacio en blanco.|`\s\S`|`" _"` en `"int __ctr"`|
|`\d`|Coincide con cualquier dígito decimal.|`\d`|`"4"` en `"4 = IV"`|
|`\D`|Coincide con cualquier carácter que no sea un dígito decimal.|`\D`|`" "`, `"="`, `" "`, `"I"`, `"V"` en `"4 = IV"`|

## <a name="anchors"></a>Delimitadores

Los delimitadores, o aserciones atómicas de ancho cero, hacen que una coincidencia tenga éxito o no dependiendo de la posición actual en la cadena, pero no hacen que el motor avance por la cadena ni consuma caracteres. Los metacaracteres enumerados en la tabla siguiente son delimitadores. Para obtener más información, consulte [Delimitadores](anchors-in-regular-expressions.md).

|Aserción|Descripción|Modelo|Coincidencias|
|---------------|-----------------|-------------|-------------|
|`^`|De forma predeterminada, la coincidencia debe comenzar al principio de la cadena; en el modo multilínea, debe comenzar al principio de la línea.|`^\d{3}`|`"901"` en `"901-333-"`|
|`$`|De forma predeterminada, la coincidencia se debe producir al final de la cadena o antes de `\n` al final de la cadena; en el modo multilínea, se debe producir antes del final de la línea o antes de `\n` al final de la línea.|`-\d{3}$`|`"-333"` en `"-901-333"`|
|`\A`|La coincidencia se debe producir al principio de la cadena.|`\A\d{3}`|`"901"` en `"901-333-"`|
|`\Z`|La coincidencia se debe producir al final de la cadena o antes de `\n` al final de la cadena.|`-\d{3}\Z`|`"-333"` en `"-901-333"`|
|`\z`|La coincidencia se debe producir al final de la cadena.|`-\d{3}\z`|`"-333"` en `"-901-333"`|
|`\G`|La coincidencia se debe producir en el punto en el que finalizó la coincidencia anterior.|`\G\(\d\)`|`"(1)"`, `"(3)"`, `"(5)"` en `"(1)(3)(5)[7](9)"`|
|`\b`|La coincidencia se debe producir en un límite entre un carácter `\w` (alfanumérico) y un carácter `\W` (no alfanumérico).|`\b\w+\s\w+\b`|`"them theme"`, `"them them"` en `"them theme them them"`|
|`\B`|La coincidencia no se debe producir en un límite `\b`.|`\Bend\w*\b`|`"ends"`, `"ender"` en `"end sends endure lender"`|

## <a name="grouping-constructs"></a>Construcciones de agrupamiento

Las construcciones de agrupamiento definen subexpresiones de una expresión regular y, normalmente, capturan subcadenas de una cadena de entrada. Las construcciones de agrupamiento incluyen los elementos del lenguaje enumerados en la tabla siguiente. Para obtener más información, consulte [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md).

|Construcción de agrupamiento|Descripción|Modelo|Coincidencias|
|------------------------|-----------------|-------------|-------------|
|`(` *subexpresión* `)`|Captura la subexpresión coincidente y le asigna un número ordinal basado en uno.|`(\w)\1`|`"ee"` en `"deep"`|
|`(?<` *nombre* `>` *subexpresión* `)`|Captura la subexpresión coincidente en un grupo con nombre.|`(?<double>\w)\k<double>`|`"ee"` en `"deep"`|
|`(?<` *nombre1* `-` *nombre2* `>` *subexpresión* `)`|Define una definición de grupo de equilibrio. Para obtener más información, consulte la sección "Definiciones de grupos de equilibrio" en [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md).|`(((?'Open'\()[^\(\)]*)+((?'Close-Open'\))[^\(\)]*)+)*(?(Open)(?!))$`|`"((1-3)*(3-1))"` en `"3+2^((1-3)*(3-1))"`|
|`(?:` *subexpresión* `)`|Define un grupo sin captura.|`Write(?:Line)?`|`"WriteLine"` en `"Console.WriteLine()"`<br /><br /> `"Write"` en `"Console.Write(value)"`|
|`(?imnsx-imnsx:` *subexpresión* `)`|Aplica o deshabilita las opciones especificadas dentro de *subexpresión*. Para obtener más información, consulte [Opciones de expresiones regulares](regular-expression-options.md).|`A\d{2}(?i:\w+)\b`|`"A12xl"`, `"A12XL"` en `"A12xl A12XL a12xl"`|
|`(?=` *subexpresión* `)`|Aserción de búsqueda anticipada positiva de ancho cero.|`\w+(?=\.)`|`"is"`, `"ran"` y `"out"` en `"He is. The dog ran. The sun is out."`|
|`(?!` *subexpresión* `)`|Aserción de búsqueda anticipada negativa de ancho cero.|`\b(?!un)\w+\b`|`"sure"`, `"used"` en `"unsure sure unity used"`|
|`(?<=` *subexpresión* `)`|Aserción de búsqueda tardía positiva de ancho cero.|`(?<=19)\d{2}\b`|`"99"`, `"50"`, `"05"` en `"1851 1999 1950 1905 2003"`|
|`(?<!` *subexpresión* `)`|Aserción de búsqueda tardía negativa de ancho cero.|`(?<!19)\d{2}\b`|`"51"`, `"03"` en `"1851 1999 1950 1905 2003"`|
|`(?>` *subexpresión* `)`|Grupo atómico.|`[13579](?>A+B+)`|`"1ABB"`, `"3ABB"` y `"5AB"` en `"1ABB 3ABBC 5AB 5AC"`|

## <a name="quantifiers"></a>Cuantificadores

Un cuantificador especifica cuántas instancias del elemento anterior (que puede ser un carácter, un grupo o una clase de caracteres) debe haber en la cadena de entrada para que se encuentre una coincidencia. Los cuantificadores incluyen los elementos del lenguaje enumerados en la tabla siguiente. Para obtener más información, consulte [Cuantificadores](quantifiers-in-regular-expressions.md).

|Cuantificador|Descripción|Modelo|Coincidencias|
|----------------|-----------------|-------------|-------------|
|`*`|Coincide con el elemento anterior cero o más veces.|`\d*\.\d`|`".0"`, `"19.9"`, `"219.9"`|
|`+`|Coincide con el elemento anterior una o más veces.|`"be+"`|`"bee"` en `"been"`, `"be"` en `"bent"`|
|`?`|Coincide con el elemento anterior cero veces o una vez.|`"rai?n"`|`"ran"`, `"rain"`|
|`{` *n* `}`|Coincide con el elemento anterior exactamente *n* veces.|`",\d{3}"`|`",043"` en `"1,043.6"`, `",876"`, `",543"` y `",210"` en `"9,876,543,210"`|
|`{` *n* `,}`|Coincide con el elemento anterior al menos *n* veces.|`"\d{2,}"`|`"166"`, `"29"`, `"1930"`|
|`{` *n* `,` *m* `}`|Coincide con el elemento anterior al menos *n* veces, pero no más de *m* veces.|`"\d{3,5}"`|`"166"`, `"17668"`<br /><br /> `"19302"` en `"193024"`|
|`*?`|Coincide con el elemento anterior cero o más veces, pero el menor número de veces que sea posible.|`\d*?\.\d`|`".0"`, `"19.9"`, `"219.9"`|
|`+?`|Coincide con el elemento anterior una o más veces, pero el menor número de veces que sea posible.|`"be+?"`|`"be"` en `"been"`, `"be"` en `"bent"`|
|`??`|Coincide con el elemento anterior cero o una vez, pero el menor número de veces que sea posible.|`"rai??n"`|`"ran"`, `"rain"`|
|`{` *n* `}?`|Coincide con el elemento precedente exactamente *n* veces.|`",\d{3}?"`|`",043"` en `"1,043.6"`, `",876"`, `",543"` y `",210"` en `"9,876,543,210"`|
|`{` *n* `,}?`|Coincide con el elemento anterior al menos *n* veces, pero el menor número de veces posible.|`"\d{2,}?"`|`"166"`, `"29"`, `"1930"`|
|`{` *n* `,` *m* `}?`|Coincide con el elemento anterior entre *n* y *m* veces, pero el menor número de veces posible.|`"\d{3,5}?"`|`"166"`, `"17668"`<br /><br /> `"193"`, `"024"` en `"193024"`|

## <a name="backreference-constructs"></a>Construcciones de referencia inversa

Una referencia inversa permite identificar una subexpresión coincidente previamente más adelante en la misma expresión regular. En la tabla siguiente se enumeran las construcciones de referencia inversa admitidas en las expresiones regulares de .NET. Para obtener más información, consulte [Construcciones de referencia inversa](backreference-constructs-in-regular-expressions.md).

|Construcción de referencias inversas|Descripción|Modelo|Coincidencias|
|-----------------------------|-----------------|-------------|-------------|
|`\` *número*|Referencia inversa Coincide con el valor de una subexpresión numerada.|`(\w)\1`|`"ee"` en `"seek"`|
|`\k<` *nombre* `>`|Referencia inversa con nombre Coincide con el valor de una expresión con nombre.|`(?<char>\w)\k<char>`|`"ee"` en `"seek"`|

## <a name="alternation-constructs"></a>Construcciones de alternancia

Las estructuras de alternancia modifican una expresión regular para habilitar o no la coincidencia. Estas construcciones incluyen los elementos del lenguaje enumerados en la tabla siguiente. Para obtener más información, consulte [Construcciones de alternancia](alternation-constructs-in-regular-expressions.md).

|Construcciones de alternancia|Descripción|Modelo|Coincidencias|
|---------------------------|-----------------|-------------|-------------|
|<code>&#124;</code>|Coincide con cualquier elemento separado por el carácter de barra vertical (<code>&#124;</code>).|<code>th(e&#124;is&#124;at)</code>|`"the"`, `"this"` en `"this is the day."`|
|`(?(` *expresión* `)` *sí* <code>&#124;</code> *no* `)`|Coincide con *sí* si el patrón de expresión regular designado por *expresión* coincide; de lo contrario, coincide con la parte opcional *no*. *expresión* se interpreta como una aserción de ancho cero.|<code>(?(A)A\d{2}\b&#124;\b\d{3}\b)</code>|`"A10"`, `"910"` en `"A10 C103 910"`|
|`(?(` *nombre* `)` *sí* <code>&#124;</code> *no* `)`|Coincide con *sí* si *nombre*, un grupo de captura con nombre o numerado, tiene una coincidencia; de lo contrario, coincide con la parte opcional *no*.|<code>(?&lt;quoted&gt;&quot;)?(?(quoted).+?&quot;&#124;\S+\s)</code>|`"Dogs.jpg "`, `"\"Yiska playing.jpg\""` en `"Dogs.jpg \"Yiska playing.jpg\""`|

## <a name="substitutions"></a>Sustituciones

Las sustituciones son elementos del lenguaje de expresiones regulares que se admiten en modelos de reemplazo. Para obtener más información, consulte [Substituciones](substitutions-in-regular-expressions.md). Los metacaracteres enumerados en la tabla siguiente son aserciones atómicas de ancho cero.

|Carácter|Descripción|Modelo|Modelo de reemplazo|Cadena de entrada|Cadena de resultado|
|---------------|-----------------|-------------|-------------------------|------------------|-------------------|
|`$` *número*|Sustituye la subcadena que coincide con el grupo *número*.|`\b(\w+)(\s)(\w+)\b`|`$3$2$1`|`"one two"`|`"two one"`|
|`${` *nombre* `}`|Sustituye la subcadena que coincide con el grupo con nombre *nombre*.|`\b(?<word1>\w+)(\s)(?<word2>\w+)\b`|`${word2} ${word1}`|`"one two"`|`"two one"`|
|`$$`|Sustituye un "$" literal.|`\b(\d+)\s?USD`|`$$$1`|`"103 USD"`|`"$103"`|
|`$&`|Sustituye una copia de toda la coincidencia.|`\$?\d*\.?\d+`|`**$&**`|`"$1.30"`|`"**$1.30**"`|
|``$` ``|Sustituye todo el texto de la cadena de entrada delante de la coincidencia.|`B+`|``$` ``|`"AABBCC"`|`"AAAACC"`|
|`$'`|Sustituye todo el texto de la cadena de entrada detrás de la coincidencia.|`B+`|`$'`|`"AABBCC"`|`"AACCCC"`|
|`$+`|Sustituye el último grupo capturado.|`B+(C+)`|`$+`|`"AABBCCDD"`|`"AACCDD"`|
|`$_`|Sustituye toda la cadena de entrada.|`B+`|`$_`|`"AABBCC"`|`"AAAABBCCCC"`|

## <a name="regular-expression-options"></a>Opciones de expresiones regulares

Puede especificar opciones que controlen cómo debe interpretar el motor de expresiones regulares un patrón de expresión regular. Muchas de estas opciones pueden especificarse alineadas (en el patrón de expresión regular) o como una o más constantes de <xref:System.Text.RegularExpressions.RegexOptions>. Esta referencia rápida solo muestra las opciones alineadas. Para obtener más información sobre las opciones alineadas y <xref:System.Text.RegularExpressions.RegexOptions>, consulte el artículo [Opciones de expresiones regulares](regular-expression-options.md).

Puede especificar una opción alineada de dos formas:

- Con la [construcción miscelánea](miscellaneous-constructs-in-regular-expressions.md) `(?imnsx-imnsx)`, donde el signo menos (-) delante de una opción o un conjunto de opciones desactiva dichas opciones. Por ejemplo, `(?i-mn)` activa una coincidencia sin distinción entre mayúsculas y minúsculas (`i`), desactiva el modo multilínea (`m`) y desactiva las capturas de grupo sin nombre (`n`). La opción se aplica al patrón de expresión regular a partir del punto en el que esta se define y es efectiva hasta el final del patrón o hasta el punto en el que otro constructor invierte la opción.
- Con la [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md)`(?imnsx-imnsx:`*subexpresión*`)`, que define opciones solo para el grupo especificado.

El motor de expresiones regulares de .NET admite las siguientes opciones insertadas:

|Opción|Descripción|Modelo|Coincidencias|
|------------|-----------------|-------------|-------------|
|`i`|Usa la coincidencia sin distinción entre mayúsculas y minúsculas.|`\b(?i)a(?-i)a\w+\b`|`"aardvark"`, `"aaaAuto"` en `"aardvark AAAuto aaaAuto Adam breakfast"`|
|`m`|Usa el modo multilínea. `^` y `$` coinciden con el principio y el final de una línea, en lugar del principio y el final de una cadena.|Para obtener un ejemplo, consulte la sección "Modo multilínea" en [Opciones de expresiones regulares](regular-expression-options.md).||
|`n`|No se capturan grupos sin nombre.|Para obtener un ejemplo, consulte la sección "Solo capturas explícitas" en [Opciones de expresiones regulares](regular-expression-options.md).||
|`s`|Usa el modo de una sola línea.|Para obtener un ejemplo, consulte la sección "Modo de una sola línea" en [Opciones de expresiones regulares](regular-expression-options.md).||
|`x`|Se omite el espacio en blanco sin escape en el patrón de expresión regular.|`\b(?x) \d+ \s \w+`|`"1 aardvark"`, `"2 cats"` en `"1 aardvark 2 cats IV centurions"`|

## <a name="miscellaneous-constructs"></a>Construcciones misceláneas

Las estructuras misceláneas modifican un modelo de expresión regular o proporcionan información sobre él. En la tabla siguiente se enumeran las construcciones misceláneas admitidas por .NET. Para obtener más información, consulte [Construcciones misceláneas](miscellaneous-constructs-in-regular-expressions.md).

|Construcción|Definición|Ejemplo|
|---------------|----------------|-------------|
|`(?imnsx-imnsx)`|Establece o deshabilita opciones como la no distinción entre mayúsculas y minúsculas en medio de un patrón. Para más información, consulte [Opciones de expresiones regulares](regular-expression-options.md).|`\bA(?i)b\w+\b` coincide con `"ABA"`, `"Able"` en `"ABA Able Act"`|
|`(?#` *comentario* `)`|Comentario alineado El comentario termina en el primer paréntesis de cierre.|`\bA(?#Matches words starting with A)\w+\b`|
|`#` [hasta el final de la línea]|Comentario en modo X El comentario comienza en un carácter `#` sin escape y continúa hasta el final de la línea.|`(?x)\bA\w+\b#Matches words starting with A`|

## <a name="see-also"></a>Vea también

- <xref:System.Text.RegularExpressions?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>
- [Expresiones regulares](regular-expressions.md)
- [Clases de expresiones regulares](the-regular-expression-object-model.md)
- [Expresiones regulares: referencia rápida (descarga en formato Word)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)
- [Expresiones regulares: referencia rápida (descarga en formato PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
