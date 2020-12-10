---
title: 'Procedimiento para serializar y deserializar JSON con C#: .NET'
description: Obtenga información sobre cómo usar el espacio de nombres System.Text.Json para serializar y deserializar desde JSON en .NET. Incluye código de ejemplo.
ms.date: 11/30/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9ea9e2fef5ef66f2a5ff816168abfbd7b2e75276
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437671"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Procedimiento para serializar y deserializar (calcular referencias y resolver referencias) JSON en .NET

En este artículo se muestra cómo usar el espacio de nombres <xref:System.Text.Json?displayProperty=fullName> para serializar y deserializar a y desde la notación de objetos JavaScript (JSON). Si va a portar el código existente de `Newtonsoft.Json`, consulte [Procedimiento para migrar a `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

Las instrucciones y el código de ejemplo usan la biblioteca directamente, no a través de un marco como [ASP.NET Core](/aspnet/core/).

La mayor parte del código de ejemplo de la serialización establece <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true` para "imprimir correctamente" el JSON (con sangría y espacio en blanco para mayor legibilidad). Para su uso en producción, normalmente aceptaría el valor predeterminado de `false` para este valor.

Los ejemplos de código hacen referencia a la siguiente clase y sus variantes:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a>Espacios de nombres

El espacio de nombres <xref:System.Text.Json> contiene todos los puntos de entrada y los tipos principales. El espacio de nombres <xref:System.Text.Json.Serialization> contiene atributos e interfaces API para escenarios avanzados y personalización específicos de la serialización y deserialización. Los ejemplos de código que se muestran en este artículo requieren directivas `using` para uno o ambos espacios de nombres:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> Los atributos del espacio de nombres <xref:System.Runtime.Serialization> no se admiten en `System.Text.Json`.

## <a name="how-to-write-net-objects-as-json-serialize"></a>Escritura de objetos .NET como JSON (serializar)

Para escribir JSON en una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se crea un archivo JSON como cadena:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

En el ejemplo siguiente se usa código sincrónico para crear un archivo JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

En el ejemplo siguiente se usa código asincrónico para crear un archivo JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

En los ejemplos anteriores se usa la inferencia de tipos para el tipo que se está serializando. Una sobrecarga de `Serialize()` toma un parámetro de tipo genérico:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a>Ejemplo de serialización

A continuación se muestra una clase de ejemplo que contiene propiedades de tipo de colección y un tipo definido por el usuario:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> "POCO" significa [objeto CRL estándar](https://en.wikipedia.org/wiki/Plain_old_CLR_object). Un POCO es un tipo de .NET que no depende de ningún tipo específico del marco, por ejemplo, a través de la herencia o atributos.

La salida JSON de la serialización de una instancia del tipo anterior es similar al ejemplo siguiente. La salida JSON es reducida (se quitan los caracteres de espacio en blanco, sangría y nueva línea) de forma predeterminada:

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

## <a name="serialize-to-utf-8"></a>Serialización a UTF-8

Para serializar a UTF-8, llame al método <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

También está disponible una sobrecarga <xref:System.Text.Json.JsonSerializer.Serialize%2A> que toma un valor <xref:System.Text.Json.Utf8JsonWriter>.

La serialización a UTF-8 es aproximadamente un 5-10 % más rápida que el uso de métodos basados en cadenas. La diferencia se debe a que no hay que convertir los bytes (como UTF-8) en cadenas (UTF-16).

## <a name="serialization-behavior"></a>Comportamiento de serialización

::: zone pivot="dotnet-5-0"

* De manera predeterminada, se serializan todas las propiedades públicas. Puede [especificar propiedades para omitir](system-text-json-ignore-properties.md).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON se minimiza. Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).
* De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET. Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](system-text-json-customize-properties.md).
* De manera predeterminada, se detectan las referencias circulares y se inician las excepciones. Puede [conservar las referencias y administrar las referencias circulares](system-text-json-preserve-references.md).
* De forma predeterminada, se omiten los [campos](../../csharp/programming-guide/classes-and-structs/fields.md). Puede [incluir campos](#include-fields).

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* De manera predeterminada, se serializan todas las propiedades públicas. Puede [especificar propiedades para omitir](system-text-json-ignore-properties.md).
* El [codificador predeterminado](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa a caracteres que no son ASCII, caracteres que distinguen HTML en el intervalo ASCII y caracteres que deben escaparse según [la especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* De forma predeterminada, JSON se minimiza. Puede [imprimir correctamente el JSON](#serialize-to-formatted-json).
* De forma predeterminada, el uso de mayúsculas y minúsculas en los nombres JSON coincide con el de los nombres de .NET. Puede [personalizar el uso de mayúsculas y minúsculas e nombres JSON](system-text-json-customize-properties.md).
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

## <a name="how-to-read-json-as-net-objects-deserialize"></a>Lectura de JSON como objetos .NET (deserializar)

Para deserializar a partir de una cadena o un archivo, llame al método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se lee JSON desde una cadena y se crea una instancia de la clase `WeatherForecastWithPOCOs` mostrada anteriormente para el [ejemplo de serialización](#serialization-example):

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

Para deserializar a partir de un archivo mediante código sincrónico, lea el archivo en una cadena, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

Para deserializar a partir de un archivo mediante código asincrónico, llame al método <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a>Deserialización desde UTF-8

Para deserializar desde UTF-8, llame a una sobrecarga <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> que tome un valor `ReadOnlySpan<byte>` o `Utf8JsonReader`, tal y como se muestra en el ejemplo siguiente. En los ejemplos se presupone que el JSON está en una matriz de bytes denominada jsonUtf8Bytes.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a>Comportamiento de la deserialización

Al deserializar JSON se aplican los comportamientos siguientes:

::: zone pivot="dotnet-5-0"

* De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas. Puede [especificar la no distinción de mayúsculas y minúsculas](system-text-json-character-casing.md).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* El serializador omite los constructores que no son públicos.
* No se admite la deserialización a objetos inmutables o propiedades de solo lectura. Vea [Tipos y registros inmutables](system-text-json-immutability.md).
* De forma predeterminada, las enumeraciones se admiten como números. Puede [serializar nombres de enumeración como cadenas](system-text-json-customize-properties.md#enums-as-strings).
* De forma predeterminada, los campos se omiten. Puede [incluir campos](#include-fields).
* De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones. Puede [permitir comentarios y comas finales](system-text-json-invalid-json.md).
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* De forma predeterminada, la coincidencia de nombres de la propiedad distingue mayúsculas de minúsculas. Puede [especificar la no distinción de mayúsculas y minúsculas](system-text-json-character-casing.md). Las aplicaciones de ASP.NET Core [especifican la no distinción de mayúsculas y minúsculas de forma predeterminada](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
* Si el archivo JSON contiene un valor para una propiedad de solo lectura, el valor se omite y no se inicia ninguna excepción.
* Para la deserialización se usa un constructor sin parámetros, que puede ser público, interno o privado.
* No se admite la deserialización a objetos inmutables o propiedades de solo lectura.
* De forma predeterminada, las enumeraciones se admiten como números. Puede [serializar nombres de enumeración como cadenas](system-text-json-customize-properties.md#enums-as-strings).
* No se admiten los campos.
* De forma predeterminada, los comentarios o las comas finales en el JSON inician excepciones. Puede [permitir comentarios y comas finales](system-text-json-invalid-json.md).
* La [profundidad máxima predeterminada](xref:System.Text.Json.JsonReaderOptions.MaxDepth) es 64.

Cuando se usa System.Text.Json indirectamente en una aplicación ASP.NET Core, algunos comportamientos predeterminados son diferentes. Para obtener más información, vea [Valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

Puede [implementar convertidores personalizados](system-text-json-converters-how-to.md) para proporcionar funcionalidad que no admiten los convertidores integrados.

## <a name="serialize-to-formatted-json"></a>Serialización a JSON con formato

Para imprimir correctamente la salida JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> en `true`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

Aquí se muestra un tipo de ejemplo que se serializa y la salida de JSON impresa correctamente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

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

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

Para omitir los campos de solo lectura, use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los campos no se admiten en System.Text.Json en .NET Core 3.1. Los [convertidores personalizados](system-text-json-converters-how-to.md) pueden proporcionar esta funcionalidad.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Métodos de extensión HttpClient y HttpContent

::: zone pivot="dotnet-5-0"

La serialización y deserialización de cargas JSON de la red son operaciones comunes. Los métodos de extensión de [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) y [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permiten realizar estas operaciones en una sola línea de código. Estos métodos de extensión usan [valores predeterminados web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).

En el siguiente ejemplo se muestra el uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

También hay métodos de extensión para System.Text.Json en [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los métodos de extensión de `HttpClient` y `HttpContent` no están disponibles en System.Text.Json en .NET Core 3.1.
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Procedimientos para escribir convertidores personalizados](system-text-json-converters-how-to.md)
* [Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
