---
title: Cómo serializar y deserializar JSON mediante C# .net
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: fdca8d957bb2453e90652af1dfe5ef99b33b1b2c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163207"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="1d4d3-102">Cómo serializar y deserializar (calcular las referencias y anular la serialización) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="1d4d3-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="1d4d3-103">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="1d4d3-104">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1d4d3-105">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir en la misma" el JSON (con sangría y espacio en blanco para la legibilidad humana).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1d4d3-106">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="1d4d3-107">Espacios de nombres de</span><span class="sxs-lookup"><span data-stu-id="1d4d3-107">Namespaces</span></span>

<span data-ttu-id="1d4d3-108">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1d4d3-109">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos y API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1d4d3-110">Los ejemplos de código que se muestran en este artículo requieren directivas de `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="1d4d3-111">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="1d4d3-112">Cómo escribir objetos .NET en JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="1d4d3-113">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d4d3-114">En el ejemplo siguiente se crea JSON como una cadena:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-115">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-116">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-117">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1d4d3-118">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="1d4d3-119">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="1d4d3-119">Serialization example</span></span>

<span data-ttu-id="1d4d3-120">A continuación se muestra una clase de ejemplo que contiene colecciones y una clase anidada:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="1d4d3-121">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1d4d3-122">De forma predeterminada, la salida JSON es reducida:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1d4d3-123">En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, con la impresión en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="1d4d3-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="1d4d3-124">Serializar a UTF-8</span><span class="sxs-lookup"><span data-stu-id="1d4d3-124">Serialize to UTF-8</span></span>

<span data-ttu-id="1d4d3-125">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-126">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1d4d3-127">La serialización a UTF-8 es aproximadamente 5-10% más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1d4d3-128">La diferencia se debe a que no es necesario convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1d4d3-129">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="1d4d3-129">Serialization behavior</span></span>

* <span data-ttu-id="1d4d3-130">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d4d3-131">Puede [especificar las propiedades que se van a excluir](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="1d4d3-132">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa los caracteres que no son ASCII, los caracteres que distinguen el código html dentro del intervalo ASCII y los caracteres que se deben escapar según [la especificación JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1d4d3-133">De forma predeterminada, JSON es reducida.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-133">By default, JSON is minified.</span></span> <span data-ttu-id="1d4d3-134">Puede [imprimir el archivo JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1d4d3-135">De forma predeterminada, las mayúsculas y minúsculas de los nombres JSON coinciden con los nombres .NET.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1d4d3-136">Puede [personalizar el uso de mayúsculas y minúsculas del nombre JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="1d4d3-137">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-137">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="1d4d3-138">Actualmente, se excluyen los campos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-138">Currently, fields are excluded.</span></span>

<span data-ttu-id="1d4d3-139">Los tipos admitidos son:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-139">Supported types include:</span></span>

* <span data-ttu-id="1d4d3-140">Primitivas de .NET que se asignan a primitivos de JavaScript, como tipos numéricos, cadenas y booleanos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-140">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1d4d3-141">[Objetos CLR antiguos sin formato](https://stackoverflow.com/questions/250001/poco-definition)definidos por el usuario (poco).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-141">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="1d4d3-142">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-142">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1d4d3-143">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement`o POCO.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-143">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1d4d3-144">Colecciones de los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-144">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="1d4d3-145">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-145">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="1d4d3-146">Cómo leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-146">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="1d4d3-147">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-147">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d4d3-148">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecast` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="1d4d3-148">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-149">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-149">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-150">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-150">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="1d4d3-151">Deserializar desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="1d4d3-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="1d4d3-152">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que toma un `Utf8JsonReader` o un `ReadOnlySpan<byte>`, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="1d4d3-153">En los ejemplos se da por supuesto que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-153">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="1d4d3-154">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="1d4d3-154">Deserialization behavior</span></span>

* <span data-ttu-id="1d4d3-155">De forma predeterminada, la coincidencia de nombres de propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-155">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1d4d3-156">Puede [especificar la distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-156">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="1d4d3-157">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-157">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1d4d3-158">No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-158">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="1d4d3-159">No se admite la deserialización a objetos inmutables o a propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-159">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="1d4d3-160">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-160">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1d4d3-161">Puede [serializar los nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-161">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="1d4d3-162">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-162">Fields aren't supported.</span></span>
* <span data-ttu-id="1d4d3-163">De forma predeterminada, los comentarios o las comas finales en el JSON producen excepciones.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-163">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1d4d3-164">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-164">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="1d4d3-165">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-165">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1d4d3-166">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar una funcionalidad que no sea compatible con los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-166">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1d4d3-167">Serializar en JSON con formato</span><span class="sxs-lookup"><span data-stu-id="1d4d3-167">Serialize to formatted JSON</span></span>

<span data-ttu-id="1d4d3-168">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-168">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="1d4d3-169">A continuación se muestra un tipo de ejemplo que se va a serializar y a la salida de JSON impresa:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-169">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="1d4d3-170">Personalización de nombres y valores de JSON</span><span class="sxs-lookup"><span data-stu-id="1d4d3-170">Customize JSON names and values</span></span>

<span data-ttu-id="1d4d3-171">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, incluido Case.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-171">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="1d4d3-172">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-172">Enum values are represented as numbers.</span></span> <span data-ttu-id="1d4d3-173">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-173">This section explains how to:</span></span>

* [<span data-ttu-id="1d4d3-174">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-174">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="1d4d3-175">Convertir todos los nombres de propiedad en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="1d4d3-175">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="1d4d3-176">Implementar una directiva de nomenclatura de propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="1d4d3-176">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="1d4d3-177">Convertir claves de diccionario en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="1d4d3-177">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="1d4d3-178">Convertir enumeraciones en cadenas y Case Camel</span><span class="sxs-lookup"><span data-stu-id="1d4d3-178">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="1d4d3-179">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-179">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="1d4d3-180">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-180">Customize individual property names</span></span>

<span data-ttu-id="1d4d3-181">Para establecer el nombre de las propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="1d4d3-181">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="1d4d3-182">Este es un tipo de ejemplo para serializar y JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-182">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d4d3-183">El nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-183">The property name set by this attribute:</span></span>

* <span data-ttu-id="1d4d3-184">Se aplica en ambas direcciones, para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-184">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="1d4d3-185">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-185">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="1d4d3-186">Usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="1d4d3-186">Use camel case for all JSON property names</span></span>

<span data-ttu-id="1d4d3-187">Para usar mayúsculas y minúsculas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-187">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="1d4d3-188">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-188">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d4d3-189">La Directiva de nomenclatura de la propiedad Case Camel:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-189">The camel case property naming policy:</span></span>

* <span data-ttu-id="1d4d3-190">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-190">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1d4d3-191">Está invalidado por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-191">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1d4d3-192">Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no es mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-192">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="1d4d3-193">Usar una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="1d4d3-193">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="1d4d3-194">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-194">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="1d4d3-195">A continuación, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-195">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-196">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-196">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d4d3-197">La Directiva de nomenclatura de propiedades JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-197">The JSON property naming policy:</span></span>

* <span data-ttu-id="1d4d3-198">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-198">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1d4d3-199">Está invalidado por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-199">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1d4d3-200">Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-200">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="1d4d3-201">Claves de Diccionario de mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="1d4d3-201">Camel case dictionary keys</span></span>

<span data-ttu-id="1d4d3-202">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, las claves de `string` se pueden convertir a mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-202">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="1d4d3-203">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-203">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-204">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tiene pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` daría como resultado una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-204">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="1d4d3-205">La Directiva de nomenclatura de mayúsculas y minúsculas Camel de las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-205">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="1d4d3-206">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON incluso si se especifica `JsonNamingPolicy.CamelCase` para la `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-206">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="1d4d3-207">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="1d4d3-207">Enums as strings</span></span>

<span data-ttu-id="1d4d3-208">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-208">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="1d4d3-209">Para serializar los nombres de enumeración como cadenas, use el <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-209">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="1d4d3-210">Por ejemplo, supongamos que necesita serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-210">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="1d4d3-211">Si el resumen es `Hot`, de forma predeterminada, el JSON serializado tiene el valor numérico 3:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-211">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="1d4d3-212">En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y se convierten los nombres en mayúsculas y minúsculas Camel:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-212">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-213">El JSON resultante es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-213">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="1d4d3-214">Los nombres de cadena de enumeración también se pueden deserializar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-214">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="1d4d3-215">Excluir propiedades de la serialización</span><span class="sxs-lookup"><span data-stu-id="1d4d3-215">Exclude properties from serialization</span></span>

<span data-ttu-id="1d4d3-216">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-216">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d4d3-217">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-217">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="1d4d3-218">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-218">This section explains how to exclude:</span></span>

* [<span data-ttu-id="1d4d3-219">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-219">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="1d4d3-220">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="1d4d3-220">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="1d4d3-221">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="1d4d3-221">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="1d4d3-222">Excluir propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-222">Exclude individual properties</span></span>

<span data-ttu-id="1d4d3-223">Para omitir las propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="1d4d3-223">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="1d4d3-224">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-224">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="1d4d3-225">Excluir todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="1d4d3-225">Exclude all read-only properties</span></span>

<span data-ttu-id="1d4d3-226">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-226">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="1d4d3-227">Para excluir todas las propiedades de solo lectura, establezca el <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-227">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-228">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="1d4d3-229">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-229">This option applies only to serialization.</span></span> <span data-ttu-id="1d4d3-230">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-230">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="1d4d3-231">Excluir todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="1d4d3-231">Exclude all null value properties</span></span>

<span data-ttu-id="1d4d3-232">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-232">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-233">A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-233">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="1d4d3-234">La propiedad</span><span class="sxs-lookup"><span data-stu-id="1d4d3-234">Property</span></span> |<span data-ttu-id="1d4d3-235">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="1d4d3-235">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="1d4d3-236">Fecha</span><span class="sxs-lookup"><span data-stu-id="1d4d3-236">Date</span></span>    | <span data-ttu-id="1d4d3-237">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="1d4d3-237">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="1d4d3-238">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1d4d3-238">TemperatureCelsius</span></span>| <span data-ttu-id="1d4d3-239">25</span><span class="sxs-lookup"><span data-stu-id="1d4d3-239">25</span></span> |
| <span data-ttu-id="1d4d3-240">Resumen</span><span class="sxs-lookup"><span data-stu-id="1d4d3-240">Summary</span></span>| <span data-ttu-id="1d4d3-241">nulo</span><span class="sxs-lookup"><span data-stu-id="1d4d3-241">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="1d4d3-242">Esta configuración se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-242">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="1d4d3-243">Para obtener información sobre su efecto en la deserialización, vea [omitir null al deserializar](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-243">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="1d4d3-244">Personalizar la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="1d4d3-244">Customize character encoding</span></span>

<span data-ttu-id="1d4d3-245">De forma predeterminada, el serializador convierte todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-245">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="1d4d3-246">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-246">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="1d4d3-247">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-247">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="1d4d3-248">Serializar juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="1d4d3-248">Serialize language character sets</span></span>

<span data-ttu-id="1d4d3-249">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique los [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-249">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="1d4d3-250">Este código no escapa ni caracteres griegos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-250">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="1d4d3-251">Si la propiedad `Summary` está establecida en cirílico жарко, el objeto de `WeatherForecast` se serializa como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-251">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="1d4d3-252">Para serializar todos los conjuntos de lenguaje sin escape, utilice <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-252">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="1d4d3-253">Serializar caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="1d4d3-253">Serialize specific characters</span></span>

<span data-ttu-id="1d4d3-254">Una alternativa consiste en especificar caracteres individuales que desea permitir a través de sin caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-254">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="1d4d3-255">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-255">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="1d4d3-256">Este es un ejemplo de JSON generado por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-256">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="1d4d3-257">Serializar todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="1d4d3-257">Serialize all characters</span></span>

<span data-ttu-id="1d4d3-258">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-258">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="1d4d3-259">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo para permitir que los caracteres pasen a través de sin escape:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-259">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="1d4d3-260">No se convierten en caracteres que no tengan en cuenta los caracteres de HTML, como `<`, `>`, `&`y `'`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-260">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="1d4d3-261">No ofrece ninguna protección adicional en profundidad frente a ataques de divulgación de información o XSS, como los que pueden ser el resultado de que el cliente y el servidor no acepten el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-261">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="1d4d3-262">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-262">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="1d4d3-263">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-263">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="1d4d3-264">Nunca permita que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-264">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="1d4d3-265">Serializar propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="1d4d3-265">Serialize properties of derived classes</span></span>

<span data-ttu-id="1d4d3-266">No se admite la serialización de una jerarquía de tipos polimórficas.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-266">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="1d4d3-267">Por ejemplo, si una propiedad se define como una interfaz o una clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo en tiempo de ejecución tenga propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-267">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="1d4d3-268">Las excepciones a este comportamiento se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-268">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="1d4d3-269">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-269">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="1d4d3-270">Y Supongamos que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-270">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="1d4d3-271">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea realmente un objeto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-271">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="1d4d3-272">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-272">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1d4d3-273">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-273">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="1d4d3-274">Para serializar las propiedades del tipo derivado en el ejemplo anterior, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-274">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="1d4d3-275">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-275">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="1d4d3-276">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-276">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="1d4d3-277">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-277">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="1d4d3-278">Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-278">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span> 

<span data-ttu-id="1d4d3-279">Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-279">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="1d4d3-280">Por ejemplo, supongamos que la clase de `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-280">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="1d4d3-281">Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-281">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="1d4d3-282">La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-282">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="1d4d3-283">La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-283">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="1d4d3-284">Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-284">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="1d4d3-285">El siguiente ejemplo de código no llama a `Serialize<object>` o `GetType`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-285">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="1d4d3-286">El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-286">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="1d4d3-287">El mismo método para definir propiedades como `object` funciona con interfaces.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-287">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="1d4d3-288">Supongamos que tiene la interfaz y la implementación siguientes, y desea serializar una clase con propiedades que contienen instancias de implementación:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-288">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="1d4d3-289">Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-289">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="1d4d3-290">En el ejemplo siguiente se muestra el JSON resultante del código anterior:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-290">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="1d4d3-291">Para obtener más información sobre la **serialización**polimórfica y para obtener información sobre la **deserialización**, consulte [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="1d4d3-291">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="1d4d3-292">Permitir comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-292">Allow comments and trailing commas</span></span>

<span data-ttu-id="1d4d3-293">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-293">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="1d4d3-294">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-294">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="1d4d3-295">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-295">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="1d4d3-296">En el ejemplo siguiente se muestra cómo permitir ambos:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-296">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-297">Este es un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-297">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="1d4d3-298">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="1d4d3-298">Case-insensitive property matching</span></span>

<span data-ttu-id="1d4d3-299">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingue entre mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-299">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="1d4d3-300">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-300">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-301">Este es un ejemplo de JSON con nombres de propiedad Case Camel.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-301">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="1d4d3-302">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades de mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-302">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="1d4d3-303">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="1d4d3-303">Handle overflow JSON</span></span>

<span data-ttu-id="1d4d3-304">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-304">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="1d4d3-305">Por ejemplo, supongamos que el tipo de destino es:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-305">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="1d4d3-306">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-306">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="1d4d3-307">Si deserializa el JSON que se muestra en el tipo que se muestra, las propiedades `DatesAvailable` y `SummaryWords` no tienen ninguna que ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-307">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="1d4d3-308">Para capturar datos adicionales, como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-308">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="1d4d3-309">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares de clave y valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-309">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="1d4d3-310">La propiedad</span><span class="sxs-lookup"><span data-stu-id="1d4d3-310">Property</span></span> |<span data-ttu-id="1d4d3-311">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="1d4d3-311">Value</span></span>  |<span data-ttu-id="1d4d3-312">Notas</span><span class="sxs-lookup"><span data-stu-id="1d4d3-312">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="1d4d3-313">Fecha</span><span class="sxs-lookup"><span data-stu-id="1d4d3-313">Date</span></span>    | <span data-ttu-id="1d4d3-314">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="1d4d3-314">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="1d4d3-315">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1d4d3-315">TemperatureCelsius</span></span>| <span data-ttu-id="1d4d3-316">0</span><span class="sxs-lookup"><span data-stu-id="1d4d3-316">0</span></span> | <span data-ttu-id="1d4d3-317">No coinciden las mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-317">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="1d4d3-318">Resumen</span><span class="sxs-lookup"><span data-stu-id="1d4d3-318">Summary</span></span> | <span data-ttu-id="1d4d3-319">Caliente</span><span class="sxs-lookup"><span data-stu-id="1d4d3-319">Hot</span></span> ||
| <span data-ttu-id="1d4d3-320">Extensiondata (</span><span class="sxs-lookup"><span data-stu-id="1d4d3-320">ExtensionData</span></span> | <span data-ttu-id="1d4d3-321">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="1d4d3-321">temperatureCelsius: 25</span></span> |<span data-ttu-id="1d4d3-322">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-322">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="1d4d3-323">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-323">DatesAvailable:</span></span><br>  <span data-ttu-id="1d4d3-324">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="1d4d3-324">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="1d4d3-325">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="1d4d3-325">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="1d4d3-326">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-326">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="1d4d3-327">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-327">SummaryWords:</span></span><br><span data-ttu-id="1d4d3-328">Geniales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-328">Cool</span></span><br><span data-ttu-id="1d4d3-329">Viento</span><span class="sxs-lookup"><span data-stu-id="1d4d3-329">Windy</span></span><br><span data-ttu-id="1d4d3-330">Húmeda</span><span class="sxs-lookup"><span data-stu-id="1d4d3-330">Humid</span></span> |<span data-ttu-id="1d4d3-331">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-331">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="1d4d3-332">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON del mismo modo que en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-332">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="1d4d3-333">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-333">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="1d4d3-334">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que no se pudiera deserializar.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-334">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="1d4d3-335">Omitir null al deserializar</span><span class="sxs-lookup"><span data-stu-id="1d4d3-335">Ignore null when deserializing</span></span>

<span data-ttu-id="1d4d3-336">De forma predeterminada, si una propiedad en JSON es null, la propiedad correspondiente en el objeto de destino se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-336">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="1d4d3-337">En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no desea que un valor null invalide el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-337">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="1d4d3-338">Por ejemplo, supongamos que el código siguiente representa el objeto de destino:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-338">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="1d4d3-339">Y Supongamos que se deserializa el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-339">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="1d4d3-340">Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-340">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="1d4d3-341">Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-341">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-342">Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "no Summary" después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-342">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="1d4d3-343">Los valores NULL en JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-343">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="1d4d3-344">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-344">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="1d4d3-345">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="1d4d3-345">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="1d4d3-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de alto rendimiento, baja asignación y de solo avance para texto JSON con codificación UTF-8, leído de un `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="1d4d3-347">El `Utf8JsonReader` es un tipo de nivel bajo que se puede utilizar para crear analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-347">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="1d4d3-348">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-348">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="1d4d3-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> es una forma de alto rendimiento de escribir texto JSON con codificación UTF-8 de tipos comunes de .NET como `String`, `Int32`y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="1d4d3-350">El escritor es un tipo de nivel bajo que se puede utilizar para crear serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-350">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="1d4d3-351">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-351">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="1d4d3-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> proporciona la capacidad de crear un Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="1d4d3-353">DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-353">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="1d4d3-354">Se puede tener acceso a los elementos JSON que componen la carga a través del tipo de <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-354">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="1d4d3-355">El tipo de `JsonElement` proporciona enumeradores de matriz y de objeto junto con las API para convertir texto JSON en tipos comunes de .NET.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-355">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="1d4d3-356">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-356">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="1d4d3-357">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-357">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="1d4d3-358">Usar JsonDocument para el acceso a los datos</span><span class="sxs-lookup"><span data-stu-id="1d4d3-358">Use JsonDocument for access to data</span></span>

<span data-ttu-id="1d4d3-359">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-359">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="1d4d3-360">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-360">The preceding code:</span></span>

* <span data-ttu-id="1d4d3-361">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-361">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="1d4d3-362">Calcula la media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-362">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="1d4d3-363">Asigna un nivel predeterminado de 70 a los estudiantes que no tienen una calificación.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-363">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="1d4d3-364">Cuenta a los estudiantes incrementando una variable de `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-364">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="1d4d3-365">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-365">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="1d4d3-366">Este es un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-366">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="1d4d3-367">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="1d4d3-367">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="1d4d3-368">En el ejemplo siguiente se muestra cómo escribir JSON desde un <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-368">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="1d4d3-369">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-369">The preceding code:</span></span>

* <span data-ttu-id="1d4d3-370">Lee un archivo JSON, carga los datos en un `JsonDocument`y escribe JSON con formato (impreso) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-370">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="1d4d3-371">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-371">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="1d4d3-372">Cuando termine, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-372">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="1d4d3-373">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-373">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="1d4d3-374">A continuación se muestra un ejemplo de entrada JSON que se va a procesar mediante el código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-374">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="1d4d3-375">El resultado es la siguiente salida JSON impresa:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-375">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="1d4d3-376">Usar Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="1d4d3-376">Use Utf8JsonWriter</span></span>

<span data-ttu-id="1d4d3-377">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-377">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="1d4d3-378">Usar Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="1d4d3-378">Use Utf8JsonReader</span></span>

<span data-ttu-id="1d4d3-379">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d4d3-380">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, codificado como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-380">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="1d4d3-381">Filtrar datos mediante Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="1d4d3-381">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="1d4d3-382">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-382">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="1d4d3-383">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-383">The preceding code:</span></span>

* <span data-ttu-id="1d4d3-384">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "Name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-384">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="1d4d3-385">Cuenta los objetos y los valores de propiedad "Name" que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="1d4d3-385">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="1d4d3-386">Supone que el archivo está codificado como UTF-16 y lo transcodifica en UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-386">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="1d4d3-387">Un archivo codificado como UTF-8 puede leerse directamente en un `ReadOnlySpan<byte>`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4d3-387">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

  <span data-ttu-id="1d4d3-388">Si el archivo contiene una marca de orden de bytes UTF-8 (BOM), quítela antes de pasar los bytes al `Utf8JsonReader`, ya que el lector espera texto.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-388">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="1d4d3-389">De lo contrario, la marca BOM se considera JSON no válido y el lector produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-389">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="1d4d3-390">A continuación se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="1d4d3-390">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="1d4d3-391">El mensaje de Resumen resultante es "2 de 4 nombres que terminan con" Universidad "":</span><span class="sxs-lookup"><span data-stu-id="1d4d3-391">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="1d4d3-392">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1d4d3-392">Additional resources</span></span>

* <span data-ttu-id="1d4d3-393">[Información general de System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-393">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="1d4d3-394">Cómo escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="1d4d3-394">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="1d4d3-395">[Cómo migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-395">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="1d4d3-396">[Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-396">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="1d4d3-397">[referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1d4d3-397">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
