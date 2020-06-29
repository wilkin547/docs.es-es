---
title: Introducción a la codificación de caracteres en .NET
description: Obtenga información sobre la codificación y descodificación de caracteres en .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 85349e1e1c4eca4dd3ef7980f48350a4145fca24
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599872"
---
# <a name="character-encoding-in-net"></a>Codificación de caracteres de .NET

En este artículo se proporciona una introducción a los sistemas de codificación de caracteres que se usan con .NET. Se explica cómo funcionan los tipos <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> y <xref:System.Globalization.StringInfo> con Unicode, UTF-16 y UTF-8.

El término *carácter* se usa aquí en el sentido general de *lo que un lector percibe como un solo elemento de presentación*. Algunos ejemplos comunes son la letra "a", el símbolo "@" y el emoji "🐂". A veces, lo que parece un carácter consta en realidad de varios elementos de visualización independientes, como se explica en la sección sobre los [clústeres de grafemas](#grapheme-clusters).

## <a name="the-string-and-char-types"></a>Tipos string y char

Una instancia de la clase [string](xref:System.String) representa texto. Un elemento `string` es de forma lógica una secuencia de valores de 16 bits, cada uno de los cuales es una instancia de la estructura [char](xref:System.Char). La propiedad [string.Length](xref:System.String.Length) devuelve el número de instancias `char` de la instancia `string`.

La función de ejemplo siguiente imprime los valores en notación hexadecimal de todas las instancias de `char` en una instancia de `string`:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

Pase el elemento string "Hello" a esta función y obtendrá el siguiente resultado:

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

Cada carácter se representa mediante un solo valor de `char`. Ese patrón se aplica a la mayoría de los idiomas del mundo. Por ejemplo, esta es la salida de dos caracteres chinos que suenan como *nǐ hǎo* y significan *Hello*:

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

Sin embargo, en algunos lenguajes y en algunos símbolos y emoji, se necesitan dos instancias de `char` para representar un único carácter. Por ejemplo, compare los caracteres y las instancias de `char` de la palabra que significa *Osage* en el idioma Osage:

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

En el ejemplo anterior, cada carácter excepto el espacio se representa mediante dos instancias de `char`.

Un solo emoji Unicode se representa mediante dos instancias de `char`, tal como se ilustra en el ejemplo siguiente, que muestra un emoji de buey:

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

En estos ejemplos se muestra que el valor de `string.Length`, que indica el número de instancias de `char`, no indica necesariamente el número de caracteres mostrados. Una sola instancia de `char` no representa necesariamente un carácter.

Los pares de `char` que se asignan a un único carácter se denominan *pares suplentes*. Para entender cómo funcionan, debe comprender la codificación Unicode y UTF-16.

## <a name="unicode-code-points"></a>Puntos de código Unicode

Unicode es un estándar de codificación internacional que se usa en varias plataformas y con varios idiomas y scripts.

El estándar Unicode define más de 1,1 millones de [puntos de código](https://www.unicode.org/glossary/#code_point). Un punto de código es un valor entero comprendido entre 0 y `U+10FFFF` (decimal 1.114.111). Algunos puntos de código se asignan a letras, símbolos o emoji. Otros se asignan a acciones que controlan el modo en que se muestra el texto o los caracteres, como el avance a una nueva línea. Muchos puntos de código todavía no se han asignado.

Estos son algunos ejemplos de asignaciones de puntos de código, con vínculos a gráficos Unicode en los que aparecen:

|Decimal|Hex       |Ejemplo|Descripción|
|------:|----------|-------|-----------|
|10     | `U+000A` |N/D| [LINE FEED](https://www.unicode.org/charts/PDF/U0000.pdf) |
|65     | `U+0061` | a | [LATIN SMALL LETTER A](https://www.unicode.org/charts/PDF/U0000.pdf) |
|562    | `U+0232` | Ȳ | [LATIN CAPITAL LETTER Y WITH MACRON](https://www.unicode.org/charts/PDF/U0180.pdf) |
|68.675 | `U+10C43`| 𐱃 | [OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|127.801| `U+1F339`| 🌹 | [ROSE emoji](https://www.unicode.org/charts/PDF/U1F300.pdf) |

Normalmente se hace referencia a los puntos de código mediante la sintaxis `U+xxxx`, donde `xxxx` es el valor entero con codificación hexadecimal.

Dentro del intervalo completo de puntos de código hay dos subintervalos:

* El **plano básico multilingüe (BMP)** en el intervalo `U+0000..U+FFFF`. Este intervalo de 16 bits proporciona 65 536 puntos de código, suficientes para cubrir la mayoría de los sistemas de escritura del mundo.
* Los **puntos de código suplementarios** en el intervalo `U+10000..U+10FFFF`. Este intervalo de 21 bits proporciona más de un millón de puntos de código adicionales que se pueden usar con idiomas menos conocidos y otros fines, como los emoji.

En el diagrama siguiente se ilustra la relación entre el BMP y los puntos de código suplementarios.

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP y puntos de código suplementarios":::

## <a name="utf-16-code-units"></a>Unidades de código UTF-16

El formato de transformación Unicode de 16 bits ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) es un sistema de codificación de caracteres que emplea *unidades de código* de 16 bits para representar puntos de código Unicode. .NET usa UTF-16 para codificar el texto de una instancia de `string`. Una instancia de `char` representa una unidad de código de 16 bits.

Una sola unidad de código de 16 bits puede representar cualquier punto de código en el intervalo de 16 bits del plano básico multilingüe. Sin embargo, un punto de código en el intervalo suplementario necesita dos instancias de `char`.

## <a name="surrogate-pairs"></a>Pares suplentes

La conversión de dos valores de 16 bits en un único valor de 21 bits se facilita mediante un intervalo especial denominado *puntos de código suplentes*, de `U+D800` a `U+DFFF` (decimal 55.296 a 57.343), ambos incluidos.

En el diagrama siguiente se ilustra la relación entre el BMP y los puntos de código suplentes.

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP y los puntos de código suplentes":::

Cuando un punto de código *suplente superior* (`U+D800..U+DBFF`) va seguido inmediatamente por un punto de código *suplente inferior* (`U+DC00..U+DFFF`), el par se interpreta como un punto de código suplementario mediante la fórmula siguiente:

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

Esta es la misma fórmula, pero con notación decimal:

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

Un punto de código suplente *superior* no tiene un valor numérico mayor que un punto de código suplente *inferior*. El punto de código suplente superior se denomina así porque se usa para calcular los 11 bits de orden superior del intervalo completo de puntos de código de 21 bits. El punto de código suplente inferior se usa para calcular los 10 bits de orden inferior.

Por ejemplo, el punto de código real que corresponde al par suplente `0xD83C` y `0xDF39` se calcula de la manera siguiente:

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

Este es el mismo cálculo, pero con notación decimal:

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

En el ejemplo anterior se muestra que `"\ud83c\udf39"` es la codificación UTF-16 del punto de código `U+1F339 ROSE ('🌹')` mencionado anteriormente.

## <a name="unicode-scalar-values"></a>Valores escalares Unicode

El término [valor escalar Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) hace referencia a todos los puntos de código distintos de los puntos de código suplentes. En otras palabras, un valor escalar es cualquier punto de código al que se le asigna un carácter o se le puede asignar en el futuro. Aquí "carácter" hace referencia a todo lo que se puede asignar a un punto de código, lo que incluye cosas como acciones que controlan cómo se muestra el texto o los caracteres.

En el diagrama siguiente se muestran los puntos de código de valor escalar.

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Valores escalares":::

### <a name="the-rune-type-as-a-scalar-value"></a>El tipo Rune como un valor escalar.

A partir de .NET Core 3.0, el tipo <xref:System.Text.Rune?displayProperty=fullName> representa un valor escalar Unicode. **`Rune` no está disponible en .NET Core 2. x o .NET Framework 4.x.**

Los constructores `Rune` validan que la instancia resultante sea un valor escalar Unicode válido; de lo contrario, inician una excepción. En el ejemplo siguiente se muestra código que crea una instancia correcta de las instancias de `Rune` porque la entrada representa valores escalares válidos:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

En el siguiente ejemplo se produce una excepción porque el punto de código está en el intervalo suplente y no es parte de un par suplente:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

En el siguiente ejemplo se produce una excepción porque el punto de código está por encima del intervalo suplementario:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="rune-usage-example-changing-letter-case"></a>Ejemplo de uso de Rune: cambio de las mayúsculas y minúsculas.

Una API que toma una instancia de `char` y da por supuesto que trabaja con un punto de código que es un valor escalar no funciona correctamente si `char` procede de un par suplente. Por ejemplo, considere el siguiente método que llama a <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> en cada char en una instancia de string:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

Si string de `input` contiene la letra minúscula `er` de Deseret (`𐑉`), este código no lo convertirá a mayúsculas (`𐐡`). El código llama a `char.ToUpperInvariant` por separado en cada punto de código suplente, `U+D801` y `U+DC49`. Sin embargo, `U+D801` no tiene suficiente información para identificarlo como una letra minúscula, por lo que `char.ToUpperInvariant` lo deja así. Y trata `U+DC49` de la misma manera. El resultado es que la "𐑉" minúscula de la instancia de string de `input` no se convierte a "𐐡" mayúscula.

A continuación se muestran dos opciones para convertir correctamente una instancia de string a mayúsculas:

* Llame a <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> en la instancia de string de entrada en lugar de recorrer en iteración `char` mediante `char`. El método `string.ToUpperInvariant` tiene acceso a ambas partes de cada par suplente, por lo que puede tratar correctamente todos los puntos de código Unicode.
* Recorra en iteración los valores escalares Unicode como instancias de `Rune` y no de `char`, como se muestra en el ejemplo siguiente. Dado que una instancia de `Rune` es un valor escalar Unicode válido, se puede pasar a las API que esperan operar en un valor escalar. Por ejemplo, al llamar a <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType>, como se ilustra en el ejemplo siguiente, se muestran los resultados correctos:

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-rune-apis"></a>Otras API de Rune

El tipo `Rune` expone las analogías de muchas de las API de `char`. Por ejemplo, los métodos siguientes reflejan las API estáticas en el tipo `char`:

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

Para obtener el valor escalar sin formato de una instancia de `Rune`, utilice la propiedad <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType>.

Para volver a convertir una instancia de `Rune` en una secuencia de instancias de `char`, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> o el método <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType>.

Dado que cualquier valor escalar Unicode se puede representar con una sola instancia de `char` o mediante un par suplente, cualquier instancia de `Rune` se puede representar como máximo con 2 instancias de `char`. Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> para ver el número de instancias de `char` necesarias para representar una instancia de `Rune`.

Para más información sobre el tipo `Rune` de .NET, consulte la referencia de API [`Rune`](xref:System.Text.Rune).

## <a name="grapheme-clusters"></a>Clústeres de grafemas

Lo que parece un carácter podría ser el resultado de una combinación de varios puntos de código, por lo que un término más descriptivo que se usa a menudo en lugar de "carácter" es [clúster de grafemas](https://www.unicode.org/glossary/#grapheme_cluster). El término equivalente en .NET es [elemento de texto](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).

Tenga en cuenta las instancias de `string` "a", "á". "á" y "`👩🏽‍🚒`". Si el sistema operativo las trata como se especifica en el estándar Unicode, cada una de estas instancias de `string` aparece como un solo elemento de texto o clúster de grafemas. Sin embargo, las dos últimas están representadas por más de un punto de código de valor escalar.

* La instancia "a" de string está representada por un valor escalar y contiene una instancia de `char`.

  * `U+0061 LATIN SMALL LETTER A`

* La instancia "á" de string está representada por un valor escalar y contiene una instancia de `char`.

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* La instancia "á" de string parece igual que "á" pero está representada por dos valores escalares y contiene dos instancias de `char`.

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* Por último, la instancia "`👩🏽‍🚒`" de string está representada por cuatro valores y contiene siete instancias de `char`.

  * `U+1F469 WOMAN` (intervalo suplementario, requiere un par suplente)
  * `U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (intervalo suplementario, requiere un par suplente)
  * `U+200D ZERO WIDTH JOINER`
  * `U+1F692 FIRE ENGINE` (intervalo suplementario, requiere un par suplente)

En algunos de los ejemplos anteriores, como el de la combinación del modificador del acento o el modificador del tono de piel, el punto de código no se muestra como un elemento independiente en la pantalla, sino que sirve para modificar el aspecto de un elemento de texto que venía antes. En estos ejemplos se muestra que puede tomar varios valores escalares para componer lo que consideramos un solo "carácter" o un "clúster de grafemas".

Para enumerar los clústeres de grafemas de una instancia de `string`, use la clase <xref:System.Globalization.StringInfo> como se muestra en el ejemplo siguiente. Si está familiarizado con Swift, el tipo `StringInfo` de .NET es conceptualmente similar al tipo `character` de [Swift](https://developer.apple.com/documentation/swift/character).

### <a name="example-count-char-rune-and-text-element-instances"></a>Ejemplo: recuento de instancias de elementos char, Rune y de texto

En las API de .NET, un clúster de grafemas se conoce como *elemento de texto*. El método siguiente muestra las diferencias entre las instancias de elementos `char`, `Rune` y de texto en una instancia de `string`:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

Si ejecuta este código en .NET Framework o .NET Core 3.1 o una versión anterior, el recuento de elementos de texto para el emoji muestra `4`. Esto se debe a un error en la clase `StringInfo` que se ha corregido en .NET 5.

### <a name="example-splitting-string-instances"></a>Ejemplo: división de las instancias de string

Al dividir las instancias de `string`, evite dividir los pares suplentes y los clústeres de grafemas. Considere el siguiente ejemplo de código incorrecto, que intenta insertar saltos de línea cada 10 caracteres en una instancia de string:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

Dado que este código enumera instancias de `char`, un par suplente que abarca un límite de 10 instancias de `char` se dividirá y una nueva línea se insertará entre ellas. Esta inserción introduce daños en los datos, porque los puntos de código suplentes solo son significativos como pares.

No se elimina la posibilidad de daños en los datos si se enumeran instancias de `Rune` (valores escalares) en lugar de instancias de `char`. Un conjunto de instancias de `Rune` podría constituir un clúster de grafemas que abarca un límite de 10 instancias de `char`. Si el conjunto de clústeres de grafemas está dividido, no se podrá interpretar correctamente.

Lo mejor sería romper la instancia de string mediante el recuento de clústeres de grafemas, o elementos de texto, como en el ejemplo siguiente:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

Como se indicó anteriormente, sin embargo, en implementaciones de .NET distintas de .NET 5, la clase `StringInfo` podría tratar de forma incorrecta algunos clústeres de grafemas.

## <a name="utf-8-and-utf-32"></a>UTF-8 y UTF-32

Las secciones anteriores se centraban en UTF-16 porque es lo que usa .NET para codificar instancias de `string`. Existen otros sistemas de codificación para Unicode: [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) y [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32). Estas codificaciones usan unidades de código de 8 bits y unidades de código de 32 bits, respectivamente.

Al igual que UTF-16, UTF-8 requiere varias unidades de código para representar algunos valores escalares Unicode. UTF-32 puede representar cualquier valor escalar en una sola unidad de código de 32 bits.

Estos son algunos ejemplos en los que se muestra cómo se representa el mismo punto de código Unicode en cada uno de estos tres sistemas de codificación Unicode:

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

Como se indicó anteriormente, una única unidad de código UTF-16 de un [par suplente](#surrogate-pairs) no tiene sentido. Del mismo modo, una sola unidad de código UTF-8 no tiene sentido si se encuentra en una secuencia de dos, tres o cuatro usadas para calcular un valor escalar.

### <a name="endianness"></a>Modos endian

En .NET, las unidades de código UTF-16 de una instancia de string se almacenan en memoria contigua como una secuencia de enteros de 16 bits (instancias de `char`). Los bits de las unidades de código individuales se disponen de acuerdo con el [modo endian](https://en.wikipedia.org/wiki/Endianness) de la arquitectura actual.

En una arquitectura little-endian, la instancia de string que consta de los puntos de código UTF-16 `[ D801 DCCC ]` se dispondría en memoria como los bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`. En una arquitectura big-endian, la misma instancia de string se dispondría en memoria como los bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.

Los sistemas informáticos que se comunican entre sí deben estar de acuerdo con la representación de los datos que atraviesan la conexión. La mayoría de los protocolos de red usan UTF-8 como estándar al transmitir texto, en parte para evitar problemas que podrían derivarse de una máquina big-endian que se comunica con una máquina little-endian. La instancia de string que consta de los puntos de código UTF-8 `[ F0 90 93 8C ]` siempre se representará como los bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` con independencia del modo endian.

Para usar UTF-8 para transmitir texto, las aplicaciones .NET a menudo usan código como el del ejemplo siguiente:

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

En el ejemplo anterior, el método [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) descodifica de nuevo la instancia de `string` UTF-16 en una serie de valores escalares Unicode, después vuelve a codificar esos valores escalares en UTF-8 y coloca la secuencia resultante en una matriz de `byte`. El método [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) realiza la transformación opuesta, al convertir una matriz de `byte` UTF-8 en una instancia de `string` UTF-16.

> [!WARNING]
> Dado que UTF-8 es habitual en Internet, puede resultar tentador leer los bytes sin formato de la conexión y tratar los datos como si fueran UTF-8. Sin embargo, debe validar que el formato es correcto. Un cliente malintencionado podría enviar UTF-8 con un formato incorrecto a su servicio. Si trabaja en esos datos como si tuvieran el formato correcto, podría provocar errores o vulnerabilidades de seguridad en la aplicación. Para validar los datos UTF-8, puede usar un método como `Encoding.UTF8.GetString`, que realizará la validación mientras convierte los datos entrantes en una instancia de `string`.

### <a name="well-formed-encoding"></a>Codificación con un formato correcto

Una codificación Unicode con un formato correcto es una instancia de string de unidades de código que se puede descodificar de forma inequívoca y sin errores en una secuencia de valores escalares Unicode. Los datos con un formato correcto se pueden transcodificar libremente entre UTF-8, UTF-16 y UTF-32.

La cuestión de si una secuencia de codificación tiene el formato correcto o no está relacionada con el modo endian de la arquitectura de una máquina. Una secuencia UTF-8 mal formada tiene un formato incorrecto tanto en máquinas big-endian como little-endian.

Estos son algunos ejemplos de codificaciones con un formato incorrecto:

* En UTF-8, la secuencia `[ 6C C2 61 ]` tiene un formato incorrecto porque `C2` no puede ir seguido de `61`.

* En UTF-16, la secuencia `[ DC00 DD00 ]` (o, en C#, la instancia de string `"\udc00\udd00"`) tiene un formato incorrecto porque el suplente inferior `DC00` no puede ir seguido de otro suplente inferior `DD00`.

* En UTF-32, la secuencia `[ 0011ABCD ]` tiene un formato incorrecto porque `0011ABCD` está fuera del intervalo de valores escalares Unicode.

En .NET, las instancias de `string` casi siempre contienen datos UTF-16 con un formato correcto, pero no se garantiza. En los siguientes ejemplos se muestra un código válido de C# que crea datos UTF-16 con un formato incorrecto en instancias de `string`.

* Un literal con un formato incorrecto:

  ```csharp
  const string s = "\ud800";
  ```

* Una subcadena que divide un par suplente:

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

Las API como [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) nunca devuelven instancias de `string` con un formato incorrecto. Los métodos `Encoding.GetString` y `Encoding.GetBytes` detectan secuencias con un formato incorrecto en la entrada y realizan la sustitución de caracteres al generar la salida. Por ejemplo, si [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) observa un byte no ASCII en la entrada (fuera del intervalo de U+0000..U+007F), inserta un "?" en la instancia de `string` devuelta. [`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) reemplaza las secuencias UTF-8 con un formato incorrecto por `U+FFFD REPLACEMENT CHARACTER ('�')` en la instancia de `string` devuelta. Para más información, consulte [el estándar Unicode](https://www.unicode.org/versions/latest/), secciones 5.22 y 3.9.

Las clases `Encoding` integradas también se pueden configurar para producir una excepción en lugar de realizar la sustitución de caracteres cuando se observan secuencias con un formato incorrecto. Este enfoque se suele usar en aplicaciones que dependen de la seguridad donde la sustitución de caracteres podría no ser aceptable.

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

Para información sobre cómo usar las clases `Encoding` integradas, consulte [Uso de las clases de codificación de caracteres en .NET](character-encoding.md).

## <a name="see-also"></a>Vea también

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [Globalización y localización](../globalization-localization/index.md)
