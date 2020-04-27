---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021663"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Cambio del tipo de excepción del serializador de JSON de `JsonException` a `NotSupportedException`

De la versión preliminar 6 a la 8 de .NET Core 3.0, el serializador producirá una <xref:System.Text.Json.JsonException> cuando encuentre un tipo de colección derivada no compatible. A partir de la versión preliminar 9 de .NET Core 3.0, el serializador produce una <xref:System.NotSupportedException> en su lugar.

#### <a name="change-description"></a>Descripción del cambio

De la versión preliminar 6 a la versión preliminar 8 de .NET Core 3.0, el serializador producirá una <xref:System.Text.Json.JsonException> cuando encuentre un tipo de colección derivada no compatible. Un *tipo de colección derivada no compatible* es cualquier tipo de colección que no se puede asignar a uno de los tipos siguientes:

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [IDictionary\<Cadena,T>](xref:System.Collections.Generic.IDictionary%602)

A partir de la versión preliminar 9 de .NET Core 3.0, el serializador produce una <xref:System.NotSupportedException> al encontrar un tipo de colección no compatible. El nuevo tipo de excepción refleja mejor por qué se produce un error en la operación de deserialización.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Si al deserializar detecta <xref:System.Text.Json.JsonException>, es posible que también quiera considerar la posibilidad de detectar <xref:System.NotSupportedException>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
