---
title: Cadenas
description: Obtenga información sobre F# cómo el tipo ' cadena ' representa texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452823"
---
# <a name="strings"></a>Cadenas

> [!NOTE]
> Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

El tipo de `string` representa el texto inmutable como una secuencia de caracteres Unicode. `string` es un alias de `System.String` en .NET Framework.

## <a name="remarks"></a>Observaciones

Los literales de cadena se delimitan mediante el carácter de Comillas ("). El carácter de barra diagonal inversa (\\) se usa para codificar determinados caracteres especiales. La barra diagonal inversa y el siguiente carácter juntos se conocen como una *secuencia de escape*. En la tabla siguiente F# se muestran las secuencias de escape que se admiten en literales de cadena.

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
|Ni|`\'`|
|carácter Unicode|`\DDD` (donde `D` indica un dígito decimal; intervalo de 000-255; por ejemplo, `\231` = "ç")|
|carácter Unicode|`\xHH` (donde `H` indica un dígito hexadecimal; intervalo de 00-FF; por ejemplo, `\xE7` = "ç")|
|carácter Unicode|`\uHHHH` (UTF-16) (donde `H` indica un dígito hexadecimal; rango de 0000-FFFF;  por ejemplo, `\u00E7` = "ç")|
|carácter Unicode|`\U00HHHHHH` (UTF-32) (donde `H` indica un dígito hexadecimal; intervalo de 000000-10FFFF;  por ejemplo, `\U0001F47D` = "👽")|

> [!IMPORTANT]
> La secuencia de escape `\DDD` es notación decimal, no notación octal como en la mayoría de los demás lenguajes. Por lo tanto, los dígitos `8` y `9` son válidos, y una secuencia de `\032` representa un espacio (U + 0020), mientras que el mismo punto de código en la notación octal sería `\040`.

> [!NOTE]
> Al estar restringido a un intervalo de 0-255 (0xFF), las secuencias de escape `\DDD` y `\x` son, de hecho, el juego de caracteres [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , ya que coincide con los primeros 256 puntos de código Unicode.

## <a name="verbatim-strings"></a>Cadenas textuales

Si va precedido por el símbolo @, el literal es una cadena textual. Esto significa que se omiten las secuencias de escape, salvo que dos caracteres de Comillas se interpretan como un carácter de comilla.

## <a name="triple-quoted-strings"></a>Triples cadenas entre comillas

Además, una cadena se puede incluir entre comillas triples. En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles. Para especificar una cadena que contenga una cadena entrecomillada insertada, puede usar una cadena textual o una cadena entre comillas triples. Si utiliza una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple. Si utiliza una cadena entre comillas triples, puede utilizar los caracteres de comilla simple sin analizarlos como el final de la cadena. Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

En el código, se aceptan cadenas con saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea. El espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa. El código siguiente genera un `str1` de cadena que tiene `"abc\ndef"` de valor y un `str2` de cadena que tiene `"abcdef"`de valor.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>Indización y segmentación de cadenas

Puede tener acceso a caracteres individuales de una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

El resultado es `b`

O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

La salida es la siguiente.

```console
abc
def
```

Puede representar cadenas ASCII por matrices de bytes sin signo, escriba `byte[]`. Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII. Los literales de cadena ASCII usados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operadores de cadena

Hay dos maneras de concatenar cadenas: mediante el operador `+` o mediante el operador `^`. El operador `+` mantiene la compatibilidad con las características de control de cadenas .NET Framework.

En el ejemplo siguiente se muestra la concatenación de cadenas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String (clase)

Dado que el tipo de F# cadena en es realmente un .NET Framework tipo de `System.String`, todos los miembros de `System.String` están disponibles. Esto incluye el operador `+`, que se usa para concatenar cadenas, la propiedad `Length` y la propiedad `Chars`, que devuelve la cadena como una matriz de caracteres Unicode. Para obtener más información sobre las cadenas, vea `System.String`.

Mediante el uso de la propiedad `Chars` de `System.String`, puede tener acceso a los caracteres individuales de una cadena especificando un índice, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Módulo de cadena

En el módulo `String` del espacio de nombres `FSharp.Core` se incluye funcionalidad adicional para el control de cadenas. Para obtener más información, vea [módulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje F#](index.md)
