---
title: Creación de una instancia de JsonSerializerOptions con System.Text.Json
description: Aprenda a crear instancias de JsonSerializerOptions mediante la copia de instancias existentes o con valores predeterminados web.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439880"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="89cae-103">Creación de instancias de JsonSerializerOptions con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89cae-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="89cae-104">En este artículo, aprenderá a crear instancias de <xref:System.Text.Json.JsonSerializerOptions> copiando instancias existentes o con valores predeterminados web.</span><span class="sxs-lookup"><span data-stu-id="89cae-104">In this article, you'll learn how to instantiate <xref:System.Text.Json.JsonSerializerOptions> instances by copying existing instances or with web defaults.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="89cae-105">Copia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="89cae-105">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89cae-106">Hay un [constructor de JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) que le permite crear una nueva instancia de con las mismas opciones que una instancia existente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89cae-106">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89cae-107">Un constructor de `JsonSerializerOptions` que toma una instancia existente no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89cae-107">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="89cae-108">Valores predeterminados web para JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="89cae-108">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89cae-109">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="89cae-109">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="89cae-110">Hay un [constructor de JsonSerializerOptions] (xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) que le permite crear una nueva instancia de con las opciones predeterminadas que ASP.NET Core utiliza para aplicaciones web, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89cae-110">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89cae-111">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="89cae-111">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="89cae-112">Un constructor de `JsonSerializerOptions` que especifica un conjunto de valores predeterminados no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89cae-112">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="89cae-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="89cae-113">See also</span></span>

* [<span data-ttu-id="89cae-114">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89cae-114">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="89cae-115">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="89cae-115">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="89cae-116">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="89cae-116">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="89cae-117">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="89cae-117">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="89cae-118">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="89cae-118">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="89cae-119">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="89cae-119">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="89cae-120">Conservación de referencias circulares</span><span class="sxs-lookup"><span data-stu-id="89cae-120">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="89cae-121">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="89cae-121">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="89cae-122">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="89cae-122">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="89cae-123">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="89cae-123">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
