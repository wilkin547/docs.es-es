---
title: 'Procedimiento para serializar y deserializar JSON con C#: .NET'
description: Obtenga información sobre cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET. Incluye código de ejemplo.
ms.date: 11/30/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9ea9e2fef5ef66f2a5ff816168abfbd7b2e75276
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437671"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="1c0ff-104">Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="1c0ff-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="1c0ff-105">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json?displayProperty=fullName> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="1c0ff-106">Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="1c0ff-107">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1c0ff-108">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1c0ff-109">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="1c0ff-110">Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a><span data-ttu-id="1c0ff-111">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="1c0ff-111">Namespaces</span></span>

<span data-ttu-id="1c0ff-112">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1c0ff-113">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1c0ff-114">Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="1c0ff-115">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="1c0ff-116">Escritura de objetos .NET como JSON (serializar)</span><span class="sxs-lookup"><span data-stu-id="1c0ff-116">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="1c0ff-117">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1c0ff-118">En el ejemplo siguiente se crea un archivo JSON como cadena:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-118">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="1c0ff-119">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-119">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="1c0ff-120">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-120">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="1c0ff-121">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1c0ff-122">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="1c0ff-123">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="1c0ff-123">Serialization example</span></span>

<span data-ttu-id="1c0ff-124">A continuación se muestra una clase de ejemplo que contiene propiedades de tipo de colección y un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="1c0ff-125">"POCO" significa [objeto CRL estándar](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="1c0ff-126">Un POCO es un tipo de .NET que no depende de ningún tipo específico del marco, por ejemplo, a través de la herencia o atributos.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="1c0ff-127">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1c0ff-128">La salida JSON es reducida (se quitan los caracteres de espacio en blanco, sangría y nueva línea) de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-128">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1c0ff-129">En el ejemplo siguiente se muestra el mismo JSON, pero con formato (es decir, impreso correctamente con espacio en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="1c0ff-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

## <a name="serialize-to-utf-8"></a><span data-ttu-id="1c0ff-130">Serialización a UTF-8</span><span class="sxs-lookup"><span data-stu-id="1c0ff-130">Serialize to UTF-8</span></span>

<span data-ttu-id="1c0ff-131">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="1c0ff-132">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1c0ff-133">La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1c0ff-134">La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1c0ff-135">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="1c0ff-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c0ff-136">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="1c0ff-137">Puede [especificar propiedades para omitir](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-137">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="1c0ff-138">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1c0ff-139">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-139">By default, JSON is minified.</span></span> <span data-ttu-id="1c0ff-140">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1c0ff-141">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1c0ff-142">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-142">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="1c0ff-143">De manera predeterminada, se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="1c0ff-144">Puede [conservar las referencias y administrar las referencias circulares](system-text-json-preserve-references.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-144">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="1c0ff-145">De forma predeterminada, se omiten los [campos](../../csharp/programming-guide/classes-and-structs/fields.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="1c0ff-146">Puede [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="1c0ff-147">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c0ff-148">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-148">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c0ff-149">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="1c0ff-150">Puede [especificar propiedades para omitir](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-150">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="1c0ff-151">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1c0ff-152">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-152">By default, JSON is minified.</span></span> <span data-ttu-id="1c0ff-153">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1c0ff-154">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1c0ff-155">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-155">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="1c0ff-156">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="1c0ff-157">Los [campos](../../csharp/programming-guide/classes-and-structs/fields.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="1c0ff-158">Los tipos no admitidos incluyen:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c0ff-159">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1c0ff-160">[Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1c0ff-161">Matrices unidimensionales y escalonadas (`T[][]`).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="1c0ff-162">Colecciones y diccionarios de los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c0ff-163">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1c0ff-164">[Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1c0ff-165">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1c0ff-166">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1c0ff-167">Colecciones de los espacios de nombres siguientes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="1c0ff-168">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="1c0ff-169">Lectura de JSON como objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="1c0ff-169">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="1c0ff-170">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1c0ff-171">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecastWithPOCOs` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="1c0ff-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="1c0ff-172">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="1c0ff-173">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="1c0ff-174">Deserialización desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="1c0ff-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="1c0ff-175">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `ReadOnlySpan<byte>` o `Utf8JsonReader`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="1c0ff-176">En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="1c0ff-177">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="1c0ff-177">Deserialization behavior</span></span>

<span data-ttu-id="1c0ff-178">Al deserializar JSON se aplican los comportamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c0ff-179">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1c0ff-180">Puede [especificar la no distinción de mayúsculas y minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-180">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="1c0ff-181">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1c0ff-182">El serializador omite los constructores que no son públicos.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="1c0ff-183">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="1c0ff-184">Vea [Tipos y registros inmutables](system-text-json-immutability.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-184">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="1c0ff-185">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1c0ff-186">Puede [serializar nombres de enumeración como cadenas](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-186">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="1c0ff-187">De forma predeterminada, los campos se omiten.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-187">By default, fields are ignored.</span></span> <span data-ttu-id="1c0ff-188">Puede [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="1c0ff-189">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1c0ff-190">Puede [permitir comentarios y comas finales](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-190">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="1c0ff-191">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1c0ff-192">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c0ff-193">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-193">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c0ff-194">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1c0ff-195">Puede [especificar la no distinción de mayúsculas y minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-195">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="1c0ff-196">Las aplicaciones de ASP.NET Core [especifican la no distinción de mayúsculas y minúsculas de forma predeterminada](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-196">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="1c0ff-197">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1c0ff-198">Para la deserialización se usa un constructor sin parámetros, que puede ser público, interno o privado.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="1c0ff-199">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="1c0ff-200">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1c0ff-201">Puede [serializar nombres de enumeración como cadenas](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-201">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="1c0ff-202">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-202">Fields aren't supported.</span></span>
* <span data-ttu-id="1c0ff-203">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1c0ff-204">Puede [permitir comentarios y comas finales](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-204">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="1c0ff-205">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1c0ff-206">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c0ff-207">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-207">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="1c0ff-208">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1c0ff-209">Serialización a JSON con formato</span><span class="sxs-lookup"><span data-stu-id="1c0ff-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="1c0ff-210">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="1c0ff-211">Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="1c0ff-212">Inclusión de campos</span><span class="sxs-lookup"><span data-stu-id="1c0ff-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c0ff-213">Use el valor global <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> o el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos al serializar o deserializar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-213">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="1c0ff-214">Para omitir los campos de solo lectura, use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-214">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c0ff-215">Los campos no se admiten en System.Text.Json en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-215">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="1c0ff-216">Los [convertidores personalizados](system-text-json-converters-how-to.md) pueden proporcionar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="1c0ff-217">Métodos de extensión HttpClient y HttpContent</span><span class="sxs-lookup"><span data-stu-id="1c0ff-217">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1c0ff-218">La serialización y deserialización de cargas JSON de la red son operaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-218">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="1c0ff-219">Los métodos de extensión de [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) y [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permiten realizar estas operaciones en una sola línea de código.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-219">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="1c0ff-220">Estos métodos de extensión usan [valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-220">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="1c0ff-221">En el siguiente ejemplo se muestra el uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1c0ff-221">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="1c0ff-222">También hay métodos de extensión para System.Text.Json en [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="1c0ff-222">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c0ff-223">Los métodos de extensión de `HttpClient` y `HttpContent` no están disponibles en System.Text.Json en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1c0ff-223">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="1c0ff-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c0ff-224">See also</span></span>

* [<span data-ttu-id="1c0ff-225">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1c0ff-225">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1c0ff-226">Procedimientos para escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="1c0ff-226">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1c0ff-227">Procedimiento para migrar desde Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="1c0ff-227">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1c0ff-228">Compatibilidad con DateTime y DateTimeOffset en System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1c0ff-228">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="1c0ff-229">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1c0ff-229">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
