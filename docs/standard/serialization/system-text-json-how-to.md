---
title: 'Procedimiento para serializar y deserializar JSON con C#: .NET'
description: Obtenga información sobre cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET. Incluye código de ejemplo.
ms.date: 10/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 0fda248b7d2e5a7cfa748447d0265565cb160b7e
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997775"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="9001d-104">Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="9001d-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="9001d-105">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json?displayProperty=fullName> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="9001d-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="9001d-106">Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="9001d-107">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="9001d-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="9001d-108">La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad).</span><span class="sxs-lookup"><span data-stu-id="9001d-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="9001d-109">Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.</span><span class="sxs-lookup"><span data-stu-id="9001d-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="9001d-110">Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:</span><span class="sxs-lookup"><span data-stu-id="9001d-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="9001d-111">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="9001d-111">Namespaces</span></span>

<span data-ttu-id="9001d-112">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="9001d-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="9001d-113">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="9001d-114">Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="9001d-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="9001d-115">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="9001d-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="9001d-116">Procedimiento para escribir objetos .NET en JSON (serializar)</span><span class="sxs-lookup"><span data-stu-id="9001d-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="9001d-117">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9001d-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9001d-118">En el ejemplo siguiente se crea un archivo JSON como cadena:</span><span class="sxs-lookup"><span data-stu-id="9001d-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-119">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-120">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-121">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="9001d-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="9001d-122">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="9001d-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="9001d-123">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="9001d-123">Serialization example</span></span>

<span data-ttu-id="9001d-124">A continuación se muestra una clase de ejemplo que contiene propiedades de tipo de colección y un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="9001d-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="9001d-125">"POCO" significa [objeto CRL estándar](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="9001d-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="9001d-126">Un POCO es un tipo de .NET que no depende de ningún tipo específico del marco, por ejemplo, a través de la herencia o atributos.</span><span class="sxs-lookup"><span data-stu-id="9001d-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="9001d-127">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9001d-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="9001d-128">La salida JSON se minimiza de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="9001d-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="9001d-129">En el ejemplo siguiente se muestra el mismo JSON, pero con formato (es decir, impreso correctamente con espacio en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="9001d-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="9001d-130">Serialización a UTF-8</span><span class="sxs-lookup"><span data-stu-id="9001d-130">Serialize to UTF-8</span></span>

<span data-ttu-id="9001d-131">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="9001d-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-132">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="9001d-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="9001d-133">La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="9001d-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="9001d-134">La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="9001d-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="9001d-135">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="9001d-135">Serialization behavior</span></span>

* <span data-ttu-id="9001d-136">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="9001d-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="9001d-137">Puede [especificar propiedades para excluir](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="9001d-137">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="9001d-138">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="9001d-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="9001d-139">De forma predeterminada, JSON se minimiza.</span><span class="sxs-lookup"><span data-stu-id="9001d-139">By default, JSON is minified.</span></span> <span data-ttu-id="9001d-140">Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="9001d-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="9001d-141">De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="9001d-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="9001d-142">Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="9001d-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="9001d-143">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="9001d-143">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="9001d-144">Actualmente, se excluyen los [campos](../../csharp/programming-guide/classes-and-structs/fields.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-144">Currently, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are excluded.</span></span>

<span data-ttu-id="9001d-145">Los tipos no admitidos incluyen:</span><span class="sxs-lookup"><span data-stu-id="9001d-145">Supported types include:</span></span>

* <span data-ttu-id="9001d-146">Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="9001d-146">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="9001d-147">[Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9001d-147">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="9001d-148">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="9001d-148">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="9001d-149">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="9001d-149">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="9001d-150">Colecciones de los espacios de nombres siguientes.</span><span class="sxs-lookup"><span data-stu-id="9001d-150">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="9001d-151">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="9001d-151">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="9001d-152">Procedimiento para leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="9001d-152">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="9001d-153">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9001d-153">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9001d-154">En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecastWithPOCOs` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="9001d-154">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-155">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-155">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-156">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="9001d-156">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="9001d-157">Deserialización desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="9001d-157">Deserialize from UTF-8</span></span>

<span data-ttu-id="9001d-158">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9001d-158">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="9001d-159">En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="9001d-159">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="9001d-160">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="9001d-160">Deserialization behavior</span></span>

<span data-ttu-id="9001d-161">Al deserializar JSON se aplican los comportamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9001d-161">The following behaviors apply when deserializing JSON:</span></span>

* <span data-ttu-id="9001d-162">De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9001d-162">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="9001d-163">Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="9001d-163">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="9001d-164">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="9001d-164">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="9001d-165">Constructores para la deserialización:</span><span class="sxs-lookup"><span data-stu-id="9001d-165">Constructors for deserialization:</span></span>
  - <span data-ttu-id="9001d-166">En .NET Core 3.0 y 3.1, para la deserialización se usa un constructor sin parámetros, que puede ser público, interno o privado.</span><span class="sxs-lookup"><span data-stu-id="9001d-166">On .NET Core 3.0 and 3.1, a parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
  - <span data-ttu-id="9001d-167">En .NET 5.0 y versiones posteriores, el serializador omite los constructores que no son públicos.</span><span class="sxs-lookup"><span data-stu-id="9001d-167">In .NET 5.0 and later, non-public constructors are ignored by the serializer.</span></span> <span data-ttu-id="9001d-168">Pero se pueden usar constructores con parámetros si no hay un constructor sin parámetros disponible.</span><span class="sxs-lookup"><span data-stu-id="9001d-168">However, parameterized constructors can be used if a parameterless constructor isn't available.</span></span>
* <span data-ttu-id="9001d-169">No se admite la deserialización a objetos inmutables o propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9001d-169">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="9001d-170">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="9001d-170">By default, enums are supported as numbers.</span></span> <span data-ttu-id="9001d-171">Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="9001d-171">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="9001d-172">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="9001d-172">Fields aren't supported.</span></span>
* <span data-ttu-id="9001d-173">De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="9001d-173">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="9001d-174">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="9001d-174">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="9001d-175">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="9001d-175">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="9001d-176">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="9001d-176">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="9001d-177">Serialización a JSON con formato</span><span class="sxs-lookup"><span data-stu-id="9001d-177">Serialize to formatted JSON</span></span>

<span data-ttu-id="9001d-178">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="9001d-178">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="9001d-179">Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="9001d-179">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="9001d-180">Personalización de nombres y valores JSON</span><span class="sxs-lookup"><span data-stu-id="9001d-180">Customize JSON names and values</span></span>

<span data-ttu-id="9001d-181">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9001d-181">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="9001d-182">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="9001d-182">Enum values are represented as numbers.</span></span> <span data-ttu-id="9001d-183">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="9001d-183">This section explains how to:</span></span>

* [<span data-ttu-id="9001d-184">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9001d-184">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="9001d-185">Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="9001d-185">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="9001d-186">Implementar una directiva de nomenclatura de propiedades personalizada</span><span class="sxs-lookup"><span data-stu-id="9001d-186">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="9001d-187">Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="9001d-187">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="9001d-188">Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="9001d-188">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="9001d-189">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-189">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="9001d-190">Personalizar nombres de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9001d-190">Customize individual property names</span></span>

<span data-ttu-id="9001d-191">Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="9001d-191">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="9001d-192">Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="9001d-192">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9001d-193">Nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="9001d-193">The property name set by this attribute:</span></span>

* <span data-ttu-id="9001d-194">Se aplica en ambas direcciones, para la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-194">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="9001d-195">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="9001d-195">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="9001d-196">Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="9001d-196">Use camel case for all JSON property names</span></span>

<span data-ttu-id="9001d-197">Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-197">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="9001d-198">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-198">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9001d-199">La directiva de nomenclatura de propiedades en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="9001d-199">The camel case property naming policy:</span></span>

* <span data-ttu-id="9001d-200">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9001d-201">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="9001d-201">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9001d-202">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="9001d-202">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="9001d-203">Uso de una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="9001d-203">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="9001d-204">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-204">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="9001d-205">Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="9001d-205">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-206">Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-206">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9001d-207">La directiva de nomenclatura de propiedades JSON personalizada:</span><span class="sxs-lookup"><span data-stu-id="9001d-207">The JSON property naming policy:</span></span>

* <span data-ttu-id="9001d-208">Se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-208">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9001d-209">Se invalida con atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="9001d-209">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9001d-210">Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="9001d-210">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="9001d-211">Claves de diccionario en mayúsculas y minúsculas combinadas Camel</span><span class="sxs-lookup"><span data-stu-id="9001d-211">Camel case dictionary keys</span></span>

<span data-ttu-id="9001d-212">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="9001d-212">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="9001d-213">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-213">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-214">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tenga pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` se traduciría en una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-214">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="9001d-215">La directiva de nomenclatura en mayúsculas y minúsculas combinadas Camel para las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-215">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="9001d-216">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON aunque se especifique `JsonNamingPolicy.CamelCase` para `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="9001d-216">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="9001d-217">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="9001d-217">Enums as strings</span></span>

<span data-ttu-id="9001d-218">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="9001d-218">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="9001d-219">Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="9001d-219">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="9001d-220">Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="9001d-220">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="9001d-221">Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="9001d-221">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="9001d-222">En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:</span><span class="sxs-lookup"><span data-stu-id="9001d-222">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-223">El JSON resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-223">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="9001d-224">Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-224">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="9001d-225">Exclusión de propiedades de la serialización</span><span class="sxs-lookup"><span data-stu-id="9001d-225">Exclude properties from serialization</span></span>

<span data-ttu-id="9001d-226">De manera predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="9001d-226">By default, all public properties are serialized.</span></span> <span data-ttu-id="9001d-227">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="9001d-227">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="9001d-228">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="9001d-228">This section explains how to exclude:</span></span>

* [<span data-ttu-id="9001d-229">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9001d-229">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="9001d-230">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9001d-230">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="9001d-231">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="9001d-231">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="9001d-232">Exclusión de propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="9001d-232">Exclude individual properties</span></span>

<span data-ttu-id="9001d-233">Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9001d-233">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="9001d-234">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-234">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="9001d-235">Exclusión de todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9001d-235">Exclude all read-only properties</span></span>

<span data-ttu-id="9001d-236">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="9001d-236">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="9001d-237">Para excluir todas las propiedades de solo lectura, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-237">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-238">Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-238">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="9001d-239">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-239">This option applies only to serialization.</span></span> <span data-ttu-id="9001d-240">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9001d-240">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="9001d-241">Exclusión de todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="9001d-241">Exclude all null value properties</span></span>

<span data-ttu-id="9001d-242">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-242">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-243">Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-243">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="9001d-244">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9001d-244">Property</span></span> |<span data-ttu-id="9001d-245">Valor</span><span class="sxs-lookup"><span data-stu-id="9001d-245">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="9001d-246">Fecha</span><span class="sxs-lookup"><span data-stu-id="9001d-246">Date</span></span>    | <span data-ttu-id="9001d-247">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="9001d-247">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="9001d-248">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9001d-248">TemperatureCelsius</span></span>| <span data-ttu-id="9001d-249">25</span><span class="sxs-lookup"><span data-stu-id="9001d-249">25</span></span> |
| <span data-ttu-id="9001d-250">Resumen</span><span class="sxs-lookup"><span data-stu-id="9001d-250">Summary</span></span>| <span data-ttu-id="9001d-251">null</span><span class="sxs-lookup"><span data-stu-id="9001d-251">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="9001d-252">Este valor se aplica a la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-252">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="9001d-253">Para obtener información sobre su efecto en la deserialización, consulte el artículo sobre cómo [omitir valores NULL al deserializar](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="9001d-253">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="9001d-254">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="9001d-254">Customize character encoding</span></span>

<span data-ttu-id="9001d-255">De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="9001d-255">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="9001d-256">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="9001d-256">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="9001d-257">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9001d-257">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="9001d-258">Serialización de juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="9001d-258">Serialize language character sets</span></span>

<span data-ttu-id="9001d-259">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-259">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="9001d-260">Este código no escapa a los caracteres cirílicos o griegos.</span><span class="sxs-lookup"><span data-stu-id="9001d-260">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="9001d-261">Si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9001d-261">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="9001d-262">Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9001d-262">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="9001d-263">Serialización de caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="9001d-263">Serialize specific characters</span></span>

<span data-ttu-id="9001d-264">Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="9001d-264">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="9001d-265">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="9001d-265">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="9001d-266">Aquí se muestra un ejemplo de JSON producido por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="9001d-266">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="9001d-267">Serialización de todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="9001d-267">Serialize all characters</span></span>

<span data-ttu-id="9001d-268">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-268">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="9001d-269">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:</span><span class="sxs-lookup"><span data-stu-id="9001d-269">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="9001d-270">No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.</span><span class="sxs-lookup"><span data-stu-id="9001d-270">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="9001d-271">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="9001d-271">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="9001d-272">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9001d-272">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="9001d-273">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="9001d-273">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="9001d-274">No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="9001d-274">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="9001d-275">Serialización de propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="9001d-275">Serialize properties of derived classes</span></span>

<span data-ttu-id="9001d-276">No se admite la serialización de una jerarquía de tipos polimórficos.</span><span class="sxs-lookup"><span data-stu-id="9001d-276">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="9001d-277">Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="9001d-277">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="9001d-278">Las excepciones a este comportamiento se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="9001d-278">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="9001d-279">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="9001d-279">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="9001d-280">Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="9001d-280">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="9001d-281">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea en realidad un objeto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="9001d-281">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="9001d-282">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="9001d-282">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="9001d-283">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9001d-283">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="9001d-284">Para serializar las propiedades del tipo derivado del ejemplo anterior, use uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="9001d-284">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="9001d-285">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="9001d-285">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="9001d-286">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="9001d-286">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="9001d-287">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-287">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="9001d-288">Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.</span><span class="sxs-lookup"><span data-stu-id="9001d-288">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="9001d-289">Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="9001d-289">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="9001d-290">Por ejemplo, supongamos que la clase `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:</span><span class="sxs-lookup"><span data-stu-id="9001d-290">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="9001d-291">Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="9001d-291">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="9001d-292">La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9001d-292">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="9001d-293">La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9001d-293">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="9001d-294">Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="9001d-294">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="9001d-295">En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:</span><span class="sxs-lookup"><span data-stu-id="9001d-295">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="9001d-296">El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="9001d-296">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="9001d-297">El mismo enfoque para definir propiedades como `object` funciona con interfaces.</span><span class="sxs-lookup"><span data-stu-id="9001d-297">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="9001d-298">Supongamos que tiene la interfaz y la implementación siguientes, y quiere serializar una clase con propiedades que contienen instancias de implementación:</span><span class="sxs-lookup"><span data-stu-id="9001d-298">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="9001d-299">Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:</span><span class="sxs-lookup"><span data-stu-id="9001d-299">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="9001d-300">En el ejemplo de código siguiente se muestra el JSON resultante del código anterior:</span><span class="sxs-lookup"><span data-stu-id="9001d-300">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="9001d-301">Para obtener más información sobre la **serialización**  polimórfica e información sobre la **deserialización**, consulte [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="9001d-301">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="9001d-302">Autorización de comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="9001d-302">Allow comments and trailing commas</span></span>

<span data-ttu-id="9001d-303">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-303">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="9001d-304">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="9001d-304">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="9001d-305">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="9001d-305">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="9001d-306">En el siguiente ejemplo se muestra cómo permitirlos ambos:</span><span class="sxs-lookup"><span data-stu-id="9001d-306">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-307">Aquí se muestra un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="9001d-307">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="9001d-308">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="9001d-308">Case-insensitive property matching</span></span>

<span data-ttu-id="9001d-309">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="9001d-309">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="9001d-310">Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="9001d-310">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-311">Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel.</span><span class="sxs-lookup"><span data-stu-id="9001d-311">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="9001d-312">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="9001d-312">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="9001d-313">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="9001d-313">Handle overflow JSON</span></span>

<span data-ttu-id="9001d-314">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="9001d-314">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="9001d-315">Por ejemplo, supongamos que el tipo de destino es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-315">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="9001d-316">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-316">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="9001d-317">Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="9001d-317">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="9001d-318">Para capturar datos adicionales tales como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="9001d-318">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="9001d-319">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="9001d-319">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="9001d-320">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9001d-320">Property</span></span> |<span data-ttu-id="9001d-321">Valor</span><span class="sxs-lookup"><span data-stu-id="9001d-321">Value</span></span>  |<span data-ttu-id="9001d-322">Notas</span><span class="sxs-lookup"><span data-stu-id="9001d-322">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="9001d-323">Fecha</span><span class="sxs-lookup"><span data-stu-id="9001d-323">Date</span></span>    | <span data-ttu-id="9001d-324">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="9001d-324">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="9001d-325">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9001d-325">TemperatureCelsius</span></span>| <span data-ttu-id="9001d-326">0</span><span class="sxs-lookup"><span data-stu-id="9001d-326">0</span></span> | <span data-ttu-id="9001d-327">Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9001d-327">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="9001d-328">Resumen</span><span class="sxs-lookup"><span data-stu-id="9001d-328">Summary</span></span> | <span data-ttu-id="9001d-329">Acceso frecuente</span><span class="sxs-lookup"><span data-stu-id="9001d-329">Hot</span></span> ||
| <span data-ttu-id="9001d-330">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="9001d-330">ExtensionData</span></span> | <span data-ttu-id="9001d-331">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="9001d-331">temperatureCelsius: 25</span></span> |<span data-ttu-id="9001d-332">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="9001d-332">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="9001d-333">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="9001d-333">DatesAvailable:</span></span><br>  <span data-ttu-id="9001d-334">1/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="9001d-334">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="9001d-335">2/8/2019 12:00 -07:00</span><span class="sxs-lookup"><span data-stu-id="9001d-335">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="9001d-336">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="9001d-336">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="9001d-337">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="9001d-337">SummaryWords:</span></span><br><span data-ttu-id="9001d-338">Geniales</span><span class="sxs-lookup"><span data-stu-id="9001d-338">Cool</span></span><br><span data-ttu-id="9001d-339">Viento</span><span class="sxs-lookup"><span data-stu-id="9001d-339">Windy</span></span><br><span data-ttu-id="9001d-340">Húmedo</span><span class="sxs-lookup"><span data-stu-id="9001d-340">Humid</span></span> |<span data-ttu-id="9001d-341">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="9001d-341">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="9001d-342">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="9001d-342">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="9001d-343">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-343">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="9001d-344">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.</span><span class="sxs-lookup"><span data-stu-id="9001d-344">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="9001d-345">Omisión de NULL al deserializar</span><span class="sxs-lookup"><span data-stu-id="9001d-345">Ignore null when deserializing</span></span>

<span data-ttu-id="9001d-346">De forma predeterminada, si una propiedad en JSON es NULL, la propiedad correspondiente en el objeto de destino se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="9001d-346">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="9001d-347">En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no se quiere que un valor NULL invalide el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9001d-347">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="9001d-348">Por ejemplo, supongamos que el siguiente código representa su objeto de destino:</span><span class="sxs-lookup"><span data-stu-id="9001d-348">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="9001d-349">Supongamos también que se deserializa el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-349">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="9001d-350">Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.</span><span class="sxs-lookup"><span data-stu-id="9001d-350">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="9001d-351">Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-351">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-352">Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "No summary" después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="9001d-352">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="9001d-353">Los valores NULL en JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="9001d-353">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="9001d-354">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="9001d-354">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="9001d-355">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="9001d-355">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="9001d-356"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="9001d-356"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="9001d-357">`Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9001d-357">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="9001d-358">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9001d-358">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="9001d-359"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="9001d-359"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="9001d-360">El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9001d-360">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="9001d-361">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9001d-361">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="9001d-362"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="9001d-362"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="9001d-363">La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-363">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="9001d-364">A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="9001d-364">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="9001d-365">El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="9001d-365">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="9001d-366">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="9001d-366">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="9001d-367">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-367">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="9001d-368">Uso de JsonDocument para acceder a datos</span><span class="sxs-lookup"><span data-stu-id="9001d-368">Use JsonDocument for access to data</span></span>

<span data-ttu-id="9001d-369">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:</span><span class="sxs-lookup"><span data-stu-id="9001d-369">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="9001d-370">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="9001d-370">The preceding code:</span></span>

* <span data-ttu-id="9001d-371">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="9001d-371">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="9001d-372">Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="9001d-372">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="9001d-373">Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.</span><span class="sxs-lookup"><span data-stu-id="9001d-373">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="9001d-374">Cuenta los alumnos incrementando una variable `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="9001d-374">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="9001d-375">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-375">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="9001d-376">Aquí se muestra un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="9001d-376">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="9001d-377">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="9001d-377">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="9001d-378">En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="9001d-378">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="9001d-379">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="9001d-379">The preceding code:</span></span>

* <span data-ttu-id="9001d-380">Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="9001d-380">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="9001d-381">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="9001d-381">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="9001d-382">Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="9001d-382">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="9001d-383">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="9001d-383">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="9001d-384">Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:</span><span class="sxs-lookup"><span data-stu-id="9001d-384">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="9001d-385">El resultado es la siguiente salida JSON impresa correctamente:</span><span class="sxs-lookup"><span data-stu-id="9001d-385">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="9001d-386">Uso de Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="9001d-386">Use Utf8JsonWriter</span></span>

<span data-ttu-id="9001d-387">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="9001d-387">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="9001d-388">Uso de Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9001d-388">Use Utf8JsonReader</span></span>

<span data-ttu-id="9001d-389">En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="9001d-389">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="9001d-390">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9001d-390">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="9001d-391">Filtrado de datos con Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9001d-391">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="9001d-392">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:</span><span class="sxs-lookup"><span data-stu-id="9001d-392">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="9001d-393">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="9001d-393">The preceding code:</span></span>

* <span data-ttu-id="9001d-394">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="9001d-394">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="9001d-395">Cuenta los objetos y los valores de propiedad "name" que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="9001d-395">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="9001d-396">Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9001d-396">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="9001d-397">Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9001d-397">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="9001d-398">Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto.</span><span class="sxs-lookup"><span data-stu-id="9001d-398">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="9001d-399">De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="9001d-399">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="9001d-400">Aquí se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="9001d-400">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="9001d-401">El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":</span><span class="sxs-lookup"><span data-stu-id="9001d-401">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="9001d-402">Lectura de una secuencia mediante Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9001d-402">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="9001d-403">Al leer un archivo grande (un gigabyte o más de tamaño, por ejemplo), puede que desee evitar tener que cargar todo el archivo en la memoria de una vez.</span><span class="sxs-lookup"><span data-stu-id="9001d-403">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="9001d-404">En este escenario, puede usar <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="9001d-404">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="9001d-405">Al usar `Utf8JsonReader` para leer de una secuencia, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="9001d-405">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="9001d-406">El búfer que contiene la carga parcial JSON debe ser al menos tan grande como el token JSON más grande que contiene para que el lector pueda avanzar.</span><span class="sxs-lookup"><span data-stu-id="9001d-406">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="9001d-407">El búfer debe ser al menos tan grande como la secuencia más grande de espacio en blanco dentro del JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-407">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="9001d-408">El lector no realiza un seguimiento de los datos que ha leído hasta que lea completamente el <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> siguiente en la carga JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-408">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="9001d-409">Por tanto, cuando haya bytes restantes en el búfer, tendrá que volver a pasarlos al lector.</span><span class="sxs-lookup"><span data-stu-id="9001d-409">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="9001d-410">Puede usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar el número de bytes que quedan.</span><span class="sxs-lookup"><span data-stu-id="9001d-410">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="9001d-411">El código siguiente muestra cómo leer desde una secuencia.</span><span class="sxs-lookup"><span data-stu-id="9001d-411">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="9001d-412">Este ejemplo se muestra <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="9001d-412">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="9001d-413">Un código similar funcionará con <xref:System.IO.FileStream>, excepto cuando `FileStream` contenga una marca BOM UTF-8 al principio.</span><span class="sxs-lookup"><span data-stu-id="9001d-413">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="9001d-414">En ese caso, debe quitar esos tres bytes del búfer antes de pasar los bytes restantes a `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="9001d-414">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="9001d-415">En caso contrario, el lector produciría una excepción, ya que la marca BOM no se considera una parte válida del JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-415">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="9001d-416">El código de ejemplo comienza con un búfer de 4 KB y duplica el tamaño del búfer cada vez que encuentra que el tamaño no es lo suficientemente grande como para ajustarse a un token JSON completo, lo que es necesario para que el lector realice el progreso de la carga de JSON.</span><span class="sxs-lookup"><span data-stu-id="9001d-416">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="9001d-417">El ejemplo de JSON proporcionado en el fragmento de código desencadena un aumento del tamaño del búfer solo si se establece un tamaño de búfer inicial muy pequeño, por ejemplo, 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="9001d-417">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="9001d-418">Si establece el tamaño de búfer inicial en 10, las instrucciones `Console.WriteLine` muestran la causa y el efecto de los aumentos del tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="9001d-418">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="9001d-419">En el tamaño de búfer inicial de 4 KB, se muestra todo el JSON de ejemplo en cada `Console.WriteLine` y el tamaño del búfer nunca se debe aumentar.</span><span class="sxs-lookup"><span data-stu-id="9001d-419">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="9001d-420">En el ejemplo anterior no se establece ningún límite para el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="9001d-420">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="9001d-421">Si el tamaño del token es demasiado grande, se podría producir un error en el código con una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="9001d-421">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="9001d-422">Esto puede ocurrir si el archivo JSON contiene un token de aproximadamente 1 GB o más de tamaño, ya que la duplicación del tamaño de 1 GB da como resultado un tamaño demasiado grande para caber en un búfer de `int32`.</span><span class="sxs-lookup"><span data-stu-id="9001d-422">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9001d-423">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9001d-423">Additional resources</span></span>

* [<span data-ttu-id="9001d-424">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9001d-424">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9001d-425">Procedimientos para escribir convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="9001d-425">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="9001d-426">Procedimiento para migrar desde Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="9001d-426">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="9001d-427">Compatibilidad con DateTime y DateTimeOffset en System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9001d-427">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="9001d-428">[Referencia de la API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="9001d-428">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
