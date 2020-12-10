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
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599081"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="b0421-103">Habilitación de la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="b0421-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="b0421-104">En este artículo, aprenderá a habilitar la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="b0421-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="b0421-105">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b0421-105">Case-insensitive property matching</span></span>

<span data-ttu-id="b0421-106">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="b0421-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="b0421-107">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="b0421-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="b0421-108">Los [valores predeterminados web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b0421-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="b0421-109">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="b0421-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="b0421-110">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="b0421-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="b0421-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0421-111">See also</span></span>

* [<span data-ttu-id="b0421-112">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="b0421-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="b0421-113">Creación de una instancia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="b0421-113">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="b0421-114">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="b0421-114">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="b0421-115">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="b0421-115">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="b0421-116">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="b0421-116">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="b0421-117">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="b0421-117">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="b0421-118">Conservación de referencias circulares</span><span class="sxs-lookup"><span data-stu-id="b0421-118">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="b0421-119">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="b0421-119">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="b0421-120">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="b0421-120">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="b0421-121">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="b0421-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
