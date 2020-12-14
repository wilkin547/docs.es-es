---
title: Creación de una instancia de JsonSerializerOptions con System.Text.Json
description: Obtenga información sobre cómo evitar problemas de rendimiento y cómo usar los constructores disponibles para instancias de JsonSerializerOptions.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009838"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="b4934-103">Creación de instancias de JsonSerializerOptions con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="b4934-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="b4934-104">En este artículo se explica cómo evitar problemas de rendimiento al usar <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="b4934-104">This article explains how to avoid performance problems when you use <xref:System.Text.Json.JsonSerializerOptions>.</span></span> <span data-ttu-id="b4934-105">También se muestra cómo usar los constructores con parámetros disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4934-105">It also shows how to use the parameterized constructors that are available.</span></span>

## <a name="reuse-jsonserializeroptions-instances"></a><span data-ttu-id="b4934-106">Reutilización de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="b4934-106">Reuse JsonSerializerOptions instances</span></span>

<span data-ttu-id="b4934-107">Si usa `JsonSerializerOptions` repetidas veces con las mismas opciones, no cree una instancia de `JsonSerializerOptions` cada vez que lo use.</span><span class="sxs-lookup"><span data-stu-id="b4934-107">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="b4934-108">Reutilice la misma instancia para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="b4934-108">Reuse the same instance for every call.</span></span> <span data-ttu-id="b4934-109">Esta instrucción se aplica al código que se escribe para convertidores personalizados y al llamar a <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> o <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4934-109">This guidance applies to code you write for custom converters and when you call <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b4934-110">En el código siguiente se muestra la penalización de rendimiento al usar nuevas instancias de opciones.</span><span class="sxs-lookup"><span data-stu-id="b4934-110">The following code demonstrates the performance penalty for using new options instances.</span></span>

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

<span data-ttu-id="b4934-111">El código anterior serializa un objeto pequeño 100 000 veces mediante la misma instancia de opciones.</span><span class="sxs-lookup"><span data-stu-id="b4934-111">The preceding code serializes a small object 100,000 times using the same options instance.</span></span> <span data-ttu-id="b4934-112">A continuación, serializa el mismo objeto el mismo número de veces y crea una nueva instancia de opciones cada vez.</span><span class="sxs-lookup"><span data-stu-id="b4934-112">Then it serializes the same object the same number of times and creates a new options instance each time.</span></span> <span data-ttu-id="b4934-113">Normalmente la diferencia en el tiempo de ejecución es de 190 milisegundos frente a 40 140.</span><span class="sxs-lookup"><span data-stu-id="b4934-113">A typical run time difference is 190 compared to 40,140 milliseconds.</span></span> <span data-ttu-id="b4934-114">Esta será mayor cuantas más iteraciones se realicen.</span><span class="sxs-lookup"><span data-stu-id="b4934-114">The difference is even greater if you increase the number of iterations.</span></span>

<span data-ttu-id="b4934-115">El serializador pasa por una fase de preparación durante la primera serialización de cada tipo en el gráfico de objetos cuando se le pasa una nueva instancia de opciones.</span><span class="sxs-lookup"><span data-stu-id="b4934-115">The serializer undergoes a warm-up phase during the first serialization of each type in the object graph when a new options instance is passed to it.</span></span> <span data-ttu-id="b4934-116">Esta preparación incluye la creación de una caché de metadatos necesaria para la serialización.</span><span class="sxs-lookup"><span data-stu-id="b4934-116">This warm-up includes creating a cache of metadata that is needed for serialization.</span></span> <span data-ttu-id="b4934-117">Los metadatos incluyen delegados para captadores de propiedades, establecedores, argumentos de constructor, atributos especificados, etc.</span><span class="sxs-lookup"><span data-stu-id="b4934-117">The metadata includes delegates to property getters, setters, constructor arguments, specified attributes, and so forth.</span></span> <span data-ttu-id="b4934-118">Esta caché de metadatos se almacena en la instancia de opciones.</span><span class="sxs-lookup"><span data-stu-id="b4934-118">This metadata cache is stored in the options instance.</span></span> <span data-ttu-id="b4934-119">El mismo proceso de preparación y caché se aplica a la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b4934-119">The same warm-up process and cache applies to deserialization.</span></span>

<span data-ttu-id="b4934-120">El tamaño de la memoria caché de metadatos en una instancia de `JsonSerializerOptions` depende del número de tipos que se van a serializar.</span><span class="sxs-lookup"><span data-stu-id="b4934-120">The size of the metadata cache in a `JsonSerializerOptions` instance depends on the number of types to be serialized.</span></span> <span data-ttu-id="b4934-121">Si pasa numerosos tipos (por ejemplo, tipos generados dinámicamente) al serializador, el tamaño de la caché seguirá creciendo y puede acabar produciendo una excepción `OutOfMemoryException`.</span><span class="sxs-lookup"><span data-stu-id="b4934-121">If you pass numerous types—for example, dynamically generated types—to the serializer, the cache size will continue to grow and can end up causing an `OutOfMemoryException`.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="b4934-122">Copia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="b4934-122">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="b4934-123">Hay un [constructor de JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) que le permite crear una nueva instancia de con las mismas opciones que una instancia existente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4934-123">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="b4934-124">Un constructor de `JsonSerializerOptions` que toma una instancia existente no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b4934-124">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="b4934-125">Valores predeterminados web para JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="b4934-125">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="b4934-126">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="b4934-126">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="b4934-127">Hay un [constructor de JsonSerializerOptions] (xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) que le permite crear una nueva instancia de con las opciones predeterminadas que ASP.NET Core utiliza para aplicaciones web, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4934-127">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="b4934-128">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="b4934-128">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="b4934-129">Un constructor de `JsonSerializerOptions` que especifica un conjunto de valores predeterminados no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b4934-129">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="b4934-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4934-130">See also</span></span>

* [<span data-ttu-id="b4934-131">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="b4934-131">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="b4934-132">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="b4934-132">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="b4934-133">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b4934-133">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="b4934-134">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="b4934-134">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="b4934-135">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="b4934-135">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="b4934-136">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="b4934-136">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="b4934-137">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="b4934-137">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="b4934-138">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="b4934-138">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="b4934-139">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="b4934-139">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="b4934-140">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="b4934-140">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="b4934-141">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="b4934-141">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="b4934-142">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4934-142">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="b4934-143">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="b4934-143">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="b4934-144">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="b4934-144">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="b4934-145">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b4934-145">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="b4934-146">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="b4934-146">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="b4934-147">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="b4934-147">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
