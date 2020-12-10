---
title: Omisión de propiedades con System.Text.Json
description: Aprenda a omitir propiedades al serializar con System.Text.Json en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439821"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a><span data-ttu-id="9d399-103">Omisión de propiedades con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9d399-103">How to ignore properties with System.Text.Json</span></span>

<span data-ttu-id="9d399-104">Al serializar objetos de C# en notación de objetos JavaScript (JSON), de forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="9d399-104">When serializing C# objects to JavaScript Object Notation (JSON), by default, all public properties are serialized.</span></span> <span data-ttu-id="9d399-105">Si no quiere que algunas de ellas aparezcan en el código JSON resultante, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="9d399-105">If you don't want some of them to appear in the resulting JSON, you have several options.</span></span> <span data-ttu-id="9d399-106">En este artículo, aprenderá a omitir las propiedades en función de varios criterios:</span><span class="sxs-lookup"><span data-stu-id="9d399-106">In this article you learn how to ignore properties based on various criteria:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="9d399-107">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9d399-107">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="9d399-108">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9d399-108">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="9d399-109">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d399-109">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="9d399-110">Todas las propiedades de valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9d399-110">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="9d399-111">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9d399-111">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="9d399-112">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9d399-112">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="9d399-113">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d399-113">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a><span data-ttu-id="9d399-114">Omisión de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9d399-114">Ignore individual properties</span></span>

<span data-ttu-id="9d399-115">Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9d399-115">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="9d399-116">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9d399-116">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9d399-117">Puede especificar la exclusión condicional estableciendo la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9d399-117">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="9d399-118">La enumeración <xref:System.Text.Json.Serialization.JsonIgnoreCondition> proporciona las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9d399-118">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="9d399-119">`Always` - La propiedad se omite siempre.</span><span class="sxs-lookup"><span data-stu-id="9d399-119">`Always` - The property is always ignored.</span></span> <span data-ttu-id="9d399-120">Si no se especifica `Condition`, se presupone esta opción.</span><span class="sxs-lookup"><span data-stu-id="9d399-120">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="9d399-121">`Never` - La propiedad siempre se serializa y deserializa, independientemente de la configuración global de `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` y `IgnoreReadOnlyFields`.</span><span class="sxs-lookup"><span data-stu-id="9d399-121">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="9d399-122">`WhenWritingDefault`: la propiedad se omite en la serialización si es un tipo de referencia `null`, un tipo de valor `null` que acepta valores NULL o un tipo de valor `default`.</span><span class="sxs-lookup"><span data-stu-id="9d399-122">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null`, a nullable value type `null`, or a value type `default`.</span></span>
* <span data-ttu-id="9d399-123">`WhenWritingNull`: la propiedad se omite en la serialización si es un tipo de referencia `null` o un tipo de valor `null` que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9d399-123">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`, or a nullable value type `null`.</span></span>

<span data-ttu-id="9d399-124">En el ejemplo siguiente se muestra el uso de la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):</span><span class="sxs-lookup"><span data-stu-id="9d399-124">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a><span data-ttu-id="9d399-125">Omisión de todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9d399-125">Ignore all read-only properties</span></span>

<span data-ttu-id="9d399-126">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="9d399-126">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="9d399-127">Para omitir todas las propiedades de solo lectura durante la serialización, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d399-127">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

<span data-ttu-id="9d399-128">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9d399-128">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="9d399-129">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="9d399-129">This option applies only to serialization.</span></span> <span data-ttu-id="9d399-130">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d399-130">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9d399-131">Esta opción solo se aplica a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9d399-131">This option applies only to properties.</span></span> <span data-ttu-id="9d399-132">Para omitir los campos de solo lectura al [serializar campos](system-text-json-how-to.md#include-fields), use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d399-132">To ignore read-only fields when [serializing fields](system-text-json-how-to.md#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

## <a name="ignore-all-null-value-properties"></a><span data-ttu-id="9d399-133">Omisión de todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d399-133">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9d399-134">Para omitir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d399-134">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9d399-135">Para omitir todas las propiedades de valores NULL al serializar, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d399-135">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

<span data-ttu-id="9d399-136">Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9d399-136">Here's an example object to serialize and JSON output:</span></span>

| <span data-ttu-id="9d399-137">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9d399-137">Property</span></span>             | <span data-ttu-id="9d399-138">Valor</span><span class="sxs-lookup"><span data-stu-id="9d399-138">Value</span></span>                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a><span data-ttu-id="9d399-139">Omisión de todas las propiedades de valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9d399-139">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9d399-140">Para evitar la serialización de valores predeterminados en las propiedades de tipo de valor, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d399-140">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="9d399-141">El valor <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> también evita la serialización de propiedades de los tipos de referencia de valor NULL y los tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9d399-141">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> setting also prevents serialization of null-value reference type and nullable value type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9d399-142">No hay ninguna manera integrada de evitar la serialización de propiedades con valores predeterminados de tipos de valor en `System.Text.Json` en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9d399-142">There is no built-in way to prevent serialization of properties with value type defaults in `System.Text.Json` in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="9d399-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d399-143">See also</span></span>

* [<span data-ttu-id="9d399-144">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9d399-144">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9d399-145">Creación de una instancia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="9d399-145">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="9d399-146">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="9d399-146">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="9d399-147">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="9d399-147">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="9d399-148">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="9d399-148">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="9d399-149">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="9d399-149">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="9d399-150">Conservación de referencias circulares</span><span class="sxs-lookup"><span data-stu-id="9d399-150">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="9d399-151">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="9d399-151">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="9d399-152">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="9d399-152">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="9d399-153">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="9d399-153">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
