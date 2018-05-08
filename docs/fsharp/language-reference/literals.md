---
title: Literales (F#)
description: 'Obtenga información acerca de los tipos literales en el lenguaje de programación de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f28ca0ae7a0b092bbc039d23625b883faffd241c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="literals"></a>Literales

> [!NOTE]
Los vínculos de referencia de API en este artículo le llevará a MSDN (por ahora).

En este tema se proporciona una tabla que muestra cómo especificar el tipo de un literal en F #.

## <a name="literal-types"></a>Tipos literales
La tabla siguiente muestran los tipos literales en F #. Los caracteres que representan dígitos en notación hexadecimal no distinguen entre mayúsculas y minúsculas; caracteres que identifican el tipo distinguen mayúsculas de minúsculas.

|Tipo|Descripción|Prefijo o sufijo|Ejemplos|
|----|-----------|----------------|--------|
|sbyte|Entero de 8 bits con signo|y|`86y`<br /><br />`0b00000101y`|
|byte|número natural de 8 bits sin signo|UY|`86uy`<br /><br />`0b00000101uy`|
|int16|Entero de 16 bits con signo|s|`86s`|
|uint16|número de natural de 16 bits sin signo|us|`86us`|
|int<br /><br />int32|Entero de 32 bits con signo|l o ninguno|`86`<br /><br />`86l`|
|uint<br /><br />uint32|número de natural de 32 bits sin signo|u o ul|`86u`<br /><br />`86ul`|
|unativeint|puntero nativo como un número natural sin signo|anular|`0x00002D3Fun`|
|int64|Entero de 64 bits con signo|L|`86L`|
|uint64|número de natural de 64 bits sin signo|UL|`86UL`|
|float32 único,|número de punto flotante de 32 bits|F o f|`4.14F` o `4.14f`|
|||LF|`0x00000000lf`|
|float; doble|número de punto flotante de 64 bits|ninguna|`4.14` o `2.3E+32` o `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|entero no limitado a la representación en forma de 64 bits|I|`9999999999999999999999999999I`|
|decimal|número fraccionario representado como un punto fijo o un número racional|M o m|`0.7833M` o `0.7833m`|
|Char|Carácter Unicode|ninguna|`'a'`|
|String|Cadena de Unicode|ninguna|`"text\n"`<br /><br />o<br /><br />`@"c:\filename"`<br /><br />o<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />o<br /><br />`"string1" + "string2"`<br /><br />Vea también [cadenas](Strings.md).|
|byte|Carácter ASCII|B|`'a'B`|
|byte[]|cadena ASCII|B|`"text"B`|
|String o byte]|literales de cadenas|prefijo @|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="remarks"></a>Comentarios
Las cadenas Unicode pueden contener codificaciones explícitas, que se pueden especificar mediante `\u` seguido por un código hexadecimal de 16 bits o codificaciones UTF-32 se pueden especificar mediante `\U` seguido por un código hexadecimal de 32 bits que representa un Unicode par suplente.

A partir de F # 3.1, puede usar el `+` iniciar sesión combinar los literales de cadena. También puede usar el bit a bit o (`|||`) operador para combinar marcadores de enumeración. Por ejemplo, el código siguiente es legal en F # 3.1:

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

No se permite el uso de otros operadores bit a bit.


## <a name="named-literals"></a>Literales con nombre
Valores que están diseñados para ser constantes se pueden marcar con el [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) atributo. Este atributo tiene el efecto de lograr que un valor se compile como una constante.

En expresiones de coincidencia de patrones, los identificadores que comiencen por caracteres en minúsculas siempre se tratan como variables a enlazar, en lugar de como literales, por lo que normalmente debe usar mayúsculas iniciales al definir literales.

## <a name="integers-in-other-bases"></a>Enteros en otras bases de datos

Los enteros de 32 bits con signo también pueden especificarse en notación hexadecimal, octal o binario con un `0x`, `0o` o `0b` prefijo respectivamente.

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Carácter de subrayado en literales numéricos

A partir de F # 4.1, puede separar los dígitos con el carácter de subrayado (`_`).

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>Vea también

[Core.LiteralAttribute (clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
