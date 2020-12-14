---
title: Habilitación de la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con System.Text.Json
description: Aprenda a habilitar la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3e2fb8cbdd35e772b5e97c731199f69aa834bd0a
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009747"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="d9d66-103">Habilitación de la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d9d66-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="d9d66-104">En este artículo, aprenderá a habilitar la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="d9d66-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="d9d66-105">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="d9d66-105">Case-insensitive property matching</span></span>

<span data-ttu-id="d9d66-106">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="d9d66-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="d9d66-107">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="d9d66-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="d9d66-108">Los [valores predeterminados web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d9d66-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="d9d66-109">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="d9d66-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="d9d66-110">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="d9d66-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="d9d66-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d66-111">See also</span></span>

* [<span data-ttu-id="d9d66-112">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d9d66-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="d9d66-113">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="d9d66-113">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="d9d66-114">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="d9d66-114">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="d9d66-115">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="d9d66-115">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="d9d66-116">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="d9d66-116">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="d9d66-117">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="d9d66-117">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="d9d66-118">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="d9d66-118">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="d9d66-119">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="d9d66-119">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="d9d66-120">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="d9d66-120">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="d9d66-121">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="d9d66-121">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="d9d66-122">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d9d66-122">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="d9d66-123">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9d66-123">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="d9d66-124">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="d9d66-124">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="d9d66-125">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="d9d66-125">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="d9d66-126">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d9d66-126">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="d9d66-127">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d9d66-127">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="d9d66-128">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="d9d66-128">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
