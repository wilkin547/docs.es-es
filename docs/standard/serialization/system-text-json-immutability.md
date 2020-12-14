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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008830"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="0f350-103">Uso de tipos inmutables y descriptores de acceso no públicos con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0f350-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="0f350-104">En este artículo, aprenderá a usar tipos inmutables, como registros, con el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="0f350-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="0f350-105">Tipos y registros inmutables</span><span class="sxs-lookup"><span data-stu-id="0f350-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0f350-106">`System.Text.Json` puede utilizar un constructor con parámetros, lo que hace posible deserializar una clase o estructura inmutable.</span><span class="sxs-lookup"><span data-stu-id="0f350-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="0f350-107">En el caso de una clase, si el único constructor está parametrizado, se utilizará ese constructor.</span><span class="sxs-lookup"><span data-stu-id="0f350-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="0f350-108">En el caso de una estructura o una clase con varios constructores, especifique el que se va a usar aplicando el atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="0f350-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="0f350-109">Cuando no se utiliza el atributo, siempre se usa un constructor sin parámetros público si está presente.</span><span class="sxs-lookup"><span data-stu-id="0f350-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="0f350-110">El atributo solo se puede usar con constructores públicos.</span><span class="sxs-lookup"><span data-stu-id="0f350-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="0f350-111">En el ejemplo siguiente se usa el atributo `[JsonConstructor]`:</span><span class="sxs-lookup"><span data-stu-id="0f350-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="0f350-112">También se admiten registros en C# 9, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f350-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="0f350-113">En el caso de los tipos que son inmutables porque todos sus establecedores de propiedad son no públicos, vea la siguiente sección sobre [los descriptores de acceso de propiedad no públicos](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="0f350-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0f350-114">`JsonConstructorAttribute` y la compatibilidad con los registros en C# 9 no están disponibles en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="0f350-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="0f350-115">Descriptores de acceso de propiedad no públicos</span><span class="sxs-lookup"><span data-stu-id="0f350-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0f350-116">Para habilitar el uso de un descriptor de acceso de propiedad no público, use el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f350-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0f350-117">Los descriptores de acceso de propiedad no públicos no se admiten en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="0f350-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="0f350-118">Para obtener más información, consulte [el artículo de migración de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="0f350-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="0f350-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f350-119">See also</span></span>

* [<span data-ttu-id="0f350-120">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0f350-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0f350-121">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="0f350-121">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="0f350-122">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="0f350-122">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="0f350-123">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f350-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="0f350-124">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="0f350-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0f350-125">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="0f350-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0f350-126">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="0f350-126">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0f350-127">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="0f350-127">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0f350-128">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="0f350-128">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0f350-129">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="0f350-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="0f350-130">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0f350-130">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="0f350-131">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="0f350-131">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="0f350-132">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="0f350-132">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="0f350-133">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="0f350-133">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="0f350-134">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0f350-134">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="0f350-135">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0f350-135">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="0f350-136">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="0f350-136">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
