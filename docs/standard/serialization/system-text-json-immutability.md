---
title: Uso de tipos inmutables y descriptores de acceso no públicos con System.Text.Json
description: Aprenda a usar tipos inmutables y descriptores de acceso no públicos durante la serialización y deserialización de JSON en .NET.
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
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439832"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="37efa-103">Uso de tipos inmutables y descriptores de acceso no públicos con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="37efa-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="37efa-104">En este artículo, aprenderá a usar tipos inmutables, como registros, con el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="37efa-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="37efa-105">Tipos y registros inmutables</span><span class="sxs-lookup"><span data-stu-id="37efa-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="37efa-106">`System.Text.Json` puede utilizar un constructor con parámetros, lo que hace posible deserializar una clase o estructura inmutable.</span><span class="sxs-lookup"><span data-stu-id="37efa-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="37efa-107">En el caso de una clase, si el único constructor está parametrizado, se utilizará ese constructor.</span><span class="sxs-lookup"><span data-stu-id="37efa-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="37efa-108">En el caso de una estructura o una clase con varios constructores, especifique el que se va a usar aplicando el atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="37efa-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="37efa-109">Cuando no se utiliza el atributo, siempre se usa un constructor sin parámetros público si está presente.</span><span class="sxs-lookup"><span data-stu-id="37efa-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="37efa-110">El atributo solo se puede usar con constructores públicos.</span><span class="sxs-lookup"><span data-stu-id="37efa-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="37efa-111">En el ejemplo siguiente se usa el atributo `[JsonConstructor]`:</span><span class="sxs-lookup"><span data-stu-id="37efa-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="37efa-112">También se admiten registros en C# 9, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37efa-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="37efa-113">En el caso de los tipos que son inmutables porque todos sus establecedores de propiedad son no públicos, vea la siguiente sección sobre [los descriptores de acceso de propiedad no públicos](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="37efa-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="37efa-114">`JsonConstructorAttribute` y la compatibilidad con los registros en C# 9 no están disponibles en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="37efa-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="37efa-115">Descriptores de acceso de propiedad no públicos</span><span class="sxs-lookup"><span data-stu-id="37efa-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="37efa-116">Para habilitar el uso de un descriptor de acceso de propiedad no público, use el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37efa-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="37efa-117">Los descriptores de acceso de propiedad no públicos no se admiten en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="37efa-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="37efa-118">Para obtener más información, consulte [el artículo de migración de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="37efa-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="37efa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="37efa-119">See also</span></span>

* [<span data-ttu-id="37efa-120">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="37efa-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="37efa-121">Creación de una instancia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="37efa-121">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="37efa-122">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="37efa-122">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="37efa-123">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="37efa-123">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="37efa-124">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="37efa-124">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="37efa-125">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="37efa-125">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="37efa-126">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="37efa-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="37efa-127">Conservación de referencias circulares</span><span class="sxs-lookup"><span data-stu-id="37efa-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="37efa-128">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="37efa-128">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="37efa-129">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="37efa-129">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
