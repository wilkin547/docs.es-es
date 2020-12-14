---
title: Conservación de las referencias con System.Text.Json
description: Aprenda a conservar las referencias y controlar las referencias circulares durante la serialización y deserialización de JSON en .NET.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008739"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="1e7e7-103">Cómo conservar las referencias y administrar las referencias circulares con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1e7e7-103">How to preserve references and handle circular references with System.Text.Json</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1e7e7-104">Para conservar las referencias y administrar las referencias circulares, establezca <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> en <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-104">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="1e7e7-105">Este valor produce el comportamiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e7e7-105">This setting causes the following behavior:</span></span>

* <span data-ttu-id="1e7e7-106">Al serializar:</span><span class="sxs-lookup"><span data-stu-id="1e7e7-106">On serialize:</span></span>

  <span data-ttu-id="1e7e7-107">Al escribir tipos complejos, el serializador también escribe propiedades de metadatos (`$id`, `$values` y `$ref`).</span><span class="sxs-lookup"><span data-stu-id="1e7e7-107">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="1e7e7-108">Al deserializar:</span><span class="sxs-lookup"><span data-stu-id="1e7e7-108">On deserialize:</span></span>

  <span data-ttu-id="1e7e7-109">Se esperan metadatos (aunque no es obligatorio) y el deserializador intenta entenderlo.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-109">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="1e7e7-110">En el siguiente código se muestra el uso del parámetro `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-110">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="1e7e7-111">Esta característica no se puede usar para conservar tipos de valor o tipos inmutables.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-111">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="1e7e7-112">En la deserialización, se crea la instancia de un tipo inmutable después de leer la carga completa.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-112">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="1e7e7-113">Por lo tanto, sería imposible deserializar la misma instancia si aparece una referencia a ella dentro de la carga de JSON.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-113">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="1e7e7-114">En el caso de los tipos de valor, los tipos inmutables y las matrices, no se serializan los metadatos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-114">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="1e7e7-115">En la deserialización, se produce una excepción si se encuentra `$ref` o `$id`.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-115">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="1e7e7-116">Sin embargo, los tipos de valor omiten `$id` (y `$values` en el caso de las colecciones) para que sea posible deserializar las cargas que se serializaron mediante Newtonsoft.Json.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-116">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="1e7e7-117">Newtonsoft.Json serializa los metadatos de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-117">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="1e7e7-118">Para determinar si los objetos son iguales, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, que usa la igualdad de referencia (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) en lugar de la igualdad de valores (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> cuando se comparan dos instancias de objeto.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-118">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="1e7e7-119">Para obtener más información sobre cómo se serializan y deserializan las referencias, vea <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-119">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1e7e7-120">La clase <xref:System.Text.Json.Serialization.ReferenceResolver> define el comportamiento de conservar las referencias en la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-120">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="1e7e7-121">Cree una clase derivada para especificar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-121">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="1e7e7-122">Para obtener un ejemplo, vea [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="1e7e7-122">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1e7e7-123">System.Text.Json en .NET Core 3.1 solo admite la serialización por valor y produce una excepción para las referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="1e7e7-123">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="1e7e7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e7e7-124">See also</span></span>

* [<span data-ttu-id="1e7e7-125">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1e7e7-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1e7e7-126">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="1e7e7-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="1e7e7-127">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="1e7e7-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="1e7e7-128">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="1e7e7-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="1e7e7-129">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="1e7e7-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="1e7e7-130">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="1e7e7-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="1e7e7-131">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="1e7e7-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="1e7e7-132">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="1e7e7-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="1e7e7-133">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="1e7e7-133">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="1e7e7-134">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="1e7e7-134">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="1e7e7-135">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1e7e7-135">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1e7e7-136">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="1e7e7-136">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="1e7e7-137">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="1e7e7-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="1e7e7-138">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="1e7e7-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1e7e7-139">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1e7e7-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="1e7e7-140">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1e7e7-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="1e7e7-141">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="1e7e7-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
