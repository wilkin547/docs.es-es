---
title: 'Cambio importante: Precisión del análisis de formato numérico estándar'
description: Obtenga información sobre el cambio importante de .NET 6 en las bibliotecas .NET básicas, donde el análisis de formato numérico estándar ahora maneja precisiones más altas.
ms.date: 02/26/2021
ms.openlocfilehash: ad1555493bbc6198541365132cc421db7c01a5a2
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256925"
---
# <a name="standard-numeric-format-parsing-precision"></a>Precisión del análisis de formato numérico estándar

.NET ahora admite valores de precisión mayores al dar formato a los números como cadenas mediante `ToString` y `TryFormat`.

## <a name="change-description"></a>Descripción del cambio

Al dar formato a los números como cadenas, el *especificador de precisión* en la [cadena de formato](../../../../standard/base-types/standard-numeric-format-strings.md) representa el número de dígitos de la cadena resultante. Dependiendo del *especificador de formato*, que es el [carácter situado al principio de la cadena](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers), la precisión puede representar el número total de dígitos, el número de dígitos significativos o el número de dígitos decimales.

En versiones anteriores de .NET, la lógica de análisis de formato numérico estándar se limita a una precisión de 99 o menos. Algunos tipos numéricos tienen más precisión, pero `ToString(string format)` no los expone correctamente. Si especifica una precisión mayor que 99, por ejemplo `32.ToString("C100")`, la cadena de formato se interpreta como una [cadena de formato numérico personalizado](../../../../standard/base-types/custom-numeric-format-strings.md) en lugar de "moneda con precisión 100". En las cadenas de formato numérico personalizado, los caracteres se interpretan como [literales de carácter](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals). Además, una cadena de formato que contiene un especificador de formato no válido se interpreta de manera diferente en función del valor de precisión. `H99` genera <xref:System.FormatException> para el especificador de formato no válido, mientras que `H100` se interpreta como una cadena de formato numérico personalizado.

A partir de .NET 6, .NET admite una precisión de hasta <xref:System.Int32.MaxValue?displayProperty=nameWithType>. Una cadena de formato que consta de un especificador de formato con cualquier número de dígitos se interpreta como una cadena de formato numérico estándar con precisión. Se produce <xref:System.FormatException> para una o ambas de las condiciones siguientes:

- El carácter especificador de formato no es un [especificador de formato estándar](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers).
- La precisión es mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>.

Este cambio se implementó en la lógica de análisis que afecta a todos los tipos numéricos.

En la tabla siguiente se muestran los cambios de comportamiento de varias cadenas de formato.

| Cadena de formato | Comportamiento anterior | Comportamiento a partir de .NET 6 |
| - | - | - |
| `C2` | Denota moneda con dos dígitos decimales | Denota moneda con dos dígitos decimales (*sin cambios*) |
| `C100` | Denota una cadena de formato numérico personalizado que imprime "C100" | Denota moneda con 100 dígitos decimales |
| `H99` | Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H" | Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H" (*sin cambios*) |
| `H100` | Denota una cadena de formato numérico personalizado | Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H" |

## <a name="version-introduced"></a>Versión introducida

6.0 (versión preliminar 2)

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio corrige el comportamiento inesperado al usar una precisión mayor para el análisis de formato numérico.

## <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, no es necesario realizar ninguna acción y se mostrará la precisión correcta en las cadenas resultantes.

Sin embargo, si desea revertir al comportamiento anterior en el que el especificador de formato se interpreta como un carácter literal cuando la precisión es mayor que 99, puede especificar ese carácter entre comillas simples o escaparlo con una barra diagonal inversa. Por ejemplo, en versiones anteriores de .NET, `42.ToString("G999")` devuelve `G999`. Para mantener ese comportamiento, cambie la cadena de formato a `"'G'999"` o `"\\G999"`. Esto funcionará en .NET Framework, .NET Core y .NET 5 y versiones posteriores.

Las cadenas de formato siguientes se seguirán interpretando como cadenas de formato numérico personalizado:

- Comienzan con cualquier carácter que no sea un carácter alfabético ASCII, por ejemplo `$` o `è`.
- Comienzan con un carácter alfabético ASCII no seguido de un dígito ASCII, por ejemplo `A$`.
- Comienzan con un carácter alfabético ASCII, seguido de una secuencia de dígitos ASCII y, a continuación, cualquier carácter que no sea un carácter de dígito ASCII, por ejemplo `A12A`.

## <a name="affected-apis"></a>API afectadas

Este cambio se implementó en la lógica de análisis que afecta a todos los tipos numéricos.

- <xref:System.Numerics.BigInteger.ToString(System.String)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>

## <a name="see-also"></a>Vea también

- [Cadenas con formato numérico estándar](../../../../standard/base-types/standard-numeric-format-strings.md)
- [Literales de carácter en cadenas de formato personalizado](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals)

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.BigInteger.ToString(System.String)`
- `M:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)`
- `M:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int32.ToString(System.String)`
- `M:System.Int32.ToString(System.String,System.IFormatProvider)`
- `M:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt32.ToString(System.String)`
- `M:System.UInt32.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Byte.ToString(System.String)`
- `M:System.Byte.ToString(System.String,System.IFormatProvider)`
- `M:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.SByte.ToString(System.String)`
- `M:System.SByte.ToString(System.String,System.IFormatProvider)`
- `M:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int16.ToString(System.String)`
- `M:System.Int16.ToString(System.String,System.IFormatProvider)`
- `M:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt16.ToString(System.String)`
- `M:System.UInt16.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int64.ToString(System.String)`
- `M:System.Int64.ToString(System.String,System.IFormatProvider)`
- `M:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt64.ToString(System.String)`
- `M:System.UInt64.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Half.ToString(System.String)`
- `M:System.Half.ToString(System.String,System.IFormatProvider)`
- `M:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Single.ToString(System.String)`
- `M:System.Single.ToString(System.String,System.IFormatProvider)`
- `M:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Double.ToString(System.String)`
- `M:System.Double.ToString(System.String,System.IFormatProvider)`
- `M:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Decimal.ToString(System.String)`
- `M:System.Decimal.ToString(System.String,System.IFormatProvider)`
- `M:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`

-->
