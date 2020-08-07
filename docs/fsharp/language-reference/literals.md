---
title: Literales
description: 'Obtenga información sobre los tipos literales en el lenguaje de programación F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855028"
---
# <a name="literals"></a>Literales

En este artículo se proporciona una tabla que muestra cómo especificar el tipo de un literal en F #.

> [!NOTE]
> La referencia de la API de docs.microsoft.com para F # no está completa. Si encuentra vínculos rotos, consulte la [documentación de la biblioteca básica de F #](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="literal-types"></a>Tipos literales

En la tabla siguiente se muestran los tipos literales de F #. Los caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; los caracteres que identifican el tipo distinguen mayúsculas de minúsculas.

|Tipo|Descripción|Sufijo o prefijo|Ejemplos|
|----|-----------|----------------|--------|
|sbyte|entero de 8 bits con signo|y|`86y`<br /><br />`0b00000101y`|
|byte|número natural de 8 bits sin signo|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|entero de 16 bits con signo|s|`86s`|
|uint16|número natural de 16 bits sin signo|americana|`86us`|
|int<br /><br />int32|entero de 32 bits con signo|l o ninguno|`86`<br /><br />`86l`|
|uint<br /><br />uint32|unsigned 32-número natural de bits|u o UL|`86u`<br /><br />`86ul`|
|nativeint|puntero nativo a un número natural con signo|n|`123n`|
|unativeint|puntero nativo como un número natural sin signo|CEPE|`0x00002D3Fun`|
|int64|entero de 64 bits con signo|L|`86L`|
|uint64|unsigned 64-número natural de bits|UL|`86UL`|
|single, float32|número de punto flotante de 32 bits|F o f|`4.14F` o `4.14f`|
|||LF|`0x00000000lf`|
|flot hace|número de punto flotante de 64 bits|ninguno|`4.14`, `2.3E+32` o `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|entero no limitado a la representación de 64 bits|I|`9999999999999999999999999999I`|
|Decimal|número fraccionario representado como un número de punto o racional fijo|M o m|`0.7833M` o `0.7833m`|
|Char|carácter Unicode|ninguno|`'a'` o `'\u0061'`|
|String|Cadena de Unicode|ninguno|`"text\n"`<br /><br />or<br /><br />`@"c:\filename"`<br /><br />or<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />or<br /><br />`"string1" + "string2"`<br /><br />Vea también [cadenas](Strings.md).|
|byte|Carácter ASCII|B|`'a'B`|
|byte[]|Cadena ASCII|B|`"text"B`|
|Cadena o Byte []|cadena textual|@ prefix|`@"\\server\share"`Unicode<br /><br />`@"\\server\share"B`ASCII|

## <a name="named-literals"></a>Literales con nombre

Los valores que están diseñados para ser constantes se pueden marcar con el atributo [literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) . Este atributo tiene el efecto de hacer que un valor se compile como una constante.

En las expresiones de coincidencia de patrones, los identificadores que comienzan con caracteres en minúsculas siempre se tratan como variables que se van a enlazar, en lugar de como literales, por lo que generalmente debe usar mayúsculas iniciales al definir los literales.

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

## <a name="remarks"></a>Observaciones

Las cadenas Unicode pueden contener codificaciones explícitas que puede especificar mediante `\u` el uso seguido de una codificación de código hexadecimal de 16 bits (0000-ffff) o UTF-32 que puede especificar mediante `\U` un código hexadecimal de 32 bits que representa cualquier punto de código Unicode (00000000-0010FFFF).

No se permite el uso de otros operadores bit a bit distintos de `|||` .

## <a name="integers-in-other-bases"></a>Enteros en otras bases

Los enteros de 32 bits con signo también se pueden especificar en hexadecimal, octal o binario mediante `0x` un `0o` `0b` prefijo, o respectivamente.

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Caracteres de subrayado en literales numéricos

Puede separar los dígitos con el carácter de subrayado ( `_` ).

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>Vea también

- [Clase Core. Literalattribute (](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
