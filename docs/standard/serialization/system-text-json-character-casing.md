---
title: Habilitación de la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con System.Text.Json
description: Aprenda a habilitar la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3e2fb8cbdd35e772b5e97c731199f69aa834bd0a
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009747"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a>Habilitación de la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con System.Text.Json

En este artículo, aprenderá a habilitar la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas con el espacio de nombres `System.Text.Json`.

## <a name="case-insensitive-property-matching"></a>Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas

De forma predeterminada, la deserialización busca coincidencias con el nombre de propiedad que distingan mayúsculas y minúsculas entre JSON y las propiedades del objeto de destino. Para cambiar ese comportamiento, establezca <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> en `true`:

> [!NOTE]
> Los [valores predeterminados web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) no distinguen entre mayúsculas y minúsculas.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

Aquí se muestra un ejemplo de JSON con nombres de propiedades en mayúsculas y minúsculas combinadas Camel. Se puede deserializar en el tipo siguiente que tenga nombres de propiedades en mayúsculas y minúsculas Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
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
