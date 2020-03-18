---
ms.openlocfilehash: 7c39fe7ffd59fa7a5564bb45f32a6a2fbe0ddb33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568186"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="6ef3b-101">Cambio en la semántica de `(string)null` en Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="6ef3b-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="6ef3b-102">En la versión preliminar 7 de .NET Core 3.0, la cadena NULL se trata como la cadena vacía en <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="6ef3b-103">A partir de la versión preliminar 8 de .NET Core 3.0, la cadena NULL produce una excepción cuando se usa como nombre de propiedad y emite el token JSON NULL cuando se usa como valor.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6ef3b-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="6ef3b-104">Change description</span></span>

<span data-ttu-id="6ef3b-105">En la versión preliminar 7 de .NET Core 3.0, la cadena `null` se trató como `""` tanto al escribir nombres de propiedad como al escribir valores.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="6ef3b-106">A partir de la versión preliminar 8 de .NET Core 3.0, un nombre de propiedad `null` produce una `ArgumentNullException` y un valor `null` se trata como llamada a <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> o <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6ef3b-107">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef3b-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="6ef3b-108">Si se ejecuta con la versión preliminar 7 de .NET Core 3.0, el escritor produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6ef3b-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="6ef3b-109">A partir de la versión preliminar 8 de .NET Core 3.0, la llamada a `writer.WriteString(propertyName1, propertyValue1)` produce una <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="6ef3b-110">Si `propertyName1 = null` se reemplaza por `propertyName1 = string.Empty`, el resultado ahora sería:</span><span class="sxs-lookup"><span data-stu-id="6ef3b-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="6ef3b-111">Este cambio se realizó para alinearse mejor con las expectativas del autor de llamada para los valores de `null`.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6ef3b-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6ef3b-112">Version introduced</span></span>

<span data-ttu-id="6ef3b-113">3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="6ef3b-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6ef3b-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6ef3b-114">Recommended action</span></span>

<span data-ttu-id="6ef3b-115">Al escribir nombres y valores de propiedad con la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="6ef3b-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="6ef3b-116">Asegúrese de que las cadenas que no sean de `null` se usen como nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="6ef3b-117">Si se desea que se produzca el comportamiento anterior, utilice una invocación de uso combinado de NULL; por ejemplo, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="6ef3b-118">Si no es conveniente escribir un literal `null` para un valor de cadena `null`, utilice una invocación de uso combinado de NULL; por ejemplo, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span><span class="sxs-lookup"><span data-stu-id="6ef3b-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="6ef3b-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="6ef3b-119">Category</span></span>

<span data-ttu-id="6ef3b-120">CoreFX</span><span class="sxs-lookup"><span data-stu-id="6ef3b-120">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6ef3b-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6ef3b-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
