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
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599081"
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
* [Creación de una instancia de JsonSerializerOptions](system-text-json-configure-options.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de referencias circulares](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
