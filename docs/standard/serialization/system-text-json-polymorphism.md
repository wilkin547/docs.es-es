---
title: Serialización de propiedades de clases derivadas con System.Text.Json
description: Aprenda a serializar objetos polimórficos durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b99a402ea4f4c664d3bfd75627ffaf94948d493
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439839"
---
# <a name="how-to-serialize-properties-of-derived-classes-with-no-locsystemtextjson"></a>Serialización de propiedades de clases derivadas con System.Text.Json

En este artículo, aprenderá a serializar las propiedades de las clases derivadas con el espacio de nombres `System.Text.Json`.

## <a name="serialize-properties-of-derived-classes"></a>Serialización de propiedades de clases derivadas

_No_ se admite la serialización de una jerarquía de tipos polimórficos. Por ejemplo, si una propiedad se define como interfaz o como clase abstracta, solo se serializan las propiedades definidas en la interfaz o la clase abstracta, aunque el tipo de entorno de ejecución tenga propiedades adicionales. Las excepciones a este comportamiento se explican en esta sección.

Por ejemplo, supongamos que tiene una clase `WeatherForecast` y una clase derivada `WeatherForecastDerived`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFDerived":::

Supongamos también que el argumento de tipo del método `Serialize` en tiempo de compilación es `WeatherForecast`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeDefault":::

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

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeGetType":::

* Declare el objeto que se va a serializar como `object`.

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeObject":::

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

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPrevious":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPreviousAsObject":::

Si la propiedad `PreviousForecast` contiene una instancia de `WeatherForecastDerived`:

* La salida JSON de la serialización `WeatherForecastWithPrevious` **no incluye** `WindSpeed`.
* La salida JSON de la serialización `WeatherForecastWithPreviousAsObject` **incluye** `WindSpeed`.

Para serializar `WeatherForecastWithPreviousAsObject`, no es necesario llamar a `Serialize<object>` o `GetType` porque el objeto raíz no es el que puede ser de un tipo derivado. En el ejemplo de código siguiente no se llama a `Serialize<object>` ni `GetType`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeSecondLevel":::

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

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/IForecast.cs":::

Cuando se serializa una instancia de `Forecasts`, solo `Tuesday` muestra la propiedad `WindSpeed`, porque `Tuesday` se define como `object`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeInterface":::

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

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Creación de una instancia de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de referencias circulares](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
