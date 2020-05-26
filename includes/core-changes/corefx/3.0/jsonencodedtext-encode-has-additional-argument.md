---
ms.openlocfilehash: d90996ae1b87cdea815daf979bece094d8602f70
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721135"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional

A partir de la versión preliminar 8 de .NET Core 3.0, los métodos <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> contienen un argumento <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional.

#### <a name="change-description"></a>Descripción del cambio

.NET Core 3.0 incluye un nuevo tipo, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>. A partir de la versión preliminar 8 de .NET Core 3.0, la firma de todas las sobrecargas de método <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> ha cambiado para incluir un parámetro <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional. Este cambio se realizó para permitir un codificador diferente o personalizado.

La firma de los métodos `Encode` en la versión preliminar 7 de .NET Core 3.0 es la siguiente:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

La firma de los mismos métodos `Encode` en la versión preliminar 8 de .NET Core 3.0 y versiones posteriores es:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

Se trata solo de un cambio importante de archivo binario; si se vuelve a compilar con la versión preliminar 8 de .NET Core 3.0 o una versión posterior, se solucionarán los problemas en tiempo de ejecución.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
