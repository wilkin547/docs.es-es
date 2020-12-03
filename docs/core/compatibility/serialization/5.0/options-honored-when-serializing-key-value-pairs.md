---
title: 'Cambio importante: Se admiten las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder para los pares clave-valor'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde se respetan las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder al serializar y deserializar los nombres de propiedad Key y Value de una instancia de par clave-valor.
ms.date: 10/18/2020
ms.openlocfilehash: 5d75cb7feea32cc4b942e5261c5b609e00a5082c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760240"
---
# <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a>Se admiten las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder al serializar y deserializar pares clave-valor

Ahora <xref:System.Text.Json.JsonSerializer> respeta las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.Encoder> al serializar los nombres de propiedad <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> de una instancia de <xref:System.Collections.Generic.KeyValuePair%602>. Además, <xref:System.Text.Json.JsonSerializer> respeta las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> al deserializar las instancias de <xref:System.Collections.Generic.KeyValuePair%602>.

## <a name="change-description"></a>Descripción del cambio

### <a name="serialization"></a>Serialización

En las versiones de .NET Core 3.x y en las versiones 4.6.0-4.7.2 del [paquete NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json), las propiedades de las instancias de <xref:System.Collections.Generic.KeyValuePair%602> se serializan siempre como "Key" y "Value" exactamente, con independencia de las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> y <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType>. En el ejemplo de código siguiente se muestra cómo en las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> *no* se usan mayúsculas y minúsculas (Camel) después de la serialización, aunque la directiva de nomenclatura de propiedades especificada lo determine.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

A partir de .NET 5.0, se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.Encoder> al serializar instancias de <xref:System.Collections.Generic.KeyValuePair%602>. En el ejemplo de código siguiente se muestra cómo en las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> se usan mayúsculas y minúsculas (Camel) después de la serialización, de acuerdo a la directiva de nomenclatura de propiedades especificada.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

### <a name="deserialization"></a>Deserialización

En las versiones de .NET Core 3.x y en las versiones 4.7.x del [paquete NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json), se inicia una excepción <xref:System.Text.Json.JsonException> cuando los nombres de las propiedades JSON no son precisamente `Key` y `Value`, por ejemplo, si no empiezan con una letra mayúscula. La excepción se inicia incluso si una directiva de nomenclatura de propiedades especificada la permite de forma expresa.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

A partir de .NET 5.0, se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> al deserializar mediante <xref:System.Text.Json.JsonSerializer>. Por ejemplo, en el fragmento de código siguiente se muestra la deserialización correcta de los nombres de propiedad <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> en minúsculas porque la directiva de nomenclatura de propiedades especificada lo permite.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

Para dar cabida a las cargas que se hayan serializado con versiones anteriores, en "Key" y "Value" se usan mayúsculas y minúsculas de forma especial durante la deserialización. Aunque en los nombres de las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> no se usan mayúsculas y minúsculas (Camel) según la opción <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> del ejemplo de código siguiente, se deserializan de forma correcta.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="reason-for-change"></a>Motivo del cambio

En numerosos comentarios de los clientes se ha indicado que se debía respetar <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy>. Por integridad, también se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> y <xref:System.Text.Json.JsonSerializerOptions.Encoder>, de modo que las instancias de <xref:System.Collections.Generic.KeyValuePair%602> se tratan como cualquier otro objeto CRL estándar (POCO).

## <a name="recommended-action"></a>Acción recomendada

Si este cambio le resulta perjudicial, puede usar un [convertidor personalizado](../../../../standard/serialization/system-text-json-converters-how-to.md) que implemente la semántica deseada.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
