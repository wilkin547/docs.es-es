---
title: Cadenas (F#)
description: "Obtenga información sobre cómo el tipo 'string' F # representa texto inmutable como una secuencia de caracteres Unicode."
ms.date: 05/16/2016
ms.openlocfilehash: 21971602093bc84b0df47d4ae46a14fb936c28bb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799348"
---
# <a name="strings"></a>Cadenas

> [!NOTE]
Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode. `string` es un alias de `System.String` en .NET Framework.

## <a name="remarks"></a>Comentarios

Literales de cadena se delimitan mediante el carácter de comillas dobles ("). El carácter de barra diagonal inversa ( \\ ) se usa para codificar caracteres especiales. La barra diagonal inversa y el carácter siguiente juntos se conocen como un *secuencia de escape*. Se admite en F # cadenas literales se muestran en la siguiente tabla de secuencias de escape.

|Carácter|Secuencia de escape|
|---------|---------------|
|Retroceso|`\b`|
|Nueva línea|`\n`|
|Retorno de carro|`\r`|
|Tab|`\t`|
|Barra diagonal inversa|`\\`|
|Comillas|`\"`|
|Apóstrofo|`\'`|
|Carácter Unicode|`\uXXXX` o `\UXXXX` (donde `X` indica un dígito hexadecimal)|

Si va precedido por el símbolo @, el literal es una cadena textual. Esto significa que se omiten las secuencias de escape, excepto en que dos caracteres de comilla se interpretan como caracteres de una comilla simple.

Además, una cadena puede estar delimitada por comillas triples. En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles. Para especificar una cadena que contiene incrustado cadena entre comillas, se puede usar una cadena textual o una cadena entre comillas el triple. Si usa una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple. Si usa una cadena entre comillas el triple, puede utilizar los caracteres de comillas simples sin ellos que se va a analizar como el final de la cadena. Esta técnica puede ser útil al trabajar con XML u otras estructuras que incluyen las comillas incrustadas.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

En el código, se aceptan cadenas que tienen los saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa es el último carácter antes del salto de línea. Espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa. El siguiente código genera una cadena `str1` que tiene el valor `"abc\ndef"` y una cadena `str2` que tiene el valor `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

Puede tener acceso a caracteres individuales de una cadena con sintaxis de matriz, como sigue.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

El resultado es `b`

O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

La salida es la siguiente.

```
abc
def
```

Puede representar cadenas ASCII por las matrices de bytes sin signo, tipo `byte[]`. Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII. Literales de cadena ASCII utilizados con matrices de bytes compatible con las mismas secuencias de escape como cadenas Unicode, excepto para las secuencias de escape Unicode.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operadores de cadena

Hay dos maneras para concatenar cadenas: mediante el uso de la `+` operador o mediante el `^` operador. El `+` operador mantiene la compatibilidad con las características de tratamiento de cadenas de .NET Framework.

El ejemplo siguiente muestra la concatenación de cadenas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>Clase de cadena

Dado que el tipo de cadena en F # es realmente una versión de .NET Framework `System.String` escriba todos los `System.String` miembros están disponibles. Esto incluye la `+` operador, que se utiliza para concatenar cadenas, la `Length` propiedad y el `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode. Para obtener más información acerca de las cadenas, vea `System.String`.

Mediante el uso de la `Chars` propiedad de `System.String`, puede tener acceso a los caracteres individuales de una cadena mediante la especificación de un índice, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Módulo de la cadena

Funcionalidad adicional para el control de la cadena se incluye en el `String` módulo en el `FSharp.Core` espacio de nombres. Para obtener más información, consulte [Core.String módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
