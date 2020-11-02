---
title: Opciones de expresiones regulares
description: Aprenda a usar opciones de expresiones regulares en .NET, como la coincidencia sin distinción entre mayúsculas y minúsculas, el modo multilínea y el modo de derecha a izquierda.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, options
- constructs, options
- .NET regular expressions, options
- inline option constructs
- options parameter
ms.assetid: c82dc689-7e82-4767-a18d-cd24ce5f05e9
ms.openlocfilehash: 5687d1e5a11e69cc9ecf2bd34067329cc52955d2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889002"
---
# <a name="regular-expression-options"></a>Opciones de expresiones regulares

De forma predeterminada, al comparar una cadena de entrada con los caracteres literales de un patrón de expresión regular, se distinguen mayúsculas de minúsculas, los espacios en blanco del patrón de expresión regular se interpretan como caracteres de espacio en blanco literales, y los grupos de captura de la expresión regular se denominan tanto implícita como explícitamente. Estos y otros aspectos del comportamiento predeterminado de la expresión regular se pueden modificar mediante la especificación de las opciones de la expresión regular. Estas opciones —que aparecen enumeradas en la tabla siguiente— se pueden insertar como parte del patrón de expresión regular, o se pueden suministrar a un constructor de clases <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> o a un método estático de coincidencia de patrones como valor de enumeración de <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

|Miembro RegexOptions|Carácter insertado|Efecto|
|-------------------------|----------------------|------------|
|<xref:System.Text.RegularExpressions.RegexOptions.None>|No disponible|Usar el comportamiento predeterminado. Para obtener más información, consulte [Opciones predeterminadas](#default-options).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>|`i`|Usa la coincidencia sin distinción entre mayúsculas y minúsculas. Para obtener más información, consulte la sección [Coincidencia sin distinción entre mayúsculas y minúsculas](#case-insensitive-matching).|
|<xref:System.Text.RegularExpressions.RegexOptions.Multiline>|`m`|Usar el modo multilínea, donde `^` y `$` coinciden con el principio y el final de cada línea (en lugar del principio y el final de la cadena de entrada). Para obtener más información, consulte la sección [Modo multilínea](#multiline-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.Singleline>|`s`|Usar el modo de una sola línea, donde el punto (.) coincide con todos los caracteres (en lugar de todos los caracteres excepto `\n`). Para obtener más información, consulte la sección [Modo de una sola línea](#single-line-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>|`n`|No se capturan grupos sin nombre. Las únicas capturas válidas son grupos con nombre explícito o numerados con el formato `(?<`*nombre*`>` *subexpresión*`)`. Para obtener más información, consulte la sección [Solo capturas explícitas](#explicit-captures-only).|
|<xref:System.Text.RegularExpressions.RegexOptions.Compiled>|No disponible|Compilar la expresión regular en un ensamblado. Para obtener más información, consulte la sección [Expresiones regulares compiladas](#compiled-regular-expressions).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace>|`x`|Excluir del patrón el espacio en blanco sin escape y habilitar los comentarios tras un signo de número (`#`). Para obtener más información, consulte la sección [Ignorar el espacio en blanco](#ignore-white-space).|
|<xref:System.Text.RegularExpressions.RegexOptions.RightToLeft>|No disponible|Cambiar la dirección de búsqueda. La búsqueda se mueve de derecha a izquierda en vez de de izquierda a derecha. Para obtener más información, consulte la sección [Modo de derecha a izquierda](#right-to-left-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ECMAScript>|No disponible|Habilitar un comportamiento conforme a ECMAScript para la expresión. Para obtener más información, consulte la sección [Comportamiento de búsqueda de coincidencias de ECMAScript](#ecmascript-matching-behavior).|
|<xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant>|No disponible|Ignorar las diferencias culturales de idioma. Para obtener más información, consulte la sección [Comparación con la referencia cultural de todos los idiomas](#comparison-using-the-invariant-culture).|

## <a name="specifying-the-options"></a>Especificación de opciones

Las opciones de las expresiones regulares se pueden especificar de tres modos:

- En el parámetro `options` de un constructor de clases <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> o método de coincidencia de patrones estático (`Shared` en Visual Basic), como <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%29> o <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>. El parámetro `options` es una combinación OR bit a bit de valores enumerados de <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

  Cuando se proporcionan opciones a una instancia <xref:System.Text.RegularExpressions.Regex> mediante el parámetro `options` de un constructor de clase, las opciones se asignan a la propiedad <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>. Sin embargo, la propiedad <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> no refleja las opciones insertadas en el mismo patrón de expresión regular.

  Esto se muestra en el ejemplo siguiente. Usa el parámetro `options` del método <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra “d”.

  [!code-csharp[Conceptual.Regex.Language.Options#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#6)]
  [!code-vb[Conceptual.Regex.Language.Options#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#6)]

- Con la aplicación de las opciones insertadas en un patrón de expresión regular con la sintaxis `(?imnsx-imnsx)`. La opción se aplica al patrón a partir del punto en que la opción se define hasta el final del patrón o hasta el punto en que otra opción insertada deja a la opción sin definir. Tenga en cuenta que la propiedad <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> de una instancia <xref:System.Text.RegularExpressions.Regex> no refleja estas opciones insertadas. Para más información, consulte el tema [Construcciones misceláneas](miscellaneous-constructs-in-regular-expressions.md).

  Esto se muestra en el ejemplo siguiente. Usa opciones insertadas para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra “d”.

  [!code-csharp[Conceptual.Regex.Language.Options#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#7)]
  [!code-vb[Conceptual.Regex.Language.Options#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#7)]

- Con la aplicación de opciones insertadas en una construcción de agrupamiento determinada en un patrón de expresión regular con la sintaxis `(?imnsx-imnsx:`*subexpresión*`)`. El conjunto de opciones se activa si no va precedido por un signo y se desactiva si va precedido por un signo menos. (`?` es una parte fija de la sintaxis del constructor de lenguaje que se necesita si las opciones están habilitadas o deshabilitadas). La opción solo se aplica a ese grupo. Para más información, consulte [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md).

  Esto se muestra en el ejemplo siguiente. Usa opciones insertadas en una construcción de agrupamiento para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas, así como para ignorar el espacio en blanco del patrón a la hora de identificar palabras que empiecen por la letra “d”.

  [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
  [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]

Si las opciones están insertadas, un signo menos (`-`) antes de una opción o conjunto de opciones desactiva dichas opciones. Por ejemplo, la construcción insertada `(?ix-ms)` activa las opciones <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> y desactiva las opciones <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. Todas las opciones de expresión regular están desactivadas de forma predeterminada.

> [!NOTE]
> Si las opciones de expresión regular especificadas en el parámetro `options` de un constructor o llamada a método están en conflicto con las opciones insertadas en un patrón de expresión regular, se usan las opciones insertadas.

Las siguientes opciones de expresión regular se pueden establecer con el parámetro y mediante inserción:

- <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>

Las siguientes cinco opciones de expresión regular se pueden establecer con el parámetro `options`, pero no mediante inserción:

- <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType>

## <a name="determining-the-options"></a>Determinación de opciones

Se pueden determinar las opciones que se proporcionaron a un objeto <xref:System.Text.RegularExpressions.Regex> al crearse su instancia; para ello, recupere el valor de la propiedad <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> de solo lectura. Esta propiedad resulta especialmente útil para determinar las opciones definidas para una expresión regular compilada que se ha creado con el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>.

Para probar la presencia de cualquier opción, excepto <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, realice una operación AND con el valor de la propiedad <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> y el valor de <xref:System.Text.RegularExpressions.RegexOptions> en el que esté interesado. Después, pruebe si el resultado es igual a ese valor <xref:System.Text.RegularExpressions.RegexOptions>. En el ejemplo siguiente se prueba si se ha establecido la opción <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Regex.Language.Options#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#19)]
[!code-vb[Conceptual.Regex.Language.Options#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#19)]

Para probar <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, determine si el valor de la propiedad <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> es igual a <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, tal como se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.Regex.Language.Options#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#20)]
[!code-vb[Conceptual.Regex.Language.Options#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#20)]

En las secciones siguientes se enumeran las opciones admitidas en una expresión regular de .NET.

## <a name="default-options"></a>Opciones predeterminadas

La opción <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> indica que no se ha especificado ninguna opción y que el motor de expresiones regulares sigue su comportamiento predeterminado. Entre estas estructuras se incluyen las siguientes:

- El patrón se interpreta como un canónico en vez de como una expresión regular ECMAScript.

- El patrón de expresión regular se compara con la cadena de entrada de izquierda a derecha.

- Las comparaciones distinguen entre mayúsculas y minúsculas.

- Los elementos de lenguaje `^` y `$` coinciden con el principio y el final de la cadena de entrada.

- El elemento de lenguaje `.` coincide con todos los caracteres excepto `\n`.

- Un espacio en blanco en un patrón de expresión regular se interpreta como un carácter de espacio literal.

- Las convenciones de la referencia cultural actual se usan al comparar el patrón con la cadena de entrada.

- Los grupos de captura del patrón de expresión regular son implícitos y explícitos.

> [!NOTE]
> La opción <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> no tiene ningún equivalente de inserción. Cuando las opciones de expresión regular se aplican mediante inserción, el comportamiento predeterminado se restaura opción por opción, mediante la desactivación de una opción concreta. Por ejemplo, `(?i)` activa la comparación sin distinción entre mayúsculas y minúsculas, y `(?-i)` restaura la comparación con distinción entre mayúsculas y minúsculas.

Debido a que la opción <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> representa el comportamiento predeterminado del motor de expresiones regulares, casi nunca se especifica de forma explícita en una llamada a método. En su lugar, se llama a un constructor o método estático de coincidencia de patrones sin un parámetro `options`.

## <a name="case-insensitive-matching"></a>Coincidencia sin distinción entre mayúsculas y minúsculas

La opción <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>, o la opción insertada `i`, proporciona coincidencia sin distinción entre mayúsculas y minúsculas. De forma predeterminada, se usan las convenciones sobre el uso de mayúsculas de la referencia cultural actual.

En el ejemplo siguiente se define un patrón de expresión regular, `\bthe\w*\b`, por el que coinciden todas las palabras que empiezan por “the”. Debido a que la primera llamada al método <xref:System.Text.RegularExpressions.Regex.Match%2A> usa la comparación predeterminada con distinción entre mayúsculas y minúsculas, el resultado indica que no hay coincidencia con la cadena “The” del inicio de la oración. Hay coincidencia cuando se llama al método <xref:System.Text.RegularExpressions.Regex.Match%2A> con las opciones establecidas en <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>.

[!code-csharp[Conceptual.Regex.Language.Options#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case1.cs#1)]
[!code-vb[Conceptual.Regex.Language.Options#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case1.vb#1)]

En el ejemplo siguiente se modifica el patrón de expresión regular del ejemplo anterior a fin de usar las opciones insertadas en vez del parámetro `options` para realizar la comparación sin distinción entre mayúsculas y minúsculas. El primer parámetro define la opción sin distinción entre mayúsculas y minúsculas en una construcción de agrupamiento que se aplica solo a la letra “t” de la cadena “the”. Como la construcción de opciones ocurre al principio del patrón, el segundo patrón aplica la opción sin distinción entre mayúsculas y minúsculas a toda la expresión regular.

[!code-csharp[Conceptual.Regex.Language.Options#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case2.cs#2)]
[!code-vb[Conceptual.Regex.Language.Options#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case2.vb#2)]

## <a name="multiline-mode"></a>Modo multilínea

La opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, o la opción insertada `m`, habilita al motor de expresiones regulares para que controle una cadena de entrada que consta de varias líneas. Cambia la interpretación de los elementos de lenguaje `^` y `$` de modo que coincidan con el inicio y el final de una línea, en vez de con el inicio y el final de la cadena de entrada.

De forma predeterminada, `$` coincide solo con el final de la cadena de entrada. Si se especifica la opción <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, coincide con el carácter de nueva línea (`\n`) o con el final de la cadena de entrada. Sin embargo, no coincide con la combinación de caracteres de retorno de carro y salto de línea. Para que coincida correctamente, use la subexpresión `\r?$` en vez de simplemente `$`.

En el ejemplo siguiente se extraen los nombres y las puntuaciones de los jugadores de bolos y se agregan a una colección <xref:System.Collections.Generic.SortedList%602> que los ordena en sentido descendente. Se realizan dos llamadas al método <xref:System.Text.RegularExpressions.Regex.Matches%2A>. En la primera llamada a método, la expresión regular es `^(\w+)\s(\d+)$` y no se establece ninguna opción. Como muestra el resultado, no se encuentran coincidencias, ya que el motor de expresiones regulares no puede hacer coincidir el patrón de entrada junto con el principio y el final de la cadena de entrada. En la segunda llamada a método, la expresión regular se cambia a `^(\w+)\s(\d+)\r?$` y las opciones se establecen en <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. Como muestra el resultado, los nombres y las puntuaciones coinciden correctamente, y las puntuaciones aparecen en orden descendente.

[!code-csharp[Conceptual.Regex.Language.Options#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline1.cs#3)]
[!code-vb[Conceptual.Regex.Language.Options#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline1.vb#3)]

El patrón de expresión regular `^(\w+)\s(\d+)\r*$` se define como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-------------|-----------------|
|`^`|Comienza al principio de la línea.|
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|
|`\s`|Coincide con un carácter de espacio en blanco.|
|`(\d+)`|Buscar coincidencias con uno o más dígitos decimales. Este es el segundo grupo de captura.|
|`\r?`|Coincidencia con cero o con un carácter de retorno de carro.|
|`$`|Finaliza al final de la línea.|

El ejemplo siguiente es equivalente al anterior, a excepción de que usa la opción insertada `(?m)` para establecer la opción multilínea.

[!code-csharp[Conceptual.Regex.Language.Options#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline2.cs#4)]
[!code-vb[Conceptual.Regex.Language.Options#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline2.vb#4)]

## <a name="single-line-mode"></a>Modo de una sola línea

La opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>, o la opción insertada `s`, hace que el motor de expresiones regulares trate a la cadena de entrada como si constase de una única línea. Para ello, se cambia el comportamiento del elemento de lenguaje punto (`.`) para que coincida con todos los caracteres, en vez de coincidir con todos los caracteres excepto con el de nueva línea `\n` o \u000A.

En el ejemplo siguiente se muestra cómo cambia el comportamiento del elemento de lenguaje `.` cuando se usa la opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. La expresión regular `^.+` comienza en el principio de la cadena y coincide con todos los caracteres. De forma predeterminada, la coincidencia termina al final de la primera línea; el patrón de la expresión regular coincide con el carácter de retorno de carro, `\r` o \u000D, pero no coincide con `\n`. Dado que la opción <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> interpreta la cadena de entrada completa como una sola línea, coincide con cada carácter de la cadena de entrada, incluido `\n`.

[!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
[!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]

El ejemplo siguiente es equivalente al anterior, a excepción de que usa la opción insertada `(?s)` para habilitar el modo de una sola línea.

[!code-csharp[Conceptual.Regex.Language.Options#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/singleline1.cs#5)]
[!code-vb[Conceptual.Regex.Language.Options#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/singleline1.vb#5)]

## <a name="explicit-captures-only"></a>Solo capturas explícitas

De forma predeterminada, los grupos de captura se definen con el uso de paréntesis en el patrón de expresión regular. A los grupos con nombre se les asigna un nombre o un número con la opción de lenguaje `(?<`*nombre*`>`*subexpresión*`)`, mientras que a los grupos sin nombre se accede mediante el índice. En el objeto <xref:System.Text.RegularExpressions.GroupCollection>, los grupos sin nombre preceden a los grupos con nombre.

A menudo, los constructores de agrupamiento se usan únicamente para aplicar cuantificadores a varios elementos de lenguaje, y las subcadenas capturadas carecen de interés. Por ejemplo, en la expresión regular siguiente:

`\b\(?((\w+),?\s?)+[\.!?]\)?`

Su única finalidad es extraer de un documento las oraciones que finalizan con un punto, signo de exclamación o signo de interrogación, y solo la oración resultante (representada mediante el objeto <xref:System.Text.RegularExpressions.Match>) es de interés. En cambio, las palabras individuales de la colección no son de interés.

Los grupos de captura que no se usan posteriormente pueden ser costosos, ya que el motor de expresiones regulares debe rellenar los objetos de colección <xref:System.Text.RegularExpressions.GroupCollection> y <xref:System.Text.RegularExpressions.CaptureCollection>. Como alternativa, se puede usar la opción <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> o la opción insertada `n` para especificar que las únicas capturas válidas son grupos con nombre o número explícitos que se designan mediante la construcción `(?<`*nombre*`>` *subexpresión*`)`.

En el ejemplo siguiente se muestra información sobre las coincidencias devueltas por el patrón de expresión regular `\b\(?((\w+),?\s?)+[\.!?]\)?` cuando se llama al método <xref:System.Text.RegularExpressions.Regex.Match%2A> con y sin la opción <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>. Tal como muestra el resultado de la primera llamada a método, el motor de expresiones regulares rellena totalmente los objetos de colección <xref:System.Text.RegularExpressions.GroupCollection> y <xref:System.Text.RegularExpressions.CaptureCollection> con información sobre las subcadenas capturadas. Dado que el segundo método se llama con `options` establecido en <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>, no se captura información en grupos.

[!code-csharp[Conceptual.Regex.Language.Options#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit1.cs#9)]
[!code-vb[Conceptual.Regex.Language.Options#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit1.vb#9)]

El patrón de expresión regular `\b\(?((?>\w+),?\s?)+[\.!?]\)?` se define como se muestra en la siguiente tabla.

|Modelo|Descripción|
|-------------|-----------------|
|`\b`|Empieza en un límite de palabras.|
|`\(?`|Busca una coincidencia con cero o con una aparición de los paréntesis de apertura ("(").|
|`(?>\w+),?`|Busca una coincidencia con uno o más caracteres alfabéticos seguidos de cero o una coma. No hay retroceso al coincidir con caracteres alfabéticos.|
|`\s?`|Busca una coincidencia con cero o un carácter de espacio en blanco.|
|`((\w+),?\s?)+`|Busca una coincidencia con la combinación de uno o varios caracteres de palabra, cero o una coma, y cero o un carácter de espacio en blanco una o varias veces.|
|`[\.!?]\)?`|Busca una coincidencia con cualquiera de los tres símbolos de puntuación, seguidos de cero o un paréntesis de cierre (")").|

También se puede usar el elemento insertado `(?n)` para suprimir las capturas automáticas. En el ejemplo siguiente se modifica el patrón de expresión regular anterior para usar el elemento insertado `(?n)` en vez de la opción <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Regex.Language.Options#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit2.cs#10)]
[!code-vb[Conceptual.Regex.Language.Options#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit2.vb#10)]

Finalmente, se puede usar el elemento de grupo insertado `(?n:)` para suprimir las capturas automáticas grupo a grupo. En el ejemplo siguiente se modifica el patrón anterior para suprimir las capturas sin nombre en el grupo externo, `((?>\w+),?\s?)`. Observe que, de este modo, también se suprimen las capturas sin nombre en el grupo interno.

[!code-csharp[Conceptual.Regex.Language.Options#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit3.cs#11)]
[!code-vb[Conceptual.Regex.Language.Options#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit3.vb#11)]

## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas

Las expresiones de .NET se interpretan de forma predeterminada. Cuando se crea una instancia de un objeto <xref:System.Text.RegularExpressions.Regex> o se llama a un método <xref:System.Text.RegularExpressions.Regex> estático, el patrón de expresión regular se analiza en un conjunto de códigos de operación para ejecutar la operación regular. Esto implica una contrapartida: el coste de inicializar el motor de expresiones regulares se minimiza a costa del rendimiento en tiempo de ejecución.

Si quiere usar expresiones regulares compiladas en vez de interpretadas, utilice la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>. En este caso, cuando un patrón se pasa al motor de expresiones regulares, se analiza en un conjunto de códigos de operación y luego se convierte en Lenguaje intermedio de Microsoft (MSIL, por sus siglas en inglés), que puede pasarse directamente a Common Language Runtime. Las expresiones regulares compiladas maximizan el rendimiento en tiempo de ejecución a costa del tiempo de inicialización.

> [!NOTE]
> Una expresión regular solo se puede compilar si se suministra el valor <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> al parámetro `options` de un constructor de clases <xref:System.Text.RegularExpressions.Regex> o de un método estático de coincidencia de patrones. No está disponible como opción insertada.

Las expresiones regulares compiladas se pueden usar en llamadas a expresiones regulares estáticas y de instancias. En expresiones regulares estáticas, la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> se pasa al parámetro `options` del método de coincidencia de patrones de expresión regular. En expresiones regulares de instancia, se pasa al parámetro `options` del constructor de clases <xref:System.Text.RegularExpressions.Regex>. En ambos casos, tiene como resultado una mejora en el rendimiento.

No obstante, esta mejora en el rendimiento solo se produce bajo las condiciones siguientes:

- Un objeto <xref:System.Text.RegularExpressions.Regex> que representa una expresión regular concreta se usa en varias llamadas a métodos de coincidencia de patrones de expresión regular.

- El objeto <xref:System.Text.RegularExpressions.Regex> no puede estar fuera del ámbito y, por tanto, se puede volver a usar.

- Una expresión regular estática se usa en varias llamadas a métodos de coincidencia de patrones de expresión regular. (La mejora de rendimiento es posible porque el motor de expresiones regulares almacena en la caché las expresiones regulares que se usan en llamadas de métodos estáticos).

> [!NOTE]
> La opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> no está relacionada con el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>, que crea un ensamblado para fines especiales y que contiene expresiones regulares compiladas predefinidas.

## <a name="ignore-white-space"></a>Ignorar el espacio en blanco

De forma predeterminada, el espacio en blanco de un patrón de expresión regular es significativo; fuerza al motor de expresiones regulares a buscar un carácter de espacio en blanco en la cadena de entrada. Debido a ello, las expresiones regulares "`\b\w+\s`" y "`\b\w+`" son, en líneas generales, expresiones regulares equivalentes. Además, cuando el signo de número (#) se detecta en un patrón de expresión regular, se interpreta como un carácter literal para el que se deben buscar coincidencias.

La opción <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>, o la opción insertada `x`, cambia su comportamiento predeterminado del modo siguiente:

- El espacio en blanco sin escape del patrón de expresión regular se ignora. Para formar parte de un patrón de expresión regular, los caracteres de espacio en blanco se deben incluir en secuencias de escape (por ejemplo, como `\s` o "`\`").

- El signo de número (#) se interpreta como el inicio de un comentario, en vez de como carácter literal. Todo el texto del patrón de expresión regular comprendido entre el carácter # y el final de la cadena se interpreta como un comentario.

No obstante, en los casos siguientes, los caracteres de espacio de una expresión regular no se ignoran, aunque se use la opción <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>:

- Un espacio en blanco dentro de una clase de caracteres se interpreta siempre de forma literal. Por ejemplo, el patrón de expresión regular `[ .,;:]` coincide con cualquier carácter de espacio en blanco, punto, coma, punto y coma o dos puntos.

- Los cuantificadores entre corchetes, como `{`*n*`}`, `{`*n*`,}` y `{`*n*`,`*m*`}`, no admiten espacios en blanco. Por ejemplo, el patrón de expresión regular `\d{1, 3}` no encontrará ninguna secuencia de entre uno y tres guarismos porque contiene un carácter de espacio en blanco.

- No se admiten espacios en blanco en una secuencia de caracteres que presenta un elemento de lenguaje. Por ejemplo:

  - El elemento de lenguaje `(?:`*subexpresión*`)` representa un grupo sin captura, y la parte `(?:` del elemento no puede tener espacios insertados. El modelo `(? :`*subexpresión*`)` produce una clase <xref:System.ArgumentException> en tiempo de ejecución porque el motor de expresiones regulares no puede analizar el modelo, y el modelo `( ?:`*subexpresión*`)` no coincide con *subexpresión* .

  - El elemento de lenguaje `\p{`*nombre*`}`, que representa una categoría Unicode o bloque con nombre, no puede incluir espacios insertados en la parte `\p{` del elemento. Si se incluye un espacio en blanco, el elemento produce una <xref:System.ArgumentException> en tiempo de ejecución.

Esta opción sirve para simplificar las expresiones regulares que a menudo resultan difíciles de analizar y entender. Además, mejora la legibilidad y posibilita la documentación de una expresión regular.

Este ejemplo define el siguiente patrón de expresión regular:

`\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.`

El modelo es similar al modelo definido en la sección [Solo capturas explícitas](#explicit-captures-only) a excepción de que utiliza la opción <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> para ignorar el espacio en blanco del modelo.

[!code-csharp[Conceptual.Regex.Language.Options#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace1.cs#12)]
[!code-vb[Conceptual.Regex.Language.Options#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace1.vb#12)]

En el ejemplo siguiente se usa la opción insertada `(?x)` para ignorar el espacio en blanco del patrón.

[!code-csharp[Conceptual.Regex.Language.Options#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace2.cs#13)]
[!code-vb[Conceptual.Regex.Language.Options#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace2.vb#13)]

## <a name="right-to-left-mode"></a>Modo de derecha a izquierda

De forma predeterminada, el motor de expresiones regulares realiza las búsquedas de izquierda a derecha. Para invertir la dirección de búsqueda, se puede usar la opción <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>. De este modo, la búsqueda empieza automáticamente en la posición del último carácter de la cadena. En los métodos de coincidencia de patrones que incluyen un parámetro de posición inicial, como <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.Int32%29?displayProperty=nameWithType>, la posición inicial es el índice del carácter situado más a la derecha en el que debe empezar la búsqueda.

> [!NOTE]
> El modo de patrón de derecha a izquierda solo está disponible si se suministra el valor <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> al parámetro `options` de un constructor de clases <xref:System.Text.RegularExpressions.Regex> o de un método estático de coincidencia de patrones. No está disponible como opción insertada.

La opción <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> únicamente cambia la dirección de búsqueda, no interpreta el patrón de expresión regular de derecha a izquierda. Por ejemplo, la expresión regular `\bb\w+\s` coincide con las palabras que empiezan por la letra “b” y van seguidas por un carácter de espacio en blanco. En el ejemplo siguiente, la cadena de entrada consta de tres palabras que incluyen uno o varios caracteres “b”. La primera palabra empieza por “b”, la segunda finaliza en “b” y la tercera incluye dos caracteres “b” en el medio de la palabra. Tal como muestra el resultado del ejemplo, solo la primera palabra coincide con el patrón de expresión regular.

[!code-csharp[Conceptual.Regex.Language.Options#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft1.cs#17)]
[!code-vb[Conceptual.Regex.Language.Options#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft1.vb#17)]

Observe también que la aserción de búsqueda anticipada (el elemento de lenguaje `(?=`*subexpresión*`)`) y la aserción de búsqueda tardía (el elemento de lenguaje `(?<=`*subexpresión*`)`) no cambian de dirección. Las aserciones de búsqueda anticipada miran hacia la derecha, mientras que las de búsqueda tardía lo hacen hacia la izquierda. Por ejemplo, la expresión regular `(?<=\d{1,2}\s)\w+,?\s\d{4}` usa la aserción de búsqueda tardía para probar una fecha que precede al nombre de un mes. Después, la expresión regular busca coincidencias con el mes y el año. Para información sobre aserciones de búsqueda anticipada y tardía, consulte [Construcciones de agrupamiento](grouping-constructs-in-regular-expressions.md).

[!code-csharp[Conceptual.Regex.Language.Options#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft2.cs#18)]
[!code-vb[Conceptual.Regex.Language.Options#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft2.vb#18)]

El patrón de expresión regular se define como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-------------|-----------------|
|`(?<=\d{1,2}\s)`|El inicio de la coincidencia debe estar precedido por uno o dos dígitos decimales seguidos de un espacio.|
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|
|`,?`|Buscar coincidencias con cero o un carácter de coma.|
|`\s`|Coincide con un carácter de espacio en blanco.|
|`\d{4}`|Buscar coincidencias con cuatro dígitos decimales.|

## <a name="ecmascript-matching-behavior"></a>Comportamiento de búsqueda de coincidencias de ECMAScript

De forma predeterminada, el motor de expresiones regulares usa un comportamiento canónico al buscar coincidencias entre un patrón de expresiones regulares y el texto de entrada. Sin embargo, se puede especificar la opción <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> para hacer que el motor de expresiones regulares use el comportamiento de búsqueda de coincidencias de ECMAScript.

> [!NOTE]
> El comportamiento conforme a ECMAScript solo está disponible si se suministra el valor <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> al parámetro `options` de un constructor de clases <xref:System.Text.RegularExpressions.Regex> o de un método estático de coincidencia de patrones. No está disponible como opción insertada.

La opción <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> únicamente se puede combinar con las opciones <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. El uso de cualquier otra opción en una expresión regular provoca una <xref:System.ArgumentOutOfRangeException>.

El comportamiento de las expresiones regulares canónicas y ECMAScript se diferencia en tres aspectos: sintaxis de la clase de caracteres, grupos de captura con autorreferencia e interpretación de referencia inversa frente a octal.

- Sintaxis de la clase de caracteres. Debido a que las expresiones regulares canónicas admiten Unicode y ECMAScript no, las clases de caracteres de ECMAScript tienen una sintaxis más limitada y algunos elementos de lenguaje de clases de caracteres tienen un significado diferente. Por ejemplo, ECMAScript no admite elementos de lenguaje como la categoría Unicode ni elementos como `\p` y `\P`. De igual modo, el elemento `\w`, que coincide con un carácter literal, es equivalente a la clase de caracteres `[a-zA-Z_0-9]` al usar ECMAScript y a `[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]` al usar comportamiento canónico. Para más información, consulte [Clases de caracteres](character-classes-in-regular-expressions.md).

  En el ejemplo siguiente se muestra la diferencia entre la búsqueda de coincidencias canónica y la de ECMAScript. Se define una expresión regular, `\b(\w+\s*)+`, que busca coincidencias con palabras seguidas de caracteres de espacio en blanco. La entrada consta de dos cadenas: una que usa el conjunto de caracteres latinos y otra que usa el conjunto de caracteres del cirílico. Tal como muestra el resultado, la llamada al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> que usa la búsqueda de coincidencias de ECMAScript no encuentra coincidencias con las palabras del cirílico, mientras que la llamada al método que usa la búsqueda de coincidencias canónica sí encuentra coincidencias con estas palabras.

  [!code-csharp[Conceptual.Regex.Language.Options#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript1.cs#16)]
  [!code-vb[Conceptual.Regex.Language.Options#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript1.vb#16)]

- Grupos de captura con autorreferencia. Una clase de captura de expresión regular con una referencia inversa a sí misma debe actualizarse con cada iteración de captura. Como se muestra en el ejemplo siguiente, esta característica permite a la expresión regular `((a+)(\1) ?)+` coincidir con la cadena “ aa aaaa aaaaaa ” si se usa ECMAScript, pero no si se usa la búsqueda de coincidencias canónica.

  [!code-csharp[Conceptual.Regex.Language.Options#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript2.cs#21)]
  [!code-vb[Conceptual.Regex.Language.Options#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript2.vb#21)]

  La expresión regular se define como se muestra en la tabla siguiente.

  |Modelo|Descripción|
  |-------------|-----------------|
  |(a+)|Busca una coincidencia con la letra “a” una o más veces. Este es el segundo grupo de captura.|
  |(\1)|Busca una coincidencia con la subcadena capturada por el primer grupo de captura. Éste es el tercer grupo de captura.|
  |?|Busca una coincidencia con cero o un carácter de espacio.|
  |((a+)(\1) ?)+|Busca una coincidencia con el patrón de uno o varios caracteres “a” seguidos por una cadena que coincide con el primer grupo de captura seguido por cero o por un carácter de espacio una o varias veces. Este es el primer grupo de captura.|

- Resolución de ambigüedades entre secuencias de escape octales y referencias inversas. En la tabla siguiente se indican las diferencias en la interpretación de referencia inversa frente a octal por parte de expresiones regulares canónicas y de ECMAScript.

  |Expresión regular|Comportamiento canónico|Comportamiento de ECMAScript|
  |------------------------|------------------------|-------------------------|
  |`\0` seguido de 0 a 2 dígitos octales|Se interpreta como un octal. Por ejemplo, `\044` se interpreta siempre como un valor octal y significa “$”.|Mismo comportamiento.|
  |`\` seguido de un dígito de 1 a 9, seguido de ningún dígito decimal adicional|Se interpreta como una referencia inversa. Por ejemplo, `\9` siempre significa una referencia inversa de 9, incluso si no existe un noveno grupo de captura. Si el grupo de captura no existe, el analizador de expresiones regulares produce una <xref:System.ArgumentException>.|Si existe un grupo de captura de un solo dígito decimal, realice una referencia inversa a ese dígito. De lo contrario, interprete el valor como literal.|
  |`\` seguido de un dígito de 1 a 9, seguido de dígitos decimales adicionales|Interprete los dígitos como un valor decimal. Si existe ese grupo de captura, interprete la expresión como una referencia inversa.<br /><br /> De lo contrario, interprete los dígitos octales iniciales hasta el octal 377; es decir, tenga en cuenta solo los 8 bits inferiores del valor. Interprete el resto de dígitos como literales. Por ejemplo, en la expresión `\3000`, si existe el grupo de captura 300, interprételo como referencia inversa de 300; si el grupo de captura 300 no existe, interprételo como un octal 300 seguido de 0.|Para interpretarlo como una referencia inversa, convierta todos los dígitos posibles en un valor decimal que pueda hacer referencia a una captura. Si no se puede convertir ningún dígito, interprételo como un octal; para ello, use los dígitos octales iniciales hasta el octal 377 e interprete el resto de dígitos como literales.|

## <a name="comparison-using-the-invariant-culture"></a>Comparación con la referencia cultural de todos los idiomas

De forma predeterminada, el motor de expresiones regulares, cuando realiza comparaciones sin distinguir entre mayúsculas y minúsculas, utiliza las convenciones sobre el uso de mayúsculas de la referencia cultural actual con el fin de determinar los caracteres equivalentes en mayúscula y minúscula.

Sin embargo, este comportamiento no es el deseado en algunos tipos de comparaciones, en particular al comparar la entrada del usuario con los nombres de recursos del sistema, como pueden ser contraseñas, archivos o direcciones URL. En el ejemplo siguiente se muestra ese escenario. La finalidad del código es bloquear el acceso a los recursos cuya dirección URL va precedida de **FILE://** . La expresión regular intenta una búsqueda de coincidencias con la cadena sin distinguir entre mayúsculas y minúsculas y, a tal fin, usa la expresión `$FILE://`. Sin embargo, cuando la referencia cultural actual del sistema es tr-TR (Turco -Turquía), “I” no es el equivalente en mayúscula de “i”. Como resultado, la llamada al método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> devuelve `false`, con lo que se permite el acceso al archivo.

[!code-csharp[Conceptual.Regex.Language.Options#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#14)]
[!code-vb[Conceptual.Regex.Language.Options#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#14)]

> [!NOTE]
> Para obtener más información sobre la comparación de cadenas con distinción entre mayúsculas y minúsculas, y con la referencia cultural de todos los idiomas, consulte [Procedimientos recomendados para el uso de cadenas](best-practices-strings.md).

En vez de usar comparaciones sin distinción entre mayúsculas y minúsculas de la referencia cultural actual, se puede especificar la opción <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType> para ignorar las diferencias culturales de idioma y usar las convenciones de la referencia cultural de todos los idiomas.

> [!NOTE]
> La comparación con la referencia cultural de todos los idiomas solo está disponible si se suministra el valor <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType> al parámetro `options` de un constructor de clases <xref:System.Text.RegularExpressions.Regex> o de un método estático de coincidencia de patrones. No está disponible como opción insertada.

El ejemplo siguiente es idéntico al anterior, excepto que se llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> estático con opciones que incluyen <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>. A pesar de que la referencia cultural actual está establecida en turco (Turquía), el motor de expresiones regulares es capaz de encontrar coincidencias con “FILE” y “file” y bloquear el acceso al recurso de archivo.

[!code-csharp[Conceptual.Regex.Language.Options#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#15)]
[!code-vb[Conceptual.Regex.Language.Options#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#15)]

## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
