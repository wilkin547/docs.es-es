---
title: Literales
description: Obtenga información sobre los tipos literales en la F# lenguaje de programación.
ms.date: 06/28/2019
ms.openlocfilehash: 53647d8cbc2a59527a50e122bc1abc6055c1fce5
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487780"
---
# <a name="literals"></a>Literales

> [!NOTE]
> Los vínculos de referencia de API en este artículo le llevará a MSDN (por ahora).

Este tema proporciona una tabla que se muestra cómo especificar el tipo de un literal en F#.

## <a name="literal-types"></a>Tipos literales

La siguiente tabla muestra los tipos literales en F#. Caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; caracteres que identifican el tipo distinguen mayúsculas de minúsculas.

|Tipo|Descripción|Prefijo o sufijo|Ejemplos|
|----|-----------|----------------|--------|
|sbyte|entero de 8 bits con signo|y|`86y`<br /><br />`0b00000101y`|
|byte|número natural de 8 bits sin signo|UY|`86uy`<br /><br />`0b00000101uy`|
|int16|entero de 16 bits con signo|s|`86s`|
|uint16|número natural de 16 bits sin signo|us|`86us`|
|int<br /><br />int32|entero de 32 bits con signo|l o none|`86`<br /><br />`86l`|
|uint<br /><br />uint32|número natural de 32 bits sin signo|u o ul|`86u`<br /><br />`86ul`|
|nativeint.|puntero nativo en un número natural con signo|n|`123n`|
|unativeint.|puntero nativo como un número natural sin signo|anular|`0x00002D3Fun`|
|int64|entero de 64 bits con signo|L|`86L`|
|uint64|número natural de 64 bits sin signo|UL|`86UL`|
|float32 único,|número de punto flotante de 32 bits|F o f|`4.14F` o `4.14f`|
|||lf|`0x00000000lf`|
|float; Double|número de punto flotante de 64 bits|ninguna|`4.14` o `2.3E+32` o `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|entero no limitado a la representación de 64 bits|I|`9999999999999999999999999999I`|
|decimal|número fraccionario representado como un punto fijo o un número racional|M o m|`0.7833M` o `0.7833m`|
|Char|Carácter Unicode|ninguna|`'a'`|
|String|Cadena de Unicode|ninguna|`"text\n"`<br /><br />o<br /><br />`@"c:\filename"`<br /><br />o<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />o<br /><br />`"string1" + "string2"`<br /><br />Vea también [cadenas](Strings.md).|
|byte|Carácter ASCII|B|`'a'B`|
|byte[]|cadena ASCII|B|`"text"B`|
|String o byte]|literales de cadenas|prefijo @|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="named-literals"></a>Literales con nombre

Los valores que están diseñados para ser constantes se pueden marcar con el [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) atributo. Este atributo tiene el efecto de la causa de un valor que se compile como una constante.

En las expresiones de coincidencia de patrón, los identificadores que comienzan con caracteres en minúscula se tratan siempre como variables para enlazar, en lugar de como literales, por lo tanto normalmente debe usar mayúsculas iniciales al definir los literales.

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a>Comentarios

Las cadenas Unicode pueden contener codificaciones explícitas que se pueden especificar mediante el uso de `\u` seguido por un código hexadecimal de 16 bits (0000 - FFFF), o codificaciones UTF-32 que se pueden especificar mediante el uso de `\U` seguido por un código hexadecimal de 32 bits que representa cualquier punto de código Unicode (00000000 - 00010FFFF).

El uso de otros operadores bit a bit distinto `|||` no está permitido.

## <a name="integers-in-other-bases"></a>Enteros en otras bases

También pueden especificarse en notación hexadecimal, octal o binario utilizando enteros de 32 bits con signo un `0x`, `0o` o `0b` prefijo respectivamente.

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Caracteres de subrayado en literales numéricos

Puede separar los dígitos con el carácter de subrayado (`_`).

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>Vea también

- [Clase Core.LiteralAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
