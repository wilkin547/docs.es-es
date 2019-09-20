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
ms.openlocfilehash: 83b1b3a7db63154dccc07325b1a1948a2db3953a
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151821"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Compatibilidad con DateTime y DateTimeOffset en System.Text.Json

La biblioteca System. Text. JSON analiza y escribe <xref:System.DateTime> <xref:System.DateTimeOffset> los valores de acuerdo con el perfil extendido ISO 8601:-2019.
Los [convertidores](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) proporcionan compatibilidad personalizada para la serialización y deserialización con <xref:System.Text.Json.JsonSerializer>.
También se puede implementar la compatibilidad personalizada al <xref:System.Text.Json.Utf8JsonReader> usar <xref:System.Text.Json.Utf8JsonWriter>y.

## <a name="support-for-the-iso-8601-12019-format"></a>Compatibilidad con el formato ISO 8601-1:2019

Los <xref:System.Text.Json.JsonSerializer>tipos <xref:System.Text.Json.Utf8JsonReader>, ,<xref:System.Text.Json.Utf8JsonWriter>y <xref:System.DateTime> <xref:System.DateTimeOffset> analizan y escriben representaciones de texto y de acuerdo con el perfil extendido del formato ISO 8601-1:2019; por ejemplo, 2019-07-26T16 <xref:System.Text.Json.JsonElement> : 59:57-05:00.

<xref:System.DateTime>los <xref:System.DateTimeOffset> datos y se pueden serializar <xref:System.Text.Json.JsonSerializer>con:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

También se pueden deserializar con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Con las opciones predeterminadas <xref:System.DateTimeOffset> , las representaciones de entrada <xref:System.DateTime> y de texto deben ajustarse al perfil ISO 8601-1:2019 extendido.
Al intentar deserializar las representaciones que no se ajustan al perfil, <xref:System.Text.Json.JsonSerializer> se producirá <xref:System.Text.Json.JsonException>una excepción:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

Proporciona acceso estructurado al contenido de una carga JSON, incluidas <xref:System.DateTime> las representaciones y <xref:System.DateTimeOffset>. <xref:System.Text.Json.JsonDocument> En el ejemplo siguiente se muestra cómo, cuando se proporciona una colección de temperaturas, se puede calcular la temperatura media de los lunes:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Al intentar calcular la temperatura media dada una carga con representaciones no compatibles <xref:System.DateTime> <xref:System.Text.Json.JsonDocument> , se producirá una <xref:System.FormatException>excepción:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Los datos y <xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> escrituras<xref:System.DateTimeOffset> de nivel inferior:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader><xref:System.DateTime> análisis y<xref:System.DateTimeOffset> datos:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Si intenta leer formatos no compatibles con <xref:System.Text.Json.Utf8JsonReader> , se producirá una <xref:System.FormatException>excepción:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Compatibilidad personalizada con <xref:System.DateTime> y<xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Al usar<xref:System.Text.Json.JsonSerializer>

Si desea que el serializador realice el análisis o el formato personalizados, puede implementar [convertidores personalizados](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).
Estos son algunos ejemplos:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Usar `DateTime(Offset).Parse` y`DateTime(Offset).ToString`

Si no puede determinar los formatos de las representaciones <xref:System.DateTime> de <xref:System.DateTimeOffset> entrada o texto, puede usar el `DateTime(Offset).Parse` método en la lógica de lectura del convertidor. Esto le permite usar. La amplia compatibilidad de la red con <xref:System.DateTime> el <xref:System.DateTimeOffset> análisis de varios formatos de texto y, como cadenas que no son ISO 8601 y formatos ISO 8601 que no se ajustan al perfil ISO 8601-1:2019 extendido. Este enfoque es significativamente menos eficaz que el uso de la implementación nativa del serializador.

Para la serialización, puede usar el `DateTime(Offset).ToString` método en la lógica de escritura del convertidor. Esto <xref:System.DateTime> le permite escribir valores y <xref:System.DateTimeOffset> con cualquiera de los formatos de [fecha y hora estándar](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)y los formatos de [fecha y hora personalizados](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).
Esto también es significativamente menos eficaz que el uso de la implementación nativa del serializador.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Al implementar <xref:System.Text.Json.Serialization.JsonConverter%601> `T` y es <xref:System.DateTime>, el`typeToConvert` parámetro siempre`typeof(DateTime)`será.
El parámetro es útil para controlar los casos polimórficos y cuando se usan genéricos para obtener `typeof(T)` una manera eficaz.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Usar <xref:System.Buffers.Text.Utf8Parser> y<xref:System.Buffers.Text.Utf8Formatter>

Puede usar los métodos de formato y análisis basados en UTF-8 rápidos en la lógica del convertidor si <xref:System.DateTime> las <xref:System.DateTimeOffset> representaciones de entrada o de texto son compatibles con una de las [cadenas de formato de fecha y hora estándar](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)"R", "l", "o" o "G", o bien desea Escriba según uno de estos formatos. Esto es mucho más rápido que `DateTime(Offset).Parse` el `DateTime(Offset).ToString`uso de y.

En este ejemplo se muestra un convertidor personalizado que serializa y deserializa <xref:System.DateTime> valores según [el formato estándar "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> El formato estándar "R" siempre tendrá una longitud de 29 caracteres.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Usar `DateTime(Offset).Parse` como reserva para el análisis nativo del serializador

Si normalmente espera que la entrada <xref:System.DateTime> o <xref:System.DateTimeOffset> los datos se ajusten al perfil extendido ISO 8601-1:2019, puede usar la lógica de análisis nativo del serializador. También puede implementar un mecanismo de reserva en caso de que se trate.
En este ejemplo se muestra que, después de no analizar <xref:System.DateTime> una representación de <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>texto mediante, el convertidor analiza correctamente los datos <xref:System.DateTime.Parse(System.String)>mediante.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Al escribir con<xref:System.Text.Json.Utf8JsonWriter>

Si desea escribir <xref:System.DateTime> una representación personalizada o <xref:System.DateTimeOffset> de texto con <xref:System.Text.Json.Utf8JsonWriter>, puede `ReadOnlySpan<Char>`dar formato a la representación personalizada en <xref:System.String>, `ReadOnlySpan<Byte>`, o <xref:System.Text.Json.JsonEncodedText>y, a continuación, pasarla al Método [Utf8JsonWriter. WriteStringValue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) o [Utf8JsonWriter. WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) .

En el ejemplo siguiente se muestra cómo <xref:System.DateTime> se puede crear un formato <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>personalizado con y, después <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> , se escribe con el método:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Al leer con<xref:System.Text.Json.Utf8JsonReader>

Si desea leer una representación personalizada <xref:System.DateTime> o <xref:System.DateTimeOffset> de texto con <xref:System.Text.Json.Utf8JsonReader>, puede obtener el valor del token JSON actual como mediante <xref:System.Text.Json.Utf8JsonReader.GetString>y, a <xref:System.String> continuación, analizar el valor mediante la lógica personalizada.

En el ejemplo siguiente se muestra cómo <xref:System.DateTimeOffset> se puede recuperar una representación de <xref:System.Text.Json.Utf8JsonReader.GetString>texto personalizada mediante y, <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>a continuación, analizar mediante:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>El perfil ISO 8601-1:2019 extendido en System. Text. JSON

### <a name="date-and-time-components"></a>Componentes de fecha y hora

El perfil extendido ISO 8601-1:2019 implementado <xref:System.Text.Json> en define los siguientes componentes para las representaciones de fecha y hora. Estos componentes se usan para definir diversos niveles de granularidad admitidos al analizar y dar <xref:System.DateTime> formato <xref:System.DateTimeOffset> y representaciones.

| Componente       | Formato                      | Descripción                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Año            | "yyyy"                      | 0001-9999                                                                       |
| Mes           | "MM"                        | 01-12                                                                           |
| Day             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basado en mes/año                                  |
| Hour            | "HH"                        | 00-23                                                                           |
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
    1. "YYYY-'-Dd't": "mm": "SS" ([el especificador de formato que se va a ordenar ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))
    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF

4. "Fecha completa ' t ' ' hora de la hora ' ': ' ' minuto ' ' desplazamiento de tiempo ' '
    1. "YYYY-'-Dd't": "mmZ"
    2. "YYYY-'-Dd't ': ' mm (' + '/'-') HH ': ' mm '

5. ' Fecha y hora '
    1. "YYYY-'-Dd't ': ' mm ': ' ssZ '
    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFFZ"
    3. "YYYY-'-Dd't ': ' mm ': ' SS (' + '/'-') HH ': ' mm '
    4. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

Si hay fracciones decimales para segundos, debe haber al menos un dígito. `2019-07-26T00:00:00.` no está permitido.
Aunque se permiten hasta 16 dígitos fraccionarios, solo se analizan los siete primeros. Cualquier cosa más allá se considera un cero.
Por ejemplo, `2019-07-26T00:00:00.1234567890` se analizará como si se tratase `2019-07-26T00:00:00.1234567`de.
Esto es para mantener la compatibilidad con <xref:System.DateTime> la implementación, que se limita a esta resolución.

No se admiten los segundos de LEAP.

### <a name="support-for-formatting"></a>Compatibilidad con el formato

Se definen los siguientes niveles de granularidad para el formato:

1. "' Fecha completa ' ' t ' ' de hora parcial ' '
    1. "YYYY-'-Dd't": "mm": "SS" ([el especificador de formato que se va a ordenar ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        Se usa para dar <xref:System.DateTime> formato a un sin fracciones de segundo y sin información de desplazamiento.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF

        Se usa para dar <xref:System.DateTime> formato a un con fracciones de segundo pero sin información de desplazamiento.

2. ' Fecha y hora '
    1. "YYYY-'-Dd't ': ' mm ': ' ssZ '

        Se usa para dar <xref:System.DateTime> formato <xref:System.DateTimeOffset> a un o sin fracciones de segundo, pero con un desplazamiento UTC.

    2. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFFZ"

        Se usa para dar <xref:System.DateTime> formato <xref:System.DateTimeOffset> a un o con fracciones de segundo y con un desplazamiento de UTC.

    3. "YYYY-'-Dd't ': ' mm ': ' SS (' + '/'-') HH ': ' mm '

        Se usa para dar <xref:System.DateTime> formato <xref:System.DateTimeOffset> a o sin fracciones de segundo, pero con un desplazamiento local.

    4. "YYYY-'-Dd't ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

        Se usa para dar <xref:System.DateTime> formato <xref:System.DateTimeOffset> a un o con fracciones de segundo y con un desplazamiento local.

Si está presente, se escribe un máximo de 7 dígitos fraccionarios. Esto se alinea con la <xref:System.DateTime> implementación, que se limita a esta resolución.
