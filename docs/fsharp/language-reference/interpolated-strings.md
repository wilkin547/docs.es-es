---
title: Cadenas interpoladas
description: 'Obtenga información sobre las cadenas interpoladas, una forma especial de cadena que permite incrustar expresiones de F # directamente dentro de ellas.'
ms.date: 11/12/2020
ms.openlocfilehash: a49d4e743306fd9bdabb1e019ec4e6c77e0e1f5a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688637"
---
# <a name="interpolated-strings"></a>Cadenas interpoladas

Las cadenas interpoladas son [cadenas](strings.md) que permiten incrustar expresiones de F # en ellas. Son útiles en una amplia gama de escenarios en los que el valor de una cadena puede cambiar en función del resultado de un valor o una expresión.

## <a name="syntax"></a>Sintaxis

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a>Comentarios

Las cadenas interpoladas permiten escribir código en "huecos" dentro de un literal de cadena. Este es un ejemplo básico:

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

El contenido entre cada `{}` par de llaves puede ser cualquier expresión de F #.

Para escapar un `{}` par de llaves, escriba dos de ellos del modo siguiente:

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a>Cadenas interpoladas con tipo

Las cadenas interpoladas también pueden tener especificadores de formato de F # para aplicar la seguridad de tipos.

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

En el ejemplo anterior, el código pasa erróneamente el `age` valor donde `name` debería ser y viceversa. Dado que las cadenas interpoladas usan especificadores de formato, se trata de un error de compilación en lugar de un error de tiempo de ejecución sutil.

Todos los especificadores de formato que se describen en [formato de texto no cifrado](plaintext-formatting.md) son válidos dentro de una cadena interpolada.

## <a name="verbatim-interpolated-strings"></a>Cadenas interpoladas textuales

F # admite cadenas interpoladas textualmente con triples de comillas para que pueda incrustar literales de cadena.

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a>Alinear expresiones en cadenas interpoladas

Puede alinear a la izquierda o alinear a la derecha expresiones dentro de cadenas interpoladas con `|` y una especificación de cuántos espacios. La siguiente cadena interpolada alinea las expresiones izquierda y derecha a la izquierda y a la derecha, respectivamente, por 7 espacios.

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a>Formatos y cadenas interpoladas `FormattableString`

También puede aplicar formato que cumpla las reglas de <xref:System.FormattableString> :

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

Además, una cadena interpolada también se puede typechecked como una <xref:System.FormattableString> a través de una anotación de tipo:

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

Tenga en cuenta que la anotación de tipo debe estar en la propia expresión de cadena interpolada. F # no convierte implícitamente una cadena interpolada en <xref:System.FormattableString> .

## <a name="see-also"></a>Vea también

* [Cadenas](strings.md)
