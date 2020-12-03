---
title: 'Cambio importante: Serialize inicia una excepción cuando el parámetro de tipo es NULL'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde los métodos de serialización de JsonSerialize que tienen un parámetro de tipo ahora inician una excepción cuando se pasa NULL para ese parámetro.
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760241"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="171a4-103">JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL</span><span class="sxs-lookup"><span data-stu-id="171a4-103">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="171a4-104">Las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> que tienen un parámetro de tipo <xref:System.Type> ahora inician una excepción <xref:System.ArgumentNullException> cada vez que se pasa `null` para ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="171a4-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a parameter of type <xref:System.Type> now throw an <xref:System.ArgumentNullException> whenever `null` is passed for that parameter.</span></span>

## <a name="change-description"></a><span data-ttu-id="171a4-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="171a4-105">Change description</span></span>

<span data-ttu-id="171a4-106">En .NET Core 3.1, las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> que tienen un parámetro <xref:System.Type> inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro `Type inputType`, pero no si el parámetro `Object value` también es `null`.</span><span class="sxs-lookup"><span data-stu-id="171a4-106">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="171a4-107">A partir de .NET 5.0, estos métodos *siempre* inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="171a4-107">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="171a4-108">Comportamiento en .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="171a4-108">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="171a4-109">Comportamiento en .NET 5.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="171a4-109">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a><span data-ttu-id="171a4-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="171a4-110">Version introduced</span></span>

<span data-ttu-id="171a4-111">5.0</span><span class="sxs-lookup"><span data-stu-id="171a4-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="171a4-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="171a4-112">Reason for change</span></span>

<span data-ttu-id="171a4-113">No se permite pasar `null` para el parámetro `Type inputType` y siempre iniciará una excepción <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="171a4-113">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="171a4-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="171a4-114">Recommended action</span></span>

<span data-ttu-id="171a4-115">Asegúrese de no pasar `null` para el parámetro `Type inputType` de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="171a4-115">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="171a4-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="171a4-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
