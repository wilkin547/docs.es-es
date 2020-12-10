---
title: Permitir algunos tipos de JSON no válido con System.Text.Json
description: Sepa cómo permitir comentarios, comas finales y números entre comillas durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439820"
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
* [Creación de una instancia de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de referencias circulares](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
