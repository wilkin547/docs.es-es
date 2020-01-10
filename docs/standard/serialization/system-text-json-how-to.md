---
title: Cómo serializar y deserializar JSON mediante C# .net
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a9c690e736a08c729a4099d5e7a519ed17ec282c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705800"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>Cómo serializar y deserializar JSON en .NET

En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json> para serializar y deserializar a y desde notación de objetos JavaScript (JSON).

Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.net Core](/aspnet/core/).

La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir en la misma" el JSON (con sangría y espacio en blanco para la legibilidad humana). Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para esta configuración.

## <a name="namespaces"></a>Espacios de nombres de

El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales. El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos y API para escenarios avanzados y personalización específicos de la serialización y deserialización. Los ejemplos de código que se muestran en este artículo requieren directivas de `using` para uno o ambos espacios de nombres:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten actualmente en `System.Text.Json`.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Cómo escribir objetos .NET en JSON (Serialize)

Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se crea JSON como una cadena:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando. Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Ejemplo de serialización

A continuación se muestra una clase de ejemplo que contiene colecciones y una clase anidada:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente. De forma predeterminada, la salida JSON es reducida: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

En el ejemplo siguiente se muestra el mismo JSON, con formato (es decir, con la impresión en blanco y sangría):

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

### <a name="serialize-to-utf-8"></a>Serializar a UTF-8

Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma <xref:System.Text.Json.Utf8JsonWriter>.

La serialización a UTF-8 es aproximadamente 5-10% más rápida que el uso de métodos basados en cadenas. La diferencia se debe a que no es necesario convertir los bytes (como UTF-8) en cadenas (UTF-16).

## <a name="serialization-behavior"></a>Comportamiento de serialización

* De forma predeterminada, se serializan todas las propiedades públicas. Puede [especificar las propiedades que se van a excluir](#exclude-properties-from-serialization).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa los caracteres que no son ASCII, los caracteres que distinguen el código html dentro del intervalo ASCII y los caracteres que se deben escapar según [la especificación JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON es reducida. Puede [imprimir el archivo JSON](#serialize-to-formatted-json).
* De forma predeterminada, las mayúsculas y minúsculas de los nombres JSON coinciden con los nombres .NET. Puede [personalizar el uso de mayúsculas y minúsculas del nombre JSON](#customize-json-names-and-values).
* Se detectan las referencias circulares y se inician las excepciones. Para obtener más información, consulte el [problema 38579 sobre referencias circulares](https://github.com/dotnet/corefx/issues/38579) en el repositorio dotnet/Corefx en github.
* Actualmente, se excluyen los campos.

Los tipos admitidos son:

* Primitivas de .NET que se asignan a primitivos de JavaScript, como tipos numéricos, cadenas y booleanos.
* [Objetos CLR antiguos sin formato](https://stackoverflow.com/questions/250001/poco-definition)definidos por el usuario (poco).
* Matrices unidimensionales y escalonadas (`ArrayName[][]`).
* `Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement`o POCO.
* Colecciones de los siguientes espacios de nombres. Para obtener más información, consulte el [tema sobre la compatibilidad con colecciones](https://github.com/dotnet/corefx/issues/36643) en el repositorio dotnet/Corefx en github.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Cómo leer JSON en objetos .NET (deserializar)

Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecast` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Deserializar desde UTF-8

Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que toma un `Utf8JsonReader` o un `ReadOnlySpan<byte>`, como se muestra en los ejemplos siguientes. En los ejemplos se da por supuesto que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Comportamiento de la deserialización

* De forma predeterminada, la coincidencia de nombres de propiedad distingue mayúsculas de minúsculas. Puede [especificar la distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* No se admite la deserialización a tipos de referencia sin un constructor sin parámetros.
* No se admite la deserialización a objetos inmutables o a propiedades de solo lectura. Para obtener más información, consulte el [problema de GitHub 38569 en compatibilidad con objetos inmutables](https://github.com/dotnet/corefx/issues/38569) y el [problema 38163 en la compatibilidad con propiedades de solo lectura](https://github.com/dotnet/corefx/issues/38163) en el repositorio dotnet/corefx en github.
* De forma predeterminada, las enumeraciones se admiten como números. Puede [serializar los nombres de enumeración como cadenas](#enums-as-strings).
* No se admiten los campos.
* De forma predeterminada, los comentarios o las comas finales en el JSON producen excepciones. Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar una funcionalidad que no sea compatible con los convertidores integrados.

## <a name="serialize-to-formatted-json"></a>Serializar en JSON con formato

Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

A continuación se muestra un tipo de ejemplo que se va a serializar y a la salida de JSON impresa:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Personalización de nombres y valores de JSON

De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, incluido Case. Los valores de enumeración se representan como números. En esta sección se explica cómo:

* [Personalizar nombres de propiedad individuales](#customize-individual-property-names)
* [Convertir todos los nombres de propiedad en mayúsculas y minúsculas Camel](#use-camel-case-for-all-json-property-names)
* [Implementar una directiva de nomenclatura de propiedades personalizadas](#use-a-custom-json-property-naming-policy)
* [Convertir claves de diccionario en mayúsculas y minúsculas Camel](#camel-case-dictionary-keys)
* [Convertir enumeraciones en cadenas y Case Camel](#enums-as-strings) 

En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Personalizar nombres de propiedad individuales

Para establecer el nombre de las propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Este es un tipo de ejemplo para serializar y JSON resultante:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

El nombre de propiedad establecido por este atributo:

* Se aplica en ambas direcciones, para la serialización y deserialización.
* Tiene prioridad sobre las directivas de nomenclatura de propiedades.

### <a name="use-camel-case-for-all-json-property-names"></a>Usar mayúsculas y minúsculas Camel para todos los nombres de propiedad JSON

Para usar mayúsculas y minúsculas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

A continuación se muestra una clase de ejemplo para serializar y la salida JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

La Directiva de nomenclatura de la propiedad Case Camel:

* Se aplica a la serialización y deserialización.
* Está invalidado por `[JsonPropertyName]` atributos. Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no es mayúsculas y minúsculas Camel.

### <a name="use-a-custom-json-property-naming-policy"></a>Usar una directiva de nomenclatura de propiedades JSON personalizada

Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

A continuación, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

A continuación se muestra una clase de ejemplo para serializar y la salida JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

La Directiva de nomenclatura de propiedades JSON:

* Se aplica a la serialización y deserialización.
* Está invalidado por `[JsonPropertyName]` atributos. Este es el motivo por el que el nombre de la propiedad JSON `Wind` en el ejemplo no está en mayúsculas.

### <a name="camel-case-dictionary-keys"></a>Claves de Diccionario de mayúsculas y minúsculas Camel

Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, las claves de `string` se pueden convertir a mayúsculas y minúsculas Camel. Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tiene pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` daría como resultado una salida JSON similar a la del ejemplo siguiente:

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

La Directiva de nomenclatura de mayúsculas y minúsculas Camel de las claves de diccionario se aplica solo a la serialización. Si se deserializa un diccionario, las claves coincidirán con el archivo JSON incluso si se especifica `JsonNamingPolicy.CamelCase` para la `DictionaryKeyPolicy`.

### <a name="enums-as-strings"></a>Enumeraciones como cadenas

De forma predeterminada, las enumeraciones se serializan como números. Para serializar los nombres de enumeración como cadenas, use el <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Por ejemplo, supongamos que necesita serializar la siguiente clase que tiene una enumeración:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Si el resumen es `Hot`, de forma predeterminada, el JSON serializado tiene el valor numérico 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y se convierten los nombres en mayúsculas y minúsculas Camel:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

El JSON resultante es similar al ejemplo siguiente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Los nombres de cadena de enumeración también se pueden deserializar, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Excluir propiedades de la serialización

De forma predeterminada, se serializan todas las propiedades públicas. Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones. En esta sección se explica cómo excluir:

* [Propiedades individuales](#exclude-individual-properties)
* [Todas las propiedades de solo lectura](#exclude-all-read-only-properties)
* [Todas las propiedades de valores NULL](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Excluir propiedades individuales

Para omitir las propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Este es un tipo de ejemplo para serializar y la salida JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Excluir todas las propiedades de solo lectura

Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público. Para excluir todas las propiedades de solo lectura, establezca el <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Este es un tipo de ejemplo para serializar y la salida JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Esta opción solo se aplica a la serialización. Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.

### <a name="exclude-all-null-value-properties"></a>Excluir todas las propiedades de valores NULL

Para excluir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

A continuación se muestra un ejemplo de un objeto para serializar y la salida JSON:

|La propiedad |{2&gt;Value&lt;2}  |
|---------|---------|
| Fecha    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureCelsius| 25 |
| Resumen| nulo|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Esta configuración se aplica a la serialización y deserialización. Para obtener información sobre su efecto en la deserialización, vea [omitir null al deserializar](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Personalizar la codificación de caracteres

De forma predeterminada, el serializador convierte todos los caracteres que no sean ASCII.  Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.  Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serializar juegos de caracteres de idioma

Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique los [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Este código no escapa ni caracteres griegos. Si la propiedad `Summary` está establecida en cirílico жарко, el objeto de `WeatherForecast` se serializa como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Para serializar todos los conjuntos de lenguaje sin escape, utilice <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Serializar caracteres específicos

Una alternativa consiste en especificar caracteres individuales que desea permitir a través de sin caracteres de escape. En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Este es un ejemplo de JSON generado por el código anterior:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Serializar todos los caracteres

Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo para permitir que los caracteres pasen a través de sin escape:
>
> * No se convierten en caracteres que no tengan en cuenta los caracteres de HTML, como `<`, `>`, `&`y `'`.
> * No ofrece ninguna protección adicional en profundidad frente a ataques de divulgación de información o XSS, como los que pueden ser el resultado de que el cliente y el servidor no acepten el *juego de caracteres*.
>
> Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8. Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`. Nunca permita que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.

## <a name="serialize-properties-of-derived-classes"></a>Serializar propiedades de clases derivadas

No se admite la serialización polimórfica cuando se especifica en tiempo de compilación el tipo que se va a serializar. Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Y Supongamos que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea realmente un objeto `WeatherForecastDerived`. Solo se serializan las propiedades de la clase base:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.

Para serializar las propiedades del tipo derivado, use uno de los métodos siguientes:

* Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Declare el objeto que se va a serializar como `object`.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

Para obtener información acerca de la deserialización polimórfica, consulte [compatibilidad con la deserialización polimórfica](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

## <a name="allow-comments-and-trailing-commas"></a>Permitir comentarios y comas finales

De forma predeterminada, los comentarios y las comas finales no se permiten en JSON. Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.
Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`. En el ejemplo siguiente se muestra cómo permitir ambos:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Este es un ejemplo de JSON con comentarios y una coma final:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas

De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingue entre mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino. Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Este es un ejemplo de JSON con nombres de propiedad Case Camel. Se puede deserializar en el tipo siguiente que tenga nombres de propiedades de mayúsculas y minúsculas Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>JSON de desbordamiento de control

Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino. Por ejemplo, supongamos que el tipo de destino es:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Y el JSON que se va a deserializar es el siguiente:

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

Si deserializa el JSON que se muestra en el tipo que se muestra, las propiedades `DatesAvailable` y `SummaryWords` no tienen ninguna que ir y se pierden. Para capturar datos adicionales, como estas propiedades, aplique el atributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares de clave y valor de la propiedad `ExtensionData`:

|La propiedad |{2&gt;Value&lt;2}  |Notas  |
|---------|---------|---------|
| Fecha    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureCelsius| 0 | No coinciden las mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad. |
| Resumen | Caliente ||
| Extensiondata ( | temperatureCelsius: 25 |Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.|
| |SummaryWords:<br>Geniales<br>Viento<br>Húmeda |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como el objeto de valor.|

Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON del mismo modo que en el JSON entrante:

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

Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON. Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que no se pudiera deserializar.

## <a name="ignore-null-when-deserializing"></a>Omitir null al deserializar

De forma predeterminada, si una propiedad en JSON es null, la propiedad correspondiente en el objeto de destino se establece en NULL. En algunos escenarios, la propiedad de destino podría tener un valor predeterminado y no desea que un valor null invalide el valor predeterminado.

Por ejemplo, supongamos que el código siguiente representa el objeto de destino:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Y Supongamos que se deserializa el siguiente JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Después de la deserialización, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es NULL.

Para cambiar este comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Con esta opción, la propiedad `Summary` del objeto `WeatherForecastWithDefault` es el valor predeterminado "no Summary" después de la deserialización.

Los valores NULL en JSON solo se omiten si son válidos. Los valores NULL para los tipos de valor que no aceptan valores NULL provocan excepciones. Para obtener más información, consulte el [problema 40922 en los tipos de valor que no aceptan valores NULL](https://github.com/dotnet/corefx/issues/40922) en el repositorio dotnet/Corefx en github.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter y JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`. El `Utf8JsonReader` es un tipo de nivel bajo que se puede utilizar para crear analizadores y deserializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> es una forma de alto rendimiento de escribir texto JSON con codificación UTF-8 de tipos comunes de .NET como `String`, `Int32`y `DateTime`. El escritor es un tipo de nivel bajo que se puede utilizar para crear serializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> proporciona la capacidad de crear un Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`. DOM proporciona acceso aleatorio a los datos en una carga JSON. Se puede tener acceso a los elementos JSON que componen la carga a través del tipo de <xref:System.Text.Json.JsonElement>. El tipo de `JsonElement` proporciona enumeradores de matriz y de objeto junto con las API para convertir texto JSON en tipos comunes de .NET. `JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.

En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Usar JsonDocument para el acceso a los datos

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

El código anterior:

* Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.
* Calcula la media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`. 
* Asigna un nivel predeterminado de 70 a los estudiantes que no tienen una calificación.
* Cuenta a los estudiantes incrementando una variable de `count` con cada iteración. Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, como se muestra en el ejemplo siguiente:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Este es un ejemplo del código JSON que este código procesa:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Uso de JsonDocument para escribir JSON

En el ejemplo siguiente se muestra cómo escribir JSON desde un <xref:System.Text.Json.JsonDocument>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

El código anterior:

* Lee un archivo JSON, carga los datos en un `JsonDocument`y escribe JSON con formato (impreso) en un archivo.
* Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.
* Cuando termine, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor. Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina. 

A continuación se muestra un ejemplo de entrada JSON que se va a procesar mediante el código de ejemplo:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

El resultado es la siguiente salida JSON impresa:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Usar Utf8JsonWriter

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonWriter>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Usar Utf8JsonReader

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.Utf8JsonReader>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, codificado como UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Filtrar datos mediante Utf8JsonReader

En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

El código anterior:

* Supone que el archivo está codificado como UTF-16 y lo transcodifica en UTF-8. Un archivo codificado como UTF-8 puede leerse directamente en un `ReadOnlySpan<byte>`, mediante el código siguiente:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "Name" de tipo cadena.
* Cuenta los objetos y `name` valores de propiedad que terminan en "University".

A continuación se muestra un ejemplo de JSON que el código anterior puede leer. El mensaje de Resumen resultante es "2 de 4 nombres que terminan con" Universidad "":

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>Recursos adicionales

* [Información general de System. Text. JSON](system-text-json-overview.md)
* [Referencia de la API System. Text. JSON](xref:System.Text.Json)
* [Escritura de convertidores personalizados para System. Text. JSON](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset en System. Text. JSON](../datetime/system-text-json-support.md)
* [Problemas de GitHub en el repositorio dotnet/corefx con la etiqueta JSON-Functional-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
