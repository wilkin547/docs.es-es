---
title: Cadenas
description: Obtenga información sobre cómo el tipo de "cadena" de F, representa el texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739574"
---
# <a name="strings"></a>Cadenas

> [!NOTE]
> Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode. `string` es un alias de `System.String` en .NET Framework.

## <a name="remarks"></a>Observaciones

Los literales de cadena están delimitados por el carácter de comillas ("). El carácter \\ de barra diagonal inversa ( ) se utiliza para codificar ciertos caracteres especiales. La barra diagonal inversa y el siguiente carácter juntos se conocen como una secuencia de *escape.* En la tabla siguiente se muestran las secuencias de escape admitidas en los literales de cadena de F.

|Carácter|Secuencia de escape|
|---------|---------------|
|Alerta|`\a`|
|Retroceso|`\b`|
|Avance de página|`\f`|
|Nueva línea|`\n`|
|Retorno de carro|`\r`|
|Pestaña|`\t`|
|Tabulación vertical|`\v`|
|Barra diagonal inversa|`\\`|
|Comillas|`\"`|
|Apóstrofo|`\'`|
|carácter Unicode|`\DDD`(donde `D` indica un dígito decimal; rango de 000 - `\231` 255; por ejemplo, á "o")|
|carácter Unicode|`\xHH`(donde `H` se indica un dígito hexadecimal; rango de `\xE7` 00 - FF; por ejemplo, á "o")|
|carácter Unicode|`\uHHHH`(UTF-16) (donde `H` indica un dígito hexadecimal; rango de 0000 - FFFF;  por ejemplo, `\u00E7` "a")|
|carácter Unicode|`\U00HHHHHH`(UTF-32) (donde `H` indica un dígito hexadecimal; rango de 000000 - 10FFFF;  por ejemplo, `\U0001F47D` 👽" ")|

> [!IMPORTANT]
> La `\DDD` secuencia de escape es notación decimal, no notación octal como en la mayoría de los otros idiomas. Por lo `8` `9` tanto, los dígitos `\032` y son válidos, y una secuencia de representa un espacio (U+0020), mientras que ese mismo punto de código en notación octal sería `\040`.

> [!NOTE]
> Al estar restringidos a un rango de 0 - `\DDD` `\x` 255 (0xFF), las secuencias y las secuencias de escape son efectivamente el juego de caracteres [ISO-8859-1,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) ya que coincide con los primeros 256 puntos de código Unicode.

## <a name="verbatim-strings"></a>Cuerdas literales

Si va precedido por el símbolo de la tecla , el literal es una cadena literal. Esto significa que se omiten las secuencias de escape, excepto que dos caracteres de comillas se interpretan como un carácter de comillas.

## <a name="triple-quoted-strings"></a>Cuerdas triples citadas

Además, una cadena puede estar entre comillas triples. En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles. Para especificar una cadena que contenga una cadena entre comillas incrustada, puede usar una cadena literal o una cadena de comillas triples. Si utiliza una cadena literal, debe especificar dos caracteres de comillas para indicar un carácter de comillas simples. Si utiliza una cadena de comillas triples, puede usar los caracteres de comillas simples sin que se analicen como el final de la cadena. Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

En el código, se aceptan cadenas que tienen saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea. El espacio en blanco inicial en la siguiente línea se omite cuando se utiliza el carácter de barra diagonal inversa. El código siguiente genera `str1` una `"abc\ndef"` cadena que `str2` tiene `"abcdef"`valor y una cadena que tiene valor .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>Indización y segmentación de cadenas

Puede tener acceso a caracteres individuales en una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

El resultado es `b`

O bien, puede extraer subcadenas mediante la sintaxis de sector de matriz, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

La salida es la siguiente.

```console
abc
def
```

Puede representar cadenas ASCII mediante matrices de `byte[]`bytes sin signo, escriba . Agregue el `B` sufijo a un literal de cadena para indicar que es una cadena ASCII. Los literales de cadena ASCII utilizados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operadores de cuerdas

El `+` operador se puede usar para concatenar cadenas, manteniendo la compatibilidad con las características de control de cadenas de .NET Framework. En el ejemplo siguiente se muestra la concatenación de cadenas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>Clase String

Debido a que el tipo de cadena `System.String` en F `System.String` es en realidad un tipo de .NET Framework, todos los miembros están disponibles. Esto incluye `+` el operador, que se utiliza `Length` para concatenar cadenas, la propiedad y la `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode. Para obtener más información `System.String`acerca de las cadenas, consulte .

Mediante el `Chars` uso `System.String`de la propiedad de , puede tener acceso a los caracteres individuales de una cadena especificando un índice, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Módulo de cadena

La funcionalidad adicional para el `String` control de `FSharp.Core` cadenas se incluye en el módulo del espacio de nombres. Para obtener más información, vea [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje f](index.md)
