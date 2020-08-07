---
title: Compatibilidad con DateTime y DateTimeOffset en System.Text.Json
description: Información general sobre cómo se admiten los tipos DateTime y DateTimeOffset en el System.Text.Jsen la biblioteca.
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 1c573712f458d3e22cd59112b9e79e85391270c1
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854898"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Compatibilidad con DateTime y DateTimeOffset en System.Text.Json

El System.Text.Jsen la biblioteca analiza y escribe <xref:System.DateTime> y <xref:System.DateTimeOffset> los valores de acuerdo con el perfil extendido ISO 8601:-2019.
Los [convertidores](xref:System.Text.Json.Serialization.JsonConverter%601) proporcionan compatibilidad personalizada para la serialización y deserialización con <xref:System.Text.Json.JsonSerializer> .
También se puede implementar la compatibilidad personalizada al usar <xref:System.Text.Json.Utf8JsonReader> y <xref:System.Text.Json.Utf8JsonWriter> .

## <a name="support-for-the-iso-8601-12019-format"></a>Compatibilidad con el formato ISO 8601-1:2019

Los <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.Utf8JsonReader> tipos,, <xref:System.Text.Json.Utf8JsonWriter> y <xref:System.Text.Json.JsonElement> analizan y escriben <xref:System.DateTime> <xref:System.DateTimeOffset> representaciones de texto y de acuerdo con el perfil extendido del formato ISO 8601-1:2019; por ejemplo, 2019-07-26T16:59:57-05:00.

<xref:System.DateTime>los <xref:System.DateTimeOffset> datos y se pueden serializar con <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

También se pueden deserializar con <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Con las opciones predeterminadas, <xref:System.DateTime> las representaciones de entrada y de <xref:System.DateTimeOffset> texto deben ajustarse al perfil ISO 8601-1:2019 extendido.
Al intentar deserializar las representaciones que no se ajustan al perfil, se producirá <xref:System.Text.Json.JsonSerializer> una excepción <xref:System.Text.Json.JsonException> :

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<xref:System.Text.Json.JsonDocument>Proporciona acceso estructurado al contenido de una carga JSON, incluidas las <xref:System.DateTime> representaciones y <xref:System.DateTimeOffset> . En el ejemplo siguiente se muestra cómo, cuando se proporciona una colección de temperaturas, se puede calcular la temperatura media de los lunes:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Al intentar calcular la temperatura media dada una carga con representaciones no compatibles <xref:System.DateTime> , se producirá <xref:System.Text.Json.JsonDocument> una excepción <xref:System.FormatException> :

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Los <xref:System.Text.Json.Utf8JsonWriter> datos y escrituras de nivel inferior <xref:System.DateTime> <xref:System.DateTimeOffset> :

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader>Análisis <xref:System.DateTime> y <xref:System.DateTimeOffset> datos:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Si intenta leer formatos no compatibles con, se <xref:System.Text.Json.Utf8JsonReader> producirá una excepción <xref:System.FormatException> :

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Compatibilidad personalizada con <xref:System.DateTime> y<xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Al usar<xref:System.Text.Json.JsonSerializer>

Si desea que el serializador realice el análisis o el formato personalizados, puede implementar [convertidores personalizados](xref:System.Text.Json.Serialization.JsonConverter%601).
Estos son algunos ejemplos:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Usar `DateTime(Offset).Parse` y`DateTime(Offset).ToString`

Si no puede determinar los formatos de las representaciones de entrada <xref:System.DateTime> o <xref:System.DateTimeOffset> texto, puede usar el `DateTime(Offset).Parse` método en la lógica de lectura del convertidor. Esto le permite usar. La amplia compatibilidad de la red con el análisis de varios <xref:System.DateTime> <xref:System.DateTimeOffset> formatos de texto y, como cadenas que no son ISO 8601 y formatos ISO 8601 que no se ajustan al perfil ISO 8601-1:2019 extendido. Este enfoque es significativamente menos eficaz que el uso de la implementación nativa del serializador.

Para la serialización, puede usar el `DateTime(Offset).ToString` método en la lógica de escritura del convertidor. Esto le permite escribir <xref:System.DateTime> valores y <xref:System.DateTimeOffset> con cualquiera de los [formatos de fecha y hora estándar](../base-types/standard-date-and-time-format-strings.md)y los [formatos de fecha y hora personalizados](../base-types/custom-date-and-time-format-strings.md).
Esto también es significativamente menos eficaz que el uso de la implementación nativa del serializador.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Al implementar <xref:System.Text.Json.Serialization.JsonConverter%601> y `T` es <xref:System.DateTime> , el `typeToConvert` parámetro siempre será `typeof(DateTime)` .
El parámetro es útil para controlar los casos polimórficos y cuando se usan genéricos para obtener `typeof(T)` una manera eficaz.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Usar <xref:System.Buffers.Text.Utf8Parser> y<xref:System.Buffers.Text.Utf8Formatter>

Puede usar los métodos de formato y análisis basados en UTF-8 rápidos en la lógica del convertidor si <xref:System.DateTime> sus <xref:System.DateTimeOffset> representaciones de entrada o de texto son compatibles con una de las [cadenas de formato de fecha y hora estándar](../base-types/standard-date-and-time-format-strings.md)"R", "l", "o" o "G", o si desea escribir de acuerdo con uno de estos formatos. Esto es mucho más rápido que el uso de `DateTime(Offset).Parse` y `DateTime(Offset).ToString` .

En este ejemplo se muestra un convertidor personalizado que serializa y deserializa <xref:System.DateTime> valores según [el formato estándar "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> El formato estándar "R" siempre tendrá una longitud de 29 caracteres.
>
> El formato "l" (minúscula "L") no está documentado con las otras [cadenas de formato de fecha y hora estándar](../base-types/standard-date-and-time-format-strings.md) , ya que solo se admite en los `Utf8Parser` `Utf8Formatter` tipos y. El formato es la RFC 1123 minúscula (una versión en minúscula del formato "R"), por ejemplo: "Thu, 25 Jul 2019 06:36:07 GMT".

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Usar `DateTime(Offset).Parse` como reserva para el análisis nativo del serializador

Si normalmente espera que la entrada <xref:System.DateTime> o los <xref:System.DateTimeOffset> datos se ajusten al perfil extendido ISO 8601-1:2019, puede usar la lógica de análisis nativo del serializador. También puede implementar un mecanismo de reserva en caso de que se trate.
En este ejemplo se muestra que, después de no analizar una <xref:System.DateTime> representación de texto mediante <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)> , el convertidor analiza correctamente los datos mediante <xref:System.DateTime.Parse(System.String)> .

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Al escribir con<xref:System.Text.Json.Utf8JsonWriter>

Si desea escribir una <xref:System.DateTime> representación personalizada o de <xref:System.DateTimeOffset> texto con <xref:System.Text.Json.Utf8JsonWriter> , puede dar formato a la representación personalizada en,, <xref:System.String> `ReadOnlySpan<Byte>` `ReadOnlySpan<Char>` o <xref:System.Text.Json.JsonEncodedText> , y, a continuación, pasarla al <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType> método o correspondiente <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType> .

En el ejemplo siguiente se muestra cómo <xref:System.DateTime> se puede crear un formato personalizado con <xref:System.DateTime.ToString(System.String,System.IFormatProvider)> y, después, se escribe con el <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> método:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Al leer con<xref:System.Text.Json.Utf8JsonReader>

Si desea leer una <xref:System.DateTime> representación personalizada o <xref:System.DateTimeOffset> de texto con <xref:System.Text.Json.Utf8JsonReader> , puede obtener el valor del token JSON actual como <xref:System.String> mediante y, <xref:System.Text.Json.Utf8JsonReader.GetString> a continuación, analizar el valor mediante la lógica personalizada.

En el ejemplo siguiente se muestra cómo <xref:System.DateTimeOffset> se puede recuperar una representación de texto personalizada mediante <xref:System.Text.Json.Utf8JsonReader.GetString> y, a continuación, analizar mediante <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)> :

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Perfil extendido ISO 8601-1:2019 en System.Text.Js

### <a name="date-and-time-components"></a>Componentes de fecha y hora

El perfil extendido ISO 8601-1:2019 implementado en <xref:System.Text.Json> define los siguientes componentes para las representaciones de fecha y hora. Estos componentes se usan para definir diversos niveles de granularidad admitidos al analizar y dar formato <xref:System.DateTime> y <xref:System.DateTimeOffset> representaciones.

| Componente       | Formato                      | Descripción                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Year            | "yyyy"                      | 0001-9999                                                                       |
| Month           | "MM"                        | 01-12                                                                           |
| Día             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basado en mes/año                                  |
| Hora            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Segundo          | "ss"                        | 00-59                                                                           |
| Segunda fracción | "FFFFFFF"                   | Mínimo de un dígito, máximo de 16 dígitos                                      |
| Desplazamiento de tiempo     | "K"                         | "Z" o "(' + '/'-') HH ': ' mm '                                                |
| Tiempo parcial    | "HH": "mm": "SS [FFFFFFF]"     | Hora sin información de desplazamiento de UTC                                             |
| Fecha completa       | "YYYY-'-DD"            | Fecha del calendario                                                                   |
| Tiempo completo       | "Time'K Partial"           | Hora UTC del día o hora local del día con el desplazamiento de tiempo entre la hora local y la hora UTC |
| Datetime       | "' ' Fecha completa ' ' t ' ' ' ' | Fecha y hora del calendario del día, por ejemplo, 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Compatibilidad con el análisis

Se definen los siguientes niveles de granularidad para el análisis:

1. ' Fecha completa '
    1. "YYYY-'-DD"

2. "Fecha completa ' t ' ' hora ' ': ' ' minuto '"
    1. "YYYY-'-Dd't": "mm"

3. "' Fecha completa ' ' t ' ' de hora parcial ' '
    1. "YYYY-'-Dd't": "mm": "SS" ([el especificador de formato que se va a ordenar ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))
    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF

4. "Fecha completa ' t ' ' hora de la hora ' ': ' ' minuto ' ' desplazamiento de tiempo ' '
    1. "YYYY-'-Dd't": "mmZ"
    2. "YYYY-'-Dd't ': ' mm (' + '/'-') HH ': ' mm '

5. ' Fecha y hora '
    1. "YYYY-'-Dd't ': ' mm ': ' ssZ '
    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFFZ"
    3. "YYYY-'-Dd't ': ' mm ': ' SS (' + '/'-') HH ': ' mm '
    4. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

Si hay fracciones decimales para segundos, debe haber al menos un dígito. `2019-07-26T00:00:00.`no está permitido.
Aunque se permiten hasta 16 dígitos fraccionarios, solo se analizan los siete primeros. Cualquier cosa más allá se considera un cero.
Por ejemplo, se `2019-07-26T00:00:00.1234567890` analizará como si se tratase de `2019-07-26T00:00:00.1234567` .
Esto es para mantener la compatibilidad con la <xref:System.DateTime> implementación, que se limita a esta resolución.

No se admiten los segundos de LEAP.

### <a name="support-for-formatting"></a>Compatibilidad con el formato

Se definen los siguientes niveles de granularidad para el formato:

1. "' Fecha completa ' ' t ' ' de hora parcial ' '
    1. "YYYY-'-Dd't": "mm": "SS" ([el especificador de formato que se va a ordenar ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))

        Se usa para dar formato a un <xref:System.DateTime> sin fracciones de segundo y sin información de desplazamiento.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF

        Se usa para dar formato a un <xref:System.DateTime> con fracciones de segundo pero sin información de desplazamiento.

2. ' Fecha y hora '
    1. "YYYY-'-Dd't ': ' mm ': ' ssZ '

        Se usa para dar formato a un <xref:System.DateTime> sin fracciones de segundo pero con un desplazamiento de UTC.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFFZ"

        Se usa para dar formato a un <xref:System.DateTime> con fracciones de segundo y con un desplazamiento de UTC.

    3. "YYYY-'-Dd't ': ' mm ': ' SS (' + '/'-') HH ': ' mm '

        Se usa para dar formato a <xref:System.DateTime> o <xref:System.DateTimeOffset> sin fracciones de segundo, pero con un desplazamiento local.

    4. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

        Se usa para dar formato a un <xref:System.DateTime> o <xref:System.DateTimeOffset> con fracciones de segundo y con un desplazamiento local.

Si la representación de [formato de ida y vuelta](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) de una <xref:System.DateTime> instancia de o <xref:System.DateTimeOffset> tiene ceros finales en las fracciones de segundo, entonces <xref:System.Text.Json.JsonSerializer> y <xref:System.Text.Json.Utf8JsonWriter> dará formato a una representación de la instancia sin ceros finales.
Por ejemplo, una <xref:System.DateTime> instancia cuya representación [de formato de ida y vuelta](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) es `2019-04-24T14:50:17.1010000Z` , se formateará como `2019-04-24T14:50:17.101Z` <xref:System.Text.Json.JsonSerializer> y <xref:System.Text.Json.Utf8JsonWriter> .

Si la representación de [formato de ida y vuelta](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) de una <xref:System.DateTime> instancia de o <xref:System.DateTimeOffset> tiene ceros en sus fracciones de segundo, <xref:System.Text.Json.JsonSerializer> y <xref:System.Text.Json.Utf8JsonWriter> dará formato a una representación de la instancia sin fracciones de segundo.
Por ejemplo, una <xref:System.DateTime> instancia cuya representación [de formato de ida y vuelta](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) es `2019-04-24T14:50:17.0000000+02:00` , se formateará como `2019-04-24T14:50:17+02:00` <xref:System.Text.Json.JsonSerializer> y <xref:System.Text.Json.Utf8JsonWriter> .

Truncar ceros en dígitos de fracciones de segundo permite que se escriba la salida más pequeña necesaria para conservar la información sobre un viaje de ida y vuelta.

Se escribe un máximo de 7 dígitos de fracciones de segundo. Esto se alinea con la <xref:System.DateTime> implementación, que se limita a esta resolución.
