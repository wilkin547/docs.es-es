---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050482"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="c4947-101">Se admiten las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder al serializar y deserializar pares clave-valor</span><span class="sxs-lookup"><span data-stu-id="c4947-101">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="c4947-102">Ahora <xref:System.Text.Json.JsonSerializer> respeta las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.Encoder> al serializar los nombres de propiedad <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> de una instancia de <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="c4947-102"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="c4947-103">Además, <xref:System.Text.Json.JsonSerializer> respeta las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> al deserializar las instancias de <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="c4947-103">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c4947-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c4947-104">Change description</span></span>

##### <a name="serialization"></a><span data-ttu-id="c4947-105">Serialización</span><span class="sxs-lookup"><span data-stu-id="c4947-105">Serialization</span></span>

<span data-ttu-id="c4947-106">En las versiones de .NET Core 3.x y en las versiones 4.6.0-4.7.2 del [paquete NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json), las propiedades de las instancias de <xref:System.Collections.Generic.KeyValuePair%602> se serializan siempre como "Key" y "Value" exactamente, con independencia de las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> y <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4947-106">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="c4947-107">En el ejemplo de código siguiente se muestra cómo en las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> *no* se usan mayúsculas y minúsculas (Camel) después de la serialización, aunque la directiva de nomenclatura de propiedades especificada lo determine.</span><span class="sxs-lookup"><span data-stu-id="c4947-107">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="c4947-108">A partir de .NET 5.0, se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.Encoder> al serializar instancias de <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="c4947-108">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="c4947-109">En el ejemplo de código siguiente se muestra cómo en las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> se usan mayúsculas y minúsculas (Camel) después de la serialización, de acuerdo a la directiva de nomenclatura de propiedades especificada.</span><span class="sxs-lookup"><span data-stu-id="c4947-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a><span data-ttu-id="c4947-110">Deserialización</span><span class="sxs-lookup"><span data-stu-id="c4947-110">Deserialization</span></span>

<span data-ttu-id="c4947-111">En las versiones de .NET Core 3.x y en las versiones 4.7.x del [paquete NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json), se inicia una excepción <xref:System.Text.Json.JsonException> cuando los nombres de las propiedades JSON no son precisamente `Key` y `Value`, por ejemplo, si no empiezan con una letra mayúscula.</span><span class="sxs-lookup"><span data-stu-id="c4947-111">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="c4947-112">La excepción se inicia incluso si una directiva de nomenclatura de propiedades especificada la permite de forma expresa.</span><span class="sxs-lookup"><span data-stu-id="c4947-112">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="c4947-113">A partir de .NET 5.0, se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> y <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> al deserializar mediante <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c4947-113">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="c4947-114">Por ejemplo, en el fragmento de código siguiente se muestra la deserialización correcta de los nombres de propiedad <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> en minúsculas porque la directiva de nomenclatura de propiedades especificada lo permite.</span><span class="sxs-lookup"><span data-stu-id="c4947-114">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="c4947-115">Para dar cabida a las cargas que se hayan serializado con versiones anteriores, en "Key" y "Value" se usan mayúsculas y minúsculas de forma especial durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="c4947-115">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="c4947-116">Aunque en los nombres de las propiedades <xref:System.Collections.Generic.KeyValuePair%602.Key> y <xref:System.Collections.Generic.KeyValuePair%602.Value> no se usan mayúsculas y minúsculas (Camel) según la opción <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> del ejemplo de código siguiente, se deserializan de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="c4947-116">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a><span data-ttu-id="c4947-117">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c4947-117">Version introduced</span></span>

<span data-ttu-id="c4947-118">5.0</span><span class="sxs-lookup"><span data-stu-id="c4947-118">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c4947-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c4947-119">Reason for change</span></span>

<span data-ttu-id="c4947-120">En numerosos comentarios de los clientes se ha indicado que se debía respetar <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy>.</span><span class="sxs-lookup"><span data-stu-id="c4947-120">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="c4947-121">Por integridad, también se respetan las opciones <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> y <xref:System.Text.Json.JsonSerializerOptions.Encoder>, de modo que las instancias de <xref:System.Collections.Generic.KeyValuePair%602> se tratan como cualquier otro objeto CRL estándar (POCO).</span><span class="sxs-lookup"><span data-stu-id="c4947-121">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c4947-122">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c4947-122">Recommended action</span></span>

<span data-ttu-id="c4947-123">Si este cambio le resulta perjudicial, puede usar un [convertidor personalizado](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) que implemente la semántica deseada.</span><span class="sxs-lookup"><span data-stu-id="c4947-123">If this change is disruptive to you, you can use a [custom converter](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

#### <a name="category"></a><span data-ttu-id="c4947-124">Categoría</span><span class="sxs-lookup"><span data-stu-id="c4947-124">Category</span></span>

<span data-ttu-id="c4947-125">Serialización</span><span class="sxs-lookup"><span data-stu-id="c4947-125">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c4947-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c4947-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
