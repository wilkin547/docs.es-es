---
title: 'Procedimiento para serializar y deserializar JSON con C#: .NET'
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6324fe28b23e4df74bcf3fd1dbb7e0c14d5e3d1b
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135807"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="c463e-102">Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="c463e-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="c463e-103">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="c463e-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="c463e-104">Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="c463e-104">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="c463e-105">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="c463e-105">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="c463e-106">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad).</span><span class="sxs-lookup"><span data-stu-id="c463e-106">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="c463e-107">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.</span><span class="sxs-lookup"><span data-stu-id="c463e-107">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="c463e-108">Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:</span><span class="sxs-lookup"><span data-stu-id="c463e-108">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="c463e-109">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="c463e-109">Namespaces</span></span>

<span data-ttu-id="c463e-110">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="c463e-110">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="c463e-111">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-111">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="c463e-112">Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="c463e-112">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="c463e-113">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="c463e-113">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="c463e-114">Procedimiento para escribir objetos .NET en JSON (serializar)</span><span class="sxs-lookup"><span data-stu-id="c463e-114">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="c463e-115">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c463e-115">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c463e-116">En el ejemplo siguiente se crea un archivo JSON como cadena:</span><span class="sxs-lookup"><span data-stu-id="c463e-116">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-117">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-117">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-118">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-118">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-119">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="c463e-119">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="c463e-120">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="c463e-120">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="c463e-121">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="c463e-121">Serialization example</span></span>

<span data-ttu-id="c463e-122">Aquí se muestra una clase de ejemplo que contiene colecciones y una clase anidada:</span><span class="sxs-lookup"><span data-stu-id="c463e-122">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="c463e-123">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c463e-123">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="c463e-124">La salida JSON se minimiza de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c463e-124">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="c463e-125">En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, impreso correctamente con espacio en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="c463e-125">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="c463e-126">Serialización a UTF-8</span><span class="sxs-lookup"><span data-stu-id="c463e-126">Serialize to UTF-8</span></span>

<span data-ttu-id="c463e-127">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="c463e-127">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-128">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="c463e-128">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="c463e-129">La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="c463e-129">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="c463e-130">La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="c463e-130">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="c463e-131">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="c463e-131">Serialization behavior</span></span>

* <span data-ttu-id="c463e-132">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="c463e-132">By default, all public properties are serialized.</span></span> <span data-ttu-id="c463e-133">Puede [especificar propiedades para excluir](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="c463e-133">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="c463e-134">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="c463e-134">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="c463e-135">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="c463e-135">By default, JSON is minified.</span></span> <span data-ttu-id="c463e-136">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="c463e-136">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="c463e-137">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="c463e-137">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="c463e-138">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="c463e-138">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="c463e-139">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="c463e-139">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="c463e-140">Actualmente, se excluyen los campos.</span><span class="sxs-lookup"><span data-stu-id="c463e-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="c463e-141">Los tipos no admitidos incluyen:</span><span class="sxs-lookup"><span data-stu-id="c463e-141">Supported types include:</span></span>

* <span data-ttu-id="c463e-142">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="c463e-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="c463e-143">[Objetos CLR antiguos sin formato (POCO)](https://stackoverflow.com/questions/250001/poco-definition) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c463e-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="c463e-144">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="c463e-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="c463e-145">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="c463e-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="c463e-146">Colecciones de los espacios de nombres siguientes.</span><span class="sxs-lookup"><span data-stu-id="c463e-146">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="c463e-147">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="c463e-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="c463e-148">Procedimiento para leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="c463e-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="c463e-149">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c463e-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c463e-150">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecast` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="c463e-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-151">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-152">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="c463e-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="c463e-153">Deserialización desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="c463e-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="c463e-154">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c463e-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="c463e-155">En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="c463e-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="c463e-156">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="c463e-156">Deserialization behavior</span></span>

* <span data-ttu-id="c463e-157">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c463e-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="c463e-158">Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="c463e-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="c463e-159">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="c463e-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="c463e-160">No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="c463e-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="c463e-161">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c463e-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="c463e-162">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="c463e-162">By default, enums are supported as numbers.</span></span> <span data-ttu-id="c463e-163">Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="c463e-163">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="c463e-164">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="c463e-164">Fields aren't supported.</span></span>
* <span data-ttu-id="c463e-165">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="c463e-165">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="c463e-166">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="c463e-166">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="c463e-167">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="c463e-167">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="c463e-168">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="c463e-168">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="c463e-169">Serialización a JSON con formato</span><span class="sxs-lookup"><span data-stu-id="c463e-169">Serialize to formatted JSON</span></span>

<span data-ttu-id="c463e-170">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="c463e-170">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="c463e-171">Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="c463e-171">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="c463e-172">Personalización de nombres y valores JSON</span><span class="sxs-lookup"><span data-stu-id="c463e-172">Customize JSON names and values</span></span>

<span data-ttu-id="c463e-173">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c463e-173">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="c463e-174">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="c463e-174">Enum values are represented as numbers.</span></span> <span data-ttu-id="c463e-175">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="c463e-175">This section explains how to:</span></span>

* [<span data-ttu-id="c463e-176">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="c463e-176">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="c463e-177">Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="c463e-177">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="c463e-178">Implementar una directiva de nomenclatura de propiedades personalizada</span><span class="sxs-lookup"><span data-stu-id="c463e-178">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="c463e-179">Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="c463e-179">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="c463e-180">Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="c463e-180">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="c463e-181">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="c463e-181">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="c463e-182">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="c463e-182">Customize individual property names</span></span>

<span data-ttu-id="c463e-183">Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="c463e-183">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="c463e-184">Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="c463e-184">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="c463e-185">Nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="c463e-185">The property name set by this attribute:</span></span>

* <span data-ttu-id="c463e-186">Se aplica en ambas direcciones, para la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-186">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="c463e-187">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c463e-187">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="c463e-188">Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="c463e-188">Use camel case for all JSON property names</span></span>

<span data-ttu-id="c463e-189">Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-189">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="c463e-190">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-190">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="c463e-191">La directiva de nomenclatura de propiedades en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="c463e-191">The camel case property naming policy:</span></span>

* <span data-ttu-id="c463e-192">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-192">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="c463e-193">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="c463e-193">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="c463e-194">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="c463e-194">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="c463e-195">Uso de una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="c463e-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="c463e-196">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="c463e-197">Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="c463e-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-198">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-198">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="c463e-199">La directiva de nomenclatura de propiedades JSON personalizada:</span><span class="sxs-lookup"><span data-stu-id="c463e-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="c463e-200">Se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="c463e-201">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="c463e-201">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="c463e-202">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c463e-202">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="c463e-203">Claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="c463e-203">Camel case dictionary keys</span></span>

<span data-ttu-id="c463e-204">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="c463e-204">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="c463e-205">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-205">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-206">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tenga pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` se traduciría en una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-206">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="c463e-207">La directiva de nomenclatura en mayúsculas y minúsculas combinadas Camel para las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-207">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="c463e-208">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON aunque se especifique `JsonNamingPolicy.CamelCase` para `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="c463e-208">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="c463e-209">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="c463e-209">Enums as strings</span></span>

<span data-ttu-id="c463e-210">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="c463e-210">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="c463e-211">Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="c463e-211">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="c463e-212">Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="c463e-212">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="c463e-213">Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c463e-213">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="c463e-214">En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="c463e-214">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-215">El JSON resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-215">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="c463e-216">Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-216">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="c463e-217">Exclusión de propiedades de la serialización</span><span class="sxs-lookup"><span data-stu-id="c463e-217">Exclude properties from serialization</span></span>

<span data-ttu-id="c463e-218">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="c463e-218">By default, all public properties are serialized.</span></span> <span data-ttu-id="c463e-219">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="c463e-219">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="c463e-220">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="c463e-220">This section explains how to exclude:</span></span>

* [<span data-ttu-id="c463e-221">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="c463e-221">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="c463e-222">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="c463e-222">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="c463e-223">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="c463e-223">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="c463e-224">Exclusión de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="c463e-224">Exclude individual properties</span></span>

<span data-ttu-id="c463e-225">Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="c463e-225">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="c463e-226">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-226">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="c463e-227">Exclusión de todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="c463e-227">Exclude all read-only properties</span></span>

<span data-ttu-id="c463e-228">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="c463e-228">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="c463e-229">Para excluir todas las propiedades de solo lectura, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-230">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-230">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="c463e-231">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-231">This option applies only to serialization.</span></span> <span data-ttu-id="c463e-232">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c463e-232">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="c463e-233">Exclusión de todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="c463e-233">Exclude all null value properties</span></span>

<span data-ttu-id="c463e-234">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-234">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-235">Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-235">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="c463e-236">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="c463e-236">Property</span></span> |<span data-ttu-id="c463e-237">Valor</span><span class="sxs-lookup"><span data-stu-id="c463e-237">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="c463e-238">Fecha</span><span class="sxs-lookup"><span data-stu-id="c463e-238">Date</span></span>    | <span data-ttu-id="c463e-239">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="c463e-239">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="c463e-240">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="c463e-240">TemperatureCelsius</span></span>| <span data-ttu-id="c463e-241">25</span><span class="sxs-lookup"><span data-stu-id="c463e-241">25</span></span> |
| <span data-ttu-id="c463e-242">Resumen</span><span class="sxs-lookup"><span data-stu-id="c463e-242">Summary</span></span>| <span data-ttu-id="c463e-243">null</span><span class="sxs-lookup"><span data-stu-id="c463e-243">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="c463e-244">Este valor se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-244">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="c463e-245">Para obtener información sobre su efecto en la deserialización, consulte el artículo sobre cómo [omitir valores NULL al deserializar](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="c463e-245">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="c463e-246">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="c463e-246">Customize character encoding</span></span>

<span data-ttu-id="c463e-247">De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="c463e-247">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="c463e-248">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="c463e-248">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="c463e-249">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c463e-249">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="c463e-250">Serialización de juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="c463e-250">Serialize language character sets</span></span>

<span data-ttu-id="c463e-251">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-251">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="c463e-252">Este código no escapa a los caracteres cirílicos o griegos.</span><span class="sxs-lookup"><span data-stu-id="c463e-252">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="c463e-253">Si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c463e-253">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="c463e-254">Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c463e-254">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="c463e-255">Serialización de caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="c463e-255">Serialize specific characters</span></span>

<span data-ttu-id="c463e-256">Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="c463e-256">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="c463e-257">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="c463e-257">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="c463e-258">Aquí se muestra un ejemplo de JSON producido por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="c463e-258">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="c463e-259">Serialización de todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="c463e-259">Serialize all characters</span></span>

<span data-ttu-id="c463e-260">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-260">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="c463e-261">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:</span><span class="sxs-lookup"><span data-stu-id="c463e-261">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="c463e-262">No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.</span><span class="sxs-lookup"><span data-stu-id="c463e-262">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="c463e-263">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="c463e-263">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="c463e-264">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c463e-264">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="c463e-265">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="c463e-265">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="c463e-266">No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="c463e-266">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="c463e-267">Serialización de propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="c463e-267">Serialize properties of derived classes</span></span>

<span data-ttu-id="c463e-268">No se admite la serialización de una jerarquía de tipos polimórficos.</span><span class="sxs-lookup"><span data-stu-id="c463e-268">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="c463e-269">Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="c463e-269">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="c463e-270">Las excepciones a este comportamiento se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="c463e-270">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="c463e-271">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="c463e-271">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="c463e-272">Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="c463e-272">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="c463e-273">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea en realidad un objeto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="c463e-273">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="c463e-274">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="c463e-274">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="c463e-275">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c463e-275">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="c463e-276">Para serializar las propiedades del tipo derivado del ejemplo anterior, use uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="c463e-276">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="c463e-277">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="c463e-277">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="c463e-278">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="c463e-278">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="c463e-279">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-279">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="c463e-280">Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.</span><span class="sxs-lookup"><span data-stu-id="c463e-280">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="c463e-281">Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="c463e-281">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="c463e-282">Por ejemplo, supongamos que la clase `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:</span><span class="sxs-lookup"><span data-stu-id="c463e-282">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="c463e-283">Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="c463e-283">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="c463e-284">La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="c463e-284">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="c463e-285">La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="c463e-285">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="c463e-286">Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="c463e-286">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="c463e-287">En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:</span><span class="sxs-lookup"><span data-stu-id="c463e-287">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="c463e-288">El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="c463e-288">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="c463e-289">El mismo enfoque para definir propiedades como `object` funciona con interfaces.</span><span class="sxs-lookup"><span data-stu-id="c463e-289">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="c463e-290">Supongamos que tiene la interfaz y la implementación siguientes, y quiere serializar una clase con propiedades que contienen instancias de implementación:</span><span class="sxs-lookup"><span data-stu-id="c463e-290">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="c463e-291">Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:</span><span class="sxs-lookup"><span data-stu-id="c463e-291">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="c463e-292">En el ejemplo de código siguiente se muestra el JSON resultante del código anterior:</span><span class="sxs-lookup"><span data-stu-id="c463e-292">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="c463e-293">Para obtener más información sobre la **serialización**  polimórfica e información sobre la **deserialización**, consulte [Migración desde Newtonsoft.json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="c463e-293">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="c463e-294">Autorización de comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="c463e-294">Allow comments and trailing commas</span></span>

<span data-ttu-id="c463e-295">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="c463e-295">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="c463e-296">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="c463e-296">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="c463e-297">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="c463e-297">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="c463e-298">En el siguiente ejemplo se muestra cómo permitirlos ambos:</span><span class="sxs-lookup"><span data-stu-id="c463e-298">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-299">Aquí se muestra un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="c463e-299">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="c463e-300">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="c463e-300">Case-insensitive property matching</span></span>

<span data-ttu-id="c463e-301">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="c463e-301">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="c463e-302">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="c463e-302">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-303">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="c463e-303">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="c463e-304">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="c463e-304">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="c463e-305">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="c463e-305">Handle overflow JSON</span></span>

<span data-ttu-id="c463e-306">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c463e-306">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="c463e-307">Por ejemplo, supongamos que el tipo de destino es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-307">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="c463e-308">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-308">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="c463e-309">Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="c463e-309">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="c463e-310">Para capturar datos adicionales tales como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="c463e-310">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="c463e-311">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="c463e-311">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="c463e-312">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="c463e-312">Property</span></span> |<span data-ttu-id="c463e-313">Valor</span><span class="sxs-lookup"><span data-stu-id="c463e-313">Value</span></span>  |<span data-ttu-id="c463e-314">Notas</span><span class="sxs-lookup"><span data-stu-id="c463e-314">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="c463e-315">Fecha</span><span class="sxs-lookup"><span data-stu-id="c463e-315">Date</span></span>    | <span data-ttu-id="c463e-316">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="c463e-316">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="c463e-317">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="c463e-317">TemperatureCelsius</span></span>| <span data-ttu-id="c463e-318">0</span><span class="sxs-lookup"><span data-stu-id="c463e-318">0</span></span> | <span data-ttu-id="c463e-319">Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c463e-319">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="c463e-320">Resumen</span><span class="sxs-lookup"><span data-stu-id="c463e-320">Summary</span></span> | <span data-ttu-id="c463e-321">Acceso frecuente</span><span class="sxs-lookup"><span data-stu-id="c463e-321">Hot</span></span> ||
| <span data-ttu-id="c463e-322">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="c463e-322">ExtensionData</span></span> | <span data-ttu-id="c463e-323">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="c463e-323">temperatureCelsius: 25</span></span> |<span data-ttu-id="c463e-324">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="c463e-324">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="c463e-325">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="c463e-325">DatesAvailable:</span></span><br>  <span data-ttu-id="c463e-326">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="c463e-326">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="c463e-327">2/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="c463e-327">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="c463e-328">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="c463e-328">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="c463e-329">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="c463e-329">SummaryWords:</span></span><br><span data-ttu-id="c463e-330">Geniales</span><span class="sxs-lookup"><span data-stu-id="c463e-330">Cool</span></span><br><span data-ttu-id="c463e-331">Viento</span><span class="sxs-lookup"><span data-stu-id="c463e-331">Windy</span></span><br><span data-ttu-id="c463e-332">Húmedo</span><span class="sxs-lookup"><span data-stu-id="c463e-332">Humid</span></span> |<span data-ttu-id="c463e-333">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="c463e-333">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="c463e-334">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="c463e-334">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="c463e-335">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="c463e-335">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="c463e-336">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.</span><span class="sxs-lookup"><span data-stu-id="c463e-336">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="c463e-337">Omisión de NULL al deserializar</span><span class="sxs-lookup"><span data-stu-id="c463e-337">Ignore null when deserializing</span></span>

<span data-ttu-id="c463e-338">De forma predeterminada, si una propiedad en JSON es NULL, la propiedad correspondiente en el objeto de destino se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="c463e-338">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="c463e-339">En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no se quiere que un valor NULL invalide el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c463e-339">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="c463e-340">Por ejemplo, supongamos que el siguiente código representa su objeto de destino:</span><span class="sxs-lookup"><span data-stu-id="c463e-340">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="c463e-341">Supongamos también que se deserializa el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-341">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="c463e-342">Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.</span><span class="sxs-lookup"><span data-stu-id="c463e-342">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="c463e-343">Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-343">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-344">Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "No summary" después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="c463e-344">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="c463e-345">Los valores NULL en JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="c463e-345">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="c463e-346">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="c463e-346">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="c463e-347">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="c463e-347">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="c463e-348"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="c463e-348"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="c463e-349">`Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="c463e-349">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="c463e-350">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c463e-350">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="c463e-351"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="c463e-351"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="c463e-352">El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="c463e-352">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="c463e-353">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c463e-353">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="c463e-354"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="c463e-354"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="c463e-355">La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="c463e-355">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="c463e-356">A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="c463e-356">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="c463e-357">El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="c463e-357">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="c463e-358">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="c463e-358">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="c463e-359">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="c463e-359">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="c463e-360">Uso de JsonDocument para acceder a datos</span><span class="sxs-lookup"><span data-stu-id="c463e-360">Use JsonDocument for access to data</span></span>

<span data-ttu-id="c463e-361">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:</span><span class="sxs-lookup"><span data-stu-id="c463e-361">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="c463e-362">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="c463e-362">The preceding code:</span></span>

* <span data-ttu-id="c463e-363">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="c463e-363">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="c463e-364">Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="c463e-364">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="c463e-365">Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.</span><span class="sxs-lookup"><span data-stu-id="c463e-365">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="c463e-366">Cuenta los alumnos incrementando una variable `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="c463e-366">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="c463e-367">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-367">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="c463e-368">Aquí se muestra un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="c463e-368">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="c463e-369">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="c463e-369">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="c463e-370">En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="c463e-370">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="c463e-371">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="c463e-371">The preceding code:</span></span>

* <span data-ttu-id="c463e-372">Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c463e-372">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="c463e-373">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="c463e-373">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="c463e-374">Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="c463e-374">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="c463e-375">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="c463e-375">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="c463e-376">Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:</span><span class="sxs-lookup"><span data-stu-id="c463e-376">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="c463e-377">El resultado es la siguiente salida JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="c463e-377">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="c463e-378">Uso de Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="c463e-378">Use Utf8JsonWriter</span></span>

<span data-ttu-id="c463e-379">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="c463e-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="c463e-380">Uso de Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="c463e-380">Use Utf8JsonReader</span></span>

<span data-ttu-id="c463e-381">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="c463e-381">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="c463e-382">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c463e-382">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="c463e-383">Filtrado de datos con Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="c463e-383">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="c463e-384">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:</span><span class="sxs-lookup"><span data-stu-id="c463e-384">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="c463e-385">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="c463e-385">The preceding code:</span></span>

* <span data-ttu-id="c463e-386">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="c463e-386">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="c463e-387">Cuenta los objetos y los valores de propiedad "name" que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="c463e-387">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="c463e-388">Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c463e-388">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="c463e-389">Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c463e-389">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="c463e-390">Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto.</span><span class="sxs-lookup"><span data-stu-id="c463e-390">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="c463e-391">De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="c463e-391">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="c463e-392">Aquí se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="c463e-392">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="c463e-393">El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":</span><span class="sxs-lookup"><span data-stu-id="c463e-393">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="c463e-394">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c463e-394">Additional resources</span></span>

* <span data-ttu-id="c463e-395">[Información general de System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c463e-395">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="c463e-396">Procedimientos para escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="c463e-396">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="c463e-397">[Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="c463e-397">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="c463e-398">[Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="c463e-398">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="c463e-399">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="c463e-399">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
