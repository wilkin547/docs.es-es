---
title: Permitir algunos tipos de JSON no válido con System.Text.Json
description: Sepa cómo permitir comentarios, comas finales y números entre comillas durante la serialización y deserialización de JSON en .NET.
ms.date: 12/03/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2559b081010fb0a2fa208b121cb095efdeb8da2e
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009816"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a>Permitir algunos tipos de JSON no válido con System.Text.Json

En este artículo, sabrá cómo permitir comentarios, comas finales y números entre comillas en JSON, y cómo escribir números como cadenas.

## <a name="allow-comments-and-trailing-commas"></a>Autorización de comentarios y comas finales

De forma predeterminada, los comentarios y las comas finales no se permiten en JSON. Para permitir comentarios en JSON, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> en `JsonCommentHandling.Skip`.
Y para permitir las comas finales, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> en `true`. En el siguiente ejemplo se muestra cómo permitirlos ambos:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

Aquí se muestra un ejemplo de JSON con comentarios y una coma final:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
  // Comments on
  /* separate lines */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a>Permitir o escribir números entre comillas

::: zone pivot="dotnet-5-0"

Algunos serializadores codifican números como cadenas JSON (entre comillas).

Por ejemplo:

```json
{
    "DegreesCelsius": "23"
}
```

En lugar de:

```json
{
    "DegreesCelsius": 23
}
```

Para serializar los números entre comillas o aceptar números entre comillas en todo el gráfico del objeto de entrada, establezca <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

Cuando se usa `System.Text.Json` indirectamente a través de ASP.NET Core, se permiten números entre comillas al deserializar porque ASP.NET Core especifica [opciones predeterminadas web](xref:System.Text.Json.JsonSerializerDefaults.Web).

Para permitir o escribir números entre comillas para propiedades, campos o tipos específicos, use el atributo [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`System.Text.Json` en .NET Core 3.1 no admite la serialización o deserialización de números entre comillas. Para obtener más información, vea [Permitir o escribir números entre comillas](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
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
