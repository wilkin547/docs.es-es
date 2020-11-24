---
title: Cadenas con formato de fecha y hora estándar
description: Aprenda a usar una cadena de formato de fecha y hora estándar para definir la representación de texto de un valor de fecha y hora en .NET.
ms.date: 11/05/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET], dates
- custom DateTime format string
- format specifiers, custom date and time
- format strings
- custom date and time format strings
- formatting [.NET], time
- date and time strings
ms.custom: contperfq2
ms.openlocfilehash: b6917fa8a012a6fe52db1ea2b79397a0484d9d8f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831330"
---
# <a name="standard-date-and-time-format-strings"></a>Cadenas con formato de fecha y hora estándar

Una cadena de formato de fecha y hora estándar usa un único carácter como especificador de formato para definir la representación de texto de un valor <xref:System.DateTime> o <xref:System.DateTimeOffset>. Cualquier cadena con formato de fecha y hora que contenga más de un carácter, incluido un espacio en blanco, se interpreta como una [cadena con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md). Una cadena de formato estándar o personalizado se puede usar de dos maneras:

- Para definir la cadena resultante una operación de formato.

- Para definir la representación de texto de un valor de fecha y hora que se puede convertir en un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> mediante una operación de análisis.

> [!TIP]
> Puede descargar la **Utilidad de formato**, que es una aplicación de Windows Forms de .NET que permite aplicar cadenas de formato a valores numéricos o de fecha y hora, y que muestra la cadena de resultado. El código fuente está disponible para [C#](/samples/dotnet/samples/windowsforms-formatting-utility-cs) y [Visual Basic](/samples/dotnet/samples/windowsforms-formatting-utility-vb).

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-with-utc-partial-note.md)]

## <a name="table-of-format-specifiers"></a>Tabla de especificadores de formato

<a name="table"></a>En la tabla siguiente se describen los especificadores de formato de fecha y hora estándar. A menos que se indique lo contrario, un determinado especificador de formato de fecha y hora estándar genera una representación de cadena idéntica independientemente de que se use con un valor <xref:System.DateTime> o <xref:System.DateTimeOffset>. Vea [Configuración del Panel de control](#control-panel-settings) y [Propiedades de DateTimeFormatInfo](#datetimeformatinfo-properties) para obtener información adicional sobre el uso de cadenas de formato de fecha y hora estándar.

|Especificador de formato|Descripción|Ejemplos|
|----------------------|-----------------|--------------|
|"d"|Patrón de fecha corta.<br /><br /> Más información: [El especificador de formato de fecha corta ("d")](#ShortDate).|2009-06-15T13:45:30 -> 6/15/2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)<br /><br /> 2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)|
|"D"|Patrón de fecha larga.<br /><br /> Más información: [El especificador de formato de fecha larga ("D")](#LongDate).|2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)|
|"f"|Patrón de fecha y hora completa (hora corta).<br /><br /> Más información: [El especificador de formato de fecha completa y hora corta ("f")](#FullDateShortTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)|
|"F"|Patrón de fecha y hora completa (hora larga).<br /><br /> Más información: [El especificador de formato de fecha completa y hora larga ("F")](#FullDateLongTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)|
|"g"|Patrón de fecha y hora general (hora corta).<br /><br /> Más información: [El especificador de formato de fecha general y hora corta ("g")](#GeneralDateShortTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)|
|"G"|Patrón de fecha y hora general (hora larga).<br /><br /> Más información: [El especificador de formato de fecha general y hora larga ("G")](#GeneralDateLongTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)|
|"M", "m"|Patrón de mes/día.<br /><br /> Más información: [El especificador de formato de mes ("M", "m")](#MonthDay).|2009-06-15T13:45:30 -> June 15 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15. juni (da-DK)<br /><br /> 2009-06-15T13:45:30 -> 15 Juni (id-ID)|
|"O", "o"|Patrón de fecha y hora de ida y vuelta.<br /><br /> Más información: [El especificador de formato de operación de ida y vuelta ("O", "o")](#Roundtrip).|Valores de <xref:System.DateTime>:<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000<br /><br /> Valores de <xref:System.DateTimeOffset>:<br /><br /> 2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00|
|"R", "r"|Patrón RFC1123.<br /><br /> Más información: [El especificador de formato RFC1123 ("R", "r")](#RFC1123).|2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT|
|"s"|Patrón de fecha y hora que se puede ordenar.<br /><br /> Más información: [El especificador de formato que se puede ordenar ("s")](#Sortable).|2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30|
|"t"|Patrón de hora corta.<br /><br /> Más información: [El especificador de formato de hora corta ("t")](#ShortTime).|2009-06-15T13:45:30 -> 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45 م (ar-EG)|
|"T"|Patrón de hora larga.<br /><br /> Más información: [El especificador de formato de hora larga ("T")](#LongTime).|2009-06-15T13:45:30 -> 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45:30 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)|
|"u"|Patrón de fecha y hora universal que se puede ordenar.<br /><br /> Más información: [El especificador de formato universal que se puede ordenar ("u")](#UniversalSortable).|Con un valor <xref:System.DateTime> de: 2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z<br /><br /> Con un valor <xref:System.DateTimeOffset> de: 2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z|
|"U"|Patrón de fecha y hora completa universal.<br /><br /> Más información: [El especificador de formato completo universal ("U")](#UniversalFull).|2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)|
|"Y", "y"|Patrón de mes y año.<br /><br /> Más información: [El especificador de formato de mes y año ("Y")](#YearMonth).|2009-06-15T13:45:30 -> June 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> juni 2009 (da-DK)<br /><br /> 2009-06-15T13:45:30 -> Juni 2009 (id-ID)|
|Cualquier otro carácter único|Especificador desconocido.|Produce una excepción <xref:System.FormatException> en tiempo de ejecución.|

## <a name="how-standard-format-strings-work"></a>Cómo funcionan las cadenas con formato estándar

En una operación de formato, una cadena de formato estándar es simplemente un alias de una cadena con formato personalizado. La ventaja de usar un alias para referirse a una cadena de formato personalizado es que, aunque el alias permanece invariable, la propia cadena de formato personalizado puede variar. Esto es importante, porque las representaciones de cadena de valores de fecha y hora suelen variar con las referencias culturales. Por ejemplo, la cadena de formato estándar "d" indica que un valor de fecha y hora se va a mostrar utilizando un patrón de fecha corta. En la referencia cultural de todos los idiomas, este patrón es "MM/dd/aaaa". En la referencia cultural fr-FR, es "dd/MM/aaaa". En la referencia cultural ja-JP, es "aaaa/MM/dd."

Si una cadena con formato estándar en una operación de formato se asigna a una cadena con formato personalizado de una referencia cultural específica, la aplicación puede definir la referencia cultural concreta cuyas cadenas con formato personalizado se usan de uno de los modos siguientes:

- Puede utilizar la referencia cultural predeterminada (o la actual). En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de la referencia cultural. En este caso, la referencia cultural actual es en-US.

  [!code-csharp-interactive[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#1)]
  [!code-vb[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#1)]

- Puede pasar un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural cuyo formato se va a usar a un método que tenga un parámetro <xref:System.IFormatProvider>. En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de la referencia cultural pt-BR.

  [!code-csharp[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#2)]
  [!code-vb[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#2)]

- Puede pasar un objeto <xref:System.Globalization.DateTimeFormatInfo> que proporcione información sobre el formato a un método que tenga un parámetro <xref:System.IFormatProvider>. En el ejemplo siguiente se muestra una fecha con el formato de fecha abreviado de un objeto <xref:System.Globalization.DateTimeFormatInfo> en la referencia cultural hr-HR.

  [!code-csharp[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#3)]
  [!code-vb[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#3)]

> [!NOTE]
> Para obtener información sobre la personalización de patrones o cadenas usadas para dar formato a valores de fecha y hora, vea el tema sobre la clase <xref:System.Globalization.NumberFormatInfo>.

En algunos casos, la cadena con formato estándar actúa como la abreviatura correspondiente de una cadena con formato personalizado más larga que es invariable. Hay cuatro cadenas de formato estándar que pertenecen a esta categoría: "O" (u "o"), "R" (o "r"), "s" y "u". Estas cadenas se corresponden con las cadenas de formato personalizado definidas en la referencia cultural de todos los idiomas. Generan representaciones de cadena de valores de fecha y hora que están pensados para que sean idénticos en todas las referencias culturales. En la tabla siguiente se proporciona información sobre estas cuatro cadenas de formato de fecha y hora estándar.

|Cadena con formato estándar|Se define en la propiedad DateTimeFormatInfo.InvariantInfo|Cadena con formato personalizado|
|----------------------------|----------------------------------------------------------|--------------------------|
|"O" u "o"|None|yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzz|
|"R" o "r"|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|ddd, dd MMM yyyy HH':'mm':'ss 'GMT'|
|"s"|<xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A>|yyyy'-'MM'-'dd'T'HH':'mm':'ss|
|"u"|<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>|yyyy'-'MM'-'dd HH':'mm':'ss'Z'|

Las cadenas de formato estándar también se pueden usar en operaciones de análisis con los métodos <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, que necesitan que una cadena de entrada se ajuste exactamente a un patrón determinado para que la operación de análisis se realice correctamente. Muchas cadenas de formato estándar se asignan a varias cadenas de formato personalizado, por lo que un valor de fecha y hora se pueden representar en diversos formatos y la operación de análisis todavía se realizará correctamente. Puede determinar la cadena o las cadenas con formato personalizado correspondientes a una cadena con formato estándar llamando al método <xref:System.Globalization.DateTimeFormatInfo.GetAllDateTimePatterns%28System.Char%29?displayProperty=nameWithType>. En el ejemplo siguiente se muestran las cadenas con formato personalizado que se asignan a la cadena de formato estándar "d" (patrón de fecha corta).

[!code-csharp[Formatting.DateAndTime.Standard#17](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/stdandparsing1.cs#17)]
[!code-vb[Formatting.DateAndTime.Standard#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/stdandparsing1.vb#17)]

En las próximas secciones se describen los especificadores de formato estándar para los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.

## <a name="date-formats"></a>Formatos de fecha

Este grupo incluye los formatos siguientes:

- [El especificador de formato de fecha corta ("d")](#the-short-date-d-format-specifier)
- [El especificador de formato de fecha larga ("D")](#the-long-date-d-format-specifier)

<a name="ShortDate"></a>

### <a name="the-short-date-d-format-specifier"></a>El especificador de formato de fecha corta ("d")

El especificador de formato estándar "d" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> de una referencia cultural concreta. Por ejemplo, la cadena de formato personalizado devuelta por la propiedad <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A> de la referencia cultural de todos los idiomas es "MM/dd/yyyy".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Define la cadena que separa los componentes de año, mes y día de una fecha.|

En el ejemplo siguiente se usa el especificador de formato "d" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#1)]
[!code-vb[Formatting.DateAndTime.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#1)]

[Volver a la tabla](#table)

<a name="LongDate"></a>

### <a name="the-long-date-d-format-specifier"></a>El especificador de formato de fecha larga ("D")

El especificador de formato estándar "D" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "dddd, dd MMMM yyyy".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|

En el ejemplo siguiente se usa el especificador de formato "D" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#2)]
[!code-vb[Formatting.DateAndTime.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#2)]

[Volver a la tabla](#table)

## <a name="date-and-time-formats"></a>Formatos de fecha y hora

Este grupo incluye los formatos siguientes:

- [El especificador de formato de fecha completa y hora corta ("f")](#the-full-date-short-time-f-format-specifier).
- [El especificador de formato de fecha completa y hora larga ("F")](#the-full-date-long-time-f-format-specifier).
- [El especificador de formato de fecha general y hora corta ("g")](#the-general-date-short-time-g-format-specifier).
- [El especificador de formato de fecha general y hora larga ("G")](#the-general-date-long-time-g-format-specifier).
- [El especificador de formato de operación de ida y vuelta ("O", "o")](#the-round-trip-o-o-format-specifier).
- [El especificador de formato RFC1123 ("R", "r")](#the-rfc1123-r-r-format-specifier).
- [El especificador de formato que se puede ordenar ("s")](#the-sortable-s-format-specifier).
- [El especificador de formato universal que se puede ordenar ("u")](#the-universal-sortable-u-format-specifier).
- [El especificador de formato completo universal ("U")](#the-universal-full-u-format-specifier).

<a name="FullDateShortTime"></a>

### <a name="the-full-date-short-time-f-format-specifier"></a>El especificador de formato de fecha completa y hora corta ("f")

El especificador de formato estándar "f" representa una combinación de los patrones de fecha larga ("D") y hora corta ("t"), separados por un espacio.

La información de formato de un objeto <xref:System.Globalization.DateTimeFormatInfo> específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por las propiedades <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> y <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Define el formato del componente de fecha de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Define el formato del componente de hora de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "f" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#3)]
[!code-vb[Formatting.DateAndTime.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#3)]

[Volver a la tabla](#table)

<a name="FullDateLongTime"></a>

### <a name="the-full-date-long-time-f-format-specifier"></a>El especificador de formato de fecha completa y hora larga ("F")

El especificador de formato estándar "F" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "dddd, dd MMMM yyyy HH:mm:ss".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "F" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#4)]
[!code-vb[Formatting.DateAndTime.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#4)]

[Volver a la tabla](#table)

<a name="GeneralDateShortTime"></a>

### <a name="the-general-date-short-time-g-format-specifier"></a>El especificador de formato de fecha general y hora corta ("g")

El especificador de formato estándar "g" representa una combinación de los patrones de fecha corta ("d") y hora corta ("t"), separados por un espacio.

La información de formato de un objeto <xref:System.Globalization.DateTimeFormatInfo> específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por las propiedades <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> y <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Define el formato del componente de fecha de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Define el formato del componente de hora de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Define la cadena que separa los componentes de año, mes y día de una fecha.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "g" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#5)]
[!code-vb[Formatting.DateAndTime.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#5)]

[Volver a la tabla](#table)

<a name="GeneralDateLongTime"></a>

### <a name="the-general-date-long-time-g-format-specifier"></a>El especificador de formato de fecha general y hora larga ("G")

El especificador de formato estándar "G" representa una combinación de los patrones de fecha corta ("d") y hora larga ("T"), separados por un espacio.

La información de formato de un objeto <xref:System.Globalization.DateTimeFormatInfo> específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por las propiedades <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> y <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Define el formato del componente de fecha de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Define el formato del componente de hora de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Define la cadena que separa los componentes de año, mes y día de una fecha.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "G" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#6)]
[!code-vb[Formatting.DateAndTime.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#6)]

[Volver a la tabla](#table)

<a name="Roundtrip"></a>

### <a name="the-round-trip-o-o-format-specifier"></a>El especificador de formato de operación de ida y vuelta ("O", "o")

El especificador de formato estándar "O" u "o" representa una cadena de formato de fecha y hora personalizado mediante un patrón que conserva la información de la zona horaria y emite una cadena de resultado que cumple con la norma ISO 8601. En los valores <xref:System.DateTime>, este especificador de formato está diseñado para conservar los valores de fecha y hora junto con la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> en el texto. La cadena con formato se puede recuperar usando el método <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> o <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> si el parámetro `styles` está establecido en <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>.

El especificador de formato estándar "O" u "o" corresponde a la cadena de formato personalizado "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK" para los valores <xref:System.DateTime> y a "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz" para los valores <xref:System.DateTimeOffset>. En esta cadena, los pares de comillas que delimitan los caracteres individuales (como guiones, signos de dos puntos y la letra "T") indican que el carácter individual es un literal que no se puede cambiar. Los apóstrofos no aparecen en la cadena de salida.

El especificador de formato estándar "O" u "o" (y la cadena de formato personalizado "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK") aprovecha los tres modos en que se representa la información de zona horaria en ISO 8601 para conservar la propiedad <xref:System.DateTime.Kind%2A> de valores <xref:System.DateTime>:

- El componente de zona horaria de valores de fecha y hora <xref:System.DateTimeKind.Local?displayProperty=nameWithType> es un desfase con respecto a la hora UTC (por ejemplo, +01:00, -07:00). Todos los valores <xref:System.DateTimeOffset> también se representan en este formato.

- El componente de zona horaria de valores de fecha y hora <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> usa "Z" (que es un desfase cero) para representar la hora UTC.

- Los valores de fecha y hora <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> no tienen información de zona horaria.

Dado que el especificador de formato estándar "O" u "o" se ajusta a un estándar internacional, la operación de formato o análisis que utiliza el especificador siempre usa la referencia cultural de todos los idiomas y el calendario gregoriano.

Las cadenas que se pasan a los métodos `Parse`, `TryParse`, `ParseExact` y `TryParseExact` de <xref:System.DateTime> y <xref:System.DateTimeOffset> se pueden analizar con el especificador de formato "O" u "o" si están en uno de estos formatos. En el caso de objetos <xref:System.DateTime>, la sobrecarga de análisis a la que llama también debe incluir un parámetro `styles` con un valor de <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>. Observe que si llama a un método de análisis con la cadena de formato personalizado que se corresponde con el especificador de formato "O" u "o", no obtendrá los mismos resultados que "O" u "o". Esto se debe a que los métodos de análisis que usan una cadena de formato personalizado no pueden analizar la representación de cadena de aquellos valores de fecha y hora que carecen de un componente de zona horaria o que usan "Z" para indicar la hora UTC.

En el ejemplo siguiente se utiliza el especificador de formato "o" para mostrar una serie de valores <xref:System.DateTime> y un valor <xref:System.DateTimeOffset> en un sistema de la zona horaria del Pacífico de EE. UU.

[!code-csharp[Formatting.DateAndTime.Standard#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/o1.cs#8)]
[!code-vb[Formatting.DateAndTime.Standard#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/o1.vb#8)]

En el ejemplo siguiente se usa el especificador de formato "o" para crear una cadena con formato y, a continuación, se restaura el valor de fecha y hora original llamando a un método `Parse` de fecha y hora.

[!code-csharp[Formatting.DateandTime.Standard#16](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Roundtrip1.cs#16)]
[!code-vb[Formatting.DateandTime.Standard#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/RoundTrip1.vb#16)]

[Volver a la tabla](#table)

<a name="RFC1123"></a>

### <a name="the-rfc1123-r-r-format-specifier"></a>El especificador de formato RFC1123 ("R", "r")

El especificador de formato estándar "R" o "r" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A?displayProperty=nameWithType>. El patrón refleja una norma definida y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "ddd, dd MMM yyyy HH':'mm':'ss 'GMT'". Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas.

Las siguientes propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.DateTimeFormatInfo.InvariantInfo%2A?displayProperty=nameWithType> que representa la referencia cultural de todos los idiomas afectan a la cadena de resultado.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|Define el formato de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A>|Define los nombres de días abreviados que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames%2A>|Define los nombres de meses abreviados que pueden aparecer en la cadena de resultado.|

Aunque la norma RFC 1123 expresa una hora según la hora universal coordinada (hora UTC), la operación de formato no modifica el valor del objeto <xref:System.DateTime> al que se está dando formato. Por consiguiente, debe convertir el valor <xref:System.DateTime> en una hora UTC llamando al método <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> antes de realizar la operación de formato. En cambio, los valores <xref:System.DateTimeOffset> realizan esta conversión automáticamente; no es necesario llamar al método <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> antes de la operación de formato.

En el ejemplo siguiente se utiliza el especificador de formato "r" para mostrar un <xref:System.DateTime> y un valor <xref:System.DateTimeOffset> en un sistema de la zona horaria del Pacífico de EE. UU.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#9)]
[!code-vb[Formatting.DateAndTime.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#9)]

[Volver a la tabla](#table)

<a name="Sortable"></a>

### <a name="the-sortable-s-format-specifier"></a>El especificador de formato que se puede ordenar ("s")

El especificador de formato estándar "s" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A?displayProperty=nameWithType>. El patrón refleja una norma definida (ISO 8601) y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "yyyy'-'MM'-'dd'T'HH':'mm':'ss".

La finalidad del especificador de formato "s" es generar cadenas de resultado de forma coherente en orden ascendente o descendente según los valores de fecha y hora. Como resultado, aunque el especificador de formato estándar "s" representa un valor de fecha y hora en un formato coherente, la operación de formato no modifica el valor del objeto de fecha y hora al que se está dando formato para reflejar su propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> o su valor <xref:System.DateTimeOffset.Offset%2A?displayProperty=nameWithType>. Por ejemplo, las cadenas de resultado que se producen al dar formato a los valores de fecha y hora 2014-11-15T18:32:17+00:00 y 2014-11-15T18:32:17+08:00 son idénticas.

Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas.

En el ejemplo siguiente se utiliza el especificador de formato "s" para mostrar un valor <xref:System.DateTime> y <xref:System.DateTimeOffset> en un sistema de la zona horaria del Pacífico de EE. UU.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#10)]
[!code-vb[Formatting.DateAndTime.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#10)]

[Volver a la tabla](#table)

<a name="UniversalSortable"></a>

### <a name="the-universal-sortable-u-format-specifier"></a>El especificador de formato universal que se puede ordenar ("u")

El especificador de formato estándar "u" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A?displayProperty=nameWithType>. El patrón refleja una norma definida y la propiedad es de solo lectura. Por consiguiente, siempre es el mismo, sea cual fuere la referencia cultural utilizada o el proveedor de formato proporcionado. La cadena de formato personalizado es "yyyy'-'MM'-'dd HH':'mm':'ss'Z'". Cuando se utiliza este especificador de formato estándar, la operación de formato o análisis utiliza siempre la referencia cultural de todos los idiomas.

Aunque la cadena de resultado debe expresar una hora como una hora universal coordinada (hora UTC), no se realiza ninguna conversión del valor <xref:System.DateTime> original durante la operación de formato. Por consiguiente, debe convertir un valor <xref:System.DateTime> en una hora UTC llamando al método <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> antes de aplicarle formato.  En cambio, los valores <xref:System.DateTimeOffset> realizan esta conversión automáticamente; no es necesario llamar al método <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> antes de la operación de formato.

En el ejemplo siguiente se usa el especificador de formato "u" para mostrar un valor de fecha y hora.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#13)]
[!code-vb[Formatting.DateAndTime.Standard#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#13)]

[Volver a la tabla](#table)

<a name="UniversalFull"></a>

### <a name="the-universal-full-u-format-specifier"></a>El especificador de formato completo universal ("U")

El especificador de formato estándar "U" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> de una referencia cultural especificada. El patrón es igual que el patrón de "F". Sin embargo, el valor <xref:System.DateTime> se convierte automáticamente en una hora UTC antes de darle formato.

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Define los nombres de días traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

El especificador de formato "U" no es compatible con el tipo <xref:System.DateTimeOffset> y provoca una excepción <xref:System.FormatException> si se usa para dar formato a un valor <xref:System.DateTimeOffset>.

En el ejemplo siguiente se usa el especificador de formato "U" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#14)]
[!code-vb[Formatting.DateAndTime.Standard#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#14)]

[Volver a la tabla](#table)

## <a name="time-formats"></a>Formatos de hora

Este grupo incluye los formatos siguientes:

- [El especificador de formato de hora corta ("t")](#the-short-time-t-format-specifier).
- [El especificador de formato de hora larga ("T")](#the-long-time-t-format-specifier).

<a name="ShortTime"></a>

### <a name="the-short-time-t-format-specifier"></a>El especificador de formato de hora corta ("t")

El especificador de formato estándar "t" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "HH:mm".

La información de formato de un objeto <xref:System.Globalization.DateTimeFormatInfo> específico afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por la propiedad <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Define el formato del componente de hora de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "t" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#11)]
[!code-vb[Formatting.DateAndTime.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#11)]

[Volver a la tabla](#table)

<a name="LongTime"></a>

### <a name="the-long-time-t-format-specifier"></a>El especificador de formato de hora larga ("T")

El especificador de formato estándar "T" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> de una referencia cultural concreta. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "HH:mm:ss".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que pueden controlar el formato de la cadena devuelta. El especificador de formato personalizado devuelto por la propiedad <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> de algunas referencias culturales quizás no use todas las propiedades.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Define el formato del componente de hora de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Define la cadena que separa los componentes de hora, minutos y segundos de una hora.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Define la cadena que indica las horas comprendidas desde medianoche hasta antes del mediodía en un reloj de 12 horas.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Define la cadena que indica las horas comprendidas desde el mediodía hasta antes de medianoche en un reloj de 12 horas.|

En el ejemplo siguiente se usa el especificador de formato "T" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#12)]
[!code-vb[Formatting.DateAndTime.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#12)]

[Volver a la tabla](#table)

## <a name="partial-date-formats"></a>Formatos de fecha parcial

Este grupo incluye los formatos siguientes:

- [El especificador de formato de mes ("M", "m")](#the-month-m-m-format-specifier).
- [El especificador de formato de mes y año ("Y", "y")](#the-year-month-y-y-format-specifier)

<a name="MonthDay"></a>

### <a name="the-month-m-m-format-specifier"></a>El especificador de formato de mes ("M", "m")

El especificador de formato estándar "M" o "m" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A?displayProperty=nameWithType> actual. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "MMMM dd".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|

En el ejemplo siguiente se usa el especificador de formato "m" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#7)]
[!code-vb[Formatting.DateAndTime.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#7)]

[Volver a la tabla](#table)

<a name="YearMonth"></a>

### <a name="the-year-month-y-y-format-specifier"></a>El especificador de formato de mes y año ("Y", "y")

El especificador de formato estándar "Y" o "y" representa una cadena de formato de fecha y hora personalizado que está definida por la propiedad <xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A?displayProperty=nameWithType> de una referencia cultural especificada. Por ejemplo, la cadena de formato personalizado para la referencia cultural de todos los idiomas es "yyyy MMMM".

En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad.|Descripción|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A>|Define el formato global de la cadena de resultado.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Define los nombres de meses traducidos que pueden aparecer en la cadena de resultado.|

En el ejemplo siguiente se usa el especificador de formato "y" para mostrar un valor de fecha y hora.

[!code-csharp[Formatting.DateAndTime.Standard#15](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#15)]
[!code-vb[Formatting.DateAndTime.Standard#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#15)]

[Volver a la tabla](#table)

<a name="Notes"></a>

## <a name="control-panel-settings"></a>Configuración del Panel de control

En Windows, los valores de configuración del elemento **Configuración regional y de idioma** del Panel de control influyen en la cadena de resultado generada por una operación de formato. Estas configuraciones se utilizan para inicializar el objeto <xref:System.Globalization.DateTimeFormatInfo> asociado a la referencia cultural del subproceso actual, que proporciona valores que se utilizan para controlar el formato. Los equipos que usan configuraciones diferentes generarán cadenas de resultado distintas.

Asimismo, si se usa el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29> para crear instancias de un nuevo objeto <xref:System.Globalization.CultureInfo> que representa la misma referencia cultural que la referencia cultural del sistema actual, cualquier personalización establecida por el elemento **Configuración regional y de idioma** del Panel de control se aplicará al nuevo objeto <xref:System.Globalization.CultureInfo> . Puede usar el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29> para crear un objeto <xref:System.Globalization.CultureInfo> que no refleje las personalizaciones de un sistema.

## <a name="datetimeformatinfo-properties"></a>Propiedades de DateTimeFormatInfo

El formato se ve influenciado por las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro <xref:System.IFormatProvider> del método que invoca el formato. En el parámetro <xref:System.IFormatProvider>, la aplicación debe especificar un objeto <xref:System.Globalization.CultureInfo>, que representa una referencia cultural, o un objeto <xref:System.Globalization.DateTimeFormatInfo>, que representa las convenciones de formato de fecha y hora de una determinada referencia cultural. Muchos de los especificadores de formato de fecha y hora estándar son alias de patrones de formato definidos en las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> actual. La aplicación puede modificar el resultado generado por algunos especificadores de formato de fecha y hora estándar al cambiar los patrones de formato de fecha y hora correspondientes de la propiedad <xref:System.Globalization.DateTimeFormatInfo> apropiada.

## <a name="see-also"></a>Vea también

- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- [Aplicación de formato a tipos](formatting-types.md)
- [Cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (C#)](/samples/dotnet/samples/windowsforms-formatting-utility-cs)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (Visual Basic)](/samples/dotnet/samples/windowsforms-formatting-utility-vb)
