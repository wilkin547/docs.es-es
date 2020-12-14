---
title: Control del código JSON de desbordamiento con System.Text.Json
description: Aprenda a controlar el código JSON de desbordamiento durante la serialización y deserialización desde JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 265ce4f77d353720419122d17c36e508a377b68f
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008921"
---
# <a name="how-to-handle-overflow-json-with-no-locsystemtextjson"></a>Control del código JSON de desbordamiento con System.Text.Json

En este artículo, aprenderá a controlar el código JSON de desbordamiento con el espacio de nombres `System.Text.Json`.

## <a name="handle-overflow-json"></a>JSON de desbordamiento de control

Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino. Por ejemplo, supongamos que el tipo de destino es el siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

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

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithExtensionData":::

Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:

| Propiedad. | Valor | Notas |
|--|--|--|
| `Date` | `"8/1/2019 12:00:00 AM -07:00"` |  |
| `TemperatureCelsius` | `0` | Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad. |
| `Summary` | `"Hot"` |  |
| `ExtensionData` | `temperatureCelsius: 25` | Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario. |
| `DatesAvailable` | `[ "8/1/2019 12:00:00 AM -07:00", "8/2/2019 12:00:00 AM -07:00" ]` | La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor. |
| `SummaryWords` | `[ "Cool", "Windy", "Humid" ]` | La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor. |

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

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
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
