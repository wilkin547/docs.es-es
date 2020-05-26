---
ms.openlocfilehash: 298cb441bf9fe7daddb30c85f9d7366dc972628c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721397"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a>Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode

Cuando la clase <xref:System.Text.UTF8Encoding> encuentra una secuencia de bytes UTF-8 con formato incorrecto durante una operación de transcodificación de byte a carácter, reemplaza esa secuencia por un carácter "�" (CARÁCTER DE REEMPLAZO DE U+FFFD) en la cadena de salida. .NET Core 3.0 se diferencia de las versiones anteriores de .NET Core y de .NET Framework en que sigue los procedimientos recomendados de Unicode para realizar este reemplazo durante la operación de transcodificación.

Esto forma parte de un trabajo mayor para mejorar el control de UTF-8 en .NET, que los nuevos tipos <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> y <xref:System.Text.Rune?displayProperty=nameWithType> incluyen. Se asignó una mecánica de control de errores mejorada al tipo <xref:System.Text.UTF8Encoding> para que genere una salida coherente con los tipos recién incorporados.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0, al transcodificar bytes en caracteres, la clase <xref:System.Text.UTF8Encoding> realiza la sustitución de caracteres en función de los procedimientos recomendados de Unicode. El mecanismo de sustitución que se usa se describe en [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) en el apartado titulado _U+FFFD Substitution of Maximal Subparts_.

Este comportamiento _solo_ se aplica cuando la secuencia de bytes de entrada contiene datos UTF-8 con formato incorrecto. Además, si la instancia de <xref:System.Text.UTF8Encoding> se ha construido con `throwOnInvalidBytes: true`, la instancia de `UTF8Encoding`continuará produciéndose en una entrada no válida en lugar de realizar el reemplazo de U+FFFD. Para obtener más información sobre el constructor `UTF8Encoding`, vea <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.

En la siguiente tabla se muestra el impacto de este cambio con una entrada de 3 bytes no válida:

| Entrada de 3 bytes con formato incorrecto | Salida antes de .NET Core 3.0          | Salida a partir de .NET Core 3.0        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | `[ FFFD FFFD ]` (salida de 2 caracteres) | `[ FFFD FFFD FFFD ]` (salida de 3 caracteres) |

La salida de 3 caracteres es la preferida, según la _tabla 3-9_ del PDF del estándar Unicode vinculado anteriormente.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
