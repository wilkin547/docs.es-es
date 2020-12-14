---
title: Omisión de propiedades con System.Text.Json
description: Aprenda a omitir propiedades al serializar con System.Text.Json en .NET.
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
ms.openlocfilehash: 6d703156d50a3e00a33cea5e15be2df911ed7c1b
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008817"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a>Omisión de propiedades con System.Text.Json

Al serializar objetos de C# en notación de objetos JavaScript (JSON), de forma predeterminada, se serializan todas las propiedades públicas. Si no quiere que algunas de ellas aparezcan en el código JSON resultante, tiene varias opciones. En este artículo, aprenderá a omitir las propiedades en función de varios criterios:

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

## <a name="ignore-individual-properties"></a>Omisión de propiedades individuales

Para omitir propiedades individuales, use el atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

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
* `WhenWritingDefault`: la propiedad se omite en la serialización si es un tipo de referencia `null`, un tipo de valor `null` que acepta valores NULL o un tipo de valor `default`.
* `WhenWritingNull`: la propiedad se omite en la serialización si es un tipo de referencia `null` o un tipo de valor `null` que acepta valores NULL.

En el ejemplo siguiente se muestra el uso de la propiedad `Condition` del atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a>Omisión de todas las propiedades de solo lectura

Una propiedad es de solo lectura si contiene un captador público pero no un establecedor público. Para omitir todas las propiedades de solo lectura durante la serialización, establezca <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> en `true`, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

Aquí se muestra un tipo de ejemplo que se va a serializar y la salida JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Esta opción solo se aplica a la serialización. Durante la deserialización, las propiedades de solo lectura se omiten de forma predeterminada.

::: zone pivot="dotnet-5-0"
Esta opción solo se aplica a las propiedades. Para omitir los campos de solo lectura al [serializar campos](system-text-json-how-to.md#include-fields), use el parámetro global <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

## <a name="ignore-all-null-value-properties"></a>Omisión de todas las propiedades de valores NULL

::: zone pivot="dotnet-5-0"
Para omitir todas las propiedades de valores NULL, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
Para omitir todas las propiedades de valores NULL al serializar, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> en `true`, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

Aquí se muestra un objeto de ejemplo que se serializa y la salida JSON:

| Propiedad.             | Valor                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a>Omisión de todas las propiedades de valor predeterminado

::: zone pivot="dotnet-5-0"
Para evitar la serialización de valores predeterminados en las propiedades de tipo de valor, establezca la propiedad <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> en <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

El valor <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> también evita la serialización de propiedades de los tipos de referencia de valor NULL y los tipos de valor que aceptan valores NULL.

::: zone pivot="dotnet-core-3-1"
No hay ninguna manera integrada de evitar la serialización de propiedades con valores predeterminados de tipos de valor en `System.Text.Json` en .NET Core 3.1.
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
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
