---
ms.openlocfilehash: 375a6f57a867c2a11fe95753c1085d6d708db2bd
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237466"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="4bd5d-101">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="4bd5d-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="4bd5d-102">A partir de la versión preliminar 8 de .NET Core 3.0, los métodos <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> contienen un argumento <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional.</span><span class="sxs-lookup"><span data-stu-id="4bd5d-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4bd5d-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="4bd5d-103">Change description</span></span>

<span data-ttu-id="4bd5d-104">.NET Core 3.0 incluye un nuevo tipo, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bd5d-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bd5d-105">A partir de la versión preliminar 8 de .NET Core 3.0, la firma de todas las sobrecargas de método <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> ha cambiado para incluir un parámetro <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional.</span><span class="sxs-lookup"><span data-stu-id="4bd5d-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="4bd5d-106">Este cambio se realizó para permitir un codificador diferente o personalizado.</span><span class="sxs-lookup"><span data-stu-id="4bd5d-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="4bd5d-107">La firma de los métodos `Encode` en la versión preliminar 7 de .NET Core 3.0 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd5d-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

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

<span data-ttu-id="4bd5d-108">La firma de los mismos métodos `Encode` en la versión preliminar 8 de .NET Core 3.0 y versiones posteriores es:</span><span class="sxs-lookup"><span data-stu-id="4bd5d-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

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

#### <a name="version-introduced"></a><span data-ttu-id="4bd5d-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4bd5d-109">Version introduced</span></span>

<span data-ttu-id="4bd5d-110">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="4bd5d-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4bd5d-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4bd5d-111">Recommended action</span></span>

<span data-ttu-id="4bd5d-112">Se trata solo de un cambio importante de archivo binario; si se vuelve a compilar con la versión preliminar 8 de .NET Core 3.0 o una versión posterior, se solucionarán los problemas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bd5d-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="4bd5d-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="4bd5d-113">Category</span></span>

<span data-ttu-id="4bd5d-114">CoreFX</span><span class="sxs-lookup"><span data-stu-id="4bd5d-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4bd5d-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4bd5d-115">Affected APIs</span></span>

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
