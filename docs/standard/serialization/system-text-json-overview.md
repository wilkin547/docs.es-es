---
title: 'Serialización y deserialización de JSON con C#: .NET'
description: En esta introducción se describe la funcionalidad del espacio de nombres System.Text.Json para serializar y deserializar con JSON en .NET.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009890"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="164e5-103">Serialización y deserialización de JSON en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="164e5-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="164e5-104">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript).</span><span class="sxs-lookup"><span data-stu-id="164e5-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="164e5-105">El diseño de biblioteca resalta el rendimiento elevado y la asignación de memoria baja en un amplio conjunto de características.</span><span class="sxs-lookup"><span data-stu-id="164e5-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="164e5-106">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en Internet y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="164e5-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="164e5-107">La biblioteca también proporciona clases para trabajar con un Document Object Model (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="164e5-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="164e5-108">Esta característica permite el acceso de solo lectura aleatorio de los elementos de una cadena o archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="164e5-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="164e5-109">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="164e5-109">How to get the library</span></span>

* <span data-ttu-id="164e5-110">La biblioteca está integrada como parte del marco compartido para .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="164e5-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="164e5-111">Para versiones anteriores del marco, instale el paquete [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) de NuGet,</span><span class="sxs-lookup"><span data-stu-id="164e5-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="164e5-112">que admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="164e5-112">The package supports:</span></span>

  * <span data-ttu-id="164e5-113">.NET Standard 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="164e5-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="164e5-114">.NET Framework 4.7.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="164e5-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="164e5-115">.NET Core 2.0, 2.1 y 2.2</span><span class="sxs-lookup"><span data-stu-id="164e5-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="164e5-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="164e5-116">Additional resources</span></span>

* [<span data-ttu-id="164e5-117">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="164e5-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="164e5-118">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="164e5-118">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="164e5-119">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="164e5-119">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="164e5-120">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="164e5-120">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="164e5-121">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="164e5-121">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="164e5-122">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="164e5-122">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="164e5-123">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="164e5-123">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="164e5-124">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="164e5-124">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="164e5-125">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="164e5-125">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="164e5-126">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="164e5-126">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="164e5-127">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="164e5-127">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="164e5-128">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="164e5-128">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="164e5-129">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="164e5-129">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="164e5-130">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="164e5-130">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="164e5-131">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="164e5-131">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="164e5-132">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="164e5-132">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="164e5-133">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="164e5-133">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
