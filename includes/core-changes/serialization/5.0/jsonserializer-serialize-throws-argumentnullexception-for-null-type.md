---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955347"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="04bd4-101">JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL</span><span class="sxs-lookup"><span data-stu-id="04bd4-101">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="04bd4-102">Las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> que tienen un parámetro <xref:System.Type> ahora inician una excepción <xref:System.ArgumentNullException> cada vez que se pasa `null` para el parámetro <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="04bd4-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter now throw an <xref:System.ArgumentNullException> whenever `null` is passed for the <xref:System.Type> parameter.</span></span>

#### <a name="change-description"></a><span data-ttu-id="04bd4-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="04bd4-103">Change description</span></span>

<span data-ttu-id="04bd4-104">En .NET Core 3.1, las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> que tienen un parámetro <xref:System.Type> inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro `Type inputType`, pero no si el parámetro `Object value` también es `null`.</span><span class="sxs-lookup"><span data-stu-id="04bd4-104">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="04bd4-105">A partir de .NET 5.0, estos métodos *siempre* inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="04bd4-105">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="04bd4-106">Comportamiento en .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="04bd4-106">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="04bd4-107">Comportamiento en .NET 5.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="04bd4-107">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a><span data-ttu-id="04bd4-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="04bd4-108">Version introduced</span></span>

<span data-ttu-id="04bd4-109">5.0</span><span class="sxs-lookup"><span data-stu-id="04bd4-109">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="04bd4-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="04bd4-110">Reason for change</span></span>

<span data-ttu-id="04bd4-111">No se permite pasar `null` para el parámetro `Type inputType` y siempre iniciará una excepción <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="04bd4-111">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="04bd4-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="04bd4-112">Recommended action</span></span>

<span data-ttu-id="04bd4-113">Asegúrese de no pasar `null` para el parámetro `Type inputType` de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="04bd4-113">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="04bd4-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="04bd4-114">Category</span></span>

<span data-ttu-id="04bd4-115">Serialización</span><span class="sxs-lookup"><span data-stu-id="04bd4-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="04bd4-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="04bd4-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
