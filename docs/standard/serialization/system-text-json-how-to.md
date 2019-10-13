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
ms.openlocfilehash: 22c2fd5fc5eaf7a5dc9b71a7335b0b844fa92b51
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291608"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="ace19-102">Cómo serializar y deserializar JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="ace19-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ace19-103">La documentación de serialización de JSON está en construcción.</span><span class="sxs-lookup"><span data-stu-id="ace19-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="ace19-104">En este artículo no se tratan todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="ace19-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="ace19-105">Para obtener más información, examine los [problemas de System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) en el repositorio dotnet/Corefx en Github, especialmente los que tienen la etiqueta [JSON-Functional-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="ace19-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="ace19-106">En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="ace19-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="ace19-107">Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="ace19-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="ace19-108">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="ace19-108">Namespaces</span></span>

<span data-ttu-id="ace19-109">El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales.</span><span class="sxs-lookup"><span data-stu-id="ace19-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="ace19-110">El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos y API para escenarios avanzados y personalización específicos de la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="ace19-111">Por lo tanto, los ejemplos de código que se muestran en este artículo requieren una o las dos directivas `using` siguientes:</span><span class="sxs-lookup"><span data-stu-id="ace19-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="ace19-112">Actualmente no se admiten los atributos del espacio de nombres <xref:System.Runtime.Serialization> en `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="ace19-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="ace19-113">Cómo escribir objetos .NET en JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="ace19-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="ace19-114">Para escribir JSON en una cadena, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ace19-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ace19-115">En el ejemplo siguiente se usa una sobrecarga con un parámetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="ace19-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="ace19-116">Puede omitir el parámetro de tipo genérico y usar la inferencia de tipo genérico en su lugar:</span><span class="sxs-lookup"><span data-stu-id="ace19-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="ace19-117">Este es un tipo de ejemplo que se va a serializar, que contiene colecciones y clases anidadas:</span><span class="sxs-lookup"><span data-stu-id="ace19-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="ace19-118">De forma predeterminada, la salida JSON es reducida:</span><span class="sxs-lookup"><span data-stu-id="ace19-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="ace19-119">En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, con la impresión en blanco y sangría):</span><span class="sxs-lookup"><span data-stu-id="ace19-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="ace19-120">Las sobrecargas de <xref:System.Text.Json.JsonSerializer.Serialize%2A> permiten serializar a un <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="ace19-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="ace19-121">Las versiones asincrónicas de las sobrecargas `Stream` están disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace19-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="ace19-122">Serializar a UTF-8</span><span class="sxs-lookup"><span data-stu-id="ace19-122">Serialize to UTF-8</span></span>

<span data-ttu-id="ace19-123">Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="ace19-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="ace19-124">Como alternativa, está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="ace19-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="ace19-125">La serialización a UTF-8 es aproximadamente 5-10% más rápida que el uso de métodos basados en cadenas.</span><span class="sxs-lookup"><span data-stu-id="ace19-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="ace19-126">La diferencia se debe a que no es necesario convertir los bytes (como UTF-8) en cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="ace19-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="ace19-127">Comportamiento de serialización</span><span class="sxs-lookup"><span data-stu-id="ace19-127">Serialization behavior</span></span>

* <span data-ttu-id="ace19-128">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="ace19-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="ace19-129">Puede [especificar las propiedades que se van a excluir](#exclude-properties).</span><span class="sxs-lookup"><span data-stu-id="ace19-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="ace19-130">El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa los caracteres que no son ASCII, los caracteres que distinguen el código html dentro del intervalo ASCII y los caracteres que se deben escapar según [la especificación JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="ace19-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="ace19-131">De forma predeterminada, JSON es reducida.</span><span class="sxs-lookup"><span data-stu-id="ace19-131">By default, JSON is minified.</span></span> <span data-ttu-id="ace19-132">Puede [imprimir el archivo JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="ace19-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="ace19-133">De forma predeterminada, las mayúsculas y minúsculas de los nombres JSON coinciden con los nombres .NET.</span><span class="sxs-lookup"><span data-stu-id="ace19-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="ace19-134">Puede [personalizar el uso de mayúsculas y minúsculas del nombre JSON](#customize-json-names).</span><span class="sxs-lookup"><span data-stu-id="ace19-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="ace19-135">Se detectan las referencias circulares y se inician las excepciones.</span><span class="sxs-lookup"><span data-stu-id="ace19-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="ace19-136">Para obtener más información, consulte el [problema sobre las referencias circulares](https://github.com/dotnet/corefx/issues/38579) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="ace19-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="ace19-137">Actualmente, se excluyen los campos.</span><span class="sxs-lookup"><span data-stu-id="ace19-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="ace19-138">Los tipos admitidos son:</span><span class="sxs-lookup"><span data-stu-id="ace19-138">Supported types include:</span></span>

* <span data-ttu-id="ace19-139">Primitivas de .NET que se asignan a primitivos de JavaScript, como tipos numéricos, cadenas y booleanos.</span><span class="sxs-lookup"><span data-stu-id="ace19-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="ace19-140">[Objetos CLR antiguos sin formato](https://stackoverflow.com/questions/250001/poco-definition)definidos por el usuario (poco).</span><span class="sxs-lookup"><span data-stu-id="ace19-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="ace19-141">Matrices unidimensionales y escalonadas (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="ace19-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="ace19-142">`Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.</span><span class="sxs-lookup"><span data-stu-id="ace19-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="ace19-143">Colecciones de los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ace19-143">Collections from the following namespaces.</span></span> <span data-ttu-id="ace19-144">Para obtener más información, consulte el [tema sobre la compatibilidad con colecciones](https://github.com/dotnet/corefx/issues/36643) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="ace19-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="ace19-145">Cómo leer JSON en objetos .NET (deserializar)</span><span class="sxs-lookup"><span data-stu-id="ace19-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="ace19-146">Para deserializar a partir de una cadena, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="ace19-147">Para obtener un ejemplo, vea la sección [Serialize](#how-to-write-net-objects-to-json-serialize) .</span><span class="sxs-lookup"><span data-stu-id="ace19-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="ace19-148">El objeto JSON y .NET son los mismos, pero la dirección se invierte.</span><span class="sxs-lookup"><span data-stu-id="ace19-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="ace19-149">Las sobrecargas de <xref:System.Text.Json.JsonSerializer.Deserialize*> permiten deserializar a partir de un `Stream`.</span><span class="sxs-lookup"><span data-stu-id="ace19-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="ace19-150">Las versiones asincrónicas de las sobrecargas `Stream` están disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace19-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="ace19-151">Deserializar desde UTF-8</span><span class="sxs-lookup"><span data-stu-id="ace19-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="ace19-152">Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que toma `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ace19-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="ace19-153">Comportamiento de la deserialización</span><span class="sxs-lookup"><span data-stu-id="ace19-153">Deserialization behavior</span></span>

* <span data-ttu-id="ace19-154">De forma predeterminada, la coincidencia de nombres de propiedad distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ace19-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="ace19-155">Puede [especificar la distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="ace19-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="ace19-156">Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="ace19-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="ace19-157">No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="ace19-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="ace19-158">No se admite la deserialización a objetos inmutables o a propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ace19-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="ace19-159">Para obtener más información, vea el [problema de github sobre la compatibilidad con objetos inmutables](https://github.com/dotnet/corefx/issues/38569) y el [problema en la compatibilidad con propiedades de solo lectura](https://github.com/dotnet/corefx/issues/38163) en el repositorio dotnet/corefx en github.</span><span class="sxs-lookup"><span data-stu-id="ace19-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="ace19-160">De forma predeterminada, las enumeraciones se admiten como números.</span><span class="sxs-lookup"><span data-stu-id="ace19-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="ace19-161">No se admiten los campos.</span><span class="sxs-lookup"><span data-stu-id="ace19-161">Fields aren't supported.</span></span>
* <span data-ttu-id="ace19-162">De forma predeterminada, los comentarios o las comas finales en el JSON producen excepciones.</span><span class="sxs-lookup"><span data-stu-id="ace19-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="ace19-163">Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas) si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ace19-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="ace19-164">La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.</span><span class="sxs-lookup"><span data-stu-id="ace19-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="ace19-165">Serializar en JSON con formato</span><span class="sxs-lookup"><span data-stu-id="ace19-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="ace19-166">Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="ace19-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-167">Este es un tipo de ejemplo que se va a serializar y a la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="ace19-168">Permitir comentarios y comas finales</span><span class="sxs-lookup"><span data-stu-id="ace19-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="ace19-169">De forma predeterminada, los comentarios y las comas finales no se permiten en JSON.</span><span class="sxs-lookup"><span data-stu-id="ace19-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="ace19-170">Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="ace19-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="ace19-171">Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ace19-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="ace19-172">En el ejemplo siguiente se muestra cómo permitir ambos:</span><span class="sxs-lookup"><span data-stu-id="ace19-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

<span data-ttu-id="ace19-173">Este es un ejemplo de JSON con comentarios y una coma final:</span><span class="sxs-lookup"><span data-stu-id="ace19-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="ace19-174">Personalización de nombres JSON</span><span class="sxs-lookup"><span data-stu-id="ace19-174">Customize JSON names</span></span>

<span data-ttu-id="ace19-175">De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, incluido Case.</span><span class="sxs-lookup"><span data-stu-id="ace19-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="ace19-176">En esta sección se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="ace19-176">This section explains how to:</span></span>

* <span data-ttu-id="ace19-177">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="ace19-177">Customize individual property names</span></span>
* <span data-ttu-id="ace19-178">Convertir todos los nombres de propiedad en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="ace19-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="ace19-179">Implementar una directiva de nomenclatura de propiedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="ace19-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="ace19-180">Convertir claves de diccionario en mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="ace19-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="ace19-181">Actualmente, no se admite la conversión automática de las enumeraciones en mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="ace19-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="ace19-182">Para obtener más información, vea el [problema en la compatibilidad con las mayúsculas y minúsculas Camel](https://github.com/dotnet/corefx/issues/37725) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="ace19-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="ace19-183">Personalizar nombres de propiedad individuales</span><span class="sxs-lookup"><span data-stu-id="ace19-183">Customize individual property names</span></span>

<span data-ttu-id="ace19-184">Para establecer el nombre de las propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="ace19-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="ace19-185">Este es un tipo de ejemplo para serializar y JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="ace19-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="ace19-186">El nombre de propiedad establecido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="ace19-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="ace19-187">Se aplica en ambas direcciones, para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="ace19-188">Tiene prioridad sobre las directivas de nomenclatura de propiedades.</span><span class="sxs-lookup"><span data-stu-id="ace19-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="ace19-189">Usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON</span><span class="sxs-lookup"><span data-stu-id="ace19-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="ace19-190">Para usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-191">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-191">Here's an example class to serialize and JSON output:</span></span>

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
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="ace19-192">La Directiva de nomenclatura de la propiedad Case Camel:</span><span class="sxs-lookup"><span data-stu-id="ace19-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="ace19-193">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="ace19-194">Se reemplaza por los atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="ace19-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="ace19-195">Usar una directiva de nomenclatura de propiedades JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="ace19-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="ace19-196">Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="ace19-197">A continuación, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="ace19-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-198">A continuación se muestra una clase de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="ace19-199">La Directiva de nomenclatura de propiedades JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="ace19-200">Se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="ace19-201">Se reemplaza por los atributos `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="ace19-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="ace19-202">Claves de Diccionario de mayúsculas y minúsculas Camel</span><span class="sxs-lookup"><span data-stu-id="ace19-202">Camel case dictionary keys</span></span>

<span data-ttu-id="ace19-203">Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, las claves de `string` se pueden convertir a mayúsculas y minúsculas Camel.</span><span class="sxs-lookup"><span data-stu-id="ace19-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="ace19-204">Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-205">A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="ace19-206">Property</span><span class="sxs-lookup"><span data-stu-id="ace19-206">Property</span></span> |<span data-ttu-id="ace19-207">Valor</span><span class="sxs-lookup"><span data-stu-id="ace19-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="ace19-208">Fecha</span><span class="sxs-lookup"><span data-stu-id="ace19-208">Date</span></span>    | <span data-ttu-id="ace19-209">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="ace19-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="ace19-210">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="ace19-210">TemperatureC</span></span>| <span data-ttu-id="ace19-211">25</span><span class="sxs-lookup"><span data-stu-id="ace19-211">25</span></span> |
| <span data-ttu-id="ace19-212">Resumen</span><span class="sxs-lookup"><span data-stu-id="ace19-212">Summary</span></span>| <span data-ttu-id="ace19-213">Conexión</span><span class="sxs-lookup"><span data-stu-id="ace19-213">Hot</span></span>|
| <span data-ttu-id="ace19-214">TemperatureRanges</span><span class="sxs-lookup"><span data-stu-id="ace19-214">TemperatureRanges</span></span> | <span data-ttu-id="ace19-215">Frío, 20</span><span class="sxs-lookup"><span data-stu-id="ace19-215">Cold, 20</span></span><br><span data-ttu-id="ace19-216">En caliente, 40</span><span class="sxs-lookup"><span data-stu-id="ace19-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="ace19-217">La Directiva de nomenclatura de mayúsculas y minúsculas Camel se aplica solo a la serialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="ace19-218">Propiedades de exclusión</span><span class="sxs-lookup"><span data-stu-id="ace19-218">Exclude properties</span></span>

<span data-ttu-id="ace19-219">De forma predeterminada, se serializan todas las propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="ace19-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="ace19-220">Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones.</span><span class="sxs-lookup"><span data-stu-id="ace19-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="ace19-221">En esta sección se explica cómo excluir:</span><span class="sxs-lookup"><span data-stu-id="ace19-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="ace19-222">Propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="ace19-222">Individual properties</span></span>
* <span data-ttu-id="ace19-223">Todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="ace19-223">All read-only properties</span></span>
* <span data-ttu-id="ace19-224">Todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="ace19-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="ace19-225">Excluir propiedades individuales</span><span class="sxs-lookup"><span data-stu-id="ace19-225">Exclude individual properties</span></span>

<span data-ttu-id="ace19-226">Para omitir las propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="ace19-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="ace19-227">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="ace19-228">Excluir todas las propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="ace19-228">Exclude all read-only properties</span></span>

<span data-ttu-id="ace19-229">Para excluir todas las propiedades de solo lectura, establezca el <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-230">Este es un tipo de ejemplo para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="ace19-231">Esta opción solo se aplica a la serialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-231">This option applies only to serialization.</span></span> <span data-ttu-id="ace19-232">Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ace19-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="ace19-233">Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.</span><span class="sxs-lookup"><span data-stu-id="ace19-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="ace19-234">Excluir todas las propiedades de valores NULL</span><span class="sxs-lookup"><span data-stu-id="ace19-234">Exclude all null value properties</span></span>

<span data-ttu-id="ace19-235">Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="ace19-236">A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="ace19-237">Property</span><span class="sxs-lookup"><span data-stu-id="ace19-237">Property</span></span> |<span data-ttu-id="ace19-238">Valor</span><span class="sxs-lookup"><span data-stu-id="ace19-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="ace19-239">Fecha</span><span class="sxs-lookup"><span data-stu-id="ace19-239">Date</span></span>    | <span data-ttu-id="ace19-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="ace19-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="ace19-241">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="ace19-241">TemperatureC</span></span>| <span data-ttu-id="ace19-242">25</span><span class="sxs-lookup"><span data-stu-id="ace19-242">25</span></span> |
| <span data-ttu-id="ace19-243">Resumen</span><span class="sxs-lookup"><span data-stu-id="ace19-243">Summary</span></span>| <span data-ttu-id="ace19-244">nulo</span><span class="sxs-lookup"><span data-stu-id="ace19-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="ace19-245">Esta configuración se aplica a la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ace19-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="ace19-246">Durante la deserialización, los valores NULL de JSON solo se omiten si son válidos.</span><span class="sxs-lookup"><span data-stu-id="ace19-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="ace19-247">Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones.</span><span class="sxs-lookup"><span data-stu-id="ace19-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="ace19-248">Para obtener más información, vea el [problema en los tipos de valor que no aceptan valores NULL](https://github.com/dotnet/corefx/issues/40922) en el repositorio dotnet/Corefx en github.</span><span class="sxs-lookup"><span data-stu-id="ace19-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="ace19-249">Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="ace19-249">Case-insensitive property matching</span></span>

<span data-ttu-id="ace19-250">De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingue entre mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="ace19-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="ace19-251">Para cambiar ese comportamiento, establezca el <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:</span><span class="sxs-lookup"><span data-stu-id="ace19-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="ace19-252">Este es un ejemplo de JSON con nombres de propiedad Case Camel.</span><span class="sxs-lookup"><span data-stu-id="ace19-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="ace19-253">Se puede deserializar en el tipo siguiente que tenga nombres de propiedades de mayúsculas y minúsculas Pascal.</span><span class="sxs-lookup"><span data-stu-id="ace19-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="ace19-254">Incluir propiedades de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="ace19-254">Include properties of derived classes</span></span>

<span data-ttu-id="ace19-255">No se admite la serialización polimórfica cuando se especifica en tiempo de compilación el tipo que se va a serializar.</span><span class="sxs-lookup"><span data-stu-id="ace19-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="ace19-256">Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="ace19-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="ace19-257">Y Supongamos que el método `Serialize` que se pasa a, o que se ha deducido, es `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="ace19-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="ace19-258">En este escenario, no se serializa la propiedad `WindSpeed` ni siquiera si el objeto `weatherForecast` es realmente un objeto @no__t 2.</span><span class="sxs-lookup"><span data-stu-id="ace19-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="ace19-259">Solo se serializan las propiedades de la clase base:</span><span class="sxs-lookup"><span data-stu-id="ace19-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="ace19-260">Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ace19-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="ace19-261">Para serializar las propiedades del tipo derivado, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ace19-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="ace19-262">Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="ace19-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="ace19-263">Declare el objeto que se va a serializar como `object`.</span><span class="sxs-lookup"><span data-stu-id="ace19-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="ace19-264">En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:</span><span class="sxs-lookup"><span data-stu-id="ace19-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="ace19-265">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="ace19-265">Handle overflow JSON</span></span>

<span data-ttu-id="ace19-266">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="ace19-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="ace19-267">Por ejemplo, supongamos que el tipo de destino es:</span><span class="sxs-lookup"><span data-stu-id="ace19-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="ace19-268">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ace19-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="ace19-269">Si deserializa el JSON mostrado en el tipo que se muestra, las propiedades `DatesAvailable` y `SummaryWords` no tienen ninguna que ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="ace19-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="ace19-270">Para capturar datos adicionales, como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="ace19-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="ace19-271">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="ace19-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="ace19-272">Property</span><span class="sxs-lookup"><span data-stu-id="ace19-272">Property</span></span> |<span data-ttu-id="ace19-273">Valor</span><span class="sxs-lookup"><span data-stu-id="ace19-273">Value</span></span>  |<span data-ttu-id="ace19-274">Notas</span><span class="sxs-lookup"><span data-stu-id="ace19-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="ace19-275">Fecha</span><span class="sxs-lookup"><span data-stu-id="ace19-275">Date</span></span>    | <span data-ttu-id="ace19-276">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="ace19-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="ace19-277">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="ace19-277">TemperatureC</span></span>| <span data-ttu-id="ace19-278">0</span><span class="sxs-lookup"><span data-stu-id="ace19-278">0</span></span> | <span data-ttu-id="ace19-279">No coinciden las mayúsculas y minúsculas (`temperatureC` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ace19-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="ace19-280">Resumen</span><span class="sxs-lookup"><span data-stu-id="ace19-280">Summary</span></span> | <span data-ttu-id="ace19-281">Conexión</span><span class="sxs-lookup"><span data-stu-id="ace19-281">Hot</span></span> ||
| <span data-ttu-id="ace19-282">Extensiondata (</span><span class="sxs-lookup"><span data-stu-id="ace19-282">ExtensionData</span></span> | <span data-ttu-id="ace19-283">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="ace19-283">temperatureC: 25</span></span> |<span data-ttu-id="ace19-284">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="ace19-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="ace19-285">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="ace19-285">DatesAvailable:</span></span><br>  <span data-ttu-id="ace19-286">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="ace19-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="ace19-287">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="ace19-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="ace19-288">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="ace19-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="ace19-289">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="ace19-289">SummaryWords:</span></span><br><span data-ttu-id="ace19-290">Geniales</span><span class="sxs-lookup"><span data-stu-id="ace19-290">Cool</span></span><br><span data-ttu-id="ace19-291">Viento</span><span class="sxs-lookup"><span data-stu-id="ace19-291">Windy</span></span><br><span data-ttu-id="ace19-292">Húmeda</span><span class="sxs-lookup"><span data-stu-id="ace19-292">Humid</span></span> |<span data-ttu-id="ace19-293">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="ace19-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="ace19-294">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON del mismo modo que en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="ace19-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="ace19-295">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="ace19-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="ace19-296">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que no se pudiera deserializar.</span><span class="sxs-lookup"><span data-stu-id="ace19-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="ace19-297">Usar Utf8JsonWriter directamente</span><span class="sxs-lookup"><span data-stu-id="ace19-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="ace19-298">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonWriter> directamente.</span><span class="sxs-lookup"><span data-stu-id="ace19-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="ace19-299">Usar Utf8JsonReader directamente</span><span class="sxs-lookup"><span data-stu-id="ace19-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="ace19-300">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonReader> directamente.</span><span class="sxs-lookup"><span data-stu-id="ace19-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="ace19-301">En el código se supone que la variable `jsonUtf8` es una matriz de bytes que contiene un valor JSON válido, codificado como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ace19-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="ace19-302">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ace19-302">Additional resources</span></span>

* [<span data-ttu-id="ace19-303">Información general de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="ace19-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="ace19-304">Referencia de la API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="ace19-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="ace19-305">Compatibilidad con DateTime y DateTimeOffset en System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="ace19-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
