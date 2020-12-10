---
title: Permitir algunos tipos de JSON no válido con System.Text.Json
description: Sepa cómo permitir comentarios, comas finales y números entre comillas durante la serialización y deserialización de JSON en .NET.
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
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439820"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a><span data-ttu-id="8fab6-103">Permitir algunos tipos de JSON no válido con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8fab6-103">How to allow some kinds of invalid JSON with System.Text.Json</span></span>

<span data-ttu-id="8fab6-104">En este artículo, sabrá cómo permitir comentarios, comas finales y números entre comillas en JSON, y cómo escribir números como cadenas.</span><span class="sxs-lookup"><span data-stu-id="8fab6-104">In this article, you will learn how to allow comments, trailing commas, and quoted numbers in JSON, and how to write numbers as strings.</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="8fab6-105">Autorización de comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="8fab6-105">Allow comments and trailing commas</span></span>

<span data-ttu-id="8fab6-106">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="8fab6-106">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="8fab6-107">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="8fab6-107">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="8fab6-108">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="8fab6-108">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="8fab6-109">En el siguiente ejemplo se muestra cómo permitirlos ambos:</span><span class="sxs-lookup"><span data-stu-id="8fab6-109">The following example shows how to allow both:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

<span data-ttu-id="8fab6-110">Aquí se muestra un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="8fab6-110">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="8fab6-111">Permitir o escribir números entre comillas</span><span class="sxs-lookup"><span data-stu-id="8fab6-111">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="8fab6-112">Algunos serializadores codifican números como cadenas JSON (entre comillas).</span><span class="sxs-lookup"><span data-stu-id="8fab6-112">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span>

<span data-ttu-id="8fab6-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8fab6-113">For example:</span></span>

```json
{
    "DegreesCelsius": "23"
}
```

<span data-ttu-id="8fab6-114">En lugar de:</span><span class="sxs-lookup"><span data-stu-id="8fab6-114">Instead of:</span></span>

```json
{
    "DegreesCelsius": 23
}
```

<span data-ttu-id="8fab6-115">Para serializar los números entre comillas o aceptar números entre comillas en todo el gráfico del objeto de entrada, establezca <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fab6-115">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

<span data-ttu-id="8fab6-116">Cuando se usa `System.Text.Json` indirectamente a través de ASP.NET Core, se permiten números entre comillas al deserializar porque ASP.NET Core especifica [opciones predeterminadas web](xref:System.Text.Json.JsonSerializerDefaults.Web).</span><span class="sxs-lookup"><span data-stu-id="8fab6-116">When you use `System.Text.Json` indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="8fab6-117">Para permitir o escribir números entre comillas para propiedades, campos o tipos específicos, use el atributo [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="8fab6-117">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8fab6-118">`System.Text.Json` en .NET Core 3.1 no admite la serialización o deserialización de números entre comillas.</span><span class="sxs-lookup"><span data-stu-id="8fab6-118">`System.Text.Json` in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="8fab6-119">Para obtener más información, vea [Permitir o escribir números entre comillas](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="8fab6-119">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="8fab6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fab6-120">See also</span></span>

* [<span data-ttu-id="8fab6-121">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8fab6-121">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8fab6-122">Creación de una instancia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="8fab6-122">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="8fab6-123">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="8fab6-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="8fab6-124">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="8fab6-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="8fab6-125">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="8fab6-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="8fab6-126">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="8fab6-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="8fab6-127">Conservación de referencias circulares</span><span class="sxs-lookup"><span data-stu-id="8fab6-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="8fab6-128">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="8fab6-128">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="8fab6-129">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="8fab6-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="8fab6-130">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8fab6-130">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
