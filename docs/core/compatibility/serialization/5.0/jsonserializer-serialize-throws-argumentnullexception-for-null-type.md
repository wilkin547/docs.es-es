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
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL

Las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> que tienen un parámetro de tipo <xref:System.Type> ahora inician una excepción <xref:System.ArgumentNullException> cada vez que se pasa `null` para ese parámetro.

## <a name="change-description"></a>Descripción del cambio

En .NET Core 3.1, las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> y <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> que tienen un parámetro <xref:System.Type> inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro `Type inputType`, pero no si el parámetro `Object value` también es `null`. A partir de .NET 5.0, estos métodos *siempre* inician una excepción <xref:System.ArgumentNullException> cuando se pasa `null` para el parámetro <xref:System.Type>.

Comportamiento en .NET Core 3.1:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

Comportamiento en .NET 5.0 y versiones posteriores:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="reason-for-change"></a>Motivo del cambio

No se permite pasar `null` para el parámetro `Type inputType` y siempre iniciará una excepción <xref:System.ArgumentNullException>.

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de no pasar `null` para el parámetro `Type inputType` de estos métodos.

## <a name="affected-apis"></a>API afectadas

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
