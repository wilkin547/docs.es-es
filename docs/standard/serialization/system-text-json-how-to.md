---
title: Cómo serializar JSON-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8ccd7afe4abb928e7723aa740507774012fc85d1
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083108"
---
# <a name="how-to-serialize-json-in-net"></a>Cómo serializar JSON en .NET

> [!IMPORTANT]
> La documentación de serialización de JSON está en construcción. En este artículo no se tratan todos los escenarios. Para obtener más información, examine los [problemas de System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) en el repositorio dotnet/Corefx en Github, especialmente los que tienen la etiqueta [JSON-Functional-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).

En este artículo se muestra cómo usar <xref:System.Text.Json> el espacio de nombres para serializar y deserializar a y desde notación de objetos JavaScript (JSON). Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.net Core](/aspnet/core/).

## <a name="namespaces"></a>Espacios de nombres

El <xref:System.Text.Json> espacio de nombres contiene todos los puntos de entrada y los tipos principales. El <xref:System.Text.Json.Serialization> espacio de nombres contiene atributos y API para escenarios avanzados y personalización específica de la serialización y deserialización. Por lo tanto, los ejemplos de código que se muestran en este artículo requieren una `using` o las dos directivas siguientes:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Los atributos del <xref:System.Runtime.Serialization> espacio de nombres no se `System.Text.Json`admiten actualmente en.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Cómo escribir objetos .NET en JSON (Serialize)

Para escribir JSON en una cadena, llame <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> al método. En el ejemplo siguiente se usa una sobrecarga con un parámetro de tipo genérico:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

Puede omitir el parámetro de tipo genérico y usar la inferencia de tipo genérico en su lugar:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

Este es un tipo de ejemplo que se va a serializar, que contiene colecciones y clases anidadas:

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

De forma predeterminada, la salida JSON es reducida: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, con la impresión en blanco y sangría):

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

Las sobrecargas <xref:System.Text.Json.JsonSerializer.Serialize%2A> de permiten la serialización <xref:System.IO.Stream>en un. Hay disponibles versiones asincrónicas de las `Stream` sobrecargas.

### <a name="serialize-to-utf-8"></a>Serializar a UTF-8

Para serializar a UTF-8, llame <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> al método:

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

Como alternativa, hay disponible <xref:System.Text.Json.JsonSerializer.Serialize%2A> una sobrecarga que toma <xref:System.Text.Json.Utf8JsonWriter> un.

La serialización a UTF-8 es aproximadamente 5-10% más rápida que el uso de métodos basados en cadenas. La diferencia se debe a que no es necesario convertir los bytes (como UTF-8) en cadenas (UTF-16).

## <a name="serialization-behavior"></a>Comportamiento de serialización

* De forma predeterminada, se serializan todas las propiedades públicas. Puede [especificar las propiedades que se van a excluir](#exclude-properties).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa los caracteres que no son ASCII, los caracteres que distinguen el código html dentro del intervalo ASCII y los caracteres que se deben escapar según [la especificación JSON](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON es reducida. Puede [imprimir el archivo JSON](#serialize-to-formatted-json).
* De forma predeterminada, las mayúsculas y minúsculas de los nombres JSON coinciden con los nombres .NET. Puede [personalizar el uso de mayúsculas y minúsculas del nombre JSON](#customize-json-names).
* Se detectan las referencias circulares y se inician las excepciones. Para obtener más información, consulte el [problema sobre las referencias circulares](https://github.com/dotnet/corefx/issues/38579) en el repositorio dotnet/Corefx en github.
* Actualmente, se excluyen los campos.

Los tipos admitidos son:

* Primitivas de .NET que se asignan a primitivos de JavaScript, como tipos numéricos, cadenas y booleanos.
* [Objetos CLR antiguos sin formato](https://stackoverflow.com/questions/250001/poco-definition)definidos por el usuario (poco).
* Matrices unidimensionales y escalonadas (`ArrayName[][]`).
* `Dictionary<string,TValue>`donde `TValue` es `object` ,`JsonElement`o un poco.
* Colecciones de los siguientes espacios de nombres. Para obtener más información, consulte el [tema sobre la compatibilidad con colecciones](https://github.com/dotnet/corefx/issues/36643) en el repositorio dotnet/Corefx en github.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Cómo leer JSON en objetos .NET (deserializar)

Para deserializar a partir de una cadena, <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> llame al método, tal y como se muestra en el ejemplo siguiente:

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Para obtener un ejemplo, vea la sección [Serialize](#how-to-write-net-objects-to-json-serialize) . El objeto JSON y .NET son los mismos, pero la dirección se invierte.

Las sobrecargas <xref:System.Text.Json.JsonSerializer.Deserialize*> de permiten la deserialización desde `Stream`un.  Hay disponibles versiones asincrónicas de las `Stream` sobrecargas.

### <a name="deserialize-from-utf-8"></a>Deserializar desde UTF-8

Para deserializar desde UTF-8, llame a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> una sobrecarga que `Utf8JsonReader` tome o `ReadOnlySpan<byte>`, tal y como se muestra en los ejemplos siguientes:

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

## <a name="deserialization-behavior"></a>Comportamiento de la deserialización

* De forma predeterminada, la coincidencia de nombres de propiedad distingue mayúsculas de minúsculas. Puede [especificar la distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.
* No se admite la deserialización a objetos inmutables o a propiedades de solo lectura. Para obtener más información, vea el [problema de github sobre la compatibilidad con objetos inmutables](https://github.com/dotnet/corefx/issues/38569) y el [problema en la compatibilidad con propiedades de solo lectura](https://github.com/dotnet/corefx/issues/38163) en el repositorio dotnet/corefx en github.
* De forma predeterminada, las enumeraciones se admiten como números.
* No se admiten los campos.
* De forma predeterminada, los comentarios o las comas finales en el JSON producen excepciones. Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas) si es necesario.
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

## <a name="serialize-to-formatted-json"></a>Serializar en JSON con formato

Para imprimir la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en: `true`

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Este es un tipo de ejemplo que se va a serializar y a la salida JSON:

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

## <a name="allow-comments-and-trailing-commas"></a>Permitir comentarios y comas finales

De forma predeterminada, los comentarios y las comas finales no se permiten en JSON. Para permitir comentarios en JSON, establezca la <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> propiedad en. `JsonCommentHandling.Skip` Y para permitir las comas finales, establezca la <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> propiedad en `true`. En el ejemplo siguiente se muestra cómo permitir ambos:

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Este es un ejemplo de JSON con comentarios y una coma final:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a>Personalización de nombres JSON

De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, incluido Case. En esta sección se explica cómo:

* Personalizar nombres de propiedad individuales
* Convertir todos los nombres de propiedad en mayúsculas y minúsculas Camel
* Implementar una directiva de nomenclatura de propiedades personalizadas
* Convertir claves de diccionario en mayúsculas y minúsculas Camel

Actualmente, no se admite la conversión automática de las enumeraciones en mayúsculas y minúsculas Camel. Para obtener más información, vea el [problema en la compatibilidad con las mayúsculas y minúsculas Camel](https://github.com/dotnet/corefx/issues/37725) en el repositorio dotnet/Corefx en github.

### <a name="customize-individual-property-names"></a>Personalizar nombres de propiedad individuales

Para establecer el nombre de las propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Este es un tipo de ejemplo para serializar y JSON resultante:

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

El nombre de propiedad establecido por este atributo:

* Se aplica en ambas direcciones, para la serialización y deserialización.
* Tiene prioridad sobre las directivas de nomenclatura de propiedades.

### <a name="use-camel-case-for-all-json-property-names"></a>Usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON

Para usar mayúsculas y minúsculas Camel en todos los <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> nombres `JsonNamingPolicy.CamelCase`de propiedad JSON, establezca en, como se muestra en el ejemplo siguiente:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

A continuación se muestra una clase de ejemplo para serializar y la salida JSON:

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

La Directiva de nomenclatura de la propiedad Case Camel:

* Se aplica a la serialización y deserialización.
* Se reemplaza por `[JsonPropertyName]` los atributos.

### <a name="use-a-custom-json-property-naming-policy"></a>Usar una directiva de nomenclatura de propiedades JSON personalizada

Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive <xref:System.Text.Json.JsonNamingPolicy> de e invalide el <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> método, como se muestra en el ejemplo siguiente:

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

Después, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> la propiedad en una instancia de la clase de directiva de nomenclatura:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

A continuación se muestra una clase de ejemplo para serializar y la salida JSON:

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

La Directiva de nomenclatura de propiedades JSON:

* Se aplica a la serialización y deserialización.
* Se reemplaza por `[JsonPropertyName]` los atributos.

### <a name="camel-case-dictionary-keys"></a>Claves de Diccionario de mayúsculas y minúsculas Camel

Si una propiedad de un objeto que se va a serializar es `Dictionary<string,TValue>`de tipo `string` , las claves se pueden convertir a mayúsculas y minúsculas Camel. Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:

|Propiedad |Valor  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| Resumen| Conexión|
| TemperatureRanges | Frío, 20<br>En caliente, 40|

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

La Directiva de nomenclatura de mayúsculas y minúsculas Camel se aplica solo a la serialización.

## <a name="exclude-properties"></a>Propiedades de exclusión

De forma predeterminada, se serializan todas las propiedades públicas. Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones. En esta sección se explica cómo excluir:

* Propiedades individuales
* Todas las propiedades de solo lectura
* Todas las propiedades de valores NULL 

### <a name="exclude-individual-properties"></a>Excluir propiedades individuales

Para omitir las propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Este es un tipo de ejemplo para serializar y la salida JSON:

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

### <a name="exclude-all-read-only-properties"></a>Excluir todas las propiedades de solo lectura

Para excluir todas las propiedades de solo lectura, <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> establezca `true`en, como se muestra en el ejemplo siguiente:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Este es un tipo de ejemplo para serializar y la salida JSON:

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

Esta opción solo se aplica a la serialización. Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada. Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público.

### <a name="exclude-all-null-value-properties"></a>Excluir todas las propiedades de valores NULL

Para excluir todas las propiedades de valores NULL <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> , establezca `true`la propiedad en, como se muestra en el ejemplo siguiente:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:

|Propiedad |Value  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| Resumen| nulo|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

Esta configuración se aplica a la serialización y deserialización. Durante la deserialización, los valores NULL de JSON solo se omiten si son válidos. Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones. Para obtener más información, vea el [problema en los tipos de valor que no aceptan valores NULL](https://github.com/dotnet/corefx/issues/40922) en el repositorio dotnet/Corefx en github.

## <a name="case-insensitive-property-matching"></a>Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas

De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingue entre mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino. Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en: `true`

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

Este es un ejemplo de JSON con nombres de propiedad Case Camel. Se puede deserializar en el tipo siguiente que tenga nombres de propiedades de mayúsculas y minúsculas Pascal.

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

## <a name="include-properties-of-derived-classes"></a>Incluir propiedades de clases derivadas

No se admite la serialización polimórfica cuando se especifica en tiempo de compilación el tipo que se va a serializar. Por ejemplo, supongamos que `WeatherForecast` tiene una clase y una `WeatherForecastWithWind`clase derivada:

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

Y Supongamos que el tipo pasado a, o deducido por `Serialize` , el método en tiempo `WeatherForecast`de compilación es:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

En este escenario, la `WindSpeed` propiedad no se serializa aunque el `weatherForecast` objeto sea realmente un `WeatherForecastWithWind` objeto. Solo se serializan las propiedades de la clase base:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.

Para serializar las propiedades del tipo derivado, use uno de los métodos siguientes:

* Llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> de que le permita especificar el tipo en tiempo de ejecución:

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* Declare el objeto que se va a `object`serializar como.

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

En el escenario de ejemplo anterior, ambos enfoques hacen `WindSpeed` que la propiedad se incluya en la salida JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a>JSON de desbordamiento de control

Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino. Por ejemplo, supongamos que el tipo de destino es:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Y el JSON que se va a deserializar es el siguiente:

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

Si deserializa el JSON que se muestra en el tipo que se muestra `DatesAvailable` , `SummaryWords` las propiedades y no tienen ninguna que ir y se pierden. Para capturar datos adicionales, como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:

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

Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares `ExtensionData` de clave y valor de la propiedad:

|Propiedad |Valor  |Notas  |
|---------|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureC| 0 | No coinciden las mayúsculas y minúsculas (`temperatureC` en JSON), por lo que no se establece la propiedad. |
| Resumen | Conexión ||
| Extensiondata ( | temperatureC: 25 |Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.|
| |SummaryWords:<br>Geniales<br>Viento<br>Húmeda |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.|

Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON del mismo modo que en el JSON entrante:

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

Observe que el `ExtensionData` nombre de la propiedad no aparece en el archivo JSON. Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que no se pudiera deserializar.

## <a name="use-utf8jsonwriter-directly"></a>Usar Utf8JsonWriter directamente

En el ejemplo siguiente se muestra cómo usar <xref:System.Text.Json.Utf8JsonWriter> la clase directamente.

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

## <a name="use-utf8jsonreader-directly"></a>Usar Utf8JsonReader directamente

En el ejemplo siguiente se muestra cómo usar <xref:System.Text.Json.Utf8JsonReader> la clase directamente. En el código se supone `jsonUtf8` que la variable es una matriz de bytes que contiene JSON válido, codificado como UTF-8.

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

## <a name="additional-resources"></a>Recursos adicionales

* [Información general de System. Text. JSON](system-text-json-overview.md)
* [Referencia de la API System. Text. JSON](xref:System.Text.Json)
* [Compatibilidad con DateTime y DateTimeOffset en System. Text. JSON](../datetime/system-text-json-support.md)
