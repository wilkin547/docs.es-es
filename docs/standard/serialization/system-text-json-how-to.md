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
ms.openlocfilehash: aba45a99562b67df17e1ff33ecc3c8bbad63ec30
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440821"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET

En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json?displayProperty=fullName> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON). Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).

La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad). Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.

Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a>Espacios de nombres

El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales. El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización. Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten en `System.Text.Json`.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Procedimiento para escribir objetos .NET en JSON (serializar)

Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se crea un archivo JSON como cadena:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando. Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Ejemplo de serialización

A continuación se muestra una clase de ejemplo que contiene propiedades de tipo de colección y un tipo definido por el usuario:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> "POCO" significa [objeto CRL estándar](https://en.wikipedia.org/wiki/Plain_old_CLR_object). Un POCO es un tipo de .NET que no depende de ningún tipo específico del marco, por ejemplo, a través de la herencia o atributos.

La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente. La salida JSON se minimiza de manera predeterminada:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

En el ejemplo siguiente se muestra el mismo JSON, pero con formato (es decir, impreso correctamente con espacio en blanco y sangría):

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

### <a name="serialize-to-utf-8"></a>Serialización a UTF-8

Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.

La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas. La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).

## <a name="serialization-behavior"></a>Comportamiento de serialización
::: zone pivot="dotnet-5-0"

* De manera predeterminada, se serializan todas las propiedades públicas. Puede [especificar propiedades para omitir](#ignore-properties).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON se minimiza. Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).
* De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET. Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).
* De manera predeterminada, se detectan las referencias circulares y se inician las excepciones. Puede [conservar las referencias y administrar las referencias circulares](#preserve-references-and-handle-circular-references).
* De forma predeterminada, se omiten los [campos](../../csharp/programming-guide/classes-and-structs/fields.md). Puede [incluir campos](#include-fields).

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* De manera predeterminada, se serializan todas las propiedades públicas. Puede [especificar propiedades para omitir](#ignore-properties).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON se minimiza. Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).
* De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET. Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](#customize-json-names-and-values).
* Se detectan las referencias circulares y se inician las excepciones.
* Los [campos](../../csharp/programming-guide/classes-and-structs/fields.md) se omiten.
::: zone-end

Los tipos no admitidos incluyen:
::: zone pivot="dotnet-5-0"

* Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.
* [Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.
* Matrices unidimensionales y escalonadas (`T[][]`).
* Colecciones y diccionarios de los siguientes espacios de nombres.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Elementos primitivos de .NET que se asignan a elementos primitivos de JavaScript, tales como tipos numéricos, cadenas y valores booleanos.
* [Objetos CLR estándar (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object) definidos por el usuario.
* Matrices unidimensionales y escalonadas (`ArrayName[][]`).
* `Dictionary<string,TValue>` donde `TValue` es `object`, `JsonElement` o un POCO.
* Colecciones de los espacios de nombres siguientes.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para controlar tipos adicionales o proporcionar funcionalidad que no admiten los convertidores integrados.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Procedimiento para leer JSON en objetos .NET (deserializar)

Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecastWithPOCOs` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Deserialización desde UTF-8

Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `Utf8JsonReader` o `ReadOnlySpan<byte>`, tal y como se muestra en el ejemplo siguiente. En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Comportamiento de la deserialización

Al deserializar JSON se aplican los comportamientos siguientes:

::: zone pivot="dotnet-5-0"

* De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas. Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* El serializador omite los constructores que no son públicos.
* No se admite la deserialización a objetos inmutables o propiedades de solo lectura. Vea [Tipos y registros inmutables](#immutable-types-and-records).
* De forma predeterminada, las enumeraciones se admiten como números. Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).
* De forma predeterminada, los campos se omiten. Puede [incluir campos](#include-fields).
* De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones. Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas. Puede [especificar la no distinción de mayúsculas y minúsculas](#case-insensitive-property-matching). Las aplicaciones de ASP.NET Core [especifican la no distinción de mayúsculas y minúsculas de forma predeterminada](#web-defaults-for-jsonserializeroptions).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* Para la deserialización se usa un constructor sin parámetros, que puede ser público, interno o privado.
* No se admite la deserialización a objetos inmutables o propiedades de solo lectura.
* De forma predeterminada, las enumeraciones se admiten como números. Puede [serializar nombres de enumeración como cadenas](#enums-as-strings).
* No se admiten los campos.
* De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones. Puede [permitir comentarios y comas finales](#allow-comments-and-trailing-commas).
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.

## <a name="serialize-to-formatted-json"></a>Serialización a JSON con formato

Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a>Inclusión de campos

::: zone pivot="dotnet-5-0"
Use el valor global <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> o el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos al serializar o deserializar, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

Para omitir los campos de solo lectura, use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los campos no se admiten en System.Text.Json en .NET Core 3.1. Los [convertidores personalizados](system-text-json-converters-how-to.md) pueden proporcionar esta funcionalidad.
::: zone-end

## <a name="customize-json-names-and-values"></a>Personalización de nombres y valores JSON

De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas. Los valores de enumeración se representan como números. En esta sección se explica cómo:

* [Personalizar nombres de propiedades individuales](#customize-individual-property-names)
* [Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel](#use-camel-case-for-all-json-property-names)
* [Implementar una directiva de nomenclatura de propiedades personalizada](#use-a-custom-json-property-naming-policy)
* [Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel](#camel-case-dictionary-keys)
* [Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel](#enums-as-strings)

En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Personalizar nombres de propiedades individuales

Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Nombre de propiedad establecido por este atributo:

* Se aplica en ambas direcciones, para la serialización y la deserialización.
* Tiene prioridad sobre las directivas de nomenclatura de propiedades.

### <a name="use-camel-case-for-all-json-property-names"></a>Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON

Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

La directiva de nomenclatura de propiedades en mayúsculas y minúsculas combinadas Camel:

* Se aplica a la serialización y deserialización.
* Se invalida con atributos `[JsonPropertyName]`. Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas y minúsculas combinadas Camel.

### <a name="use-a-custom-json-property-naming-policy"></a>Uso de una directiva de nomenclatura de propiedades JSON personalizada

Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

La directiva de nomenclatura de propiedades JSON personalizada:

* Se aplica a la serialización y la deserialización.
* Se invalida con atributos `[JsonPropertyName]`. Este es el motivo por el que el nombre de la propiedad JSON `Wind` del ejemplo no usa mayúsculas.

### <a name="camel-case-dictionary-keys"></a>Claves de diccionario en mayúsculas y minúsculas combinadas Camel

Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel. Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

La serialización de un objeto con un diccionario denominado `TemperatureRanges` que tenga pares clave-valor `"ColdMinTemp", 20` y `"HotMinTemp", 40` se traduciría en una salida JSON similar a la del ejemplo siguiente:

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

La directiva de nomenclatura en mayúsculas y minúsculas combinadas Camel para las claves de diccionario se aplica solo a la serialización. Si se deserializa un diccionario, las claves coincidirán con el archivo JSON aunque se especifique `JsonNamingPolicy.CamelCase` para `DictionaryKeyPolicy`.

### <a name="enums-as-strings"></a>Enumeraciones como cadenas

De forma predeterminada, las enumeraciones se serializan como números. Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

El JSON resultante tendrá un aspecto similar al siguiente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a>Omisión de propiedades

De manera predeterminada, se serializan todas las propiedades públicas. Si no quiere que algunas de ellas aparezcan en la salida JSON, tiene varias opciones. En esta sección se explica cómo omitir:

::: zone pivot="dotnet-5-0"

* [Propiedades individuales](#ignore-individual-properties)
* [Todas las propiedades de solo lectura](#ignore-all-read-only-properties)
* [Todas las propiedades de valores NULL](#ignore-all-null-value-properties)
* [Todas las propiedades de valor predeterminado](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [Propiedades individuales](#ignore-individual-properties)
* [Todas las propiedades de solo lectura](#ignore-all-read-only-properties)
* [Todas las propiedades de valores NULL](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a>Omisión de propiedades individuales

Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
Puede especificar la exclusión condicional estableciendo la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute). La enumeración <xref:System.Text.Json.Serialization.JsonIgnoreCondition> proporciona las siguientes opciones:

* `Always` - La propiedad se omite siempre. Si no se especifica `Condition`, se presupone esta opción.
* `Never` - La propiedad siempre se serializa y deserializa, independientemente de la configuración global de `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` y `IgnoreReadOnlyFields`.
* `WhenWritingDefault` - La propiedad se omite en la serialización si es un tipo de referencia `null` o un tipo de valor `default`.
* `WhenWritingNull` - La propiedad se omite en la serialización si es un tipo de referencia `null`.

En el ejemplo siguiente se muestra el uso de la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a>Omisión de todas las propiedades de solo lectura

Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público. Para omitir todas las propiedades de solo lectura durante la serialización, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Esta opción solo se aplica a la serialización. Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.

::: zone pivot="dotnet-5-0"
Esta opción solo se aplica a las propiedades. Para omitir los campos de solo lectura al [serializar campos](#include-fields), use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

### <a name="ignore-all-null-value-properties"></a>Omisión de todas las propiedades de valores NULL

::: zone pivot="dotnet-5-0"
Para omitir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
Para omitir todas las propiedades de valores NULL al serializar, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:

|Propiedad. |Value  |
|---------|---------|
| Fecha    | 1/8/2019 12:00 -07:00|
| TemperatureCelsius| 25 |
| Resumen| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a>Omisión de todas las propiedades de valor predeterminado

::: zone pivot="dotnet-5-0"
Para evitar la serialización de valores predeterminados en las propiedades de tipo de valor, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

El valor `WhenWritingDefault` también evita la serialización de propiedades de tipo de referencia de valor NULL.

::: zone pivot="dotnet-core-3-1"
No hay ninguna manera integrada de evitar la serialización de propiedades con valores predeterminados de tipos de valor en System.Text.Json en .NET Core 3.1.
::: zone-end

## <a name="customize-character-encoding"></a>Personalización de la codificación de caracteres

De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.  Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.  Por ejemplo, si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serialización de juegos de caracteres de idioma

Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Este código no escapa a los caracteres cirílicos o griegos. Si la propiedad `Summary` está establecida en cirílico жарко, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Serialización de caracteres específicos

Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape. En el ejemplo siguiente se serializan solo los dos primeros caracteres de жарко:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Aquí se muestra un ejemplo de JSON producido por el código anterior:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Serialización de todos los caracteres

Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:
>
> * No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.
> * No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.
>
> Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8. Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`. No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.

## <a name="serialize-properties-of-derived-classes"></a>Serialización de propiedades de clases derivadas

No se admite la serialización de una jerarquía de tipos polimórficos. Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales. Las excepciones a este comportamiento se explican en esta sección.

Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

En este escenario, la propiedad `WindSpeed` no se serializa aunque el objeto `weatherForecast` sea en realidad un objeto `WeatherForecastDerived`. Solo se serializan las propiedades de la clase base:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Este comportamiento está diseñado para ayudar a evitar la exposición accidental de datos en un tipo derivado creado en tiempo de ejecución.

Para serializar las propiedades del tipo derivado del ejemplo anterior, use uno de los enfoques siguientes:

* Llame a una sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que le permita especificar el tipo en tiempo de ejecución:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Declare el objeto que se va a serializar como `object`.

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

En el escenario de ejemplo anterior, ambos enfoques hacen que la propiedad `WindSpeed` se incluya en la salida JSON:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Estos enfoques proporcionan serialización polimórfica solo para el objeto raíz que se va a serializar, no para las propiedades de dicho objeto raíz.

Puede obtener una serialización polimórfica para objetos de nivel inferior si se definen como tipo `object`. Por ejemplo, supongamos que la clase `WeatherForecast` tiene una propiedad denominada `PreviousForecast` que se puede definir como tipo `WeatherForecast` o `object`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:

* La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.
* La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.

Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado. En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

El código anterior serializa correctamente `WeatherForecastWithPreviousAsObject`:

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

El mismo enfoque para definir propiedades como `object` funciona con interfaces. Supongamos que tiene la interfaz y la implementación siguientes, y quiere serializar una clase con propiedades que contienen instancias de implementación:

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

En el ejemplo de código siguiente se muestra el JSON resultante del código anterior:

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

Para obtener más información sobre la **serialización**  polimórfica e información sobre la **deserialización**, consulte [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="allow-comments-and-trailing-commas"></a>Autorización de comentarios y comas finales

De forma predeterminada, los comentarios y las comas finales no se permiten en JSON. Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.
Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`. En el siguiente ejemplo se muestra cómo permitirlos ambos:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Aquí se muestra un ejemplo de JSON con comentarios y una coma final:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas

De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino. Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel. Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>JSON de desbordamiento de control

Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino. Por ejemplo, supongamos que el tipo de destino es el siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

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

Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden. Para capturar datos adicionales tales como estas propiedades, aplique el atributo [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:

|Propiedad. |Value  |Notas  |
|---------|---------|---------|
| Fecha    | 1/8/2019 12:00 -07:00||
| TemperatureCelsius| 0 | Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad. |
| Resumen | Acceso frecuente ||
| ExtensionData | temperatureCelsius: 25 |Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.|
|| DatesAvailable:<br>  1/8/2019 12:00 -07:00<br>2/8/2019 12:00 -07:00 |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.|
| |SummaryWords:<br>Geniales<br>Viento<br>Húmedo |La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.|

Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:

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

Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON. Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.

## <a name="preserve-references-and-handle-circular-references"></a>Conservación de las referencias y administración de las referencias circulares

::: zone pivot="dotnet-5-0"

Para conservar las referencias y administrar las referencias circulares, establezca <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> en <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>. Este valor produce el comportamiento siguiente:

* Al serializar:

  Al escribir tipos complejos, el serializador también escribe propiedades de metadatos (`$id`, `$values` y `$ref`).

* Al deserializar:

  Se esperan metadatos (aunque no es obligatorio) y el deserializador intenta entenderlo.

En el siguiente código se muestra el uso del parámetro `Preserve`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Esta característica no se puede usar para conservar tipos de valor o tipos inmutables. En la deserialización, se crea la instancia de un tipo inmutable después de leer la carga completa. Por lo tanto, sería imposible deserializar la misma instancia si aparece una referencia a ella dentro de la carga de JSON.

En el caso de los tipos de valor, los tipos inmutables y las matrices, no se serializan los metadatos de referencia. En la deserialización, se produce una excepción si se encuentra `$ref` o `$id`. Sin embargo, los tipos de valor omiten `$id` (y `$values` en el caso de las colecciones) para que sea posible deserializar las cargas que se serializaron mediante Newtonsoft.Json.  Newtonsoft.Json serializa los metadatos de estos tipos.

Para determinar si los objetos son iguales, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, que usa la igualdad de referencia (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) en lugar de la igualdad de valores (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> cuando se comparan dos instancias de objeto.

Para obtener más información sobre cómo se serializan y deserializan las referencias, vea <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.

La clase <xref:System.Text.Json.Serialization.ReferenceResolver> define el comportamiento de conservar las referencias en la serialización y deserialización. Cree una clase derivada para especificar el comportamiento personalizado. Para obtener un ejemplo, vea [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json en .NET Core 3.1 solo admite la serialización por valor y produce una excepción para las referencias circulares.
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a>Permitir o escribir números entre comillas

::: zone pivot="dotnet-5-0"

Algunos serializadores codifican números como cadenas JSON (entre comillas). Por ejemplo, `{"DegreesCelsius":"23"}` en lugar de `{"DegreesCelsius":23}`. Para serializar los números entre comillas o aceptar números entre comillas en todo el gráfico del objeto de entrada, establezca <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

Cuando se usa System.Text.Json indirectamente a través de ASP.NET Core, se permiten números entre comillas al deserializar porque ASP.NET Core especifica [opciones predeterminadas web](xref:System.Text.Json.JsonSerializerDefaults.Web).

Para permitir o escribir números entre comillas para propiedades, campos o tipos específicos, use el atributo [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).
::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json en .NET Core 3.1 no admite la serialización o deserialización de números entre comillas. Para obtener más información, vea [Permitir o escribir números entre comillas](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).
::: zone-end

## <a name="immutable-types-and-records"></a>Tipos y registros inmutables

::: zone pivot="dotnet-5-0"
System.Text.Json puede utilizar un constructor con parámetros, lo que hace posible deserializar una clase o estructura inmutable. En el caso de una clase, si el único constructor está parametrizado, se utilizará ese constructor. En el caso de una estructura o una clase con varios constructores, especifique el que se va a usar aplicando el atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A). Cuando no se utiliza el atributo, siempre se usa un constructor sin parámetros público si está presente. El atributo solo se puede usar con constructores públicos. En el ejemplo siguiente se usa el atributo `[JsonConstructor]`:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

También se admiten registros en C# 9, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

En el caso de los tipos que son inmutables porque todos sus establecedores de propiedad son no públicos, vea la siguiente sección sobre [los descriptores de acceso de propiedad no públicos](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` y la compatibilidad con los registros en C# 9 no están disponibles en .NET Core 3.1.
::: zone-end

## <a name="non-public-property-accessors"></a>Descriptores de acceso de propiedad no públicos

::: zone pivot="dotnet-5-0"
Para habilitar el uso de un descriptor de acceso de propiedad no público, use el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los descriptores de acceso de propiedad no públicos no se admiten en .NET Core 3.1. Para obtener más información, consulte [el artículo de migración de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

## <a name="copy-jsonserializeroptions"></a>Copia de JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Hay un [constructor de JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) que le permite crear una nueva instancia de con las mismas opciones que una instancia existente, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Un constructor de `JsonSerializerOptions` que toma una instancia existente no está disponible en .NET Core 3.1.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Valores predeterminados web para JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Hay un [constructor de JsonSerializerOptions] (xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) que le permite crear una nueva instancia de con las opciones predeterminadas que ASP.NET Core utiliza para aplicaciones web, tal como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Un constructor de `JsonSerializerOptions` que especifica un conjunto de valores predeterminados no está disponible en .NET Core 3.1.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Métodos de extensión HttpClient y HttpContent

::: zone pivot="dotnet-5-0"

La serialización y deserialización de cargas JSON de la red son operaciones comunes. Los métodos de extensión de [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) y [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permiten realizar estas operaciones en una sola línea de código. Estos métodos de extensión usan [valores predeterminados web para JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).

En el siguiente ejemplo se muestra el uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

También hay métodos de extensión para System.Text.Json en [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los métodos de extensión de `HttpClient` y `HttpContent` no están disponibles en System.Text.Json en .NET Core 3.1.
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter y JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`. `Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`. El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`. La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON. A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>. El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes. `JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.

En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Uso de JsonDocument para acceder a datos

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

El código anterior:

* Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.
* Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.
* Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.
* Cuenta los alumnos incrementando una variable `count` con cada iteración. Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Aquí se muestra un ejemplo del código JSON que este código procesa:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Uso de JsonDocument para escribir JSON

En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

El código anterior:

* Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.
* Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.
* Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor. Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.

Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

El resultado es la siguiente salida JSON impresa correctamente:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Uso de Utf8JsonWriter

En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Uso de Utf8JsonReader

En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Filtrado de datos con Utf8JsonReader

En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

(Hay disponible una versión [asincrónica de este ejemplo](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs)).

El código anterior:

* Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.
* Cuenta los objetos y los valores de propiedad "name" que terminan en "University".
* Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8. Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto. De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.

Aquí se muestra un ejemplo de JSON que el código anterior puede leer. El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Lectura de una secuencia mediante Utf8JsonReader

Al leer un archivo grande (un gigabyte o más de tamaño, por ejemplo), puede que desee evitar tener que cargar todo el archivo en la memoria de una vez. En este escenario, puede usar <xref:System.IO.FileStream>.

Al usar `Utf8JsonReader` para leer de una secuencia, se aplican las siguientes reglas:

* El búfer que contiene la carga parcial JSON debe ser al menos tan grande como el token JSON más grande que contiene para que el lector pueda avanzar.
* El búfer debe ser al menos tan grande como la secuencia más grande de espacio en blanco dentro del JSON.
* El lector no realiza un seguimiento de los datos que ha leído hasta que lea completamente el <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> siguiente en la carga JSON. Por tanto, cuando haya bytes restantes en el búfer, tendrá que volver a pasarlos al lector. Puede usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar el número de bytes que quedan.

El código siguiente muestra cómo leer desde una secuencia. Este ejemplo se muestra <xref:System.IO.MemoryStream>. Un código similar funcionará con <xref:System.IO.FileStream>, excepto cuando `FileStream` contenga una marca BOM UTF-8 al principio. En ese caso, debe quitar esos tres bytes del búfer antes de pasar los bytes restantes a `Utf8JsonReader`. En caso contrario, el lector produciría una excepción, ya que la marca BOM no se considera una parte válida del JSON.

El código de ejemplo comienza con un búfer de 4 KB y duplica el tamaño del búfer cada vez que encuentra que el tamaño no es lo suficientemente grande como para ajustarse a un token JSON completo, lo que es necesario para que el lector realice el progreso de la carga de JSON. El ejemplo de JSON proporcionado en el fragmento de código desencadena un aumento del tamaño del búfer solo si se establece un tamaño de búfer inicial muy pequeño, por ejemplo, 10 bytes. Si establece el tamaño de búfer inicial en 10, las instrucciones `Console.WriteLine` muestran la causa y el efecto de los aumentos del tamaño del búfer. En el tamaño de búfer inicial de 4 KB, se muestra todo el JSON de ejemplo en cada `Console.WriteLine` y el tamaño del búfer nunca se debe aumentar.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

En el ejemplo anterior no se establece ningún límite para el tamaño del búfer. Si el tamaño del token es demasiado grande, se podría producir un error en el código con una excepción <xref:System.OutOfMemoryException>. Esto puede ocurrir si el archivo JSON contiene un token de aproximadamente 1 GB o más de tamaño, ya que la duplicación del tamaño de 1 GB da como resultado un tamaño demasiado grande para caber en un búfer de `int32`.

## <a name="additional-resources"></a>Recursos adicionales

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Procedimientos para escribir convertidores personalizados](system-text-json-converters-how-to.md)
* [Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
