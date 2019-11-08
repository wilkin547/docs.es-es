---
title: Cómo serializar y deserializar JSON mediante C# .net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740434"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="e088a-102">Cómo serializar y deserializar JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="e088a-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e088a-103">La documentación de serialización de JSON está en construcción.</span><span class="sxs-lookup"><span data-stu-id="e088a-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="e088a-104">En este artículo no se tratan todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="e088a-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="e088a-105">Para obtener más información, examine los [problemas de System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) en el repositorio dotnet/Corefx en Github, especialmente los que tienen la etiqueta [JSON-Functional-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="e088a-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="e088a-106">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="e088a-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="e088a-107">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="e088a-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="e088a-108">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="e088a-108">Namespaces</span></span>

<span data-ttu-id="e088a-109">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="e088a-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="e088a-110">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos y API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="e088a-111">Los ejemplos de código que se muestran en este artículo requieren directivas de `using` para uno o ambos espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="e088a-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="e088a-112">Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="e088a-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="e088a-113">Cómo escribir objetos .NET en JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="e088a-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="e088a-114">Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e088a-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e088a-115">En el ejemplo siguiente se crea JSON como una cadena:</span><span class="sxs-lookup"><span data-stu-id="e088a-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="e088a-116">En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="e088a-117">En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="e088a-118">En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando.</span><span class="sxs-lookup"><span data-stu-id="e088a-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="e088a-119">Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="e088a-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="e088a-120">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="e088a-120">Serialization example</span></span>

<span data-ttu-id="e088a-121">Este es un tipo de ejemplo que contiene colecciones y clases anidadas:</span><span class="sxs-lookup"><span data-stu-id="e088a-121">Here's an example type that contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="e088a-122">La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e088a-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="e088a-123">De forma predeterminada, la salida JSON es reducida:</span><span class="sxs-lookup"><span data-stu-id="e088a-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="e088a-124">En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, con la impresión en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="e088a-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="e088a-125">Serializar a UTF-8</span><span class="sxs-lookup"><span data-stu-id="e088a-125">Serialize to UTF-8</span></span>

<span data-ttu-id="e088a-126">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e088a-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="e088a-127">También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="e088a-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="e088a-128">La serialización a UTF-8 es aproximadamente 5-10% más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="e088a-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="e088a-129">La diferencia se debe a que no es necesario convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="e088a-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="e088a-130">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="e088a-130">Serialization behavior</span></span>

* <span data-ttu-id="e088a-131">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="e088a-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="e088a-132">Puede [especificar las propiedades que se van a excluir](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="e088a-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="e088a-133">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa los caracteres que no son ASCII, los caracteres que distinguen el código html dentro del intervalo ASCII y los caracteres que se deben escapar según [la especificación JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="e088a-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="e088a-134">De forma predeterminada, JSON es reducida.</span><span class="sxs-lookup"><span data-stu-id="e088a-134">By default, JSON is minified.</span></span> <span data-ttu-id="e088a-135">Puede [imprimir el archivo JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="e088a-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="e088a-136">De forma predeterminada, las mayúsculas y minúsculas de los nombres JSON coinciden con los nombres .NET.</span><span class="sxs-lookup"><span data-stu-id="e088a-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="e088a-137">Puede [personalizar el uso de mayúsculas y minúsculas del nombre JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="e088a-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="e088a-138">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="e088a-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="e088a-139">Para obtener más información, consulte el [problema sobre las referencias circulares](https://github.com/dotnet/corefx/issues/38579) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="e088a-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="e088a-140">Actualmente, se excluyen los campos.</span><span class="sxs-lookup"><span data-stu-id="e088a-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="e088a-141">Los tipos admitidos son:</span><span class="sxs-lookup"><span data-stu-id="e088a-141">Supported types include:</span></span>

* <span data-ttu-id="e088a-142">Primitivas de .NET que se asignan a primitivos de JavaScript, como tipos numéricos, cadenas y booleanos.</span><span class="sxs-lookup"><span data-stu-id="e088a-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="e088a-143">[Objetos CLR antiguos sin formato](https://stackoverflow.com/questions/250001/poco-definition)definidos por el usuario (poco).</span><span class="sxs-lookup"><span data-stu-id="e088a-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="e088a-144">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="e088a-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="e088a-145">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement`o POCO.</span><span class="sxs-lookup"><span data-stu-id="e088a-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="e088a-146">Colecciones de los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="e088a-146">Collections from the following namespaces.</span></span> <span data-ttu-id="e088a-147">Para obtener más información, consulte el [tema sobre la compatibilidad con colecciones](https://github.com/dotnet/corefx/issues/36643) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="e088a-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="e088a-148">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="e088a-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="e088a-149">Cómo leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="e088a-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="e088a-150">Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e088a-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e088a-151">En el ejemplo siguiente se lee JSON desde una cadena:</span><span class="sxs-lookup"><span data-stu-id="e088a-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="e088a-152">Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="e088a-153">Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="e088a-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="e088a-154">Para obtener un tipo de ejemplo y el correspondiente JSON, vea la sección [ejemplo de serialización](#serialization-example) .</span><span class="sxs-lookup"><span data-stu-id="e088a-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="e088a-155">Deserializar desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="e088a-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="e088a-156">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que toma un `Utf8JsonReader` o un `ReadOnlySpan<byte>`, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e088a-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="e088a-157">En los ejemplos se da por supuesto que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="e088a-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="e088a-158">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="e088a-158">Deserialization behavior</span></span>

* <span data-ttu-id="e088a-159">De forma predeterminada, la coincidencia de nombres de propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e088a-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="e088a-160">Puede [especificar la distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="e088a-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="e088a-161">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="e088a-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="e088a-162">No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="e088a-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="e088a-163">No se admite la deserialización a objetos inmutables o a propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e088a-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="e088a-164">Para obtener más información, vea el [problema de github sobre la compatibilidad con objetos inmutables](https://github.com/dotnet/corefx/issues/38569) y el [problema en la compatibilidad con propiedades de solo lectura](https://github.com/dotnet/corefx/issues/38163) en el repositorio dotnet/corefx en github.</span><span class="sxs-lookup"><span data-stu-id="e088a-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="e088a-165">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="e088a-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="e088a-166">Puede [serializar los nombres de enumeración como cadenas](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="e088a-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="e088a-167">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="e088a-167">Fields aren't supported.</span></span>
* <span data-ttu-id="e088a-168">De forma predeterminada, los comentarios o las comas finales en el JSON producen excepciones.</span><span class="sxs-lookup"><span data-stu-id="e088a-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="e088a-169">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="e088a-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="e088a-170">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="e088a-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="e088a-171">Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar una funcionalidad que no sea compatible con los convertidores integrados.</span><span class="sxs-lookup"><span data-stu-id="e088a-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="e088a-172">Serializar en JSON con formato</span><span class="sxs-lookup"><span data-stu-id="e088a-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="e088a-173">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="e088a-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-174">A continuación se muestra un tipo de ejemplo que se va a serializar y a la salida de JSON impresa:</span><span class="sxs-lookup"><span data-stu-id="e088a-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="e088a-175">Personalización de nombres y valores de JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-175">Customize JSON names and values</span></span>

<span data-ttu-id="e088a-176">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, incluido Case.</span><span class="sxs-lookup"><span data-stu-id="e088a-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="e088a-177">Los valores de enumeración se representan como números.</span><span class="sxs-lookup"><span data-stu-id="e088a-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="e088a-178">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="e088a-178">This section explains how to:</span></span>

* <span data-ttu-id="e088a-179">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="e088a-179">Customize individual property names</span></span>
* <span data-ttu-id="e088a-180">Convertir todos los nombres de propiedad en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="e088a-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="e088a-181">Implementar una directiva de nomenclatura de propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="e088a-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="e088a-182">Convertir claves de diccionario en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="e088a-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="e088a-183">Convertir enumeraciones en cadenas y Case Camel</span><span class="sxs-lookup"><span data-stu-id="e088a-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="e088a-184">En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="e088a-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="e088a-185">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="e088a-185">Customize individual property names</span></span>

<span data-ttu-id="e088a-186">Para establecer el nombre de las propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e088a-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="e088a-187">Este es un tipo de ejemplo para serializar y JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="e088a-187">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e088a-188">El nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="e088a-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="e088a-189">Se aplica en ambas direcciones, para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="e088a-190">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e088a-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="e088a-191">Usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="e088a-192">Para usar mayúsculas y minúsculas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-193">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e088a-194">La Directiva de nomenclatura de la propiedad Case Camel:</span><span class="sxs-lookup"><span data-stu-id="e088a-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="e088a-195">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="e088a-196">Está invalidado por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="e088a-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="e088a-197">Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no es mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="e088a-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="e088a-198">Usar una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="e088a-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="e088a-199">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="e088a-200">A continuación, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="e088a-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-201">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-201">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e088a-202">La Directiva de nomenclatura de propiedades JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="e088a-203">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="e088a-204">Está invalidado por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="e088a-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="e088a-205">Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="e088a-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="e088a-206">Claves de Diccionario de mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="e088a-206">Camel case dictionary keys</span></span>

<span data-ttu-id="e088a-207">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, las claves de `string` se pueden convertir a mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="e088a-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="e088a-208">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-209">La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tiene pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` daría como resultado una salida JSON similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="e088a-210">La Directiva de nomenclatura de mayúsculas y minúsculas Camel de las claves de diccionario se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="e088a-211">Si se deserializa un diccionario, las claves coincidirán con el archivo JSON incluso si se especifica `JsonNamingPolicy.CamelCase` para la `DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="e088a-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="e088a-212">Enumeraciones como cadenas</span><span class="sxs-lookup"><span data-stu-id="e088a-212">Enums as strings</span></span>

<span data-ttu-id="e088a-213">De forma predeterminada, las enumeraciones se serializan como números.</span><span class="sxs-lookup"><span data-stu-id="e088a-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="e088a-214">Para serializar los nombres de enumeración como cadenas, use el <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="e088a-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="e088a-215">Por ejemplo, supongamos que necesita serializar la siguiente clase que tiene una enumeración:</span><span class="sxs-lookup"><span data-stu-id="e088a-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="e088a-216">Si el resumen es `Hot`, de forma predeterminada, el JSON serializado tiene el valor numérico 3:</span><span class="sxs-lookup"><span data-stu-id="e088a-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="e088a-217">En el código de ejemplo siguiente se serializan los nombres de enumeración en su lugar y se convierten en mayúsculas y minúsculas Camel:</span><span class="sxs-lookup"><span data-stu-id="e088a-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="e088a-218">El JSON resultante es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="e088a-219">La compatibilidad con las enumeraciones como cadenas se aplica también a la deserialización, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="e088a-220">Excluir propiedades de la serialización</span><span class="sxs-lookup"><span data-stu-id="e088a-220">Exclude properties from serialization</span></span>

<span data-ttu-id="e088a-221">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="e088a-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="e088a-222">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="e088a-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="e088a-223">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="e088a-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="e088a-224">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="e088a-224">Individual properties</span></span>
* <span data-ttu-id="e088a-225">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="e088a-225">All read-only properties</span></span>
* <span data-ttu-id="e088a-226">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="e088a-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="e088a-227">Excluir propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="e088a-227">Exclude individual properties</span></span>

<span data-ttu-id="e088a-228">Para omitir las propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e088a-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="e088a-229">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-229">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="e088a-230">Excluir todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="e088a-230">Exclude all read-only properties</span></span>

<span data-ttu-id="e088a-231">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="e088a-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="e088a-232">Para excluir todas las propiedades de solo lectura, establezca el <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-233">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-233">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="e088a-234">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-234">This option applies only to serialization.</span></span> <span data-ttu-id="e088a-235">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e088a-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="e088a-236">Excluir todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="e088a-236">Exclude all null value properties</span></span>

<span data-ttu-id="e088a-237">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-238">A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="e088a-239">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="e088a-239">Property</span></span> |<span data-ttu-id="e088a-240">Valor</span><span class="sxs-lookup"><span data-stu-id="e088a-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="e088a-241">Fecha</span><span class="sxs-lookup"><span data-stu-id="e088a-241">Date</span></span>    | <span data-ttu-id="e088a-242">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e088a-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="e088a-243">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="e088a-243">TemperatureC</span></span>| <span data-ttu-id="e088a-244">25</span><span class="sxs-lookup"><span data-stu-id="e088a-244">25</span></span> |
| <span data-ttu-id="e088a-245">Resumen</span><span class="sxs-lookup"><span data-stu-id="e088a-245">Summary</span></span>| <span data-ttu-id="e088a-246">nulo</span><span class="sxs-lookup"><span data-stu-id="e088a-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="e088a-247">Esta configuración se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="e088a-248">Para obtener información sobre su efecto en la deserialización, vea [omitir null al deserializar](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="e088a-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="e088a-249">Personalizar la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="e088a-249">Customize character encoding</span></span>

<span data-ttu-id="e088a-250">De forma predeterminada, el serializador convierte todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="e088a-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="e088a-251">Es decir, los reemplaza por `\uxxxx` donde `xxxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="e088a-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="e088a-252">Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e088a-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="e088a-253">Serializar juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="e088a-253">Serialize language character sets</span></span>

<span data-ttu-id="e088a-254">Para serializar los juegos de caracteres de uno o más idiomas, especifique los [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-255">Este código serializa los caracteres cirílico y griego.</span><span class="sxs-lookup"><span data-stu-id="e088a-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="e088a-256">Los caracteres cirílicos se muestran en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="e088a-257">Para especificar todos los idiomas, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e088a-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="e088a-258">Serializar caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="e088a-258">Serialize specific characters</span></span>

<span data-ttu-id="e088a-259">Una alternativa consiste en especificar caracteres individuales que desea permitir a través de sin caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="e088a-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="e088a-260">En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:</span><span class="sxs-lookup"><span data-stu-id="e088a-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="e088a-261">Este es un ejemplo de JSON generado por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="e088a-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="e088a-262">Serializar todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="e088a-262">Serialize all characters</span></span>

<span data-ttu-id="e088a-263">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="e088a-264">A diferencia del codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping`:</span><span class="sxs-lookup"><span data-stu-id="e088a-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="e088a-265">No se convierte en caracteres que no tengan en cuenta las mayúsculas y minúsculas, como `<`, `>`, `&`y `'`.</span><span class="sxs-lookup"><span data-stu-id="e088a-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="e088a-266">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, como los que pueden ser el resultado del cliente y el servidor que no acuerdan el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="e088a-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="e088a-267">Es más permisivo que el codificador predeterminado en el que se permite que los caracteres pasen a través de sin escape.</span><span class="sxs-lookup"><span data-stu-id="e088a-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="e088a-268">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e088a-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="e088a-269">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="e088a-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="e088a-270">Nunca permita que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="e088a-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="e088a-271">Serializar propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="e088a-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="e088a-272">No se admite la serialización polimórfica cuando se especifica en tiempo de compilación el tipo que se va a serializar.</span><span class="sxs-lookup"><span data-stu-id="e088a-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="e088a-273">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="e088a-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="e088a-274">Y Supongamos que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="e088a-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="e088a-275">En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea realmente un objeto `WeatherForecastWithWind`.</span><span class="sxs-lookup"><span data-stu-id="e088a-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="e088a-276">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="e088a-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="e088a-277">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e088a-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="e088a-278">Para serializar las propiedades del tipo derivado, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e088a-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="e088a-279">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="e088a-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="e088a-280">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="e088a-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="e088a-281">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="e088a-282">Para obtener información acerca de la deserialización polimórfica, consulte [compatibilidad con la deserialización polimórfica](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="e088a-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="e088a-283">Permitir comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="e088a-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="e088a-284">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="e088a-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="e088a-285">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="e088a-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="e088a-286">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="e088a-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="e088a-287">En el ejemplo siguiente se muestra cómo permitir ambos:</span><span class="sxs-lookup"><span data-stu-id="e088a-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="e088a-288">Este es un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="e088a-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="e088a-289">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="e088a-289">Case-insensitive property matching</span></span>

<span data-ttu-id="e088a-290">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingue entre mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="e088a-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="e088a-291">Para cambiar ese comportamiento, establezca el <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="e088a-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="e088a-292">Este es un ejemplo de JSON con nombres de propiedad Case Camel.</span><span class="sxs-lookup"><span data-stu-id="e088a-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="e088a-293">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades de mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="e088a-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="e088a-294">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="e088a-294">Handle overflow JSON</span></span>

<span data-ttu-id="e088a-295">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e088a-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="e088a-296">Por ejemplo, supongamos que el tipo de destino es:</span><span class="sxs-lookup"><span data-stu-id="e088a-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="e088a-297">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-297">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="e088a-298">Si deserializa el JSON que se muestra en el tipo que se muestra, las propiedades `DatesAvailable` y `SummaryWords` no tienen ninguna que ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="e088a-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="e088a-299">Para capturar datos adicionales, como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="e088a-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="e088a-300">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares de clave y valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="e088a-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="e088a-301">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="e088a-301">Property</span></span> |<span data-ttu-id="e088a-302">Valor</span><span class="sxs-lookup"><span data-stu-id="e088a-302">Value</span></span>  |<span data-ttu-id="e088a-303">Notas</span><span class="sxs-lookup"><span data-stu-id="e088a-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="e088a-304">Fecha</span><span class="sxs-lookup"><span data-stu-id="e088a-304">Date</span></span>    | <span data-ttu-id="e088a-305">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e088a-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="e088a-306">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="e088a-306">TemperatureC</span></span>| <span data-ttu-id="e088a-307">0</span><span class="sxs-lookup"><span data-stu-id="e088a-307">0</span></span> | <span data-ttu-id="e088a-308">No coinciden las mayúsculas y minúsculas (`temperatureC` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e088a-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="e088a-309">Resumen</span><span class="sxs-lookup"><span data-stu-id="e088a-309">Summary</span></span> | <span data-ttu-id="e088a-310">Conexión</span><span class="sxs-lookup"><span data-stu-id="e088a-310">Hot</span></span> ||
| <span data-ttu-id="e088a-311">Extensiondata (</span><span class="sxs-lookup"><span data-stu-id="e088a-311">ExtensionData</span></span> | <span data-ttu-id="e088a-312">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="e088a-312">temperatureC: 25</span></span> |<span data-ttu-id="e088a-313">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="e088a-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="e088a-314">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="e088a-314">DatesAvailable:</span></span><br>  <span data-ttu-id="e088a-315">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e088a-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="e088a-316">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e088a-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="e088a-317">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="e088a-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="e088a-318">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="e088a-318">SummaryWords:</span></span><br><span data-ttu-id="e088a-319">Geniales</span><span class="sxs-lookup"><span data-stu-id="e088a-319">Cool</span></span><br><span data-ttu-id="e088a-320">Viento</span><span class="sxs-lookup"><span data-stu-id="e088a-320">Windy</span></span><br><span data-ttu-id="e088a-321">Húmeda</span><span class="sxs-lookup"><span data-stu-id="e088a-321">Humid</span></span> |<span data-ttu-id="e088a-322">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="e088a-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="e088a-323">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON del mismo modo que en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="e088a-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="e088a-324">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="e088a-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="e088a-325">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que no se pudiera deserializar.</span><span class="sxs-lookup"><span data-stu-id="e088a-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="e088a-326">Omitir null al deserializar</span><span class="sxs-lookup"><span data-stu-id="e088a-326">Ignore null when deserializing</span></span>

<span data-ttu-id="e088a-327">De forma predeterminada, si una propiedad en JSON es null, la propiedad correspondiente en el objeto de destino se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="e088a-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="e088a-328">En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no desea que un valor null invalide el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e088a-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="e088a-329">Por ejemplo, supongamos que el código siguiente representa el objeto de destino:</span><span class="sxs-lookup"><span data-stu-id="e088a-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="e088a-330">Y Supongamos que se deserializa el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="e088a-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="e088a-331">Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.</span><span class="sxs-lookup"><span data-stu-id="e088a-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="e088a-332">Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="e088a-333">Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "no Summary" después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="e088a-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="e088a-334">Los valores NULL en JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="e088a-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="e088a-335">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="e088a-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="e088a-336">Para obtener más información, vea el [problema en los tipos de valor que no aceptan valores NULL](https://github.com/dotnet/corefx/issues/40922) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="e088a-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="e088a-337">Utf8JsonReader, Utf8JsonWriter y JsonDocument</span><span class="sxs-lookup"><span data-stu-id="e088a-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="e088a-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="e088a-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="e088a-339">El `Utf8JsonReader` es un tipo de nivel bajo que se puede utilizar para crear analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="e088a-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="e088a-340">El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e088a-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="e088a-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> es una forma de alto rendimiento de escribir texto JSON con codificación UTF-8 de tipos comunes de .NET como `String`, `Int32`y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="e088a-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="e088a-342">El escritor es un tipo de nivel bajo que se puede utilizar para crear serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="e088a-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="e088a-343">El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e088a-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="e088a-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> proporciona la capacidad de crear un Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="e088a-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="e088a-345">DOM proporciona acceso aleatorio a los datos en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="e088a-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="e088a-346">Se puede tener acceso a los elementos JSON que componen la carga a través del tipo de <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="e088a-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="e088a-347">El `JsonElement` proporciona enumeradores de matriz y de objeto junto con las API para convertir texto JSON en tipos comunes de .NET.</span><span class="sxs-lookup"><span data-stu-id="e088a-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="e088a-348">`JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="e088a-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="e088a-349">En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.</span><span class="sxs-lookup"><span data-stu-id="e088a-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="e088a-350">Usar JsonDocument para el acceso a los datos</span><span class="sxs-lookup"><span data-stu-id="e088a-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="e088a-351">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos:</span><span class="sxs-lookup"><span data-stu-id="e088a-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="e088a-352">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="e088a-352">The preceding code:</span></span>

* <span data-ttu-id="e088a-353">Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="e088a-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="e088a-354">Calcula la media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.</span><span class="sxs-lookup"><span data-stu-id="e088a-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="e088a-355">Asigna un nivel predeterminado de 70 a los estudiantes que no tienen una calificación.</span><span class="sxs-lookup"><span data-stu-id="e088a-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="e088a-356">Cuenta a los estudiantes incrementando una variable de `count` con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="e088a-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="e088a-357">Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span><span class="sxs-lookup"><span data-stu-id="e088a-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="e088a-358">Este es un ejemplo del código JSON que este código procesa:</span><span class="sxs-lookup"><span data-stu-id="e088a-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="e088a-359">Uso de JsonDocument para escribir JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="e088a-360">En el ejemplo siguiente se muestra cómo escribir JSON desde un <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="e088a-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="e088a-361">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="e088a-361">The preceding code:</span></span>

* <span data-ttu-id="e088a-362">Lee un archivo JSON, carga los datos en un `JsonDocument`y escribe JSON con formato (impreso) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e088a-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="e088a-363">Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="e088a-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="e088a-364">Cuando termine, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor.</span><span class="sxs-lookup"><span data-stu-id="e088a-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="e088a-365">Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.</span><span class="sxs-lookup"><span data-stu-id="e088a-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="e088a-366">A continuación se muestra un ejemplo de entrada JSON que se va a procesar mediante el código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e088a-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="e088a-367">El resultado es la siguiente salida JSON impresa:</span><span class="sxs-lookup"><span data-stu-id="e088a-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="e088a-368">Usar Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e088a-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="e088a-369">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="e088a-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader"></a><span data-ttu-id="e088a-370">Usar Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="e088a-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="e088a-371">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="e088a-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

<span data-ttu-id="e088a-372">En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, codificado como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e088a-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="e088a-373">Filtrar datos mediante Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="e088a-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="e088a-374">En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:</span><span class="sxs-lookup"><span data-stu-id="e088a-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="e088a-375">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="e088a-375">The preceding code:</span></span>

* <span data-ttu-id="e088a-376">Supone que el archivo está codificado como UTF-16 y lo transcodifica en UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e088a-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="e088a-377">Un archivo codificado como UTF-8 puede leerse directamente en un `ReadOnlySpan<byte>`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e088a-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="e088a-378">Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "Name" de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="e088a-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="e088a-379">Cuenta los objetos y `name` valores de propiedad que terminan en "University".</span><span class="sxs-lookup"><span data-stu-id="e088a-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="e088a-380">A continuación se muestra un ejemplo de JSON que el código anterior puede leer.</span><span class="sxs-lookup"><span data-stu-id="e088a-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="e088a-381">El mensaje de Resumen resultante es "2 de 4 nombres que terminan con" Universidad "":</span><span class="sxs-lookup"><span data-stu-id="e088a-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="e088a-382">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e088a-382">Additional resources</span></span>

* [<span data-ttu-id="e088a-383">Información general de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="e088a-384">Referencia de la API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="e088a-385">Escritura de convertidores personalizados para System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="e088a-386">Compatibilidad con DateTime y DateTimeOffset en System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e088a-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
