---
title: 'Procedimiento para serializar y deserializar JSON con C#: .NET'
description: Obtenga información sobre cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET. Incluye código de ejemplo.
ms.date: 11/05/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 1e8c46e11d3a82ca0bce29f9cb7bbc749c219198
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676730"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="89a70-104">Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="89a70-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="89a70-105">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json?displayProperty=fullName> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="89a70-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="89a70-106">Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="89a70-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="89a70-107">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="89a70-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="89a70-108">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad).</span><span class="sxs-lookup"><span data-stu-id="89a70-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="89a70-109">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.</span><span class="sxs-lookup"><span data-stu-id="89a70-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="89a70-110">Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:</span><span class="sxs-lookup"><span data-stu-id="89a70-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="89a70-111">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="89a70-111">Namespaces</span></span>

<span data-ttu-id="89a70-112">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="89a70-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="89a70-113">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="89a70-114">Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="89a70-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="89a70-115">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="89a70-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="89a70-116">Procedimiento para escribir objetos .NET en JSON (serializar)</span><span class="sxs-lookup"><span data-stu-id="89a70-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="89a70-117">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="89a70-118">En el ejemplo siguiente se crea un archivo JSON como cadena:</span><span class="sxs-lookup"><span data-stu-id="89a70-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-119">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-120">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-121">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="89a70-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="89a70-122">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="89a70-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="89a70-123">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="89a70-123">Serialization example</span></span>

<span data-ttu-id="89a70-124">A continuación se muestra una clase de ejemplo que contiene propiedades de tipo de colección y un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="89a70-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="89a70-125">"POCO" significa [objeto CRL estándar](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="89a70-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="89a70-126">Un POCO es un tipo de .NET que no depende de ningún tipo específico del marco, por ejemplo, a través de la herencia o atributos.</span><span class="sxs-lookup"><span data-stu-id="89a70-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="89a70-127">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="89a70-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="89a70-128">La salida JSON se minimiza de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="89a70-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="89a70-129">En el ejemplo siguiente se muestra el mismo JSON, pero con formato (es decir, impreso correctamente con espacio en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="89a70-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="89a70-130">Serialización a UTF-8</span><span class="sxs-lookup"><span data-stu-id="89a70-130">Serialize to UTF-8</span></span>

<span data-ttu-id="89a70-131">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="89a70-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-132">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="89a70-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="89a70-133">La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="89a70-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="89a70-134">La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="89a70-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="89a70-135">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="89a70-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="89a70-136">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="89a70-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="89a70-137">Puede [especificar propiedades para omitir](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="89a70-137">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="89a70-138">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="89a70-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="89a70-139">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="89a70-139">By default, JSON is minified.</span></span> <span data-ttu-id="89a70-140">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="89a70-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="89a70-141">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="89a70-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="89a70-142">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="89a70-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="89a70-143">De manera predeterminada, se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="89a70-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="89a70-144">Puede [conservar las referencias y administrar las referencias circulares](#preserve-references-and-handle-circular-references).</span><span class="sxs-lookup"><span data-stu-id="89a70-144">You can [preserve references and handle circular references](#preserve-references-and-handle-circular-references).</span></span>
* <span data-ttu-id="89a70-145">De forma predeterminada, se omiten los [campos](../../csharp/programming-guide/classes-and-structs/fields.md).</span><span class="sxs-lookup"><span data-stu-id="89a70-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="89a70-146">Puede [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="89a70-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="89a70-147">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="89a70-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="89a70-148">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="89a70-148">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="89a70-149">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="89a70-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="89a70-150">Puede [especificar propiedades para omitir](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="89a70-150">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="89a70-151">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="89a70-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="89a70-152">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="89a70-152">By default, JSON is minified.</span></span> <span data-ttu-id="89a70-153">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="89a70-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="89a70-154">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="89a70-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="89a70-155">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="89a70-155">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="89a70-156">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="89a70-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="89a70-157">Los [campos](../../csharp/programming-guide/classes-and-structs/fields.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="89a70-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="89a70-158">Los tipos no admitidos incluyen:</span><span class="sxs-lookup"><span data-stu-id="89a70-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="89a70-159">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="89a70-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="89a70-160">[Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="89a70-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="89a70-161">Matrices unidimensionales y escalonadas (`T[][]`).</span><span class="sxs-lookup"><span data-stu-id="89a70-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="89a70-162">Colecciones y diccionarios de los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="89a70-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="89a70-163">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="89a70-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="89a70-164">[Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="89a70-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="89a70-165">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="89a70-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="89a70-166">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="89a70-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="89a70-167">Colecciones de los espacios de nombres siguientes.</span><span class="sxs-lookup"><span data-stu-id="89a70-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="89a70-168">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="89a70-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="89a70-169">Procedimiento para leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="89a70-169">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="89a70-170">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="89a70-171">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecastWithPOCOs` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="89a70-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="89a70-172">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="89a70-173">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="89a70-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="89a70-174">Deserialización desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="89a70-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="89a70-175">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="89a70-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="89a70-176">En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="89a70-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="89a70-177">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="89a70-177">Deserialization behavior</span></span>

<span data-ttu-id="89a70-178">Al deserializar JSON se aplican los comportamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="89a70-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="89a70-179">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="89a70-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="89a70-180">Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="89a70-180">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="89a70-181">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="89a70-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="89a70-182">El serializador omite los constructores que no son públicos.</span><span class="sxs-lookup"><span data-stu-id="89a70-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="89a70-183">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="89a70-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="89a70-184">Vea [Tipos y registros inmutables](#immutable-types-and-records).</span><span class="sxs-lookup"><span data-stu-id="89a70-184">See [Immutable types and Records](#immutable-types-and-records).</span></span>
* <span data-ttu-id="89a70-185">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="89a70-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="89a70-186">Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="89a70-186">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="89a70-187">De forma predeterminada, los campos se omiten.</span><span class="sxs-lookup"><span data-stu-id="89a70-187">By default, fields are ignored.</span></span> <span data-ttu-id="89a70-188">Puede [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="89a70-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="89a70-189">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="89a70-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="89a70-190">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="89a70-190">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="89a70-191">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="89a70-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="89a70-192">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="89a70-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="89a70-193">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="89a70-193">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="89a70-194">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="89a70-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="89a70-195">Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="89a70-195">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span> <span data-ttu-id="89a70-196">Las aplicaciones de ASP.NET Core [especifican la no distinción de mayúsculas y minúsculas de forma predeterminada](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="89a70-196">ASP.NET Core apps [specify case-insensitivity by default](#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="89a70-197">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="89a70-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="89a70-198">Para la deserialización se usa un constructor sin parámetros, que puede ser público, interno o privado.</span><span class="sxs-lookup"><span data-stu-id="89a70-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="89a70-199">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="89a70-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="89a70-200">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="89a70-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="89a70-201">Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="89a70-201">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="89a70-202">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="89a70-202">Fields aren't supported.</span></span>
* <span data-ttu-id="89a70-203">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="89a70-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="89a70-204">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="89a70-204">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="89a70-205">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="89a70-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="89a70-206">Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="89a70-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="89a70-207">Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="89a70-207">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="89a70-208">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="89a70-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="89a70-209">Serialización a JSON con formato</span><span class="sxs-lookup"><span data-stu-id="89a70-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="89a70-210">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="89a70-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="89a70-211">Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="89a70-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="89a70-212">Inclusión de campos</span><span class="sxs-lookup"><span data-stu-id="89a70-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-213">Use el valor global <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> o el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos al serializar o deserializar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-213">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

<span data-ttu-id="89a70-214">Para omitir los campos de solo lectura, use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-214">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-215">Los campos no se admiten en System.Text.Json en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-215">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="89a70-216">Los [convertidores personalizados](system-text-json-converters-how-to.md) pueden proporcionar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="89a70-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="customize-json-names-and-values"></a><span data-ttu-id="89a70-217">Personalización de nombres y valores JSON</span><span class="sxs-lookup"><span data-stu-id="89a70-217">Customize JSON names and values</span></span>

<span data-ttu-id="89a70-218">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="89a70-218">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="89a70-219">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="89a70-219">Enum values are represented as numbers.</span></span> <span data-ttu-id="89a70-220">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="89a70-220">This section explains how to:</span></span>

* [<span data-ttu-id="89a70-221">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="89a70-221">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="89a70-222">Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="89a70-222">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="89a70-223">Implementar una directiva de nomenclatura de propiedades personalizada</span><span class="sxs-lookup"><span data-stu-id="89a70-223">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="89a70-224">Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="89a70-224">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="89a70-225">Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="89a70-225">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="89a70-226">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="89a70-226">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="89a70-227">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="89a70-227">Customize individual property names</span></span>

<span data-ttu-id="89a70-228">Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="89a70-228">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="89a70-229">Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="89a70-229">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="89a70-230">Nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="89a70-230">The property name set by this attribute:</span></span>

* <span data-ttu-id="89a70-231">Se aplica en ambas direcciones, para la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-231">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="89a70-232">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="89a70-232">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="89a70-233">Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="89a70-233">Use camel case for all JSON property names</span></span>

<span data-ttu-id="89a70-234">Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-234">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="89a70-235">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-235">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="89a70-236">La directiva de nomenclatura de propiedades en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="89a70-236">The camel case property naming policy:</span></span>

* <span data-ttu-id="89a70-237">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-237">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="89a70-238">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="89a70-238">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="89a70-239">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="89a70-239">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="89a70-240">Uso de una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="89a70-240">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="89a70-241">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-241">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="89a70-242">Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="89a70-242">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-243">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-243">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="89a70-244">La directiva de nomenclatura de propiedades JSON personalizada:</span><span class="sxs-lookup"><span data-stu-id="89a70-244">The JSON property naming policy:</span></span>

* <span data-ttu-id="89a70-245">Se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-245">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="89a70-246">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="89a70-246">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="89a70-247">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="89a70-247">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="89a70-248">Claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="89a70-248">Camel case dictionary keys</span></span>

<span data-ttu-id="89a70-249">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="89a70-249">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="89a70-250">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-250">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-251">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tenga pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` se traduciría en una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-251">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="89a70-252">La directiva de nomenclatura en mayúsculas y minúsculas combinadas Camel para las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-252">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="89a70-253">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON aunque se especifique `JsonNamingPolicy.CamelCase` para `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="89a70-253">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="89a70-254">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="89a70-254">Enums as strings</span></span>

<span data-ttu-id="89a70-255">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="89a70-255">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="89a70-256">Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="89a70-256">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="89a70-257">Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="89a70-257">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="89a70-258">Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="89a70-258">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="89a70-259">En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="89a70-259">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-260">El JSON resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-260">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="89a70-261">Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-261">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a><span data-ttu-id="89a70-262">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="89a70-262">Ignore properties</span></span>

<span data-ttu-id="89a70-263">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="89a70-263">By default, all public properties are serialized.</span></span> <span data-ttu-id="89a70-264">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="89a70-264">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="89a70-265">En esta sección se explica cómo omitir:</span><span class="sxs-lookup"><span data-stu-id="89a70-265">This section explains how to ignore:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="89a70-266">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="89a70-266">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="89a70-267">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="89a70-267">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="89a70-268">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="89a70-268">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="89a70-269">Todas las propiedades de valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="89a70-269">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="89a70-270">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="89a70-270">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="89a70-271">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="89a70-271">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="89a70-272">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="89a70-272">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a><span data-ttu-id="89a70-273">Omisión de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="89a70-273">Ignore individual properties</span></span>

<span data-ttu-id="89a70-274">Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="89a70-274">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="89a70-275">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-275">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-276">Puede especificar la exclusión condicional estableciendo la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="89a70-276">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="89a70-277">La enumeración <xref:System.Text.Json.Serialization.JsonIgnoreCondition> proporciona las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="89a70-277">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="89a70-278">`Always` - La propiedad se omite siempre.</span><span class="sxs-lookup"><span data-stu-id="89a70-278">`Always` - The property is always ignored.</span></span> <span data-ttu-id="89a70-279">Si no se especifica `Condition`, se presupone esta opción.</span><span class="sxs-lookup"><span data-stu-id="89a70-279">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="89a70-280">`Never` - La propiedad siempre se serializa y deserializa, independientemente de la configuración global de `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` y `IgnoreReadOnlyFields`.</span><span class="sxs-lookup"><span data-stu-id="89a70-280">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="89a70-281">`WhenWritingDefault` - La propiedad se omite en la serialización si es un tipo de referencia `null` o un tipo de valor `default`.</span><span class="sxs-lookup"><span data-stu-id="89a70-281">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null` or a value type `default`.</span></span>
* <span data-ttu-id="89a70-282">`WhenWritingNull` - La propiedad se omite en la serialización si es un tipo de referencia `null`.</span><span class="sxs-lookup"><span data-stu-id="89a70-282">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`.</span></span>

<span data-ttu-id="89a70-283">En el ejemplo siguiente se muestra el uso de la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):</span><span class="sxs-lookup"><span data-stu-id="89a70-283">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a><span data-ttu-id="89a70-284">Omisión de todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="89a70-284">Ignore all read-only properties</span></span>

<span data-ttu-id="89a70-285">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="89a70-285">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="89a70-286">Para omitir todas las propiedades de solo lectura durante la serialización, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-286">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-287">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-287">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="89a70-288">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-288">This option applies only to serialization.</span></span> <span data-ttu-id="89a70-289">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89a70-289">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-290">Esta opción solo se aplica a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="89a70-290">This option applies only to properties.</span></span> <span data-ttu-id="89a70-291">Para omitir los campos de solo lectura al [serializar campos](#include-fields), use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-291">To ignore read-only fields when [serializing fields](#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

### <a name="ignore-all-null-value-properties"></a><span data-ttu-id="89a70-292">Omisión de todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="89a70-292">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-293">Para omitir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-293">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-294">Para omitir todas las propiedades de valores NULL al serializar, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-294">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-295">Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-295">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="89a70-296">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="89a70-296">Property</span></span> |<span data-ttu-id="89a70-297">Value</span><span class="sxs-lookup"><span data-stu-id="89a70-297">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="89a70-298">Fecha</span><span class="sxs-lookup"><span data-stu-id="89a70-298">Date</span></span>    | <span data-ttu-id="89a70-299">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="89a70-299">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="89a70-300">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="89a70-300">TemperatureCelsius</span></span>| <span data-ttu-id="89a70-301">25</span><span class="sxs-lookup"><span data-stu-id="89a70-301">25</span></span> |
| <span data-ttu-id="89a70-302">Resumen</span><span class="sxs-lookup"><span data-stu-id="89a70-302">Summary</span></span>| <span data-ttu-id="89a70-303">null</span><span class="sxs-lookup"><span data-stu-id="89a70-303">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a><span data-ttu-id="89a70-304">Omisión de todas las propiedades de valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="89a70-304">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-305">Para evitar la serialización de valores predeterminados en las propiedades de tipo de valor, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-305">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="89a70-306">El valor `WhenWritingDefault` también evita la serialización de propiedades de tipo de referencia de valor NULL.</span><span class="sxs-lookup"><span data-stu-id="89a70-306">The `WhenWritingDefault` setting also prevents serialization of null-value reference type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-307">No hay ninguna manera integrada de evitar la serialización de propiedades con valores predeterminados de tipos de valor en System.Text.Json en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-307">There is no built-in way to prevent serialization of properties with value type defaults in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="customize-character-encoding"></a><span data-ttu-id="89a70-308">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="89a70-308">Customize character encoding</span></span>

<span data-ttu-id="89a70-309">De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="89a70-309">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="89a70-310">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="89a70-310">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="89a70-311">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89a70-311">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="89a70-312">Serialización de juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="89a70-312">Serialize language character sets</span></span>

<span data-ttu-id="89a70-313">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-313">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="89a70-314">Este código no escapa a los caracteres cirílicos o griegos.</span><span class="sxs-lookup"><span data-stu-id="89a70-314">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="89a70-315">Si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89a70-315">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="89a70-316">Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-316">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="89a70-317">Serialización de caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="89a70-317">Serialize specific characters</span></span>

<span data-ttu-id="89a70-318">Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="89a70-318">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="89a70-319">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="89a70-319">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="89a70-320">Aquí se muestra un ejemplo de JSON producido por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="89a70-320">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="89a70-321">Serialización de todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="89a70-321">Serialize all characters</span></span>

<span data-ttu-id="89a70-322">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-322">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="89a70-323">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:</span><span class="sxs-lookup"><span data-stu-id="89a70-323">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="89a70-324">No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.</span><span class="sxs-lookup"><span data-stu-id="89a70-324">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="89a70-325">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="89a70-325">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="89a70-326">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="89a70-326">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="89a70-327">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="89a70-327">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="89a70-328">No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="89a70-328">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="89a70-329">Serialización de propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="89a70-329">Serialize properties of derived classes</span></span>

<span data-ttu-id="89a70-330">No se admite la serialización de una jerarquía de tipos polimórficos.</span><span class="sxs-lookup"><span data-stu-id="89a70-330">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="89a70-331">Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="89a70-331">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="89a70-332">Las excepciones a este comportamiento se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="89a70-332">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="89a70-333">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="89a70-333">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="89a70-334">Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="89a70-334">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="89a70-335">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea en realidad un objeto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="89a70-335">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="89a70-336">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="89a70-336">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="89a70-337">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="89a70-337">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="89a70-338">Para serializar las propiedades del tipo derivado del ejemplo anterior, use uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="89a70-338">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="89a70-339">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="89a70-339">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="89a70-340">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="89a70-340">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="89a70-341">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-341">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="89a70-342">Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.</span><span class="sxs-lookup"><span data-stu-id="89a70-342">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="89a70-343">Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="89a70-343">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="89a70-344">Por ejemplo, supongamos que la clase `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:</span><span class="sxs-lookup"><span data-stu-id="89a70-344">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="89a70-345">Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="89a70-345">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="89a70-346">La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="89a70-346">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="89a70-347">La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="89a70-347">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="89a70-348">Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="89a70-348">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="89a70-349">En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:</span><span class="sxs-lookup"><span data-stu-id="89a70-349">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="89a70-350">El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="89a70-350">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="89a70-351">El mismo enfoque para definir propiedades como `object` funciona con interfaces.</span><span class="sxs-lookup"><span data-stu-id="89a70-351">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="89a70-352">Supongamos que tiene la interfaz y la implementación siguientes, y quiere serializar una clase con propiedades que contienen instancias de implementación:</span><span class="sxs-lookup"><span data-stu-id="89a70-352">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="89a70-353">Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:</span><span class="sxs-lookup"><span data-stu-id="89a70-353">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="89a70-354">En el ejemplo de código siguiente se muestra el JSON resultante del código anterior:</span><span class="sxs-lookup"><span data-stu-id="89a70-354">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="89a70-355">Para obtener más información sobre la **serialización**  polimórfica e información sobre la **deserialización**, consulte [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="89a70-355">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="89a70-356">Autorización de comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="89a70-356">Allow comments and trailing commas</span></span>

<span data-ttu-id="89a70-357">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-357">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="89a70-358">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="89a70-358">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="89a70-359">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="89a70-359">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="89a70-360">En el siguiente ejemplo se muestra cómo permitirlos ambos:</span><span class="sxs-lookup"><span data-stu-id="89a70-360">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="89a70-361">Aquí se muestra un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="89a70-361">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="89a70-362">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="89a70-362">Case-insensitive property matching</span></span>

<span data-ttu-id="89a70-363">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="89a70-363">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="89a70-364">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="89a70-364">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="89a70-365">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="89a70-365">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="89a70-366">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="89a70-366">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="89a70-367">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="89a70-367">Handle overflow JSON</span></span>

<span data-ttu-id="89a70-368">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="89a70-368">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="89a70-369">Por ejemplo, supongamos que el tipo de destino es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-369">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="89a70-370">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-370">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="89a70-371">Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="89a70-371">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="89a70-372">Para capturar datos adicionales tales como estas propiedades, aplique el atributo [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="89a70-372">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="89a70-373">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="89a70-373">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="89a70-374">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="89a70-374">Property</span></span> |<span data-ttu-id="89a70-375">Value</span><span class="sxs-lookup"><span data-stu-id="89a70-375">Value</span></span>  |<span data-ttu-id="89a70-376">Notas</span><span class="sxs-lookup"><span data-stu-id="89a70-376">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="89a70-377">Fecha</span><span class="sxs-lookup"><span data-stu-id="89a70-377">Date</span></span>    | <span data-ttu-id="89a70-378">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="89a70-378">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="89a70-379">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="89a70-379">TemperatureCelsius</span></span>| <span data-ttu-id="89a70-380">0</span><span class="sxs-lookup"><span data-stu-id="89a70-380">0</span></span> | <span data-ttu-id="89a70-381">Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="89a70-381">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="89a70-382">Resumen</span><span class="sxs-lookup"><span data-stu-id="89a70-382">Summary</span></span> | <span data-ttu-id="89a70-383">Acceso frecuente</span><span class="sxs-lookup"><span data-stu-id="89a70-383">Hot</span></span> ||
| <span data-ttu-id="89a70-384">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="89a70-384">ExtensionData</span></span> | <span data-ttu-id="89a70-385">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="89a70-385">temperatureCelsius: 25</span></span> |<span data-ttu-id="89a70-386">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="89a70-386">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="89a70-387">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="89a70-387">DatesAvailable:</span></span><br>  <span data-ttu-id="89a70-388">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="89a70-388">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="89a70-389">2/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="89a70-389">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="89a70-390">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="89a70-390">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="89a70-391">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="89a70-391">SummaryWords:</span></span><br><span data-ttu-id="89a70-392">Geniales</span><span class="sxs-lookup"><span data-stu-id="89a70-392">Cool</span></span><br><span data-ttu-id="89a70-393">Viento</span><span class="sxs-lookup"><span data-stu-id="89a70-393">Windy</span></span><br><span data-ttu-id="89a70-394">Húmedo</span><span class="sxs-lookup"><span data-stu-id="89a70-394">Humid</span></span> |<span data-ttu-id="89a70-395">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="89a70-395">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="89a70-396">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="89a70-396">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="89a70-397">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-397">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="89a70-398">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.</span><span class="sxs-lookup"><span data-stu-id="89a70-398">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="89a70-399">Conservación de las referencias y administración de las referencias circulares</span><span class="sxs-lookup"><span data-stu-id="89a70-399">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="89a70-400">Para conservar las referencias y administrar las referencias circulares, establezca <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> en <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span><span class="sxs-lookup"><span data-stu-id="89a70-400">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="89a70-401">Este valor produce el comportamiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-401">This setting causes the following behavior:</span></span>

* <span data-ttu-id="89a70-402">Al serializar:</span><span class="sxs-lookup"><span data-stu-id="89a70-402">On serialize:</span></span>

  <span data-ttu-id="89a70-403">Al escribir tipos complejos, el serializador también escribe propiedades de metadatos (`$id`, `$values` y `$ref`).</span><span class="sxs-lookup"><span data-stu-id="89a70-403">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="89a70-404">Al deserializar:</span><span class="sxs-lookup"><span data-stu-id="89a70-404">On deserialize:</span></span>

  <span data-ttu-id="89a70-405">Se esperan metadatos (aunque no es obligatorio) y el deserializador intenta entenderlo.</span><span class="sxs-lookup"><span data-stu-id="89a70-405">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="89a70-406">En el siguiente código se muestra el uso del parámetro `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="89a70-406">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="89a70-407">Esta característica no se puede usar para conservar tipos de valor o tipos inmutables.</span><span class="sxs-lookup"><span data-stu-id="89a70-407">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="89a70-408">En la deserialización, se crea la instancia de un tipo inmutable después de leer la carga completa.</span><span class="sxs-lookup"><span data-stu-id="89a70-408">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="89a70-409">Por lo tanto, sería imposible deserializar la misma instancia si aparece una referencia a ella dentro de la carga de JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-409">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="89a70-410">En el caso de los tipos de valor, los tipos inmutables y las matrices, no se serializan los metadatos de referencia.</span><span class="sxs-lookup"><span data-stu-id="89a70-410">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="89a70-411">En la deserialización, se produce una excepción si se encuentra `$ref` o `$id`.</span><span class="sxs-lookup"><span data-stu-id="89a70-411">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="89a70-412">Sin embargo, los tipos de valor omiten `$id` (y `$values` en el caso de las colecciones) para que sea posible deserializar las cargas que se serializaron mediante Newtonsoft.Json.</span><span class="sxs-lookup"><span data-stu-id="89a70-412">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="89a70-413">Newtonsoft.Json serializa los metadatos de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="89a70-413">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="89a70-414">Para determinar si los objetos son iguales, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, que usa la igualdad de referencia (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) en lugar de la igualdad de valores (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> cuando se comparan dos instancias de objeto.</span><span class="sxs-lookup"><span data-stu-id="89a70-414">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="89a70-415">Para obtener más información sobre cómo se serializan y deserializan las referencias, vea <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89a70-415">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="89a70-416">La clase <xref:System.Text.Json.Serialization.ReferenceResolver> define el comportamiento de conservar las referencias en la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="89a70-416">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="89a70-417">Cree una clase derivada para especificar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="89a70-417">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="89a70-418">Para obtener un ejemplo, vea [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="89a70-418">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-419">System.Text.Json en .NET Core 3.1 solo admite la serialización por valor y produce una excepción para las referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="89a70-419">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="89a70-420">Permitir o escribir números entre comillas</span><span class="sxs-lookup"><span data-stu-id="89a70-420">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="89a70-421">Algunos serializadores codifican números como cadenas JSON (entre comillas).</span><span class="sxs-lookup"><span data-stu-id="89a70-421">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="89a70-422">Por ejemplo, `{"DegreesCelsius":"23"}` en lugar de `{"DegreesCelsius":23}`.</span><span class="sxs-lookup"><span data-stu-id="89a70-422">For example: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="89a70-423">Para serializar los números entre comillas o aceptar números entre comillas en todo el gráfico del objeto de entrada, establezca <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-423">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

<span data-ttu-id="89a70-424">Cuando se usa System.Text.Json indirectamente a través de ASP.NET Core, se permiten números entre comillas al deserializar porque ASP.NET Core especifica [opciones predeterminadas web](xref:System.Text.Json.JsonSerializerDefaults.Web).</span><span class="sxs-lookup"><span data-stu-id="89a70-424">When you use System.Text.Json indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="89a70-425">Para permitir o escribir números entre comillas para propiedades, campos o tipos específicos, use el atributo [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="89a70-425">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-426">System.Text.Json en .NET Core 3.1 no admite la serialización o deserialización de números entre comillas.</span><span class="sxs-lookup"><span data-stu-id="89a70-426">System.Text.Json in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="89a70-427">Para obtener más información, vea [Permitir o escribir números entre comillas](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="89a70-427">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="immutable-types-and-records"></a><span data-ttu-id="89a70-428">Tipos y registros inmutables</span><span class="sxs-lookup"><span data-stu-id="89a70-428">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-429">System.Text.Json puede utilizar un constructor con parámetros, lo que hace posible deserializar una clase o estructura inmutable.</span><span class="sxs-lookup"><span data-stu-id="89a70-429">System.Text.Json can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="89a70-430">En el caso de una clase, si el único constructor está parametrizado, se utilizará ese constructor.</span><span class="sxs-lookup"><span data-stu-id="89a70-430">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="89a70-431">En el caso de una estructura o una clase con varios constructores, especifique el que se va a usar aplicando el atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="89a70-431">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="89a70-432">Cuando no se utiliza el atributo, siempre se usa un constructor sin parámetros público si está presente.</span><span class="sxs-lookup"><span data-stu-id="89a70-432">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="89a70-433">El atributo solo se puede usar con constructores públicos.</span><span class="sxs-lookup"><span data-stu-id="89a70-433">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="89a70-434">En el ejemplo siguiente se usa el atributo `[JsonConstructor]`:</span><span class="sxs-lookup"><span data-stu-id="89a70-434">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="89a70-435">También se admiten registros en C# 9, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-435">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="89a70-436">En el caso de los tipos que son inmutables porque todos sus establecedores de propiedad son no públicos, vea la siguiente sección sobre [los descriptores de acceso de propiedad no públicos](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="89a70-436">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-437">`JsonConstructorAttribute` y la compatibilidad con los registros en C# 9 no están disponibles en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-437">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="89a70-438">Descriptores de acceso de propiedad no públicos</span><span class="sxs-lookup"><span data-stu-id="89a70-438">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-439">Para habilitar el uso de un descriptor de acceso de propiedad no público, use el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-439">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-440">Los descriptores de acceso de propiedad no públicos no se admiten en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-440">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="89a70-441">Para obtener más información, consulte [el artículo de migración de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="89a70-441">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="89a70-442">Copia de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="89a70-442">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-443">Hay un [constructor de JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) que le permite crear una nueva instancia de con las mismas opciones que una instancia existente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-443">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-444">Un constructor de `JsonSerializerOptions` que toma una instancia existente no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-444">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="89a70-445">Valores predeterminados web para JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="89a70-445">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="89a70-446">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="89a70-446">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="89a70-447">Hay un [constructor de JsonSerializerOptions] (xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) que le permite crear una nueva instancia de con las opciones predeterminadas que ASP.NET Core utiliza para aplicaciones web, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-447">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-448">Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:</span><span class="sxs-lookup"><span data-stu-id="89a70-448">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="89a70-449">Un constructor de `JsonSerializerOptions` que especifica un conjunto de valores predeterminados no está disponible en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-449">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="89a70-450">Métodos de extensión HttpClient y HttpContent</span><span class="sxs-lookup"><span data-stu-id="89a70-450">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="89a70-451">La serialización y deserialización de cargas JSON de la red son operaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="89a70-451">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="89a70-452">Los métodos de extensión de [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) y [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permiten realizar estas operaciones en una sola línea de código.</span><span class="sxs-lookup"><span data-stu-id="89a70-452">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="89a70-453">Estos métodos de extensión usan [valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="89a70-453">These extension methods use [web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="89a70-454">En el siguiente ejemplo se muestra el uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="89a70-454">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

<span data-ttu-id="89a70-455">También hay métodos de extensión para System.Text.Json en [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="89a70-455">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="89a70-456">Los métodos de extensión de `HttpClient` y `HttpContent` no están disponibles en System.Text.Json en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="89a70-456">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="89a70-457">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="89a70-457">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="89a70-458"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="89a70-458"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="89a70-459">`Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="89a70-459">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="89a70-460">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="89a70-460">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="89a70-461"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="89a70-461"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="89a70-462">El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="89a70-462">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="89a70-463">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="89a70-463">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="89a70-464"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="89a70-464"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="89a70-465">La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-465">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="89a70-466">A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="89a70-466">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="89a70-467">El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="89a70-467">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="89a70-468">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="89a70-468">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="89a70-469">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-469">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="89a70-470">Uso de JsonDocument para acceder a datos</span><span class="sxs-lookup"><span data-stu-id="89a70-470">Use JsonDocument for access to data</span></span>

<span data-ttu-id="89a70-471">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:</span><span class="sxs-lookup"><span data-stu-id="89a70-471">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="89a70-472">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="89a70-472">The preceding code:</span></span>

* <span data-ttu-id="89a70-473">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="89a70-473">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="89a70-474">Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="89a70-474">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="89a70-475">Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.</span><span class="sxs-lookup"><span data-stu-id="89a70-475">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="89a70-476">Cuenta los alumnos incrementando una variable `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="89a70-476">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="89a70-477">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-477">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="89a70-478">Aquí se muestra un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="89a70-478">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="89a70-479">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="89a70-479">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="89a70-480">En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="89a70-480">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="89a70-481">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="89a70-481">The preceding code:</span></span>

* <span data-ttu-id="89a70-482">Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="89a70-482">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="89a70-483">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="89a70-483">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="89a70-484">Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="89a70-484">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="89a70-485">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="89a70-485">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="89a70-486">Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:</span><span class="sxs-lookup"><span data-stu-id="89a70-486">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="89a70-487">El resultado es la siguiente salida JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="89a70-487">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="89a70-488">Uso de Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="89a70-488">Use Utf8JsonWriter</span></span>

<span data-ttu-id="89a70-489">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="89a70-489">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="89a70-490">Uso de Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="89a70-490">Use Utf8JsonReader</span></span>

<span data-ttu-id="89a70-491">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="89a70-491">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="89a70-492">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="89a70-492">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="89a70-493">Filtrado de datos con Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="89a70-493">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="89a70-494">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor.</span><span class="sxs-lookup"><span data-stu-id="89a70-494">The following example shows how to read a file synchronously and search for a value.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="89a70-495">(Hay disponible una versión [asincrónica de este ejemplo](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs)).</span><span class="sxs-lookup"><span data-stu-id="89a70-495">(An [async version of this example](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs) is available.)</span></span>

<span data-ttu-id="89a70-496">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="89a70-496">The preceding code:</span></span>

* <span data-ttu-id="89a70-497">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="89a70-497">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="89a70-498">Cuenta los objetos y los valores de propiedad "name" que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="89a70-498">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="89a70-499">Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="89a70-499">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="89a70-500">Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89a70-500">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="89a70-501">Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto.</span><span class="sxs-lookup"><span data-stu-id="89a70-501">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="89a70-502">De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="89a70-502">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="89a70-503">Aquí se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="89a70-503">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="89a70-504">El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":</span><span class="sxs-lookup"><span data-stu-id="89a70-504">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="89a70-505">Lectura de una secuencia mediante Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="89a70-505">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="89a70-506">Al leer un archivo grande (un gigabyte o más de tamaño, por ejemplo), puede que desee evitar tener que cargar todo el archivo en la memoria de una vez.</span><span class="sxs-lookup"><span data-stu-id="89a70-506">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="89a70-507">En este escenario, puede usar <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="89a70-507">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="89a70-508">Al usar `Utf8JsonReader` para leer de una secuencia, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="89a70-508">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="89a70-509">El búfer que contiene la carga parcial JSON debe ser al menos tan grande como el token JSON más grande que contiene para que el lector pueda avanzar.</span><span class="sxs-lookup"><span data-stu-id="89a70-509">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="89a70-510">El búfer debe ser al menos tan grande como la secuencia más grande de espacio en blanco dentro del JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-510">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="89a70-511">El lector no realiza un seguimiento de los datos que ha leído hasta que lea completamente el <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> siguiente en la carga JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-511">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="89a70-512">Por tanto, cuando haya bytes restantes en el búfer, tendrá que volver a pasarlos al lector.</span><span class="sxs-lookup"><span data-stu-id="89a70-512">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="89a70-513">Puede usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar el número de bytes que quedan.</span><span class="sxs-lookup"><span data-stu-id="89a70-513">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="89a70-514">El código siguiente muestra cómo leer desde una secuencia.</span><span class="sxs-lookup"><span data-stu-id="89a70-514">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="89a70-515">Este ejemplo se muestra <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="89a70-515">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="89a70-516">Un código similar funcionará con <xref:System.IO.FileStream>, excepto cuando `FileStream` contenga una marca BOM UTF-8 al principio.</span><span class="sxs-lookup"><span data-stu-id="89a70-516">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="89a70-517">En ese caso, debe quitar esos tres bytes del búfer antes de pasar los bytes restantes a `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="89a70-517">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="89a70-518">En caso contrario, el lector produciría una excepción, ya que la marca BOM no se considera una parte válida del JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-518">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="89a70-519">El código de ejemplo comienza con un búfer de 4 KB y duplica el tamaño del búfer cada vez que encuentra que el tamaño no es lo suficientemente grande como para ajustarse a un token JSON completo, lo que es necesario para que el lector realice el progreso de la carga de JSON.</span><span class="sxs-lookup"><span data-stu-id="89a70-519">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="89a70-520">El ejemplo de JSON proporcionado en el fragmento de código desencadena un aumento del tamaño del búfer solo si se establece un tamaño de búfer inicial muy pequeño, por ejemplo, 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="89a70-520">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="89a70-521">Si establece el tamaño de búfer inicial en 10, las instrucciones `Console.WriteLine` muestran la causa y el efecto de los aumentos del tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="89a70-521">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="89a70-522">En el tamaño de búfer inicial de 4 KB, se muestra todo el JSON de ejemplo en cada `Console.WriteLine` y el tamaño del búfer nunca se debe aumentar.</span><span class="sxs-lookup"><span data-stu-id="89a70-522">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="89a70-523">En el ejemplo anterior no se establece ningún límite para el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="89a70-523">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="89a70-524">Si el tamaño del token es demasiado grande, se podría producir un error en el código con una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="89a70-524">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="89a70-525">Esto puede ocurrir si el archivo JSON contiene un token de aproximadamente 1 GB o más de tamaño, ya que la duplicación del tamaño de 1 GB da como resultado un tamaño demasiado grande para caber en un búfer de `int32`.</span><span class="sxs-lookup"><span data-stu-id="89a70-525">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89a70-526">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="89a70-526">Additional resources</span></span>

* [<span data-ttu-id="89a70-527">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89a70-527">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="89a70-528">Procedimientos para escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="89a70-528">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="89a70-529">Procedimiento para migrar desde Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="89a70-529">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="89a70-530">Compatibilidad con DateTime y DateTimeOffset en System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="89a70-530">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="89a70-531">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="89a70-531">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
