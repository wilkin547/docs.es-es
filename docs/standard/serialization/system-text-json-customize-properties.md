---
title: Personalización de los nombres y valores de propiedades con System.Text.Json
description: Aprenda a personalizar los nombres y valores de propiedades al serializar con System.Text.Json en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b88509313e719ea993e00d889bc6145f4976a2d
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008908"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a>Personalización de los nombres y valores de propiedades con System.Text.Json

De forma predeterminada, los nombres de propiedad y las claves de diccionario no se modifican en la salida JSON, ni siquiera el uso de mayúsculas y minúsculas. Los valores de enumeración se representan como números. En este artículo, aprenderá a:

> [!NOTE]
> Los [valores predeterminados web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) son mayúsculas y minúsculas Camel.

* [Personalizar nombres de propiedades individuales](#customize-individual-property-names)
* [Convertir todos los nombres de propiedad en mayúsculas y minúsculas combinadas Camel](#use-camel-case-for-all-json-property-names)
* [Implementar una directiva de nomenclatura de propiedades personalizada](#use-a-custom-json-property-naming-policy)
* [Convertir claves de diccionario en mayúsculas y minúsculas combinadas Camel](#camel-case-dictionary-keys)
* [Convertir enumeraciones en cadenas y palabras con mayúsculas y minúsculas combinadas Camel](#enums-as-strings)

En el caso de otros escenarios que requieran un tratamiento especial de los nombres y valores de propiedades JSON, puede [implementar convertidores personalizados](system-text-json-converters-how-to.md).

## <a name="customize-individual-property-names"></a>Personalizar nombres de propiedades individuales

Para establecer el nombre de propiedades individuales, use el atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Aquí se muestra un tipo de ejemplo que se serializa y el JSON resultante:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="use-camel-case-for-all-json-property-names"></a>Uso de mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON

Para usar palabras con mayúsculas y minúsculas combinadas Camel en todos los nombres de propiedad JSON, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="use-a-custom-json-property-naming-policy"></a>Uso de una directiva de nomenclatura de propiedades JSON personalizada

Para usar una directiva de nomenclatura de propiedades JSON personalizada, cree una clase que derive de <xref:System.Text.Json.JsonNamingPolicy> e invalide el método <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

Establezca luego la propiedad <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> en una instancia de la clase de directiva de nomenclatura:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

Aquí se muestra una clase de ejemplo que se serializa y la salida JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="camel-case-dictionary-keys"></a>Claves de diccionario en mayúsculas y minúsculas combinadas Camel

Si una propiedad de un objeto que se va a serializar es de tipo `Dictionary<string,TValue>`, se pueden convertir las claves `string` en mayúsculas y minúsculas combinadas Camel. Para ello, establezca <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> en `JsonNamingPolicy.CamelCase`, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

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

## <a name="enums-as-strings"></a>Enumeraciones como cadenas

De forma predeterminada, las enumeraciones se serializan como números. Para serializar nombres de enumeración como cadenas, use <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Por ejemplo, supongamos que hay que serializar la siguiente clase que tiene una enumeración:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

Si el resumen es `Hot`, el JSON serializado tiene el valor numérico 3 de forma predeterminada:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

En el código de ejemplo siguiente se serializan los nombres de enumeración en lugar de los valores numéricos y los nombres se convierten en mayúsculas y minúsculas combinadas Camel:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

El JSON resultante tendrá un aspecto similar al siguiente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Los nombres de cadena de enumeración también se pueden deserializar, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de las referencias](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Personalización de la codificación de caracteres](system-text-json-character-encoding.md)
* [Escritura de serializadores y deserializadores personalizados](write-custom-serializer-deserializer.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset](../datetime/system-text-json-support.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
