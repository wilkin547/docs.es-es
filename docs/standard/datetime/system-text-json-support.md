---
title: Compatibilidad con DateTime y DateTimeOffset en System.Text.Json
description: Información general sobre cómo se admiten los tipos DateTime y DateTimeOffset en la biblioteca System. Text. JSON.
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
ms.openlocfilehash: 8198359e2c54c4ed098703fbcc070f7469b3362a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344654"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Compatibilidad con DateTime y DateTimeOffset en System.Text.Json

La biblioteca System. Text. JSON analiza y escribe los valores <xref:System.DateTime> y <xref:System.DateTimeOffset> según el perfil extendido ISO 8601:-2019.
Los [convertidores](xref:System.Text.Json.Serialization.JsonConverter%601) proporcionan compatibilidad personalizada para serializar y deserializar con <xref:System.Text.Json.JsonSerializer>.
También se puede implementar la compatibilidad personalizada cuando se usa <xref:System.Text.Json.Utf8JsonReader> y <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="support-for-the-iso-8601-12019-format"></a>Compatibilidad con el formato ISO 8601-1:2019

Los tipos <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>y <xref:System.Text.Json.JsonElement> analizan y escriben representaciones de <xref:System.DateTime> y <xref:System.DateTimeOffset> texto de acuerdo con el perfil extendido del formato ISO 8601-1:2019; por ejemplo, 2019-07-26T16:59:57-05:00.

<xref:System.DateTime> y <xref:System.DateTimeOffset> datos se pueden serializar con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

También se pueden deserializar con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Con las opciones predeterminadas, las representaciones de <xref:System.DateTime> de entrada y <xref:System.DateTimeOffset> texto deben ajustarse al perfil ISO 8601-1:2019 extendido.
Al intentar deserializar las representaciones que no se ajustan al perfil, <xref:System.Text.Json.JsonSerializer> producirá una <xref:System.Text.Json.JsonException>:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

El <xref:System.Text.Json.JsonDocument> proporciona acceso estructurado al contenido de una carga de JSON, incluidas las representaciones de <xref:System.DateTime> y <xref:System.DateTimeOffset>. En el ejemplo siguiente se muestra cómo, cuando se proporciona una colección de temperaturas, se puede calcular la temperatura media de los lunes:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Si se intenta calcular la temperatura media dada una carga con representaciones de <xref:System.DateTime> no compatibles, <xref:System.Text.Json.JsonDocument> producirá una <xref:System.FormatException>:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

El nivel inferior <xref:System.Text.Json.Utf8JsonWriter> escribe los datos <xref:System.DateTime> y <xref:System.DateTimeOffset>:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> analiza <xref:System.DateTime> y <xref:System.DateTimeOffset> datos:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Si intenta leer formatos no compatibles con <xref:System.Text.Json.Utf8JsonReader>, se producirá un <xref:System.FormatException>:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Compatibilidad personalizada para <xref:System.DateTime> y <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Al utilizar <xref:System.Text.Json.JsonSerializer>

Si desea que el serializador realice el análisis o el formato personalizados, puede implementar [convertidores personalizados](xref:System.Text.Json.Serialization.JsonConverter%601).
Estos son algunos ejemplos:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Usar `DateTime(Offset).Parse` y `DateTime(Offset).ToString`

Si no puede determinar los formatos de entrada <xref:System.DateTime> o <xref:System.DateTimeOffset> representaciones de texto, puede usar el método `DateTime(Offset).Parse` en la lógica de lectura del convertidor. Esto le permite usar. La amplia compatibilidad de la red con el análisis de varios formatos de texto <xref:System.DateTime> y <xref:System.DateTimeOffset>, incluidas las cadenas que no son ISO 8601 y los formatos ISO 8601 que no se ajustan al perfil ISO 8601-1:2019 extendido. Este enfoque es significativamente menos eficaz que el uso de la implementación nativa del serializador.

Para la serialización, puede usar el método `DateTime(Offset).ToString` en la lógica de escritura del convertidor. Esto le permite escribir <xref:System.DateTime> y <xref:System.DateTimeOffset> valores con cualquiera de los [formatos de fecha y hora estándar](../base-types/standard-date-and-time-format-strings.md)y los [formatos de fecha y hora personalizados](../base-types/custom-date-and-time-format-strings.md).
Esto también es significativamente menos eficaz que el uso de la implementación nativa del serializador.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Al implementar <xref:System.Text.Json.Serialization.JsonConverter%601>y `T` se <xref:System.DateTime>, el parámetro `typeToConvert` siempre será `typeof(DateTime)`.
El parámetro es útil para controlar los casos polimórficos y cuando se usan genéricos para obtener `typeof(T)` de forma eficaz.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Usar <xref:System.Buffers.Text.Utf8Parser> y <xref:System.Buffers.Text.Utf8Formatter>

Puede usar los métodos de formato y análisis basados en UTF-8 rápidos en la lógica del convertidor si la entrada <xref:System.DateTime> o <xref:System.DateTimeOffset> representaciones de texto son compatibles con una de las [cadenas de formato de fecha y hora estándar](../base-types/standard-date-and-time-format-strings.md)"R", "l", "o" o "G", o bien desea escribir de acuerdo con uno de estos formatos. Esto es mucho más rápido que el uso de `DateTime(Offset).Parse` y `DateTime(Offset).ToString`.

En este ejemplo se muestra un convertidor personalizado que serializa y deserializa los valores de <xref:System.DateTime> según [el formato estándar "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> El formato estándar "R" siempre tendrá una longitud de 29 caracteres.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Usar `DateTime(Offset).Parse` como reserva para el análisis nativo del serializador

Si normalmente espera que los datos de entrada <xref:System.DateTime> o <xref:System.DateTimeOffset> cumplan el perfil ISO 8601-1:2019 extendido, puede usar la lógica de análisis nativo del serializador. También puede implementar un mecanismo de reserva en caso de que se trate.
En este ejemplo se muestra que, después de no analizar una representación de <xref:System.DateTime> texto mediante <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, el convertidor analiza correctamente los datos mediante <xref:System.DateTime.Parse(System.String)>.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Al escribir con <xref:System.Text.Json.Utf8JsonWriter>

Si desea escribir un <xref:System.DateTime> personalizado o <xref:System.DateTimeOffset> representación de texto con <xref:System.Text.Json.Utf8JsonWriter>, puede dar formato a la representación personalizada en una <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`o <xref:System.Text.Json.JsonEncodedText>y, a continuación, pasarla al método <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType> o <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType> correspondiente.

En el ejemplo siguiente se muestra cómo se puede crear un formato de <xref:System.DateTime> personalizado con <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>y, después, se escribe con el método <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)>:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Al leer con <xref:System.Text.Json.Utf8JsonReader>

Si desea leer un <xref:System.DateTime> personalizado o <xref:System.DateTimeOffset> representación de texto con <xref:System.Text.Json.Utf8JsonReader>, puede obtener el valor del token JSON actual como un <xref:System.String> con <xref:System.Text.Json.Utf8JsonReader.GetString>y, a continuación, analizar el valor mediante la lógica personalizada.

En el ejemplo siguiente se muestra cómo se puede recuperar una representación de texto de <xref:System.DateTimeOffset> personalizado mediante <xref:System.Text.Json.Utf8JsonReader.GetString>y, a continuación, analizar con <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>El perfil ISO 8601-1:2019 extendido en System. Text. JSON

### <a name="date-and-time-components"></a>Componentes de fecha y hora

El perfil extendido ISO 8601-1:2019 implementado en <xref:System.Text.Json> define los siguientes componentes para las representaciones de fecha y hora. Estos componentes se usan para definir diversos niveles de granularidad admitidos al analizar y dar formato a <xref:System.DateTime> y <xref:System.DateTimeOffset> representaciones.

| Componente       | Formato                      | Descripción                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Año            | "yyyy"                      | 0001-9999                                                                       |
| Mes           | "MM"                        | 01-12                                                                           |
| Día             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basado en mes/año                                  |
| Hora            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| Segunda fracción | "FFFFFFF"                   | Mínimo de un dígito, máximo de 16 dígitos                                      |
| Desplazamiento de tiempo     | "K"                         | "Z" o "(' + '/'-') HH ': ' mm '                                                |
| Tiempo parcial    | "HH": "mm": "SS [FFFFFFF]"     | Hora sin información de desplazamiento de UTC                                             |
| Fecha completa       | "YYYY-'-DD"            | Fecha del calendario                                                                   |
| Tiempo completo       | "Time'K Partial"           | Hora UTC del día o hora local del día con el desplazamiento de tiempo entre la hora local y la hora UTC |
| Fecha y hora       | "' ' Fecha completa ' ' t ' ' ' ' | Fecha y hora del calendario del día, por ejemplo, 2019-07-26T16:59:57-05:00                   |

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

Si hay fracciones decimales para segundos, debe haber al menos un dígito. no se permite `2019-07-26T00:00:00.`.
Aunque se permiten hasta 16 dígitos fraccionarios, solo se analizan los siete primeros. Cualquier cosa más allá se considera un cero.
Por ejemplo, `2019-07-26T00:00:00.1234567890` se analizará como si estuviera `2019-07-26T00:00:00.1234567`.
Esto es para mantener la compatibilidad con la implementación de <xref:System.DateTime>, que está limitada a esta resolución.

No se admiten los segundos de LEAP.

### <a name="support-for-formatting"></a>Compatibilidad con el formato

Se definen los siguientes niveles de granularidad para el formato:

1. "' Fecha completa ' ' t ' ' de hora parcial ' '
    1. "YYYY-'-Dd't": "mm": "SS" ([el especificador de formato que se va a ordenar ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))

        Se utiliza para dar formato a un <xref:System.DateTime> sin fracciones de segundo y sin información de desplazamiento.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF

        Se usa para dar formato a un <xref:System.DateTime> con fracciones de segundo pero sin información de desplazamiento.

2. ' Fecha y hora '
    1. "YYYY-'-Dd't ': ' mm ': ' ssZ '

        Se usa para dar formato a un <xref:System.DateTime> sin fracciones de segundo pero con un desplazamiento UTC.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFFZ"

        Se usa para dar formato a un <xref:System.DateTime> con fracciones de segundo y con un desplazamiento de UTC.

    3. "YYYY-'-Dd't ': ' mm ': ' SS (' + '/'-') HH ': ' mm '

        Se usa para dar formato a un <xref:System.DateTime> o <xref:System.DateTimeOffset> sin fracciones de segundo pero con un desplazamiento local.

    4. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

        Se usa para dar formato a un <xref:System.DateTime> o <xref:System.DateTimeOffset> con fracciones de segundo y con un desplazamiento local.

Si está presente, se escribe un máximo de 7 dígitos fraccionarios. Esto se alinea con la implementación de <xref:System.DateTime>, que se limita a esta resolución.
