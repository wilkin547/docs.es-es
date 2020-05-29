---
title: ''
description: En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET. Incluye código de ejemplo.
ms.date: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords: []
ms.openlocfilehash: f1a5da448b08f9b4f1cf3fa6cba67fb376b00a6f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702290"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="b6d08-103">Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="b6d08-103">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="b6d08-104">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="b6d08-104">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="b6d08-105">Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="b6d08-105">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="b6d08-106">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="b6d08-106">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="b6d08-107">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad).</span><span class="sxs-lookup"><span data-stu-id="b6d08-107">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="b6d08-108">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.</span><span class="sxs-lookup"><span data-stu-id="b6d08-108">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="b6d08-109">Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:</span><span class="sxs-lookup"><span data-stu-id="b6d08-109">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="b6d08-110">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="b6d08-110">Namespaces</span></span>

<span data-ttu-id="b6d08-111">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="b6d08-111">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="b6d08-112">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-112">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="b6d08-113">Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="b6d08-113">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="b6d08-114">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-114">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="b6d08-115">Procedimiento para escribir objetos .NET en JSON (serializar)</span><span class="sxs-lookup"><span data-stu-id="b6d08-115">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="b6d08-116">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-116">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="b6d08-117">En el ejemplo siguiente se crea un archivo JSON como cadena:</span><span class="sxs-lookup"><span data-stu-id="b6d08-117">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-118">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-118">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-119">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-119">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-120">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="b6d08-120">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="b6d08-121">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="b6d08-121">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="b6d08-122">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="b6d08-122">Serialization example</span></span>

<span data-ttu-id="b6d08-123">Aquí se muestra una clase de ejemplo que contiene colecciones y una clase anidada:</span><span class="sxs-lookup"><span data-stu-id="b6d08-123">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="b6d08-124">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b6d08-124">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="b6d08-125">La salida JSON se minimiza de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b6d08-125">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="b6d08-126">En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, impreso correctamente con espacio en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="b6d08-126">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="b6d08-127">Serialización a UTF-8</span><span class="sxs-lookup"><span data-stu-id="b6d08-127">Serialize to UTF-8</span></span>

<span data-ttu-id="b6d08-128">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b6d08-128">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-129">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-129">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="b6d08-130">La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-130">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="b6d08-131">La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="b6d08-131">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="b6d08-132">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="b6d08-132">Serialization behavior</span></span>

* <span data-ttu-id="b6d08-133">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-133">By default, all public properties are serialized.</span></span> <span data-ttu-id="b6d08-134">Puede [especificar propiedades para excluir](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="b6d08-134">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="b6d08-135">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="b6d08-135">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="b6d08-136">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="b6d08-136">By default, JSON is minified.</span></span> <span data-ttu-id="b6d08-137">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="b6d08-137">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="b6d08-138">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-138">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="b6d08-139">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="b6d08-139">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="b6d08-140">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="b6d08-140">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="b6d08-141">Actualmente, se excluyen los campos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-141">Currently, fields are excluded.</span></span>

<span data-ttu-id="b6d08-142">Los tipos no admitidos incluyen:</span><span class="sxs-lookup"><span data-stu-id="b6d08-142">Supported types include:</span></span>

* <span data-ttu-id="b6d08-143">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-143">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="b6d08-144">[Objetos CLR antiguos sin formato (POCO)](https://stackoverflow.com/questions/250001/poco-definition) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b6d08-144">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="b6d08-145">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="b6d08-145">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="b6d08-146">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="b6d08-146">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="b6d08-147">Colecciones de los espacios de nombres siguientes.</span><span class="sxs-lookup"><span data-stu-id="b6d08-147">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="b6d08-148">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="b6d08-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="b6d08-149">Procedimiento para leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="b6d08-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="b6d08-150">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="b6d08-151">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecast` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="b6d08-151">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-152">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-153">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="b6d08-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="b6d08-154">Deserialización desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="b6d08-154">Deserialize from UTF-8</span></span>

<span data-ttu-id="b6d08-155">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b6d08-155">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="b6d08-156">En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="b6d08-156">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="b6d08-157">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="b6d08-157">Deserialization behavior</span></span>

* <span data-ttu-id="b6d08-158">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-158">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="b6d08-159">Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="b6d08-159">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="b6d08-160">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="b6d08-160">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="b6d08-161">No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="b6d08-161">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="b6d08-162">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b6d08-162">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="b6d08-163">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="b6d08-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="b6d08-164">Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="b6d08-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="b6d08-165">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-165">Fields aren't supported.</span></span>
* <span data-ttu-id="b6d08-166">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="b6d08-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="b6d08-167">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="b6d08-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="b6d08-168">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="b6d08-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="b6d08-169">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="b6d08-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="b6d08-170">Serialización a JSON con formato</span><span class="sxs-lookup"><span data-stu-id="b6d08-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="b6d08-171">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="b6d08-172">Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="b6d08-173">Personalización de nombres y valores JSON</span><span class="sxs-lookup"><span data-stu-id="b6d08-173">Customize JSON names and values</span></span>

<span data-ttu-id="b6d08-174">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="b6d08-175">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="b6d08-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="b6d08-176">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="b6d08-176">This section explains how to:</span></span>

* [<span data-ttu-id="b6d08-177">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="b6d08-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="b6d08-178">Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="b6d08-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="b6d08-179">Implementar una directiva de nomenclatura de propiedades personalizada</span><span class="sxs-lookup"><span data-stu-id="b6d08-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="b6d08-180">Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="b6d08-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="b6d08-181">Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="b6d08-181">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="b6d08-182">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="b6d08-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="b6d08-183">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="b6d08-183">Customize individual property names</span></span>

<span data-ttu-id="b6d08-184">Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="b6d08-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="b6d08-185">Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="b6d08-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b6d08-186">Nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="b6d08-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="b6d08-187">Se aplica en ambas direcciones, para la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="b6d08-188">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b6d08-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="b6d08-189">Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="b6d08-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="b6d08-190">Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="b6d08-191">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b6d08-192">La directiva de nomenclatura de propiedades en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="b6d08-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="b6d08-193">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="b6d08-194">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="b6d08-195">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="b6d08-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="b6d08-196">Uso de una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="b6d08-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="b6d08-197">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="b6d08-198">Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="b6d08-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-199">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b6d08-200">La directiva de nomenclatura de propiedades JSON personalizada:</span><span class="sxs-lookup"><span data-stu-id="b6d08-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="b6d08-201">Se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="b6d08-202">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="b6d08-203">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="b6d08-204">Claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="b6d08-204">Camel case dictionary keys</span></span>

<span data-ttu-id="b6d08-205">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="b6d08-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="b6d08-206">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-207">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tenga pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` se traduciría en una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="b6d08-208">La directiva de nomenclatura en mayúsculas y minúsculas combinadas Camel para las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="b6d08-209">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON aunque se especifique `JsonNamingPolicy.CamelCase` para `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="b6d08-210">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="b6d08-210">Enums as strings</span></span>

<span data-ttu-id="b6d08-211">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="b6d08-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="b6d08-212">Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="b6d08-213">Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="b6d08-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="b6d08-214">Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b6d08-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="b6d08-215">En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="b6d08-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-216">El JSON resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="b6d08-217">Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="b6d08-218">Exclusión de propiedades de la serialización</span><span class="sxs-lookup"><span data-stu-id="b6d08-218">Exclude properties from serialization</span></span>

<span data-ttu-id="b6d08-219">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="b6d08-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="b6d08-220">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="b6d08-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="b6d08-221">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="b6d08-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="b6d08-222">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="b6d08-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="b6d08-223">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="b6d08-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="b6d08-224">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="b6d08-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="b6d08-225">Exclusión de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="b6d08-225">Exclude individual properties</span></span>

<span data-ttu-id="b6d08-226">Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="b6d08-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="b6d08-227">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="b6d08-228">Exclusión de todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="b6d08-228">Exclude all read-only properties</span></span>

<span data-ttu-id="b6d08-229">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="b6d08-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="b6d08-230">Para excluir todas las propiedades de solo lectura, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-231">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="b6d08-232">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-232">This option applies only to serialization.</span></span> <span data-ttu-id="b6d08-233">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b6d08-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="b6d08-234">Exclusión de todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="b6d08-234">Exclude all null value properties</span></span>

<span data-ttu-id="b6d08-235">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-236">Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="b6d08-237">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6d08-237">Property</span></span> |<span data-ttu-id="b6d08-238">Valor</span><span class="sxs-lookup"><span data-stu-id="b6d08-238">Value</span></span>  |
|---
<span data-ttu-id="b6d08-239">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-239">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-240">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-240">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-241">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-241">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-242">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-242">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-243">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-243">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b6d08-244">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-244">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-245">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-245">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-246">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-246">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-247">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-247">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-248">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-248">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b6d08-249">-----|--- title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-249">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-250">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-250">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-251">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-251">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-252">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-252">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-253">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-253">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b6d08-254">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-254">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-255">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-255">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-256">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-256">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-257">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-257">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-258">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-258">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b6d08-259">-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|</span><span class="sxs-lookup"><span data-stu-id="b6d08-259">-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="b6d08-260">Este valor se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-260">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="b6d08-261">Para obtener información sobre su efecto en la deserialización, consulte el artículo sobre cómo [omitir valores NULL al deserializar](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="b6d08-261">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="b6d08-262">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="b6d08-262">Customize character encoding</span></span>

<span data-ttu-id="b6d08-263">De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="b6d08-263">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="b6d08-264">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="b6d08-264">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="b6d08-265">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6d08-265">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="b6d08-266">Serialización de juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="b6d08-266">Serialize language character sets</span></span>

<span data-ttu-id="b6d08-267">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-267">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="b6d08-268">Este código no escapa a los caracteres cirílicos o griegos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-268">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="b6d08-269">Si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6d08-269">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="b6d08-270">Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-270">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="b6d08-271">Serialización de caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="b6d08-271">Serialize specific characters</span></span>

<span data-ttu-id="b6d08-272">Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="b6d08-272">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="b6d08-273">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="b6d08-273">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="b6d08-274">Aquí se muestra un ejemplo de JSON producido por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="b6d08-274">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="b6d08-275">Serialización de todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="b6d08-275">Serialize all characters</span></span>

<span data-ttu-id="b6d08-276">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-276">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="b6d08-277">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:</span><span class="sxs-lookup"><span data-stu-id="b6d08-277">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="b6d08-278">No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-278">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="b6d08-279">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="b6d08-279">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="b6d08-280">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b6d08-280">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="b6d08-281">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-281">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="b6d08-282">No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-282">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="b6d08-283">Serialización de propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="b6d08-283">Serialize properties of derived classes</span></span>

<span data-ttu-id="b6d08-284">No se admite la serialización de una jerarquía de tipos polimórficos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-284">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="b6d08-285">Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="b6d08-285">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="b6d08-286">Las excepciones a este comportamiento se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="b6d08-286">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="b6d08-287">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-287">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="b6d08-288">Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-288">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="b6d08-289">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea en realidad un objeto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-289">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="b6d08-290">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="b6d08-290">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="b6d08-291">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6d08-291">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="b6d08-292">Para serializar las propiedades del tipo derivado del ejemplo anterior, use uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d08-292">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="b6d08-293">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="b6d08-293">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="b6d08-294">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-294">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="b6d08-295">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-295">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="b6d08-296">Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.</span><span class="sxs-lookup"><span data-stu-id="b6d08-296">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="b6d08-297">Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-297">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="b6d08-298">Por ejemplo, supongamos que la clase `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-298">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="b6d08-299">Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-299">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="b6d08-300">La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-300">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="b6d08-301">La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-301">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="b6d08-302">Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="b6d08-302">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="b6d08-303">En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-303">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="b6d08-304">El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-304">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="b6d08-305">El mismo enfoque para definir propiedades como `object` funciona con interfaces.</span><span class="sxs-lookup"><span data-stu-id="b6d08-305">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="b6d08-306">Supongamos que tiene la interfaz y la implementación siguientes, y quiere serializar una clase con propiedades que contienen instancias de implementación:</span><span class="sxs-lookup"><span data-stu-id="b6d08-306">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="b6d08-307">Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-307">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="b6d08-308">En el ejemplo de código siguiente se muestra el JSON resultante del código anterior:</span><span class="sxs-lookup"><span data-stu-id="b6d08-308">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="b6d08-309">Para obtener más información sobre la **serialización**  polimórfica e información sobre la **deserialización**, consulte [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="b6d08-309">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="b6d08-310">Autorización de comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="b6d08-310">Allow comments and trailing commas</span></span>

<span data-ttu-id="b6d08-311">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-311">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="b6d08-312">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-312">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="b6d08-313">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-313">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="b6d08-314">En el siguiente ejemplo se muestra cómo permitirlos ambos:</span><span class="sxs-lookup"><span data-stu-id="b6d08-314">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-315">Aquí se muestra un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="b6d08-315">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="b6d08-316">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b6d08-316">Case-insensitive property matching</span></span>

<span data-ttu-id="b6d08-317">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="b6d08-317">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="b6d08-318">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-318">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-319">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="b6d08-319">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="b6d08-320">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="b6d08-320">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="b6d08-321">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="b6d08-321">Handle overflow JSON</span></span>

<span data-ttu-id="b6d08-322">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="b6d08-322">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="b6d08-323">Por ejemplo, supongamos que el tipo de destino es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-323">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="b6d08-324">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-324">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="b6d08-325">Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="b6d08-325">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="b6d08-326">Para capturar datos adicionales tales como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-326">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="b6d08-327">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="b6d08-327">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="b6d08-328">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6d08-328">Property</span></span> |<span data-ttu-id="b6d08-329">Valor</span><span class="sxs-lookup"><span data-stu-id="b6d08-329">Value</span></span>  |<span data-ttu-id="b6d08-330">Notas</span><span class="sxs-lookup"><span data-stu-id="b6d08-330">Notes</span></span>  |
|---
<span data-ttu-id="b6d08-331">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-331">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-332">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-332">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-333">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-333">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-334">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-334">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-335">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-335">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b6d08-336">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-336">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-337">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-337">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-338">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-338">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-339">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-339">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-340">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-340">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b6d08-341">-----|--- title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-341">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-342">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-342">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-343">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-343">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-344">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-344">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-345">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-345">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b6d08-346">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-346">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-347">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-347">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-348">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-348">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-349">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-349">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-350">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-350">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b6d08-351">-----|--- title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-351">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-352">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-352">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-353">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-353">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-354">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-354">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-355">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-355">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b6d08-356">title: description: "En este artículo se muestra cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d08-356">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b6d08-357">Incluye código de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="b6d08-357">It includes sample code.'</span></span>
<span data-ttu-id="b6d08-358">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b6d08-358">ms.date: no-loc:</span></span>
- <span data-ttu-id="b6d08-359">"System.Text.Json"</span><span class="sxs-lookup"><span data-stu-id="b6d08-359">'System.Text.Json'</span></span>
- <span data-ttu-id="b6d08-360">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-360">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b6d08-361">-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6d08-361">-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> <span data-ttu-id="b6d08-362">| | Summary | Hot || | ExtensionData | temperatureCelsius: 25 | Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.| || DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="b6d08-362">| | Summary | Hot || | ExtensionData | temperatureCelsius: 25 |Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.| || DatesAvailable:</span></span><br>  <span data-ttu-id="b6d08-363">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="b6d08-363">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="b6d08-364">8/2/2019 12:00:00 AM -07:00 | La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.| | |SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="b6d08-364">8/2/2019 12:00:00 AM -07:00 |Extra property from the JSON becomes a key-value pair, with an array as the value object.| | |SummaryWords:</span></span><br><span data-ttu-id="b6d08-365">Geniales</span><span class="sxs-lookup"><span data-stu-id="b6d08-365">Cool</span></span><br><span data-ttu-id="b6d08-366">Viento</span><span class="sxs-lookup"><span data-stu-id="b6d08-366">Windy</span></span><br><span data-ttu-id="b6d08-367">Humid |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.|</span><span class="sxs-lookup"><span data-stu-id="b6d08-367">Humid |Extra property from the JSON becomes a key-value pair, with an array as the value object.|</span></span>

<span data-ttu-id="b6d08-368">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="b6d08-368">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="b6d08-369">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-369">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="b6d08-370">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.</span><span class="sxs-lookup"><span data-stu-id="b6d08-370">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="b6d08-371">Omisión de NULL al deserializar</span><span class="sxs-lookup"><span data-stu-id="b6d08-371">Ignore null when deserializing</span></span>

<span data-ttu-id="b6d08-372">De forma predeterminada, si una propiedad en JSON es NULL, la propiedad correspondiente en el objeto de destino se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="b6d08-372">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="b6d08-373">En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no se quiere que un valor NULL invalide el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b6d08-373">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="b6d08-374">Por ejemplo, supongamos que el siguiente código representa su objeto de destino:</span><span class="sxs-lookup"><span data-stu-id="b6d08-374">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="b6d08-375">Supongamos también que se deserializa el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-375">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="b6d08-376">Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.</span><span class="sxs-lookup"><span data-stu-id="b6d08-376">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="b6d08-377">Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-377">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-378">Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "No summary" después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b6d08-378">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="b6d08-379">Los valores NULL en JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="b6d08-379">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="b6d08-380">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="b6d08-380">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="b6d08-381">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="b6d08-381">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="b6d08-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="b6d08-383">`Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6d08-383">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="b6d08-384">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6d08-384">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="b6d08-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="b6d08-386">El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6d08-386">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="b6d08-387">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6d08-387">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="b6d08-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="b6d08-389">La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-389">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="b6d08-390">A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-390">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="b6d08-391">El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="b6d08-391">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="b6d08-392">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-392">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="b6d08-393">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-393">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="b6d08-394">Uso de JsonDocument para acceder a datos</span><span class="sxs-lookup"><span data-stu-id="b6d08-394">Use JsonDocument for access to data</span></span>

<span data-ttu-id="b6d08-395">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:</span><span class="sxs-lookup"><span data-stu-id="b6d08-395">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="b6d08-396">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="b6d08-396">The preceding code:</span></span>

* <span data-ttu-id="b6d08-397">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-397">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="b6d08-398">Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-398">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="b6d08-399">Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.</span><span class="sxs-lookup"><span data-stu-id="b6d08-399">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="b6d08-400">Cuenta los alumnos incrementando una variable `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="b6d08-400">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="b6d08-401">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-401">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="b6d08-402">Aquí se muestra un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="b6d08-402">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="b6d08-403">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="b6d08-403">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="b6d08-404">En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="b6d08-404">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="b6d08-405">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="b6d08-405">The preceding code:</span></span>

* <span data-ttu-id="b6d08-406">Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b6d08-406">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="b6d08-407">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="b6d08-407">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="b6d08-408">Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="b6d08-408">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="b6d08-409">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="b6d08-409">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="b6d08-410">Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:</span><span class="sxs-lookup"><span data-stu-id="b6d08-410">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="b6d08-411">El resultado es la siguiente salida JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-411">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="b6d08-412">Uso de Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="b6d08-412">Use Utf8JsonWriter</span></span>

<span data-ttu-id="b6d08-413">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="b6d08-413">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="b6d08-414">Uso de Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="b6d08-414">Use Utf8JsonReader</span></span>

<span data-ttu-id="b6d08-415">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="b6d08-415">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="b6d08-416">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b6d08-416">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="b6d08-417">Filtrado de datos con Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="b6d08-417">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="b6d08-418">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:</span><span class="sxs-lookup"><span data-stu-id="b6d08-418">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="b6d08-419">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="b6d08-419">The preceding code:</span></span>

* <span data-ttu-id="b6d08-420">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="b6d08-420">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="b6d08-421">Cuenta los objetos y los valores de propiedad "name" que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="b6d08-421">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="b6d08-422">Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b6d08-422">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="b6d08-423">Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d08-423">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="b6d08-424">Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto.</span><span class="sxs-lookup"><span data-stu-id="b6d08-424">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="b6d08-425">De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="b6d08-425">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="b6d08-426">Aquí se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="b6d08-426">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="b6d08-427">El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":</span><span class="sxs-lookup"><span data-stu-id="b6d08-427">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="b6d08-428">Lectura de una secuencia mediante Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="b6d08-428">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="b6d08-429">Al leer un archivo grande (un gigabyte o más de tamaño, por ejemplo), puede que desee evitar tener que cargar todo el archivo en la memoria de una vez.</span><span class="sxs-lookup"><span data-stu-id="b6d08-429">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="b6d08-430">En este escenario, puede usar <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-430">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="b6d08-431">Al usar `Utf8JsonReader` para leer de una secuencia, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="b6d08-431">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="b6d08-432">El búfer que contiene la carga parcial JSON debe ser al menos tan grande como el token JSON más grande que contiene para que el lector pueda avanzar.</span><span class="sxs-lookup"><span data-stu-id="b6d08-432">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="b6d08-433">El búfer debe ser al menos tan grande como la secuencia más grande de espacio en blanco dentro del JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-433">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="b6d08-434">El lector no realiza un seguimiento de los datos que ha leído hasta que lea completamente el <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> siguiente en la carga JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-434">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="b6d08-435">Por tanto, cuando haya bytes restantes en el búfer, tendrá que volver a pasarlos al lector.</span><span class="sxs-lookup"><span data-stu-id="b6d08-435">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="b6d08-436">Puede usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar el número de bytes que quedan.</span><span class="sxs-lookup"><span data-stu-id="b6d08-436">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="b6d08-437">El código siguiente muestra cómo leer desde una secuencia.</span><span class="sxs-lookup"><span data-stu-id="b6d08-437">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="b6d08-438">Este ejemplo se muestra <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-438">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="b6d08-439">Un código similar funcionará con <xref:System.IO.FileStream>, excepto cuando `FileStream` contenga una marca BOM UTF-8 al principio.</span><span class="sxs-lookup"><span data-stu-id="b6d08-439">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="b6d08-440">En ese caso, debe quitar esos tres bytes del búfer antes de pasar los bytes restantes a `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-440">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="b6d08-441">En caso contrario, el lector produciría una excepción, ya que la marca BOM no se considera una parte válida del JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-441">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="b6d08-442">El código de ejemplo comienza con un búfer de 4 KB y duplica el tamaño del búfer cada vez que encuentra que el tamaño no es lo suficientemente grande como para ajustarse a un token JSON completo, lo que es necesario para que el lector realice el progreso de la carga de JSON.</span><span class="sxs-lookup"><span data-stu-id="b6d08-442">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="b6d08-443">El ejemplo de JSON proporcionado en el fragmento de código desencadena un aumento del tamaño del búfer solo si se establece un tamaño de búfer inicial muy pequeño, por ejemplo, 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="b6d08-443">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="b6d08-444">Si establece el tamaño de búfer inicial en 10, las instrucciones `Console.WriteLine` muestran la causa y el efecto de los aumentos del tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="b6d08-444">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="b6d08-445">En el tamaño de búfer inicial de 4 KB, se muestra todo el JSON de ejemplo en cada `Console.WriteLine` y el tamaño del búfer nunca se debe aumentar.</span><span class="sxs-lookup"><span data-stu-id="b6d08-445">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="b6d08-446">En el ejemplo anterior no se establece ningún límite para el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="b6d08-446">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="b6d08-447">Si el tamaño del token es demasiado grande, se podría producir un error en el código con una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="b6d08-447">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="b6d08-448">Esto puede ocurrir si el archivo JSON contiene un token de aproximadamente 1 GB o más de tamaño, ya que la duplicación del tamaño de 1 GB da como resultado un tamaño demasiado grande para caber en un búfer de `int32`.</span><span class="sxs-lookup"><span data-stu-id="b6d08-448">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6d08-449">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b6d08-449">Additional resources</span></span>

* <span data-ttu-id="b6d08-450">[Información general de System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b6d08-450">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="b6d08-451">Procedimientos para escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="b6d08-451">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="b6d08-452">[Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="b6d08-452">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="b6d08-453">[Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="b6d08-453">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="b6d08-454">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="b6d08-454">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
