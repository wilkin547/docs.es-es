---
title: Personalización de la codificación de caracteres con System.Text.Json
description: Aprenda a personalizar la codificación de caracteres durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f6a50a3ca2a5e871294cf7c056cbf197a61cd668
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439877"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a>Personalización de la codificación de caracteres con System.Text.Json

De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII. Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter. Por ejemplo, si la propiedad `Summary` del siguiente código JSON está establecida en cirílico `жарко`, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a>Serialización de juegos de caracteres de idioma

Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

Este código no escapa a los caracteres cirílicos o griegos. Si la propiedad `Summary` está establecida en cirílico `жарко`, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

## <a name="serialize-specific-characters"></a>Serialización de caracteres específicos

Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape. En el ejemplo siguiente se serializan solo los dos primeros caracteres de `жарко`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

Aquí se muestra un ejemplo de JSON producido por el código anterior:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a>Serialización de todos los caracteres

Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:
>
> * No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.
> * No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.
>
> Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8. Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`. No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Escritura de serializadores y deserializadores personalizados](write-custom-serializer-deserializer.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
